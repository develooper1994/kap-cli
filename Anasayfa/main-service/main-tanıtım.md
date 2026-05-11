# main

## Tanıtım

Bu ağ isteği, Kamuyu Aydınlatma Platformu (KAP) üzerindeki en güncel şirket bildirimlerini (kapandığı ana kadarki son açıklamalar) listeleyen ana veri servisidir.

## İstek Amacı

Bu servis, ana sayfada gösterilen "Son Bildirimler" akışını besler. Finansal raporlar, sorumluluk beyanları ve özel durum açıklamaları gibi kategorize edilmiş verileri JSON formatında döndürür.

## DataRaw (İstek Gövdesi) Parametreleri

İsteğin içeriğinde gönderilen parametreler, sunucudan dönen veriyi filtrelemek ve sayfalamak için kullanılır. Genellikle şu yapıdadır:

- **disclosureClass:** Bildirim sınıfını filtreler (Örn: FR - Finansal Rapor, ODA - Özel Durum Açıklaması). Boş bırakılırsa tüm sınıfları getirir.
- **fromDate / toDate:** Belirli bir tarih aralığındaki bildirimleri sorgulamak için kullanılır (Format: YYYY-MM-DD).
- **market:** Belirli bir pazar türüne (Örn: Yıldız Pazar, Ana Pazar) göre filtreleme yapar.
- **isSearch:** Bir arama işlemi olup olmadığını belirten boolean değerdir.
- **count:** Tek seferde kaç adet bildirimin döneceğini belirler.
- **disclosureTypes:** Spesifik bildirim tiplerini içeren bir dizidir.

## Teknik Analiz

- **Yanıt Süresi:** 722 ms ile bir önceki takvim isteğine göre belirgin şekilde daha yavaştır. Bunun temel sebebi, sunucunun veritabanından dinamik ve geniş kapsamlı bir veri seti derlemesidir.
- **Veri Yapısı:** Yanıt, disclosureBasic (başlık, şirket kodu, yayın tarihi) ve disclosureDetail (ek döküman id'leri, denetçi görüşü vb.) olmak üzere iki ana objeden oluşur.
- **Optimizasyon:** Content-Encoding: gzip aktif durumdadır. Ancak, büyük veri setlerinde Waiting for server response (TTFB) süresinin 649 ms olması, sunucu tarafında sorgu optimizasyonu yapılabileceğine işaret eder.

## Kritik Not

- Bu istekte Content-Length değeri mevcut ancak gönderilen payload (DataRaw) tam metni paylaşılmamış. Eğer özel bir filtreleme yapıyorsanız, bu JSON gövdesi içindeki disclosureClass veya companyOid gibi alanlar sonuç setini doğrudan etkiler.
- Ayrıca Bu istek sonucunda gerçekten çok büyük cevap gelebiliyor! 10MB json dosya geldiğini ve editorun çöktüğünü gördüm.
- İstek javascript kodunda belli aralıklarla tetikleniyor ve sürekli büyüyor.

## Giriş Parametreleri

### Şirket Bildirimleri

Tüm parametreler aynı anda kullanılmaz!

#### Zaman(DD.MM.YY)

- Arayüzde görünen: Bugün, Dün, "Son 15 Gün", "Tarih aralığı Seç":
- fromDate ve toDate tarihlerini belirtir. Bugün ve Dün seçimlerinde fromDate ve toDate aynı olacaktır.Bugün ise bugünün tarihi, dün ise dünün tarihi yazılır.
- Kural: Seçilen Tarih aralığı 3 aydan fazla olamaz!

#### Şirket Tipi(memberTypes)

- Arayüzde Görünen: BIST Şirketleri(IGS), Yatırım Kuruluşları(YK), Portföy Yönetim Şirketleri(PYS), Düzenleyici Düzenleyici Kurumlar(DDK), Kripto Varlık Hizmet Sağlayıcı(KVH), Diğer Kap Üyeleri(DG)
- Şirket Bildirimleri dışında kullanılmaz.

#### Bildirim Tipi(disclosureTypes)

- Arayüzde Görünen: Özel Durum Açıklaması(ODA), Finansal Rapor(FR), Düzenleyici Kurum Bildirimleri(DUY), Diğer(DG), Hak Kullanımları(CA)
- Hak Kullanımları(CA) fon bildirimlerinde kullanılmaz.

#### Şirket Ünvanı(mkkMemberOid)

- Şirket Bildirimleri kullanılacaksa doldurulabilir. Diğer bildirim türlerinde kullanılmaz.
- mkkMemberOid verilmesi şart değildir. Sadece sonuçları daraltarak daha küçük boyutlarda veri elde etmeyi sağlar. 
mkkMemberOid verilmezse yanıt çok büyük olabilir.
null gibi gözükse de aslında member/filter/{Sorgu Meti} servisinden gelen mkkMemberOid UUID numarasını kullanır. 
Bu yüzden https://www.kap.org.tr/tr/api/member/filter/{Sorgu Metni} servisini de incele.

#### Fon Tipi(fundTypes)

- Arayüzde Görünen: Bireysel Yatırım Fonları(BYF), Yatırım Fonları(YF), Emeklilik Yatırım Fonları(EYF), OKS Emeklilik Yatırım Fonları(OKS), Yabancı Yatırım Fonları(YYF), Varlık Finansman Fonları(VFF), Konut Finansmanı Fonları(KFF), Gayrimenkul Yatırım Fonları(GMF), Firişim Sermayesi Fonları(GSF), Proje Finansmanı Fonları(PFF)
- Fon Bildirimleri dışında kullanılmaz.

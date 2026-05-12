# company - Şirket Bildirimi

url: <https://www.kap.org.tr/tr/api/expected-disclosure-inquiry/company>

Bu ağ isteği, Kamuyu Aydınlatma Platformu (KAP) üzerindeki şirketlerin gelecekteki beklenen bildirim tarihlerini (finansal raporlar, faaliyet raporları vb.) sorgulamak için kullanılan bir API uç noktasıdır.

## Analiz

- **Amaç:** Belirli şirketler için 2026 ve 2027 yıllarına ait finansal takvimi (başlangıç ve bitiş tarihleri dahil) JSON formatında döndürür. Yanıt; THY, ASELSAN ve AFYON gibi şirketlerin 6 aylık, 9 aylık ve yıllık raporlama dönemlerini içermektedir.
- **Durum:** 200 OK koduyla istek başarıyla tamamlanmış ve veri alınmıştır.
- **Performans:** Toplam süre 796 ms'dir. Bunun büyük çoğunluğu (793 ms) sunucunun yanıt hazırlama sürecinde (Waiting for server response) geçmiştir. Veri indirme süresi (0.7 ms) oldukça düşüktür, bu da sıkıştırmanın (gzip) verimli çalıştığını gösterir.

## Teknik Tespitler

- **Kök Sebep:** Sunucu tarafındaki işlem süresi (TTFB), toplam sürenin %99'unu oluşturmaktadır. Veritabanı sorgusunun karmaşıklığı veya sunucu yükü bu gecikmeye neden olabilir.

## Öneriler

- **Önbelleğe Alma:** Yanıt başlıklarında Cache-Control: private ifadesi yer alıyor ve max-age tanımlanmamış. Veriler nadiren değişiyorsa (yıllık takvim), istemci tarafında veya bir CDN üzerinde önbellekleme yapılarak 793 ms'lik gecikme ortadan kaldırılabilir.
- **Veri Filtreleme:** Eğer tüm şirketlerin verisi gerekmiyorsa, payload boyutunu ve sunucu yükünü azaltmak için istekte filtreleme parametreleri kullanılmalıdır.

## Arayüz(Filter) Parametreleri

Arayüzde görünen alanların isimleri ve açıklamaları:

### Şirket ve Tarih Aralığı

#### Şirket Grubu(memberTypes)

İşlem Gören Şirketler(IGS), Yatırım Kuruluşları(YK), Portföy Yönetim Şirketleri(PYS), Derecelendirme Şirketleri, Bağımsız Denetim Kuruluşları, Düzenleyici Denetleyici Kurumlar(DDK), Diğer KAP Üyeleri(DG), Kripto Varlık Hizmet Sağlayıcı(KVH)

#### Şirketler(mkkMemberOidList)

Şirket listesi muhtemelen html için gömülü geldiğinden SSR'de işleniyor olabilir. Bu yüzden mkkMemberOid'ları kullanarak şirketleri filtrelemek daha sağlıklı olabilir.
Belki Aktif-Pasif servislerinden de alınabilir.

#### Tarih Aralığı

- Bugün, Önümüzdeki 1 Hafta, Önümüzdeki 1 ay, Önümüzdeki 3 ay, Önümüzdeki 6 ay, Önümüzdeki 1 yıl gibi seçenekler var. Tarih aralığı seçildiğinde fromDate ve toDate parametreleri gönderilir. Bugün ve Dün seçimlerinde fromDate ve toDate aynı olacaktır.Bugün ise bugünün tarihi, dün ise dünün tarihi yazılır.

#### Başlangıç Tarihi(startDate)

- Arama başlangıç tarihi. Format: YYYY-MM-DD

#### Bitiş Tarihi(endDate)

- Arama bitiş tarihi. Format: YYYY-MM-DD

### Beklenen Bildirim Kriterleri

> curl 'https://www.kap.org.tr/tr/beklenen-bildirim-sorgu' -X POST \
   -H 'Content-Type: application/json;charset=UTF-8' \
   -H 'Referer: https://www.kap.org.tr/tr/beklenen-bildirim-sorgu' \
   -H 'Origin: https://www.kap.org.tr' \
   -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36' \
   --data-raw '{}' > beklenen-bildirim-sorgu.html

- Maalesef burada hiçbir servis çağrısı yok. nextjs ile çağrıları server side render yaparak yapıyor. bu yüzden tüm veriler html parse ile elde edilebilir.
[Aktif - Pasif](Aktif%20-%20Pasif.md) servisleri de buna alternatif olabilir ama bu servisler İşlem Gören Şirketlerin listesini vermiyor.
- Arayüzde her şirket grubu için farklı parametre grubu görünüyor.

> IGS için Sektör, Pazar, Endeks, Bildirim Tipi, Konu gibi filtreler var. Diğer şirket gruplarında bu filtreler değişiyor.

### Beklenen Bildirim Kriterleri(YK)

#### [Bildirim Tipi(disclosureClass)](Bildirim%20Tipleri.md)

Tüm Bildirim Tipleri için boş bırakılabilir. Belirli bir bildirim tipi seçilirse, sadece o tipe ait bildirimler döner. Örneğin "Finansal Raporlar" seçilirse, sadece finansal raporlarla ilgili bildirimler döner.

#### [Konu(subject)](Konu.md)

Tüm Konular için boş bırakılabilir. Belirli bir konu seçilirse, sadece o konuya ait bildirimler döner. Örneğin "2023 Yılı Finansal Sonuçları" seçilirse, sadece bu konuya ait bildirimler döner.

## İşlem Gören Şirketler(IGS)

### Request

curl 'https://www.kap.org.tr/tr/api/expected-disclosure-inquiry/company' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'DNT: 1' \
  -H 'Origin: https://www.kap.org.tr' \
  -H 'Referer: https://www.kap.org.tr/tr/beklenen-bildirim-sorgu' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  --data-raw '{"startDate":"2026-05-11","endDate":"2026-11-07","memberTypes":["IGS"],"mkkMemberOidList":["4028e4a140f2ed720140f376bebb01a7","4028e4a1413b7ef401413bc2251e0047","4028e4a140e95bea0140edeb7a54015d"],"disclosureClass":"","subjects":[],"mainSector":"","sector":"","subSector":"","market":"","index":"","year":"","term":"","ruleType":""}'

### Response

[
    {
        "kapTitle": "AGESA HAYAT VE EMEKLİLİK A.Ş.",
        "ruleOid": "4028328c8b2fcee7018cd4c4561a55f8",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d537aad0a015383c58b8b451a",
        "year": 2026
    },
    {
        "kapTitle": "AGESA HAYAT VE EMEKLİLİK A.Ş.",
        "ruleOid": "4028328c8b2fcee7018cd4c4561a55f8",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "8aca490d4ed89f8b014ed8d3cd1c012b",
        "year": 2026
    },
    {
        "kapTitle": "AGESA HAYAT VE EMEKLİLİK A.Ş.",
        "ruleOid": "4028328c8b2fcee7018cd4c59160560b",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide)",
        "taxonomyOid": "4028328d537aad0a015383f3d5ef4624",
        "year": 2026
    },
    {
        "kapTitle": "AGESA HAYAT VE EMEKLİLİK A.Ş.",
        "ruleOid": "4028328c8b2fcee7018cd4c59160560b",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f35000461a",
        "year": 2026
    },
    {
        "kapTitle": "AGESA HAYAT VE EMEKLİLİK A.Ş.",
        "ruleOid": "4028328c8b2fcee7018cd4c4561a55f8",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Faaliyet Raporu (Konsolide)",
        "taxonomyOid": "8aca490d509dddbb01509de7f0f10008",
        "year": 2026
    },
    {
        "kapTitle": "AGESA HAYAT VE EMEKLİLİK A.Ş.",
        "ruleOid": "4028328c8b2fcee7018cd4c4561a55f8",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Faaliyet Raporu (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f6a405462e",
        "year": 2026
    },
    {
        "kapTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
        "ruleOid": "4028328d55036e0e015505d6bc532eda",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "8a8ae44e49f558ec014a04f3b49d0020",
        "year": 2026
    },
    {
        "kapTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
        "ruleOid": "4028328d55036e0e015505dca67a2eeb",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide)",
        "taxonomyOid": "4028328d537aad0a015383f3d5ef4624",
        "year": 2026
    },
    {
        "kapTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
        "ruleOid": "4028328d55036e0e015505d6bc532eda",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Faaliyet Raporu (Konsolide)",
        "taxonomyOid": "8aca490d509dddbb01509de7f0f10008",
        "year": 2026
    },
    {
        "kapTitle": "TÜRK HAVA YOLLARI A.O.",
        "ruleOid": "4028328d55036e0e015505d6bc532eda",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "8a8ae44e49f558ec014a04f3b49d0020",
        "year": 2026
    },
    {
        "kapTitle": "TÜRK HAVA YOLLARI A.O.",
        "ruleOid": "4028328d55036e0e015505dca67a2eeb",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide)",
        "taxonomyOid": "4028328d537aad0a015383f3d5ef4624",
        "year": 2026
    },
    {
        "kapTitle": "TÜRK HAVA YOLLARI A.O.",
        "ruleOid": "4028328d55036e0e015505d6bc532eda",
        "ruleTypeTerm": "6 Aylık",
        "startDate": "01.07.2026",
        "endDate": "19.08.2026",
        "stockCode": null,
        "subject": "Faaliyet Raporu (Konsolide)",
        "taxonomyOid": "8aca490d509dddbb01509de7f0f10008",
        "year": 2026
    }
]

## Yatırım Kuruluşları(YK)

### Request

curl 'https://www.kap.org.tr/tr/api/expected-disclosure-inquiry/company' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'DNT: 1' \
  -H 'Origin: https://www.kap.org.tr' \
  -H 'Referer: https://www.kap.org.tr/tr/beklenen-bildirim-sorgu' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  --data-raw '{"startDate":"2026-05-11","endDate":"2026-08-09","memberTypes":["YK"],"mkkMemberOidList":["4028e4a240e8d1830140e905edcd0006","1DE05DAA8212073AE0530A4A622A2EBD","4028e4a24a5df6e7014af304f4c61b28","4028e4a24184e9e2014192b3be212661","AA1836BDEC5602E4E0530A4A622B2939","4028e4a141558bdd01415622f45a05be","4028e4a14184e9c90141982b09bd45a3","4028e4a243372090014348a3a42b34c5","1DE05DAA8402073AE0530A4A622A2EBD","4028e4a1416e696301416ec49d6f2842","4028e4a24158e42201415adceafc5e96","8acae2c482b7ea0b0182f949649916a8","4028e4a24371e09b01437caad56f2d64","4028e4a140f2ed720140f3187e00012e","8acae2c59145e00e0193c06bb0317fbe","4028e4a142140a8c014222e4b272248f","567b1f70a6d5424c8f1fd534c5b4ebe4"],"disclosureClass":"","subjects":[],"mainSector":"","sector":"","subSector":"","market":"","index":"","year":"","term":"","ruleType":""}'

### Request

[
    {
        "kapTitle": "ICBC TURKEY YATIRIM MENKUL DEĞERLER A.Ş.",
        "ruleOid": "4028328c550c744a015515182cdf02a9",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "11.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "8a8ae44e49f558ec014a04f3b49d0020",
        "year": 2026
    },
    {
        "kapTitle": "ICBC TURKEY YATIRIM MENKUL DEĞERLER A.Ş.",
        "ruleOid": "4028328c550c744a0155151a3b0702bc",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "11.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide)",
        "taxonomyOid": "4028328d537aad0a015383f3d5ef4624",
        "year": 2026
    },
    {
        "kapTitle": "PAY MENKUL DEĞERLER A.Ş.",
        "ruleOid": "4028328c550c744a015515182cdf02a9",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "11.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "8a8ae44e49f558ec014a04f3b49d0020",
        "year": 2026
    },
    {
        "kapTitle": "PAY MENKUL DEĞERLER A.Ş.",
        "ruleOid": "4028328c550c744a0155151a3b0702bc",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "11.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide)",
        "taxonomyOid": "4028328d537aad0a015383f3d5ef4624",
        "year": 2026
    },
    {
        "kapTitle": "BANKPOZİTİF KREDİ VE KALKINMA BANKASI A.Ş.",
        "ruleOid": "4028328c550c744a01551529b5b302f3",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b523f5a5157",
        "year": 2026
    },
    {
        "kapTitle": "BANKPOZİTİF KREDİ VE KALKINMA BANKASI A.Ş.",
        "ruleOid": "4028328c550c744a0155152cd3640309",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f35000461a",
        "year": 2026
    },
    {
        "kapTitle": "GSD YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328c550c744a01551529b5b302f3",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b523f5a5157",
        "year": 2026
    },
    {
        "kapTitle": "GSD YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328c550c744a0155152cd3640309",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f35000461a",
        "year": 2026
    },
    {
        "kapTitle": "JP MORGAN CHASE BANK N.A. MERKEZİ COLUMBUS OHIO - İSTANBUL TÜRKİYE ŞUBESİ",
        "ruleOid": "4028328c550c744a01551529b5b302f3",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b523f5a5157",
        "year": 2026
    },
    {
        "kapTitle": "JP MORGAN CHASE BANK N.A. MERKEZİ COLUMBUS OHIO - İSTANBUL TÜRKİYE ŞUBESİ",
        "ruleOid": "4028328c550c744a0155152cd3640309",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f35000461a",
        "year": 2026
    },
    {
        "kapTitle": "T.O.M. KATILIM BANKASI A.Ş.",
        "ruleOid": "4028328c550c744a01551529b5b302f3",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b53696e5177",
        "year": 2026
    },
    {
        "kapTitle": "T.O.M. KATILIM BANKASI A.Ş.",
        "ruleOid": "4028328c550c744a0155152cd3640309",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f35000461a",
        "year": 2026
    },
    {
        "kapTitle": "ZİRAAT DİNAMİK BANKA A.Ş.",
        "ruleOid": "4028328c550c744a01551529b5b302f3",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b523f5a5157",
        "year": 2026
    },
    {
        "kapTitle": "ZİRAAT DİNAMİK BANKA A.Ş.",
        "ruleOid": "4028328c550c744a0155152cd3640309",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "15.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f35000461a",
        "year": 2026
    },
    {
        "kapTitle": "AKTİF YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328d550c7a8b0155115ac8580760",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "20.05.2026",
        "stockCode": "AFB, AKTIF",
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b505b655131",
        "year": 2026
    },
    {
        "kapTitle": "AKTİF YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328d550c7a8b0155115ac8580760",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "20.05.2026",
        "stockCode": "AFB, AKTIF",
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b523f5a5157",
        "year": 2026
    },
    {
        "kapTitle": "AKTİF YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328d550c7a8b0155115ebdbc077a",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "20.05.2026",
        "stockCode": "AFB, AKTIF",
        "subject": "Sorumluluk Beyanı (Konsolide)",
        "taxonomyOid": "4028328d537aad0a015383f3d5ef4624",
        "year": 2026
    },
    {
        "kapTitle": "AKTİF YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328d550c7a8b0155115ebdbc077a",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "20.05.2026",
        "stockCode": "AFB, AKTIF",
        "subject": "Sorumluluk Beyanı (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f35000461a",
        "year": 2026
    },
    {
        "kapTitle": "GOLDEN GLOBAL YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328d550c7a8b0155153518780bac",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "25.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b505b655131",
        "year": 2026
    },
    {
        "kapTitle": "GOLDEN GLOBAL YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328d550c7a8b0155153518780bac",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "25.05.2026",
        "stockCode": null,
        "subject": "Finansal Rapor",
        "taxonomyOid": "4028328d6233239a01629b523f5a5157",
        "year": 2026
    },
    {
        "kapTitle": "GOLDEN GLOBAL YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328d550c7a8b01551536b4260bbd",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "25.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide Olmayan)",
        "taxonomyOid": "4028328d537aad0a015383f35000461a",
        "year": 2026
    },
    {
        "kapTitle": "GOLDEN GLOBAL YATIRIM BANKASI A.Ş.",
        "ruleOid": "4028328d550c7a8b01551536b4260bbd",
        "ruleTypeTerm": "3 Aylık",
        "startDate": "01.04.2026",
        "endDate": "25.05.2026",
        "stockCode": null,
        "subject": "Sorumluluk Beyanı (Konsolide)",
        "taxonomyOid": "4028328d537aad0a015383f3d5ef4624",
        "year": 2026
    }
]

## Portföy Yönetim Şirketleri(PYS)

### Request

### Response

## Derecelendirme Şirketleri

### Request

### Response

## Bağımsız Denetim Kuruluşları

### Request

### Response

## Düzenleyici Denetleyici Kurumlar(DDK)

### Request

### Response

## Diğer KAP Üyeleri(DG)

### Request

### Response

## Kripto Varlık Hizmet Sağlayıcı(KVH)

### Request

### Response

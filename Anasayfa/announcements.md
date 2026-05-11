# announcements

Bu ağ isteği, KAP ana sayfasındaki "Genel Mektuplar" ve "Duyurular" bölümlerini doldurmak için kullanılan içerik servisidir.

## Analiz

- **Amaç:** MKK veya SPK tarafından yayımlanan resmi genel mektupları ve sistem duyurularını listelemek.
- **İçerik:** Yanıt iki ana kategoriye ayrılmıştır:
  - **Genel Mektuplar:** 2026 yılı finansal rapor tarihleri ve hizmet bedelleri gibi operasyonel konuları içerir.
  - **Duyurular:** Kurumsal yönetim tebliğleri ve site güncellemeleri gibi genel bilgilendirmeleri kapsar.
- **Performans:** İstek toplamda 35 ms sürmüştür. Waiting for server response (TTFB) süresinin 18 ms olması, sunucunun veriyi anında döndürdüğünü gösterir.

## Teknik Notlar

- **Önbellek (Caching):** Cache-Control: max-age=1800,public başlığı sayesinde veri 30 dakika boyunca tarayıcıda saklanır. Age: 1138 değeri, bu verinin yaklaşık 19 dakikadır sunucu önbelleğinde hazır beklediğini teyit eder.
- **Veri Bağlantısı:** Her duyurunun detayına gitmek için staticPagefileOid alanı anahtar kimlik (ID) olarak kullanılmaktadır.

## Kök Neden

İstek başarılıdır ve beklenen verileri eksiksiz getirmiştir. Herhangi bir darboğaz tespit edilmemiştir.

## Request

curl 'https://www.kap.org.tr/tr/api/home-data/announcements' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'DNT: 1' \
  -H 'If-None-Match: "KXBBPGFIFNSVSWYY"' \
  -H 'Referer: https://www.kap.org.tr/tr' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'

## Response

[
  {
    "id": "8a019492945fbe080194accf5adc27df",
    "menuTitle": "Genel Mektuplar",
    "menuUrl": "genel-mektuplar",
    "menuOrder": 2,
    "menuLang": "TR",
    "menuType": "list",
    "menuItself": null,
    "menuSuperOid": "8a019492945fbe080194ac9d67b626dd",
    "contentList": [
      {
        "listDate": "07.01.2026",
        "listNo": "1058",
        "listOrder": null,
        "listSubject": "2026 Yılı Finansal Rapor İlan Tarihleri",
        "staticPagefileOid": "8a019492945fbe080194acf109622904"
      },
      {
        "listDate": "07.01.2026",
        "listNo": "1057",
        "listOrder": null,
        "listSubject": "2026 Yılı KAP Hizmet Bedeli Tutarları",
        "staticPagefileOid": "8a0292b094bc3a500194cbe321b5003b"
      },
      {
        "listDate": "12.12.2025",
        "listNo": "1055",
        "listOrder": null,
        "listSubject": "KAP Kullanıcı Sertifikası Zorunluluğu ve Kripto Varlık Hizmet Sağlayıcıların KAP Üyeliğine İlişkin Yönerge Değişikliği",
        "staticPagefileOid": "525639a883ac494995eccc1da9919873"
      }
    ]
  },
  {
    "id": "8a019492945fbe080194accf716327e0",
    "menuTitle": "Duyurular",
    "menuUrl": "duyurular",
    "menuOrder": 1,
    "menuLang": "TR",
    "menuType": "list",
    "menuItself": null,
    "menuSuperOid": "8a019492945fbe080194ac9d67b626dd",
    "contentList": [
      {
        "listDate": "26.01.2026",
        "listNo": "1",
        "listOrder": null,
        "listSubject": "SPK'nın II-17.1 Sayılı Kurumsal Yönetim Tebliği Uyarınca Payları Borsada İşlem Gören Ortaklıkların 2026 Yılı İçin Dahil Oldukları Gruplar",
        "staticPagefileOid": "8a019492945fbe080194b271bbf248b6"
      },
      {
        "listDate": "22.03.2025",
        "listNo": "1",
        "listOrder": null,
        "listSubject": "KAP İnternet Sitesi Yenilendi.",
        "staticPagefileOid": "402832a195b3017d0195bd0ff0921236"
      },
      {
        "listDate": "27.11.2024",
        "listNo": "1",
        "listOrder": null,
        "listSubject": "Kamuyu Aydınlatma Platformu Veri Yayın Servisi Rest Api Entegrasyonu",
        "staticPagefileOid": "8a019492945fbe080194b26d8bed4873"
      }
    ]
  }
]

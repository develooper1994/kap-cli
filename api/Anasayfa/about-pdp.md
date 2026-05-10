# about-pdp

Bu ağ isteği, Kamu Aydınlatma Platformu (KAP) web sitesinin "Hakkında" veya "PDP" (Public Disclosure Platform) menü yapısını oluşturmak için kullanılan bir API çağrısıdır.

## Analiz:

- **Amaç:** Sunucudan İngilizce dilindeki menü başlıklarını ("General Information", "Related Web Links") ve bunlara ait yönlendirme yollarını içeren JSON verisini çekmek.
- **Durum:** 200 OK kodu, verinin başarıyla alındığını gösterir.
- **Performans:** Toplam 14 ms süren bu istek oldukça hızlıdır. Sunucu yanıt süresinin (TTFB) 6 ms olması, arka uç tarafında verinin muhtemelen önbellekten (cache) veya optimize edilmiş bir veritabanından sunulduğunu gösterir.
- **Önbellek:** Cache-Control: max-age=1800 başlığı, bu verinin tarayıcı veya ara sunucular tarafından 30 dakika boyunca saklanabileceğini belirtir. Bu durum, gereksiz ağ trafiğini azaltır.

## Kök Neden (Performans/Hata)

Herhangi bir performans sorunu veya hata saptanmamıştır. İstek ideal şekilde çalışmaktadır.

## Öneri

- **Geliştirme:** Eğer menü içeriği nadiren değişiyorsa, max-age süresi daha da artırılarak sunucu yükü minimize edilebilir.

## Request

curl 'https://www.kap.org.tr/en/api/menu/about-pdp' \
  -H 'Accept: */*' \
  -H 'Accept-Language: en' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -b '_ga=GA1.1.1580744861.1771666924; NSC_xxx.lbq.psh.us_tjuf_ejt=7ce2a3d9ddad9f0439920efb260b36acad4a64f3df2ef79bda6c88b7f8de60bb9ae4e5ca; client-ip=176.234.129.110; AGVY-Cookie=MDMAAA4A0lXwSwAAAACw6oFuCksAai3FSpkelF8UzLjYz-oDLWrQFEgLAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAIaJTslFrIwM_-rlurnobK0XTzhYC0sAagAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAJPY7Hc3oKUmdG5n1tC62tpUCbJE; KAP=AA47CksAajv3Rk0AAAAAADsUL9ZOBg_0wi2-O4NRJy7WEOkObmPiwRIWEldg1kXWOw==PEwAag==scmLPQjRedineP9oNTMvWPxiY5Q=; _ga_L21W6S1YS4=GS2.1.s1778402398$o16$g1$t1778404106$j55$l0$h0' \
  -H 'DNT: 1' \
  -H 'If-None-Match: "KXBBPGFIFNWPRNYY"' \
  -H 'Referer: https://www.kap.org.tr/en' \
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
    "id": "8a019492945fbe080194b22c06f84504",
    "menuTitle": "General Information",
    "menuUrl": "general-information",
    "menuOrder": 1,
    "menuLang": "EN",
    "urlStatus": "IN",
    "menuItself": "single",
    "menuOrigin": "KH"
  },
  {
    "id": "8a019492945fbe080194b22ed50e4547",
    "menuTitle": "Related Web Links",
    "menuUrl": "related-web-links",
    "menuOrder": 2,
    "menuLang": "EN",
    "urlStatus": "IN",
    "menuItself": "single",
    "menuOrigin": "KH"
  }
]

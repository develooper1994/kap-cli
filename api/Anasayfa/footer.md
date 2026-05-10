# footer

Bu ağ isteği, Kamu Aydınlatma Platformu (KAP) web sitesinin alt bilgi (footer) menüsünü oluşturmak için kullanılan bir API çağrısıdır.

## Analiz

- **Amaç:** Sayfanın en altındaki "Copyright and Disclaimer Notice", "Protection of Personal Data", "Site Help" ve "Contact" gibi menü kalemlerini ve bunlara ait URL yollarını JSON formatında çekmek.
- **Durum:** 200 OK başarılı. Sunucu veriyi beklenen şekilde döndürmüş.
- **Performans:** Toplam 10 ms süren bu işlem son derece verimlidir. Bekleme süresi (TTFB) 6 ms ile minimum düzeydedir.
- **Önbellek:** Veri gzip ile sıkıştırılmış ve 30 dakika (max-age=1800) geçerli olacak şekilde önbelleğe alınmıştır. Age: 949 değeri, yanıtın halihazırda bir ara sunucudan (CDN/Proxy) geldiğini doğrular.

## Kök Neden

Hata veya darboğaz bulunmamaktadır. İstek ideal hızda ve yapıdadır.

## Öneri

- **Optimizasyon:** Statik bir içerik olan footer verisi için 30 dakikalık önbellek süresi yeterlidir; ancak trafiği daha da azaltmak için bu süre uzatılabilir.

## Request

curl 'https://www.kap.org.tr/en/api/menu/footer' \
  -H 'Accept: */*' \
  -H 'Accept-Language: en' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -b '_ga=GA1.1.1580744861.1771666924; NSC_xxx.lbq.psh.us_tjuf_ejt=7ce2a3d9ddad9f0439920efb260b36acad4a64f3df2ef79bda6c88b7f8de60bb9ae4e5ca; client-ip=176.234.129.110; AGVY-Cookie=MDMAAA4A0lXwSwAAAACw6oFuCksAai3FSpkelF8UzLjYz-oDLWrQFEgLAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAIaJTslFrIwM_-rlurnobK0XTzhYC0sAagAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAJPY7Hc3oKUmdG5n1tC62tpUCbJE; _ga_L21W6S1YS4=GS2.1.s1778402398$o16$g1$t1778404106$j55$l0$h0; KAP=AA47CksAajv3Rk0AAAAAADsUL9ZOBg_0wi2-O4NRJy7WEOkObmPiwRIWEldg1kXWOw==PUwAag==Y9wT4-KWZdvuApIs8_k-6e7dsJU=' \
  -H 'DNT: 1' \
  -H 'If-None-Match: "KXBBPGFIFNWUYMYY"' \
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
    "id": "8a02910894b6de660194b70ed4910018",
    "menuTitle": "Copyright and Disclaimer Notice",
    "menuUrl": "copyright-and-disclaimer-notice",
    "menuOrder": 1,
    "menuLang": "EN",
    "urlStatus": null,
    "menuItself": null,
    "menuOrigin": "FO"
  },
  {
    "id": "8a02910894b6de660194b70ef6ee001a",
    "menuTitle": "Protection of Personal Data",
    "menuUrl": "protection-of-personal-data",
    "menuOrder": 2,
    "menuLang": "EN",
    "urlStatus": null,
    "menuItself": null,
    "menuOrigin": "FO"
  },
  {
    "id": "8a02910894b6de660194b70f0bc5001c",
    "menuTitle": "Site Help",
    "menuUrl": "site-help",
    "menuOrder": 3,
    "menuLang": "EN",
    "urlStatus": null,
    "menuItself": null,
    "menuOrigin": "FO"
  },
  {
    "id": "8a02910894b6de660194b70f27c3001e",
    "menuTitle": "Contact",
    "menuUrl": "contact",
    "menuOrder": 4,
    "menuLang": "EN",
    "urlStatus": null,
    "menuItself": null,
    "menuOrigin": "FO"
  }
]

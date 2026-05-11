# Bildirim

- url: <https://www.kap.org.tr/tr/Bildirim/{disclosureIndex}>
- [Hak Kullanımı](../Anasayfa/Hak%20Kullan%C4%B1m%C4%B1/Hak%20Kullan%C4%B1m%C4%B1.md) sayfasında belirtilen linke tıklandığında, bu sayfaya yönlendirilir.

## Request

curl 'https://www.kap.org.tr/tr/Bildirim/1575261' \
  -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7' \
  -H 'Accept-Language: en-US,en;q=0.9,tr-TR;q=0.8,tr;q=0.7' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'DNT: 1' \
  -H 'If-None-Match: "KXBBPGFIFNRNNLXY"' \
  -H 'Referer: https://www.kap.org.tr/tr' \
  -H 'Sec-Fetch-Dest: document' \
  -H 'Sec-Fetch-Mode: navigate' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'Sec-Fetch-User: ?1' \
  -H 'Upgrade-Insecure-Requests: 1' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'

## Response

- İçeriğinde bildirim detaylarının bulunduğu HTML döner. html içeriğinde Şirket ismi, bildirim tarihi, bildirim türü gibi bilgiler bulunur. 
Ayrıca pdf dosyasının linki bulunur.

# Finansal Tablolar

İçeriğinde finansal tablolar bulunan raporları indirmek için kullanılan API servisleridir.

- istek 1: <https://www.kap.org.tr/tr/api/financialTable/listCompanyExcelMembers/{mkkMemberOid}/{year}/{period}>
- istek 2: <https://www.kap.org.tr/tr/api/home-financial/download-file/{mkkMemberOid}/{year}/{period}>

## Parametreler

data-raw ile parametre almaz, url üzerinden parametre alır.

### mkkMemberOid

- <https://www.kap.org.tr/tr/api/member/filter/{Sorgu Metni}> servisi kullanılarak mkkMemberOid değeri bulunabilir. Sorgu metni şirketin adı veya hisse kodu olabilir. Örneğin, ASELSAN için sorgu metni "ASELS" olabilir.

### year

- Sorgunun yapılacağı yıldan en fazla 17 yıl öncesine kadar olan yıllar sorgulanabilir. Örneğin, 2026 yılı için 2009 yılına kadar sorgulama yapılabilir.

### period

- 1: 3 aylık
- 2: 6 aylık
- 3: 9 aylık
- 4: Yıllık(12 aylık)
- T: Tüm dönemler

## istek 1

Finansal tablo

### Request(istek 1)

curl 'https://www.kap.org.tr/tr/api/financialTable/listCompanyExcelMembers/4028e4a1416e696301416f321c3d5ca7/2026/1' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'DNT: 1' \
  -H 'Referer: https://www.kap.org.tr/tr' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'

### Response(istek 1)

[
    {
        "mkkMemberOid": "4028e4a1416e696301416f321c3d5ca7",
        "stockCode": "ULUFA",
        "pdOid": "4028328c9d7b22d3019db4dcdbe268a7",
        "disclosureIndex": 1596830,
        "year": 2026,
        "period": 1,
        "title": "ULUSAL FAKTORİNG A.Ş."
    }
]

## istek 2

### Request(istek 2)

curl 'https://www.kap.org.tr/tr/api/home-financial/download-file/4028e4a1416e696301416f321c3d5ca7/2026/1' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'DNT: 1' \
  -H 'Referer: https://www.kap.org.tr/tr' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'

### Response(istek 2)

> istek 1 gönderildikten sonra aynı mkkMemberOid ile zip dosyası indirmek üzere get isteği atılır. Bu kısmın nasıl çalıştığını bilmiyorum. Dosya nasıl indirilecek bilmiyorum.

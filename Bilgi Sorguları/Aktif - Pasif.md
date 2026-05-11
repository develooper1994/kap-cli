# Aktif - Pasif

- url: https://www.kap.org.tr/tr/api/company/items/{memberTypes}/{state}
- Şirket Grubu(memberTypes): Yatırım Kuruluşları(YK), Portföy Yönetim Şirketleri(PYS)
- state: Aktif şirketler için A, Pasif şirketler için P kullanılır.
- Yanıtlar çok uzun olabiliyor.

## Aktif

### Request - YK

curl 'https://www.kap.org.tr/tr/api/company/items/YK/A' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'DNT: 1' \
  -H 'Referer: https://www.kap.org.tr/tr/beklenen-bildirim-sorgu' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'

### Response - YK

[
    {
        "kapMemberOid": "33E5FED7048700EAE0530A4A622B2AEA",
        "kapMemberType": "YK",
        "kapMemberState": "A",
        "financialType": "SIR",
        "kayitliSermayeTavani": null,
        "faaliyetDurumu": "N",
        "payIslemDurumu": "0",
        "mkkMemberOid": "4028e4a2416e696c01416f6cb7c071d9",
        "kapMemberTitle": "ACAR MENKUL DEĞERLER A.Ş.",
        "taxNo": "0040032382",
        "taxOffice": "İSTANBUL - Boğaziçi Kurumlar Vergi Dairesi Müdürlüğü",
        "tradeRegNo": "232983",
        "tradeRegOffice": "İSTANBUL",
        "tradeRegDate": "13/04/1987 00:00:00",
        "paidCapital": 12887787,
        "relatedMemberOid": "33E5FED7250C00EAE0530A4A622B2AEA",
        "relatedMemberTitle": "REPORT BAĞIMSIZ DENETİM A.Ş.",
        "stockCode": "ACA",
        "abcdCode": "B",
        "companyCode": "1254",
        "kapTypes": "YK",
        "nonInactiveCount": 1,
        "cityName": "İSTANBUL",
        "sgbfOrtaklikYapisi": "N"
    },
    {
        "kapMemberOid": "8acae2c557ff627301581b1939f71021",
        "kapMemberType": "YK",
        "kapMemberState": "A",
        "financialType": "SIR",
        "kayitliSermayeTavani": null,
        "faaliyetDurumu": "N",
        "payIslemDurumu": "0",
        "mkkMemberOid": "b50f7181e8214f789bc426313a5b4b4a",
        "kapMemberTitle": "AHLATCI YATIRIM MENKUL DEĞERLER A.Ş.",
        "taxNo": "0100564530",
        "taxOffice": "İSTANBUL - Alemdağ Vergi Dairesi",
        "tradeRegNo": "38058-5",
        "tradeRegOffice": "İSTANBUL",
        "tradeRegDate": "30/12/2015 00:00:00",
        "paidCapital": 600000000,
        "relatedMemberOid": "8acae2c561c44d7401620088778531b5",
        "relatedMemberTitle": "REFORM BAĞIMSIZ DENETİM A.Ş.",
        "stockCode": "AYX",
        "abcdCode": "A",
        "companyCode": "4315",
        "kapTypes": "YK",
        "nonInactiveCount": 1,
        "cityName": "İSTANBUL",
        "sgbfOrtaklikYapisi": "N"
    },
    {
        "kapMemberOid": "33E5FED7048B00EAE0530A4A622B2AEA",
        "kapMemberType": "YK",
        "kapMemberState": "A",
        "financialType": "SIR",
        "kayitliSermayeTavani": null,
        "faaliyetDurumu": "N",
        "payIslemDurumu": "0",
        "mkkMemberOid": "4028e4a240e8d16e0140e8f3d0fe0047",
        "kapMemberTitle": "AK YATIRIM MENKUL DEĞERLER A.Ş.",
        "taxNo": "0110077837",
        "taxOffice": "İSTANBUL - Boğaziçi Kurumlar Vergi Dairesi Müdürlüğü",
        "tradeRegNo": "358178-305760",
        "tradeRegOffice": "İSTANBUL",
        "tradeRegDate": "11/12/1996 00:00:00",
        "paidCapital": 80000000,
        "relatedMemberOid": "33E5FED7244500EAE0530A4A622B2AEA",
        "relatedMemberTitle": "DRT BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "stockCode": "AKM, AKMEN",
        "abcdCode": "A, -",
        "companyCode": "2485",
        "kapTypes": "IGS,YK",
        "nonInactiveCount": 2,
        "cityName": "İSTANBUL",
        "sgbfOrtaklikYapisi": "N"
    },
    {
        "kapMemberOid": "33E5FED7070500EAE0530A4A622B2AEA",
        "kapMemberType": "YK",
        "kapMemberState": "A",
        "financialType": "BNK",
        "kayitliSermayeTavani": null,
        "faaliyetDurumu": "N",
        "payIslemDurumu": "0",
        "mkkMemberOid": "4028e4a240e8d1830140e905edcd0006",
        "kapMemberTitle": "AKBANK T.A.Ş.",
        "taxNo": "0150015264",
        "taxOffice": "İSTANBUL - Büyük Mükellefler Vergi Dairesi Müdürlüğü",
        "tradeRegNo": "90418-35272",
        "tradeRegOffice": "İSTANBUL",
        "tradeRegDate": "30/01/1948 00:00:00",
        "paidCapital": 5200000000,
        "relatedMemberOid": "33E5FED7244500EAE0530A4A622B2AEA",
        "relatedMemberTitle": "DRT BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "stockCode": "AKBNK",
        "abcdCode": "-",
        "companyCode": "2413",
        "kapTypes": "IGS,YK",
        "nonInactiveCount": 2,
        "cityName": "İSTANBUL",
        "sgbfOrtaklikYapisi": "N"
    },
    {
        "kapMemberOid": "33E5FED7067D00EAE0530A4A622B2AEA",
        "kapMemberType": "YK",
        "kapMemberState": "A",
        "financialType": "BNK",
        "kayitliSermayeTavani": null,
        "faaliyetDurumu": "N",
        "payIslemDurumu": "0",
        "mkkMemberOid": "1DE05DAA8212073AE0530A4A622A2EBD",
        "kapMemberTitle": "AKTİF YATIRIM BANKASI A.Ş.",
        "taxNo": "2250136537",
        "taxOffice": "İSTANBUL - Büyük Mükellefler Vergi Dairesi Müdürlüğü",
        "tradeRegNo": "424040",
        "tradeRegOffice": "İSTANBUL",
        "tradeRegDate": "28/07/1999 00:00:00",
        "paidCapital": 1193585477,
        "relatedMemberOid": "33E5FED7244500EAE0530A4A622B2AEA",
        "relatedMemberTitle": "DRT BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "stockCode": "AFB, AKTIF",
        "abcdCode": "-, -",
        "companyCode": "2212",
        "kapTypes": "IGS,YK",
        "nonInactiveCount": 2,
        "cityName": "İSTANBUL",
        "sgbfOrtaklikYapisi": "N"
    }
]

## Pasif

### Request - YK

curl 'https://www.kap.org.tr/tr/api/company/items/YK/P' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'DNT: 1' \
  -H 'Referer: https://www.kap.org.tr/tr/beklenen-bildirim-sorgu' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'

### Response - YK

[
    {
        "kapMemberOid": "33E5FED7048600EAE0530A4A622B2AEA",
        "kapMemberType": "YK",
        "kapMemberState": "P",
        "financialType": null,
        "kayitliSermayeTavani": null,
        "faaliyetDurumu": null,
        "payIslemDurumu": "0",
        "mkkMemberOid": "33E5FED7048500EAE0530A4A622B2AEA",
        "kapMemberTitle": "ABN AMRO YATIRIM MENKUL DEĞERLER A.Ş.",
        "taxNo": null,
        "taxOffice": null,
        "tradeRegNo": null,
        "tradeRegOffice": null,
        "tradeRegDate": "",
        "paidCapital": null,
        "relatedMemberOid": null,
        "relatedMemberTitle": null,
        "stockCode": "AHG",
        "abcdCode": "-",
        "companyCode": "1253",
        "kapTypes": null,
        "nonInactiveCount": 0,
        "cityName": "İSTANBUL",
        "sgbfOrtaklikYapisi": "N"
    },
    {
        "kapMemberOid": "33E5FED7048A00EAE0530A4A622B2AEA",
        "kapMemberType": "YK",
        "kapMemberState": "P",
        "financialType": null,
        "kayitliSermayeTavani": null,
        "faaliyetDurumu": null,
        "payIslemDurumu": "0",
        "mkkMemberOid": "33E5FED7048900EAE0530A4A622B2AEA",
        "kapMemberTitle": "ADA MENKUL DEĞERLER A.Ş.",
        "taxNo": "1",
        "taxOffice": "ADANA - 5 Ocak Vergi Dairesi Müdürlüğü",
        "tradeRegNo": "1",
        "tradeRegOffice": "ACIPAYAM",
        "tradeRegDate": "",
        "paidCapital": null,
        "relatedMemberOid": "33E5FED7248500EAE0530A4A622B2AEA",
        "relatedMemberTitle": "SAYGIN YEMİNLİ MALİ MÜŞAVİRLİK VE DENETİM A.Ş.",
        "stockCode": "ADM",
        "abcdCode": "-",
        "companyCode": "1255",
        "kapTypes": null,
        "nonInactiveCount": 0,
        "cityName": "İSTANBUL",
        "sgbfOrtaklikYapisi": "N"
    },
    {
        "kapMemberOid": "33E5FED7048D00EAE0530A4A622B2AEA",
        "kapMemberType": "YK",
        "kapMemberState": "P",
        "financialType": null,
        "kayitliSermayeTavani": null,
        "faaliyetDurumu": null,
        "payIslemDurumu": "0",
        "mkkMemberOid": "1DE05DAA817C073AE0530A4A622A2EBD",
        "kapMemberTitle": "AKDENİZ MENKUL DEĞERLER TİCARETİ A.Ş.",
        "taxNo": "0210051072",
        "taxOffice": null,
        "tradeRegNo": "263283/210855",
        "tradeRegOffice": null,
        "tradeRegDate": "01/03/1990 00:00:00",
        "paidCapital": 0,
        "relatedMemberOid": "33E5FED724BA00EAE0530A4A622B2AEA",
        "relatedMemberTitle": "KARDEN PARTNERS BAĞIMSIZ DENETİM VE SMMM A.Ş.",
        "stockCode": "AKD",
        "abcdCode": "-",
        "companyCode": "1257",
        "kapTypes": null,
        "nonInactiveCount": 0,
        "cityName": "İSTANBUL",
        "sgbfOrtaklikYapisi": "N"
    }
]



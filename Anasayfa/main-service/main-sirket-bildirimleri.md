# main(Şirket Bildirimleri)

## request

curl 'https://www.kap.org.tr/tr/api/disclosure/list/main' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -b '_ga=GA1.1.1671240860.1776072570; client-ip=185.81.238.214; AGVY-Cookie=MDMAAAcA45wuEwAAAAC5Ue7WuGgBanJRbKFsGMjpsXmm2jNDCVns2KsuAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAANnhxSlpjAdqnEkV4Ec4Ysfh0qriumgBagAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAMX8KzniCbsidoW7EM2NrjuACnoW; _ga_L21W6S1YS4=GS2.1.s1778477236$o6$g1$t1778477268$j28$l0$h0; NSC_xxx.lbq.psh.us_tjuf_ejt=7ce2a3d9ddad9f0439920efb260b36acad4a64f3df2ef79bda6c88b7f8de60bb9ae4e5ca; KAP=AAc7uGgBajtUiFYAAAAAADsUL9ZOBg_0wi2-O_xu4s6Nvv0CgUba9If1if1AWwePOw==lm4Bag==zN-BFm4EeCrlYKSxZovF2PU8KUA=' \
  -H 'DNT: 1' \
  -H 'Origin: https://www.kap.org.tr' \
  -H 'Referer: https://www.kap.org.tr/tr' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  --data-raw '{"fromDate":"26.04.2026","toDate":"11.05.2026","disclosureTypes":["ODA","FR","DUY","DG","CA"],"memberTypes":["IGS","DDK","YK","PYS","KVH","DG"],"mkkMemberOid":"4028e4a1413b7ef401413bc2251e0047"}'

## response

[
    {
        "disclosureBasic": {
            "title": "Genel Kurul İşlemlerine İlişkin Bildirim",
            "mkkMemberOid": "4028e4a1413b7ef401413bc2251e0047",
            "companyTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
            "stockCode": "ASELS",
            "relatedStocks": null,
            "disclosureClass": "ODA",
            "disclosureType": "CA",
            "disclosureCategory": "STT",
            "publishDate": "04.05.2026 18:14:33",
            "disclosureId": "4028328c9d7b22d3019df32754701076",
            "disclosureIndex": 1600707,
            "summary": "Olağan Genel Kurul Çağrısı/Bağımsız Yönetim Kurulu Aday Bilgisi",
            "attachmentCount": 2,
            "year": null,
            "donem": null,
            "period": "HZ",
            "hasMultiLanguageSupport": "Y",
            "fundType": null,
            "isLate": false,
            "relatedDisclosureOid": "4028328d9d7b24c9019d9b26949d4e83",
            "senderType": null,
            "isChanged": null,
            "isBlocked": false
        },
        "disclosureDetail": {
            "ftNiteligi": null,
            "decimalDegree": null,
            "opinion": null,
            "opinionType": null,
            "auditType": null,
            "mainDisclosureDocumentId": null,
            "opinionMemberTitle": null,
            "relatedDisclosureIndex": null,
            "oldKap": false,
            "fundOid": null,
            "senderTypes": null,
            "nonInactiveCount": null,
            "blockedDescription": null,
            "memberType": null
        }
    },
    {
        "disclosureBasic": {
            "title": "Yeni İş İlişkisi",
            "mkkMemberOid": "4028e4a1413b7ef401413bc2251e0047",
            "companyTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
            "stockCode": "ASELS",
            "relatedStocks": null,
            "disclosureClass": "ODA",
            "disclosureType": "ODA",
            "disclosureCategory": "ODA",
            "publishDate": "30.04.2026 09:21:17",
            "disclosureId": "4028328c9d7b22d2019ddd0aaf19266f",
            "disclosureIndex": 1599128,
            "summary": "Sözleşme İmzalanması",
            "attachmentCount": 0,
            "year": null,
            "donem": null,
            "period": "HZ",
            "hasMultiLanguageSupport": "Y",
            "fundType": null,
            "isLate": false,
            "relatedDisclosureOid": null,
            "senderType": null,
            "isChanged": null,
            "isBlocked": false
        },
        "disclosureDetail": {
            "ftNiteligi": null,
            "decimalDegree": null,
            "opinion": null,
            "opinionType": null,
            "auditType": null,
            "mainDisclosureDocumentId": null,
            "opinionMemberTitle": null,
            "relatedDisclosureIndex": null,
            "oldKap": false,
            "fundOid": null,
            "senderTypes": null,
            "nonInactiveCount": null,
            "blockedDescription": null,
            "memberType": null
        }
    },
    {
        "disclosureBasic": {
            "title": "Şirket Genel Bilgi Formu",
            "mkkMemberOid": "4028e4a1413b7ef401413bc2251e0047",
            "companyTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
            "stockCode": "ASELS",
            "relatedStocks": null,
            "disclosureClass": "DG",
            "disclosureType": "DG",
            "disclosureCategory": "STT",
            "publishDate": "28.04.2026 18:32:45",
            "disclosureId": "4028328c9d7b22d2019dd2fe077c0cf2",
            "disclosureIndex": 1598323,
            "summary": null,
            "attachmentCount": 0,
            "year": null,
            "donem": null,
            "period": "HZ",
            "hasMultiLanguageSupport": "Y",
            "fundType": null,
            "isLate": false,
            "relatedDisclosureOid": null,
            "senderType": null,
            "isChanged": null,
            "isBlocked": false
        },
        "disclosureDetail": {
            "ftNiteligi": null,
            "decimalDegree": null,
            "opinion": null,
            "opinionType": null,
            "auditType": null,
            "mainDisclosureDocumentId": null,
            "opinionMemberTitle": null,
            "relatedDisclosureIndex": null,
            "oldKap": false,
            "fundOid": null,
            "senderTypes": null,
            "nonInactiveCount": null,
            "blockedDescription": null,
            "memberType": null
        }
    },
    {
        "disclosureBasic": {
            "title": "Sorumluluk Beyanı (Konsolide)",
            "mkkMemberOid": "4028e4a1413b7ef401413bc2251e0047",
            "companyTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
            "stockCode": "ASELS",
            "relatedStocks": null,
            "disclosureClass": "FR",
            "disclosureType": "FR",
            "disclosureCategory": "ODA",
            "publishDate": "28.04.2026 18:32:04",
            "disclosureId": "4028328c9d7b22d3019dd446e16e0074",
            "disclosureIndex": 1598321,
            "summary": "28 Nisan 2026 Z-AS331-843.05.01-10727",
            "attachmentCount": 0,
            "year": 2026,
            "donem": 1,
            "period": "3AB",
            "hasMultiLanguageSupport": "N",
            "fundType": null,
            "isLate": false,
            "relatedDisclosureOid": null,
            "senderType": null,
            "isChanged": null,
            "isBlocked": false
        },
        "disclosureDetail": {
            "ftNiteligi": null,
            "decimalDegree": null,
            "opinion": null,
            "opinionType": null,
            "auditType": null,
            "mainDisclosureDocumentId": null,
            "opinionMemberTitle": null,
            "relatedDisclosureIndex": null,
            "oldKap": false,
            "fundOid": null,
            "senderTypes": null,
            "nonInactiveCount": null,
            "blockedDescription": null,
            "memberType": null
        }
    },
    {
        "disclosureBasic": {
            "title": "Faaliyet Raporu (Konsolide)",
            "mkkMemberOid": "4028e4a1413b7ef401413bc2251e0047",
            "companyTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
            "stockCode": "ASELS",
            "relatedStocks": null,
            "disclosureClass": "FR",
            "disclosureType": "FR",
            "disclosureCategory": "ODA",
            "publishDate": "28.04.2026 18:31:52",
            "disclosureId": "4028328c9d7b22d3019dd43eeb857fb8",
            "disclosureIndex": 1598319,
            "summary": "28 Nisan 2026 1304 Sayılı Yönetim Kurulu Kararı",
            "attachmentCount": 2,
            "year": 2026,
            "donem": 1,
            "period": "3AB",
            "hasMultiLanguageSupport": "Y",
            "fundType": null,
            "isLate": false,
            "relatedDisclosureOid": null,
            "senderType": null,
            "isChanged": null,
            "isBlocked": false
        },
        "disclosureDetail": {
            "ftNiteligi": null,
            "decimalDegree": null,
            "opinion": null,
            "opinionType": null,
            "auditType": null,
            "mainDisclosureDocumentId": null,
            "opinionMemberTitle": null,
            "relatedDisclosureIndex": null,
            "oldKap": false,
            "fundOid": null,
            "senderTypes": null,
            "nonInactiveCount": null,
            "blockedDescription": null,
            "memberType": null
        }
    },
    {
        "disclosureBasic": {
            "title": "Finansal Rapor",
            "mkkMemberOid": "4028e4a1413b7ef401413bc2251e0047",
            "companyTitle": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
            "stockCode": "ASELS",
            "relatedStocks": null,
            "disclosureClass": "FR",
            "disclosureType": "FR",
            "disclosureCategory": "FR",
            "publishDate": "28.04.2026 18:31:38",
            "disclosureId": "4028328d9d7b24c9019dd4491f413f19",
            "disclosureIndex": 1598316,
            "summary": "31 Mart 2026 Finansal Tabloları",
            "attachmentCount": 2,
            "year": 2026,
            "donem": 1,
            "period": "3AB",
            "hasMultiLanguageSupport": "Y",
            "fundType": null,
            "isLate": false,
            "relatedDisclosureOid": null,
            "senderType": null,
            "isChanged": null,
            "isBlocked": false
        },
        "disclosureDetail": {
            "ftNiteligi": null,
            "decimalDegree": null,
            "opinion": null,
            "opinionType": null,
            "auditType": null,
            "mainDisclosureDocumentId": null,
            "opinionMemberTitle": null,
            "relatedDisclosureIndex": null,
            "oldKap": false,
            "fundOid": null,
            "senderTypes": null,
            "nonInactiveCount": null,
            "blockedDescription": null,
            "memberType": null
        }
    }
]


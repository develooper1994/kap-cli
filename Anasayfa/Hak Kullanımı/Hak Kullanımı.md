# Hak Kullanımı

İçeriğinde hak kullanımı bilgileri bulunan raporları arar ve gerekli linke yönlendirir. Hak kullanımı bilgileri, şirketlerin genel kurul toplantıları, sermaye artırımları, temettü ödemeleri gibi olayları içerir.

Not: Bir tür alive mesajı olsa gerek. "bot-response:"!!!!"" string döndüren bir istek var. market-data-tracker.js scriptinin içindeki link her istekte değişiyor. Bu istekler hak kullanımı sayfasına erişildiğinde yapılıyor. Ancak bu isteklerin amacı ve dönen verinin içeriği henüz anlaşılamadı. Bu nedenle bu istekler hakkında bilgi verilmemiştir.

- İstek 1: <https://www.kap.org.tr/tr/api/ca/allCa/{year}/{period}>
- İstek 2: <https://www.kap.org.tr/tr/api/ca/filteredCa/{year}/{period}/{mkkMemberOid}>

## Yönlendirilen link

- url: <https://www.kap.org.tr/tr/Bildirim/{disclosureIndex}>
- [Bildirim](../../Bildirim/Bildirim.md) sayfasına yönlendirilir.

## Parametreler

data-raw ile parametre almaz, url üzerinden parametre alır.

### year

- Sadece sorgunun yapılacağı yıl sorgulanabilir.

### period

Ay numarasını belirtir.

- 01: Ocak
- 02: Şubat
- 03: Mart
- 04: Nisan
- 05: Mayıs
- 06: Haziran
- 07: Temmuz
- 08: Ağustos
- 09: Eylül
- 10: Ekim
- 11: Kasım
- 12: Aralık

### mkkMemberOid

- <https://www.kap.org.tr/tr/api/member/filter/{Sorgu> Metni} servisi kullanılarak mkkMemberOid değeri bulunabilir. Sorgu metni şirketin adı veya hisse kodu olabilir. Örneğin, ASELSAN için sorgu metni "ASELS" olabilir.

## İstek 1

- Amaç: Belirtilen yıl ve ay için hak kullanımı bilgilerini listeler.

### Request(istek 1)

curl '<https://www.kap.org.tr/tr/api/ca/allCa/2026/04>' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'DNT: 1' \
  -H 'Referer: <https://www.kap.org.tr/tr>' \
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
        "date": "2026/04/01",
        "generalMeeting": null,
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": {
            "companies": [
                "QNB FİNANSAL KİRALAMA A.Ş."
            ],
            "disclosureIndex": [
                1602535
            ],
            "count": 1
        },
        "dividendPayment": {
            "companies": [
                "AFYON ÇİMENTO SANAYİ T.A.Ş.",
                "ANADOLU ANONİM TÜRK SİGORTA ŞİRKETİ",
                "ASCE GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "ÇİMSA ÇİMENTO SANAYİ VE TİCARET A.Ş.",
                "HACI ÖMER SABANCI HOLDİNG A.Ş.",
                "İŞ YATIRIM MENKUL DEĞERLER A.Ş.",
                "TÜRKİYE İŞ BANKASI A.Ş."
            ],
            "disclosureIndex": [
                1579144,
                1579442,
                1579152,
                1579304,
                1580562,
                1579549,
                1580260
            ],
            "count": 7
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/02",
        "generalMeeting": {
            "companies": [
                "BANTAŞ BANDIRMA AMBALAJ SANAYİ VE TİCARET A.Ş.",
                "DENİZ GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "GALATA WIND ENERJİ A.Ş.",
                "MEDİTERA TIBBİ MALZEME SANAYİ VE TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1584662,
                1595745,
                1597447,
                1583384
            ],
            "count": 4
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": null,
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/03",
        "generalMeeting": {
            "companies": [
                "HÜRRİYET GAZETECİLİK VE MATBAACILIK A.Ş."
            ],
            "disclosureIndex": [
                1595034
            ],
            "count": 1
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "AKSA AKRİLİK KİMYA SANAYİİ A.Ş."
            ],
            "disclosureIndex": [
                1581038
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/04",
        "generalMeeting": {
            "companies": [
                "YENİ GİMAT GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş."
            ],
            "disclosureIndex": [
                1594765
            ],
            "count": 1
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": null,
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/06",
        "generalMeeting": {
            "companies": [
                "BİOTREND ÇEVRE VE ENERJİ YATIRIMLARI A.Ş.",
                "TUREKS TURUNÇ MADENCİLİK İÇ VE DIŞ TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1597274,
                1586979
            ],
            "count": 2
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "ULUSAL FAKTORİNG A.Ş."
            ],
            "disclosureIndex": [
                1575261
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/07",
        "generalMeeting": {
            "companies": [
                "AKMERKEZ GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "ALKİM KAĞIT SANAYİ VE TİCARET A.Ş.",
                "A1 CAPİTAL YATIRIM MENKUL DEĞERLER A.Ş.",
                "BORUSAN YATIRIM VE PAZARLAMA A.Ş.",
                "ENSARİ SINAİ YATIRIMLAR A.Ş.",
                "GÜNDOĞDU GIDA SÜT ÜRÜNLERİ SANAYİ VE DIŞ TİCARET A.Ş.",
                "SMART GÜNEŞ ENERJİSİ TEKNOLOJİLERİ ARAŞTIRMA GELİŞTİRME ÜRETİM SANAYİ VE TİCARET A.Ş.",
                "SODAŞ SODYUM SANAYİİ A.Ş.",
                "TEMAPOL POLİMER PLASTİK VE İNŞAAT SANAYİ TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1592325,
                1592165,
                1590932,
                1593485,
                1590874,
                1591951,
                1598726,
                1589973,
                1588152
            ],
            "count": 9
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "TÜRKİYE GARANTİ BANKASI A.Ş.",
                "YENİ GİMAT GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş."
            ],
            "disclosureIndex": [
                1581049,
                1584134
            ],
            "count": 2
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/08",
        "generalMeeting": {
            "companies": [
                "COCA-COLA İÇECEK A.Ş.",
                "LDR TURİZM A.Ş.",
                "MEGA METAL SANAYİ VE TİCARET A.Ş.",
                "ODİNE SOLUTİONS TEKNOLOJİ TİCARET VE SANAYİ A.Ş.",
                "TÜRKİYE KALKINMA VE YATIRIM BANKASI A.Ş."
            ],
            "disclosureIndex": [
                1589387,
                1592971,
                1591187,
                1593509,
                1587800
            ],
            "count": 5
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "BORUSAN YATIRIM VE PAZARLAMA A.Ş.",
                "ENKA İNŞAAT VE SANAYİ A.Ş."
            ],
            "disclosureIndex": [
                1585800,
                1577628
            ],
            "count": 2
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/09",
        "generalMeeting": {
            "companies": [
                "ALKİM ALKALİ KİMYA A.Ş.",
                "BEYAZ FİLO OTO KİRALAMA A.Ş.",
                "FLAP KONGRE TOPLANTI HİZMETLERİ OTOMOTİV VE TURİZM A.Ş.",
                "GELECEK VARLIK YÖNETİMİ A.Ş.",
                "GRAINTURK HOLDİNG A.Ş.",
                "HATEKS HATAY TEKSTİL İŞLETMELERİ A.Ş.",
                "KIRAÇ GALVANİZ TELEKOMİNİKASYON METAL MAKİNE İNŞAAT ELEKTRİK SANAYİ VE TİCARET A.Ş.",
                "KUZUGRUP GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "PASİFİK GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "RAL YATIRIM HOLDİNG A.Ş.",
                "RAL YATIRIM HOLDİNG A.Ş.",
                "TÜRK HAVA YOLLARI A.O.",
                "TÜRK TELEKOMÜNİKASYON A.Ş.",
                "TÜRKİYE HALK BANKASI A.Ş.",
                "TÜRKİYE SİGORTA A.Ş.",
                "TÜRKİYE VAKIFLAR BANKASI T.A.O.",
                "VAKKO TEKSTİL VE HAZIR GİYİM SANAYİ İŞLETMELERİ A.Ş.",
                "YONGA MOBİLYA SANAYİ VE TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1597134,
                1591064,
                1590427,
                1596914,
                1595755,
                1603985,
                1593334,
                1593315,
                1591112,
                1590045,
                1593337,
                1592906,
                1596236,
                1596245,
                1597028,
                1595504,
                1597115,
                1591056
            ],
            "count": 18
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": null,
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/10",
        "generalMeeting": {
            "companies": [
                "ARMADA GIDA TİCARET SANAYİ A.Ş.",
                "BAYRAK EBT TABAN SANAYİ VE TİCARET A.Ş.",
                "DEVA HOLDİNG A.Ş.",
                "DOĞAN ŞİRKETLER GRUBU HOLDİNG A.Ş.",
                "KARDEMİR KARABÜK DEMİR ÇELİK SANAYİ VE TİCARET A.Ş.",
                "POLİTEKNİK METAL SANAYİ VE TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1596369,
                1590851,
                1594110,
                1597459,
                1597193,
                1593976
            ],
            "count": 6
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": null,
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/13",
        "generalMeeting": {
            "companies": [
                "ALARKO HOLDİNG A.Ş.",
                "ANADOLU EFES BİRACILIK VE MALT SANAYİİ A.Ş.",
                "ESCAR FİLO KİRALAMA HİZMETLERİ A.Ş.",
                "MİGROS TİCARET A.Ş.",
                "OBASE BİLGİSAYAR VE DANIŞMANLIK HİZMETLERİ TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1597768,
                1602713,
                1593842,
                1598399,
                1601409
            ],
            "count": 5
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "DOĞUŞ OTOMOTİV SERVİS VE TİCARET A.Ş.",
                "ENERJİSA ENERJİ A.Ş.",
                "GELECEK VARLIK YÖNETİMİ A.Ş."
            ],
            "disclosureIndex": [
                1589325,
                1575612,
                1590326
            ],
            "count": 3
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/14",
        "generalMeeting": {
            "companies": [
                "AKİŞ GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "DESA DERİ SANAYİ VE TİCARET A.Ş.",
                "İZDEMİR ENERJİ ELEKTRİK ÜRETİM A.Ş.",
                "İZMİR DEMİR ÇELİK SANAYİ A.Ş.",
                "KARTONSAN KARTON SANAYİ VE TİCARET A.Ş.",
                "MAKİNA TAKIM ENDÜSTRİSİ A.Ş.",
                "SUR TATİL EVLERİ GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "YEO TEKNOLOJİ ENERJİ VE ENDÜSTRİ A.Ş."
            ],
            "disclosureIndex": [
                1596229,
                1598719,
                1596563,
                1594904,
                1594336,
                1596898,
                1595231,
                1598458
            ],
            "count": 8
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "VAKKO TEKSTİL VE HAZIR GİYİM SANAYİ İŞLETMELERİ A.Ş."
            ],
            "disclosureIndex": [
                1590209
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/15",
        "generalMeeting": {
            "companies": [
                "ADEL KALEMCİLİK TİCARET VE SANAYİ A.Ş.",
                "AYEN ENERJİ A.Ş.",
                "BİEN YAPI ÜRÜNLERİ SANAYİ TURİZM VE TİCARET A.Ş.",
                "JANTSA JANT SANAYİ VE TİCARET A.Ş.",
                "KRON TEKNOLOJİ A.Ş.",
                "LİDER FAKTORİNG A.Ş.",
                "MATRİKS FİNANSAL TEKNOLOJİLER A.Ş.",
                "OYAK YATIRIM ORTAKLIĞI A.Ş.",
                "PARSAN MAKİNA PARÇALARI SANAYİİ A.Ş.",
                "SDT UZAY VE SAVUNMA TEKNOLOJİLERİ A.Ş.",
                "YAYLA ENERJİ ÜRETİM TURİZM VE İNŞAAT TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1593721,
                1595757,
                1596467,
                1594079,
                1595278,
                1598082,
                1596023,
                1593881,
                1593917,
                1594958,
                1594196
            ],
            "count": 11
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "AKMERKEZ GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "ALBARAKA TÜRK KATILIM BANKASI A.Ş.",
                "BATI EGE GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş."
            ],
            "disclosureIndex": [
                1589983,
                1577845,
                1493228
            ],
            "count": 3
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/16",
        "generalMeeting": {
            "companies": [
                "ÇELEBİ HAVA SERVİSİ A.Ş.",
                "DÖKTAŞ DÖKÜMCÜLÜK TİCARET VE SANAYİ A.Ş.",
                "MİSTRAL GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "NETCAD YAZILIM A.Ş.",
                "SAFKAR EGE SOĞUTMACILIK KLİMA SOĞUK HAVA TESİSLERİ İHRACAT İTHALAT SANAYİ VE TİCARET A.Ş.",
                "SAN-EL MÜHENDİSLİK ELEKTRİK TAAHHÜT SANAYİ VE TİCARET A.Ş.",
                "TERA FİNANSAL YATIRIMLAR HOLDİNG A.Ş.",
                "UŞAK SERAMİK SANAYİ A.Ş.",
                "VAKIF FİNANSAL KİRALAMA A.Ş.",
                "VAKIF MENKUL KIYMET YATIRIM ORTAKLIĞI A.Ş."
            ],
            "disclosureIndex": [
                1595903,
                1597276,
                1597323,
                1595524,
                1595361,
                1594281,
                1596715,
                1594776,
                1599494,
                1594479
            ],
            "count": 10
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": null,
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/17",
        "generalMeeting": {
            "companies": [
                "AG ANADOLU GRUBU HOLDİNG A.Ş.",
                "AKSU ENERJİ VE TİCARET A.Ş.",
                "AKSU ENERJİ VE TİCARET A.Ş.",
                "ANADOLU ISUZU OTOMOTİV SANAYİ VE TİCARET A.Ş.",
                "EGEYAPI AVRUPA GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "İNFO YATIRIM MENKUL DEĞERLER A.Ş.",
                "KARSU TEKSTİL SANAYİİ VE TİCARET A.Ş.",
                "OSMANLI YATIRIM MENKUL DEĞERLER A.Ş.",
                "PASİFİK EURASİA LOJİSTİK DIŞ TİCARET A.Ş.",
                "PASİFİK TEKNOLOJİ A.Ş.",
                "VAKIF FAKTORİNG A.Ş.",
                "VAKIF GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "YÜNSA YÜNLÜ SANAYİ VE TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1597728,
                1595450,
                1595451,
                1598357,
                1596368,
                1594627,
                1603263,
                1599544,
                1599017,
                1601462,
                1597678,
                1599013,
                1599980
            ],
            "count": 13
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "SELÇUK ECZA DEPOSU TİCARET VE SANAYİ A.Ş."
            ],
            "disclosureIndex": [
                1579042
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/20",
        "generalMeeting": {
            "companies": [
                "AKDENİZ YATIRIM HOLDİNG A.Ş.",
                "KALESERAMİK ÇANAKKALE KALEBODUR SERAMİK SANAYİ A.Ş.",
                "ORÇAY ORTAKÖY ÇAY SANAYİ VE TİCARET A.Ş.",
                "PASİFİK HOLDİNG A.Ş."
            ],
            "disclosureIndex": [
                1595807,
                1599097,
                1597324,
                1596222
            ],
            "count": 4
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "AKİŞ GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "KUŞTUR KUŞADASI TURİZM ENDÜSTRİSİ A.Ş."
            ],
            "disclosureIndex": [
                1593377,
                1575573
            ],
            "count": 2
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/21",
        "generalMeeting": {
            "companies": [
                "BURÇELİK BURSA ÇELİK DÖKÜM SANAYİİ A.Ş.",
                "BURÇELİK VANA SANAYİ VE TİCARET A.Ş.",
                "DİTAŞ DOĞAN YEDEK PARÇA İMALAT VE TEKNİK A.Ş.",
                "DOĞU ARAS ENERJİ YATIRIMLARI A.Ş.",
                "EDİP GAYRİMENKUL YATIRIM SANAYİ VE TİCARET A.Ş.",
                "ERBOSAN ERCİYAS BORU SANAYİ VE TİCARET A.Ş.",
                "İZMİR FIRÇA SANAYİ VE TİCARET A.Ş.",
                "KALEKİM KİMYEVİ MADDELER SANAYİ VE TİCARET A.Ş.",
                "ZİRAAT GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş."
            ],
            "disclosureIndex": [
                1597110,
                1597114,
                1596734,
                1598732,
                1602416,
                1596692,
                1595963,
                1598470,
                1598688
            ],
            "count": 9
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": {
            "companies": [
                "EURO KAPİTAL YATIRIM ORTAKLIĞI A.Ş.",
                "EURO MENKUL KIYMET YATIRIM ORTAKLIĞI A.Ş.",
                "EURO TREND YATIRIM ORTAKLIĞI A.Ş."
            ],
            "disclosureIndex": [
                1597580,
                1598256,
                1598280
            ],
            "count": 3
        },
        "dividendPayment": {
            "companies": [
                "AYEN ENERJİ A.Ş."
            ],
            "disclosureIndex": [
                1593808
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/22",
        "generalMeeting": {
            "companies": [
                "ÇELİK HALAT VE TEL SANAYİİ A.Ş.",
                "ÇİMBETON HAZIRBETON VE PREFABRİK YAPI ELEMANLARI SANAYİ VE TİCARET A.Ş.",
                "ÇİMENTAŞ İZMİR ÇİMENTO FABRİKASI T.A.Ş.",
                "DEMİSAŞ DÖKÜM EMAYE MAMÜLLERİ SANAYİ A.Ş.",
                "EGE GÜBRE SANAYİİ A.Ş.",
                "FORMET METAL VE CAM SANAYİ A.Ş.",
                "FORMET METAL VE CAM SANAYİ A.Ş."
            ],
            "disclosureIndex": [
                1598976,
                1597654,
                1597669,
                1601176,
                1598178,
                1597632,
                1597633
            ],
            "count": 7
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": null,
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/24",
        "generalMeeting": {
            "companies": [
                "AGROTECH YÜKSEK TEKNOLOJİ VE YATIRIM A.Ş.",
                "GIPTA OFİS KIRTASİYE VE PROMOSYON ÜRÜNLERİ İMALAT SANAYİ A.Ş.",
                "GSD DENİZCİLİK GAYRİMENKUL İNŞAAT SANAYİ VE TİCARET A.Ş.",
                "GSD HOLDİNG A.Ş.",
                "KAREL ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
                "PANORA GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "SARKUYSAN ELEKTROLİTİK BAKIR SANAYİ VE TİCARET A.Ş.",
                "SEĞMEN KARDEŞLER GIDA ÜRETİM VE AMBALAJ SANAYİ A.Ş.",
                "TARKİM BİTKİ KORUMA SANAYİ VE TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1597212,
                1598181,
                1599849,
                1599856,
                1597348,
                1602441,
                1601193,
                1600441,
                1601703
            ],
            "count": 9
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": {
            "companies": [
                "ÖZYAŞAR TEL VE GALVANİZLEME SANAYİ A.Ş."
            ],
            "disclosureIndex": [
                1596581
            ],
            "count": 1
        },
        "dividendPayment": {
            "companies": [
                "ÇELEBİ HAVA SERVİSİ A.Ş."
            ],
            "disclosureIndex": [
                1594222
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/27",
        "generalMeeting": {
            "companies": [
                "GARANTİ YATIRIM ORTAKLIĞI A.Ş.",
                "HEDEF GİRİŞİM SERMAYESİ YATIRIM ORTAKLIĞI A.Ş.",
                "HEDEF HOLDİNG A.Ş.",
                "KAFEİN YAZILIM HİZMETLERİ TİCARET A.Ş.",
                "MARMARA HOLDİNG A.Ş.",
                "OSTİM ENDÜSTRİYEL YATIRIMLAR VE İŞLETME A.Ş.",
                "OYAK YATIRIM MENKUL DEĞERLER A.Ş.",
                "RAİNBOW POLİKARBONAT SANAYİ TİCARET A.Ş.",
                "VİŞNE MADENCİLİK ÜRETİM SANAYİ VE TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1597482,
                1602008,
                1599429,
                1599365,
                1602684,
                1597602,
                1603618,
                1598566,
                1600204
            ],
            "count": 9
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": {
            "companies": [
                "TURK İLAÇ VE SERUM SANAYİ A.Ş."
            ],
            "disclosureIndex": [
                1598826
            ],
            "count": 1
        },
        "dividendPayment": {
            "companies": [
                "YÜNSA YÜNLÜ SANAYİ VE TİCARET A.Ş."
            ],
            "disclosureIndex": [
                1594996
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/28",
        "generalMeeting": {
            "companies": [
                "AKFEN YENİLENEBİLİR ENERJİ A.Ş.",
                "ALARKO GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "BİRLEŞİM GRUP ENERJİ YATIRIMLARI A.Ş.",
                "BİRLEŞİM MÜHENDİSLİK ISITMA SOĞUTMA HAVALANDIRMA SANAYİ VE TİCARET A.Ş.",
                "BORUSAN BİRLEŞİK BORU FABRİKALARI SANAYİ VE TİCARET A.Ş.",
                "DOFER YAPI MALZEMELERİ SANAYİ VE TİCARET A.Ş.",
                "ELİTE NATUREL ORGANİK GIDA SANAYİ VE TİCARET A.Ş.",
                "EURO KAPİTAL YATIRIM ORTAKLIĞI A.Ş.",
                "EURO MENKUL KIYMET YATIRIM ORTAKLIĞI A.Ş.",
                "EURO TREND YATIRIM ORTAKLIĞI A.Ş.",
                "GENTAŞ DEKORATİF YÜZEYLER SANAYİ VE TİCARET A.Ş.",
                "GÖZDE GİRİŞİM SERMAYESİ YATIRIM ORTAKLIĞI A.Ş.",
                "HUB GİRİŞİM SERMAYESİ YATIRIM ORTAKLIĞI A.Ş.",
                "MEKA GLOBAL MAKİNE İMALAT SANAYİ VE TİCARET A.Ş.",
                "MLP SAĞLIK HİZMETLERİ A.Ş.",
                "SÖKTAŞ TEKSTİL SANAYİ VE TİCARET A.Ş.",
                "YÜKSELEN ÇELİK A.Ş."
            ],
            "disclosureIndex": [
                1601323,
                1601493,
                1600694,
                1601311,
                1602797,
                1600572,
                1602145,
                1598297,
                1598263,
                1598285,
                1603875,
                1598416,
                1598225,
                1602406,
                1599364,
                1603835,
                1598393
            ],
            "count": 17
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": {
            "companies": [
                "CEM ZEYTİN A.Ş."
            ],
            "disclosureIndex": [
                1596810
            ],
            "count": 1
        },
        "dividendPayment": {
            "companies": [
                "KATILIMEVİM TASARRUF FİNANSMAN A.Ş.",
                "MİSTRAL GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "OSMANLI YATIRIM MENKUL DEĞERLER A.Ş."
            ],
            "disclosureIndex": [
                1594527,
                1594359,
                1594755
            ],
            "count": 3
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/29",
        "generalMeeting": {
            "companies": [
                "AKHAN UN FABRİKASI VE TARIM ÜRÜNLERİ GIDA SANAYİ TİCARET A.Ş.",
                "ALVES KABLO SANAYİ VE TİCARET A.Ş.",
                "ATAKULE GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "BMS BİRLEŞİK METAL SANAYİ VE TİCARET A.Ş.",
                "BOSCH FREN SİSTEMLERİ SANAYİ VE TİCARET A.Ş.",
                "ÇUHADAROĞLU METAL SANAYİ VE PAZARLAMA A.Ş.",
                "EMLAK KONUT GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "MAVİ GİYİM SANAYİ VE TİCARET A.Ş.",
                "METROPAL KURUMSAL HİZMETLER A.Ş.",
                "REYSAŞ GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "REYSAŞ TAŞIMACILIK VE LOJİSTİK TİCARET A.Ş.",
                "RUZY MADENCİLİK VE ENERJİ YATIRIMLARI SANAYİ VE TİCARET A.Ş.",
                "TAT GIDA SANAYİ A.Ş.",
                "ZERAY GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş."
            ],
            "disclosureIndex": [
                1602338,
                1598783,
                1603111,
                1601152,
                1601168,
                1598752,
                1598993,
                1598579,
                1598596,
                1598765,
                1598755,
                1600411,
                1598731,
                1599018
            ],
            "count": 14
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": {
            "companies": [
                "SÜMER VARLIK YÖNETİM A.Ş."
            ],
            "disclosureIndex": [
                1599214
            ],
            "count": 1
        },
        "dividendPayment": null,
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    },
    {
        "date": "2026/04/30",
        "generalMeeting": {
            "companies": [
                "BAREM AMBALAJ SANAYİ VE TİCARET A.Ş.",
                "DİNAMİK ISI MAKİNA YALITIM MALZEMELERİ SANAYİ VE TİCARET A.Ş.",
                "DOF ROBOTİK SANAYİ A.Ş.",
                "ECZACIBAŞI YATIRIM HOLDİNG ORTAKLIĞI A.Ş.",
                "EİS ECZACIBAŞI İLAÇ SINAİ VE FİNANSAL YATIRIMLAR SANAYİ VE TİCARET A.Ş.",
                "GENTAŞ KİMYA SANAYİ VE TİCARET PAZARLAMA A.Ş.",
                "HALK GAYRİMENKUL YATIRIM ORTAKLIĞI A.Ş.",
                "ICBC TURKEY BANK A.Ş.",
                "İNTEMA İNŞAAT VE TESİSAT MALZEMELERİ YATIRIM VE PAZARLAMA A.Ş.",
                "KARSAN OTOMOTİV SANAYİİ VE TİCARET A.Ş.",
                "MAKİM MAKİNA TEKNOLOJİLERİ SANAYİ VE TİCARET A.Ş.",
                "POLİSAN HOLDİNG A.Ş.",
                "SKYALP FİNANSAL TEKNOLOJİLER VE DANIŞMANLIK A.Ş."
            ],
            "disclosureIndex": [
                1601859,
                1601805,
                1599319,
                1600022,
                1600023,
                1599356,
                1599953,
                1599246,
                1600024,
                1600299,
                1599422,
                1600117,
                1601173
            ],
            "count": 13
        },
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "NETCAD YAZILIM A.Ş."
            ],
            "disclosureIndex": [
                1594289
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    }
]

## İstek 2

- Amaç: İstenen raporu indirmek üzere gerekli API isteğini yapmak.

### Request(istek 2)

curl '<https://www.kap.org.tr/tr/api/ca/filteredCa/2026/04/4028e4a1416e696301416f321c3d5ca7>' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'DNT: 1' \
  -H 'Referer: <https://www.kap.org.tr/tr>' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'

### Response(istek 2)

[
    {
        "date": "2026/04/06",
        "generalMeeting": null,
        "mergerDemergerAssignSubject": null,
        "capitalIncreaseDecrease": null,
        "dividendPayment": {
            "companies": [
                "ULUSAL FAKTORİNG A.Ş."
            ],
            "disclosureIndex": [
                1575261
            ],
            "count": 1
        },
        "retirementRight": null,
        "saleOutRight": null,
        "tenderOffer": null
    }
]

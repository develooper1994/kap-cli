# https://www.kap.org.tr/tr/api/member/filter/{Sorgu Metni}

https://www.kap.org.tr/tr/api/member/filter/{Sorgu Metni} servisi, Kamuyu Aydınlatma Platformu'nun (KAP) şirket rehberi arama motorudur. Bir metin dizesini alıp, veritabanındaki kayıtlı üye şirketlerle eşleştirerek teknik kimlik bilgilerini döndürür.

## Teknik Özellikler

- **İşlevi:** "Fuzzy search" (yaklaşık eşleme) mantığıyla çalışır. Tam unvanı yazmasanız bile (örneğin sadece "THY" veya "Hava Yolları") eşleşen sonuçları listeler.
- **Veri İlişkisi:** Kullanıcının girdiği metni, sistemin içindeki mkkMemberOid (Unique Object ID) değerine bağlayan bir köprü görevi görür.
- **Mimari:** Bir GET isteğidir. Yanıt formatı her zaman bir JSON Array (Dizi) nesnesidir, çünkü tek bir kelime birden fazla şirketle eşleşebilir.

## Yanıt Parametreleri

Servis her eşleşme için şu dört kritik bilgiyi sağlar:

- **mkkMemberOid:** Şirketin sistemdeki parmak izidir. Bildirimleri çekmek için kullanılan asıl ID budur.
- **companyCode:** Şirketin KAP üzerindeki sayısal kısa kodu (örn: "1107").
- **title:** Şirketin ticaret sicilindeki resmi tam unvanı.
- **permaLink:** Şirketin KAP profil sayfasına giden kalıcı bağlantı uzantısı.

## Kullanım Senaryosu

Eğer KAP verilerini dışarıdan çekmek istiyorsanız:

- Önce bu servise şirket adını sorarsınız.
- Dönen listeden doğru şirketi seçip mkkMemberOid değerini alırsınız.
- Bu ID'yi .../api/disclosure/list/main gibi diğer veri servislerine parametre olarak gönderirsiniz.

## Önemli Not

Bu API doğrudan sunucu tarafından render edilen bir sayfa yerine, bir veri kaynağıdır. URL içindeki {Sorgu Metni} kısmı Türkçe karakter içeriyorsa, isteğin hatalı gitmemesi için karakterlerin UTF-8 olarak kodlanmış olması (URL encoding) gerekir.

## Request

curl 'https://www.kap.org.tr/tr/api/member/filter/ASE' \
  -H 'Accept: */*' \
  -H 'Accept-Language: en-US,en;q=0.9,tr-TR;q=0.8,tr;q=0.7' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -b '_ga=GA1.1.1671240860.1776072570; client-ip=185.81.238.214; AGVY-Cookie=MDMAAAcA45wuEwAAAAC5Ue7WuGgBanJRbKFsGMjpsXmm2jNDCVns2KsuAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAANnhxSlpjAdqnEkV4Ec4Ysfh0qriumgBagAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAMX8KzniCbsidoW7EM2NrjuACnoW; _ga_L21W6S1YS4=GS2.1.s1778477236$o6$g1$t1778477268$j28$l0$h0; NSC_xxx.lbq.psh.us_tjuf_ejt=7ce2a3d9ddad9f0439920efb260b36acad4a64f3df2ef79bda6c88b7f8de60bb9ae4e5ca; KAP=AAc7uGgBajtUiFYAAAAAADsUL9ZOBg_0wi2-O_xu4s6Nvv0CgUba9If1if1AWwePOw==XmsBag==3JDZZ0n9Qg6N5A3vQHz7DUJ3lAA=' \
  -H 'DNT: 1' \
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
        "companyCode": "866",
        "mkkMemberOid": "4028e4a1413b7ef401413bc2251e0047",
        "title": "ASELSAN ELEKTRONİK SANAYİ VE TİCARET A.Ş.",
        "permaLink": "866-aselsan-elektronik-sanayi-ve-ticaret-a-s"
    },
    {
        "companyCode": "6068",
        "mkkMemberOid": "8acae2c59145e00e019560fcbd5947c7",
        "title": "ATR BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "permaLink": "6068-atr-bagimsiz-denetim-ve-serbest-muhasebeci-mali-musavirlik-a-s"
    },
    {
        "companyCode": "5878",
        "mkkMemberOid": "8acae2c486d22a3a018b03b5cfbe29b8",
        "title": "BORLEASE OTOMOTİV A.Ş.",
        "permaLink": "5878-borlease-otomotiv-a-s"
    },
    {
        "companyCode": "106",
        "mkkMemberOid": "33E5FED7243F00EAE0530A4A622B2AEA",
        "title": "DENGE BAĞIMSIZ DENETİM SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "permaLink": "106-denge-bagimsiz-denetim-serbest-muhasebeci-mali-musavirlik-a-s"
    },
    {
        "companyCode": "5457",
        "mkkMemberOid": "8acae2c47afb298b017ccb97632144e5",
        "title": "DOĞU ARAS ENERJİ YATIRIMLARI A.Ş.",
        "permaLink": "5457-dogu-aras-enerji-yatirimlari-a-s"
    },
    {
        "companyCode": "109",
        "mkkMemberOid": "33E5FED7244500EAE0530A4A622B2AEA",
        "title": "DRT BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "permaLink": "109-drt-bagimsiz-denetim-ve-serbest-muhasebeci-mali-musavirlik-a-s"
    },
    {
        "companyCode": "118",
        "mkkMemberOid": "33E5FED7245700EAE0530A4A622B2AEA",
        "title": "GÜNEY BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "permaLink": "118-guney-bagimsiz-denetim-ve-serbest-muhasebeci-mali-musavirlik-a-s"
    },
    {
        "companyCode": "2022",
        "mkkMemberOid": "1DE05DAA8402073AE0530A4A622A2EBD",
        "title": "JP MORGAN CHASE BANK N.A. MERKEZİ COLUMBUS OHIO - İSTANBUL TÜRKİYE ŞUBESİ",
        "permaLink": "2022-jp-morgan-chase-bank-n-a-merkezi-columbus-ohio-istanbul-turkiye-subesi"
    },
    {
        "companyCode": "82",
        "mkkMemberOid": "33E5FED7240F00EAE0530A4A622B2AEA",
        "title": "KPMG BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "permaLink": "82-kpmg-bagimsiz-denetim-ve-serbest-muhasebeci-mali-musavirlik-a-s"
    },
    {
        "companyCode": "4261",
        "mkkMemberOid": "8acae2c5553c6b3501559170a7892d07",
        "title": "LİDYA BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "permaLink": "4261-lidya-bagimsiz-denetim-ve-serbest-muhasebeci-mali-musavirlik-a-s"
    },
    {
        "companyCode": "5596",
        "mkkMemberOid": "8acae2c57f7cbb49018050e4303b068b",
        "title": "OBASE BİLGİSAYAR VE DANIŞMANLIK HİZMETLERİ TİCARET A.Ş.",
        "permaLink": "5596-obase-bilgisayar-ve-danismanlik-hizmetleri-ticaret-a-s"
    },
    {
        "companyCode": "5826",
        "mkkMemberOid": "8acae2c586d22c5101887ae575873835",
        "title": "PASİFİK EURASİA LOJİSTİK DIŞ TİCARET A.Ş.",
        "permaLink": "5826-pasifik-eurasia-lojistik-dis-ticaret-a-s"
    },
    {
        "companyCode": "92",
        "mkkMemberOid": "33E5FED7242300EAE0530A4A622B2AEA",
        "title": "PwC BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş",
        "permaLink": "92-pwc-bagimsiz-denetim-ve-serbest-muhasebeci-mali-musavirlik-a-s"
    },
    {
        "companyCode": "5811",
        "mkkMemberOid": "8acae2c586d22c5301875c14b4a27137",
        "title": "VARLIK GLOBAL BAĞIMSIZ DENETİM VE SERBEST MUHASEBECİ MALİ MÜŞAVİRLİK A.Ş.",
        "permaLink": "5811-varlik-global-bagimsiz-denetim-ve-serbest-muhasebeci-mali-musavirlik-a-s"
    }
]


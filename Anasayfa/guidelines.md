# guidelines

Bu ağ isteği, KAP ana sayfasındaki "Kılavuzlar" bölümünü doldurmak için kullanılan verileri çeker.

## Analiz

- **Amaç:** Kullanıcıların platformu kullanabilmesi için gerekli olan finansal rapor hazırlama, özel durum açıklaması ve sertifika kullanım kılavuzları gibi yardımcı dokümanların listesini getirmektir.
- **İçerik:** Yanıt; doküman adı, yayınlanma tarihi ve dokümana ulaşmak için kullanılan staticPagefileOid bilgilerini içeren bir JSON nesnesidir.
- **Performans:** İstek toplamda 37 ms gibi çok kısa bir sürede tamamlanmıştır. Sunucu yanıt süresi (11 ms) oldukça düşüktür.

## Teknik Değerlendirme

- **Önbellek (Caching):** Cache-Control: max-age=1800 ve Age: 956 başlıkları, verinin başarılı bir şekilde önbellekten (cache) sunulduğunu gösterir. Bu, sunucu yükünü azaltır ve hızı artırır.
- **Durum:** 200 OK durumuyla istek başarıyla sonuçlanmıştır. Herhangi bir hata veya darboğaz bulunmamaktadır.

## Özet

İstek, statik içerik listesini getirmek için optimize edilmiş, hızlı ve sağlıklı bir API çağrısıdır.

## Request

curl 'https://www.kap.org.tr/tr/api/home-data/guidelines' \
  -H 'Accept: */*' \
  -H 'Accept-Language: tr' \
  -H 'Cache-Control: max-age=0' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -b '_ga=GA1.1.1580744861.1771666924; client-ip=176.234.129.110; NSC_xxx.lbq.psh.us_tjuf_ejt=7ce2a3d9ddad9f0439920efb260b36acad4a64f3df2ef79bda6c88b7f8de60bb9ae4e5ca; _ga_L21W6S1YS4=GS2.1.s1778402398$o16$g1$t1778402419$j39$l0$h0; AGVY-Cookie=MDMAAAwARbQTMwAAAACw6oFuY0QAagAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKp2aJx5poJDkrAZC8BTFeuLuBlDfUQAagAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAOjar63ESS5NJzz2obrgfMq2j_a4; KAP=AAw7Y0QAajuIfUoAAAAAADsUL9ZOBg_0wi2-OwI6rujFTTSyh4-EMvESMlmk_KJTOw==qUUAag==NMRu7YgI3RLwtcxrEeagSgFKJHM=' \
  -H 'DNT: 1' \
  -H 'If-None-Match: "KXBBPGFIFNKQSUYY"' \
  -H 'Referer: https://www.kap.org.tr/tr' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Chromium";v="148", "Google Chrome";v="148", "Not/A)Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'

## Response

{
   "id":"8a02910894b6de660194b735218b0031",
   "menuTitle":"Kılavuzlar",
   "menuUrl":"kilavuzlar",
   "menuOrder":3,
   "menuLang":"TR",
   "menuType":"list",
   "menuItself":null,
   "menuSuperOid":"8a019492945fbe080194ac9d67b626dd",
   "contentList":[
      {
         "listDate":"22.03.2025",
         "listNo":"",
         "listOrder":null,
         "listSubject":"KAP İnternet Sitesine İlişkin Kılavuz",
         "staticPagefileOid":"402832a195b3017d0195bd17e2e07e9a"
      },
      {
         "listDate":"17.11.2023",
         "listNo":"",
         "listOrder":null,
         "listSubject":"  Hak Kullanımı Süreçlerine İlişkin Açıklamalar",
         "staticPagefileOid":"8a02910894b6de660194b74eb0cc005f"
      },
      {
         "listDate":"17.11.2023",
         "listNo":"",
         "listOrder":null,
         "listSubject":"Borçlanma Araçları İçin Hak Kullanımı Süreçlerine İlişkin Açıklamalar",
         "staticPagefileOid":"8a02910894b6de660194b74e9b75005d"
      },
      {
         "listDate":"17.11.2023",
         "listNo":"",
         "listOrder":null,
         "listSubject":"  KAP 4.0 Hak Kullanım İşlemleri Kılavuzu",
         "staticPagefileOid":"8a02910894b6de660194b74f127d006b"
      },
      {
         "listDate":"23.08.2022",
         "listNo":"",
         "listOrder":null,
         "listSubject":"Katılım İlkeleri Finans Formu Kılavuzu",
         "staticPagefileOid":"8a02910894b6de660194b74ec3930061"
      },
      {
         "listDate":"24.11.2021",
         "listNo":"",
         "listOrder":null,
         "listSubject":"Özel Durum Açıklaması Hazırlama Kılavuzu",
         "staticPagefileOid":"8a02910894b6de660194b74defbd0049"
      },
      {
         "listDate":"08.10.2021",
         "listNo":"",
         "listOrder":null,
         "listSubject":"Finansal Rapor Hazırlama Kılavuzu",
         "staticPagefileOid":"8a0292b094bc3a500194cbfa4bd90054"
      },
      {
         "listDate":"17.09.2021",
         "listNo":"",
         "listOrder":null,
         "listSubject":"Nitelikli Elektronik Sertifika Kullanım Kılavuzu",
         "staticPagefileOid":"8a0292b094bc3a500194cbf192550046"
      }
   ]
}

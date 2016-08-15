---
layout: post
title: "Sass ile kutu oluşturma"
date: 2016-08-15 15:06:14 +0300
comments: true
categories: 
---

 Kutular web sayfası tasarlarken sıkça kullandığımız yardımcılardır. Bu yazımda d  3 adet kutuyu yanyana dizeceğiz.
 Bunun için ilk olarak bir dış bölme tasarlayacağız daha sonra ise iç bölmeler ile bu alanı 3 adet kutu şekline dönüştüreceğiz.
 O zaman şimdi site.css.sass kısmına bölmelerimizle ilgili özellikleri yazıyoruz.
 
 ``` sass
 
 
 #dis_bolme
   width: 500px
   height: 150px
   background-color: white
   margin: auto
   
 .ic_bolme
   float: left
   width: 130px
   height: 100px
   background-color: white
   margin: 51px
   font-size: 7px
  ```
  
  
  Şimdi sırayla yukarıdaki komutların ne anlama geldiğine bakalım. `width` ve `height` diye bahsettiğimiz kısımlar oluşacak bölümlerin genişliğini ve uzunluğunu temsil ediyor.`background-color` arka planın rengini ayarlamamızı sağlıyor.`margin: auto` ise oluşturduğumuz dış bölmenin ortalanmasını sağlıyor.
  Sırada iç bölmelerdeki kutuları incelemekte.`float: left` oluşturduğumuz kutuların yanyana olmasını sağlayan komuttur.
  Şimdi kutularımızı index.html.haml kısmında oluşturalım.
  
  
  ``` sass
  #dis_bolme
    .ic_bolme

    .ic_bolme
     
    .ic_bolme
      
    .ic_bolme
      
   ```
   Artık yanyana 3 adet bölmemiz oldu istediğimiz şekilde bu kutuların içine resim koyabilir yazı yazabiliriz.
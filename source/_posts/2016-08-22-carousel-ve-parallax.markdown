---
layout: post
title: "Carousel ve Parallax"
date: 2016-08-22 10:32:14 +0300
comments: true
categories: 
---


   CAROUSEL NEDİR?
   
   Carousel hazırladığım resim veya yazıların slayt gösterisi şeklinde olmasını sağlıyor.Carousel kodunu JavaSprict kodu olarak vericeğim için ilk öncelikle Java ile bağlantıyı kurmamız gerekmektedir.
   Bunun için layout.html.haml sayfasına `= javascript_include_tag '//code.jquery.com/jquery-3.1.0.js','//maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js', :all` kodunu yapıştımalıyız.
   Artık kodumuzu yazdığımız zaman hata almayacağız.Şimdi ise aşağıdaki carousel kodunu inceleyelim.
   
   ``` sass
   #carousel-example-generic.carousel.slide{"data-ride" => "carousel"}
     / Indicators
     %ol.carousel-indicators
       %li.active{"data-slide-to" => "0", "data-target" => "#carousel-example-generic"}
       %li{"data-slide-to" => "1", "data-target" => "#carousel-example-generic"}
       %li{"data-slide-to" => "2", "data-target" => "#carousel-example-generic"}
     / Wrapper for slides
     .carousel-inner{:role => "listbox"}
       .item.active
         %img{:alt => "...", :src => "..."}/
         .carousel-caption
           \...
       .item
         %img{:alt => "...", :src => "..."}/
         .carousel-caption
           \...
       \...
     / Controls
     %a.left.carousel-control{"data-slide" => "prev", :href => "#carousel-example-generic", :role => "button"}
       %span.glyphicon.glyphicon-chevron-left{"aria-hidden" => "true"}
       %span.sr-only Previous
     %a.right.carousel-control{"data-slide" => "next", :href => "#carousel-example-generic", :role => "button"}
       %span.glyphicon.glyphicon-chevron-right{"aria-hidden" => "true"}
       %span.sr-only Next
   ```
   
   
   İç içe carousel belirtilemez.Ayrıca yukarIdaki item kısımlarını arttırıp slaytın daha fazla sayfalı olmasını ayarlayabiliriz.
   
   PARALLAX NEDİR?
    
   Paralax durağan nesnelerin farklı zamanda gözlenen doğrultuda ilerlemesi ile meydana gelen değişimlerdir ve web sayfamızın dikkat çekici görünmesine yardımcı olur.
   
   ``` sass
   .parallax 
       background-image: url("img_parallax.jpg");
       height: 500px;
       width:1000px
       background-attachment: fixed;
       background-position: center;
       background-size: cover;
   ```
   
   Yukarıdaki komutumuzu inceleyecek olursak ilk önce resmimizi tanımlayıp daha sonra boyutlarını belirlemişiz. `background-attachment: fixed` komutu ile parallax'ı gerçekleştirmiş oluyoruz ve artık yüklediğimiz resim belirtilen ölçülerde aşağıya doğru kayabiliyor.
   `background-size: cover` komutu ise resmimizin belirtilen ölçülere göre ayarlanmasını sağlıyor.
   
   
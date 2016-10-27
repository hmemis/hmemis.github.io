---
layout: post
title: "Javascript ile hareketli resim yapmak"
date: 2016-10-27 15:27:02 +0300
comments: true
categories: 
---

  Bugün Javascript ile hareketli resim yapımını anlatacağım.Bunun için öncelikle Javascript kodlarını .js uzantılı dosyaya kaydetmemiz gerekiyor.
  https://github.com/Prinzhorn/skrollr adresinden skrollr.js dosyasını indiriyoruz ve bu dosyayı projemizin javascript bölümüne .js uzantılı olarak kaydediyoruz.
  Daha sonra layout.html.haml sayfasına `= javascript_include_tag'skrollr.js` komutunu yapıştırıyoruz ve app.js sayfamıza `skrollr.init();` komutunu yazarak dosyamızı kullanılabilir hale getiriyoruz.
  Ben bir dünya resminin etrafındaki ay resminin belli bir yörüngedeki hareketini oluşturdum.
  index.html.haml sayfasına dünya, ay  ve yörünge resmini yüklettim. `'data-0':` komutu ile sayfa aşağı kaydığında ayın değişteceği konum ayarlamalarını yapabiliriz.
  
  ```haml
  %div.dünya{:style => "position: relative; background:url('images/earth-92a7ffc515bb9139749cb15c709fc1e1.png'); "}
    .yörünge
    %img.ay{src:"images/ball.png", 'data-0':'top:90px; right: -40px; max-width: 50px; opacity: 0','data-20':'top:15px; right: -60px; max-width: 70px; opacity:1','data-50':'top:5px; right:60px; max-width:80px; opacity:1', 'data-100':'top:30px; right:120px; max-width: 90px; opacity: 1','data-150':'top:50px; max-width:110px; right:180px; opacity:1','data-200':'top:130px; right: 250px; max-width:130px; opacity: 1 ','data-200':'top:90px; right: 210px; max-width:150px; opacity: 1','data-250':'top:300px; right:300px; max-width:100px; opacity:1','data-270':'top:290px; right:200px; max-width:50px; opacity:1'}
  
   ```
   
   `max-width` komutu ile resmin belirtilen aralıklardaki boyutunu belirledim.`opacity` komutu ile de ay resminin görülmesini istediğim zamanları belirledim.
   site.css.sass sayfasınada resimlerle ilgili ayarlamaları yaptım.
   
  ```css
   
   .yörünge
     background-image: url("../images/earth-and-moon-sq-4-cfccccab234693b29b2d336674dc899a.png")
     background-size: cover
     width: 558px
     height: 431px
     margin-left: -95px
     background-size: cover
     padding-top: -50px
     position: absolute
     margin-top: -72px
     
   .ay
     position: absolute
     top: 70px
     right: -20px
     max-width: 50px
     
    .dünya
     width:320px
     height:320px
     background-size: cover 
     margin-left: 270px
     margin-top: 100px
     
   ```
---
layout: post
title: "Bootstrap ile Izgara Yöntemi"
date: 2016-08-15 14:09:27 +0300
comments: true
categories: 
---


  Bu yazımda ızgara yöntemini kısaca tanıyacağız ve kullanım şeklini inceleyeğiz.Kullanımı işimizi kolaylaştırır.Izgara (Grid) sistemleri sitemizin belli standarda uygun ve hızlı bir şekilde sayfa planını oluşturmamıza yarayan sistemlerdir.
  İlk önce kodumuzu inceleyelim daha sonra bunun üzerinde konuşalım.
  
  
  
  ``` bootstrap
  .container
      .row
        %br
        .col-xs-3.col-sm-3.col-md-3.col-lg-2
          .yazi-style2
            Contact
          .yazi-style
            %br
            VegeShop
            %br
            Warzywna 5/6
            %br
            87-100 Torun
            %br
            +47 791 054 214
  
        .col-xs-3.col-sm-3.col-md-3.col-lg-2
          .yazi-style2
            Shop
          .yazi-style
            %br
            Products
            %br
            Blog
            %br
            Help
            %br
            Terms
  
        .col-xs-3.col-sm-3.col-md-3.col-lg-2
          .yazi-style2
            Shoppig
          .yazi-style
            %br
            Delivery time
            %br
            Payments method
            %br
            Complaints and returns
        .col-xs-3.col-sm-3.col-md-3.col-lg-2
          .yazi-style2
            Follow us on
   ```
   
   
   Izgara yönteminde 12 sütuna kadar uygun olarak ölçekler.Izgara kolonları ölçmek istediğiniz 12 hazır kolonların belirli numaraları tarafından oluşturulur. Örneğin üç eşit kolon için .col-xs-4 kullanılırdı.
  
  <br> Bootstrap ızgara sistemi 3 ana yapıdan oluşur.
  <br> Kapsayıcı (.container) <br>
   Satırlar (.row)   <br>
   Kolonlar (col-*) <br>
   
   Kapsayıcı (.container) : 
   Bootstrap ızgara sisteminde satırların tam yerleşmesi için bir kapsayıcı elemana ihtiyacı vardır. Kapsayıcı eleman siteye yapısına göre iki farklı sınıf alır.
  <br> .container : sabit genişlikteki sitelerde <br>
   .container-fluid : esnek yapılı sitelerde  <br>
   
   
   Satırlar (.row) : 
   Her 12’li kolonu kapsayan bir kapsayıcıdır. kolonlar float:left ile yan yana dizildiği için satır aynı zamanda taşan kolonları satır başı yaptırmaya yarar.
   Ayrıca `.row` container'ın olmadığı yerlerde çalışmıyor.
   
   Yukarıdaki komutumuza bakarsak `.container` ve `.row` komutları ile sayfa düzeninde ızgara sistemimiz oluşuyor ve `.col-xs-3.col-sm-3.col-md-3.col-lg-2` komutu sayesinde 12 lik ızgara sistemine göre yanyana 4 adet sütun oluşturmuş oluyoruz.Daha sonra bir tab boşluk ile sütuna yazmak istediklerimizi yazıyoruz.
   
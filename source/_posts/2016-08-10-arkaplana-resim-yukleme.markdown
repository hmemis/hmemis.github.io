---
layout: post
title: "Arkaplana resim yükleme"
date: 2016-08-10 14:04:43 +0300
comments: true
categories: 
---

Sass ile arkaplan resmi oluşturmak

 Bu yazımda web sayfamıza sass ile nasıl resim koyacağımıza ve yazının üstüne nasıl yazı yazacağımızı inceleyeceğiz.
 İlk öncelikle dosyamızın source / stylesheets kısmına geliyoruz ve `.css.sass` uzantılı bir dosya oluşturuyoruz.Bu dosya ile kullanmak istediğimiz resmin boyutunu ,genişliğini , üzerine yazacağımız yazının şeklini, boyutunu ,rengini ayarlayabiliriz.
Şimdi sass dosyasında ile resmimizi ve üzerine yazacağımız yazının nasıl olacağını aşağıdaki komutla ayarlıyoruz.
```sass
.resim
  background-image: url("http://tarfanlarorganik.com/wp-content/uploads/2016/04/Slider-3.jpg")   
  width: 900px
  height: 400px
.yazi
  font-color: white
  font-size: 20px
  margin: 0 0 0 15em
```
 Yukarıda belirttiğimiz `margin: 0 0 0 15em` komutundaki 15em yazının ne kadar sağa kayacağını belirtiyor.Sayıyı arttırırsak yazımız o kadar sağa kayar.

Şimdi index.html.haml sayfamızda sadece komutları çağırmamız lazım. `.yazi` yi `.resim` in içine yazıyoruz ki resmin üstüne yazı yazabilelim
```sass
.resim
  .yazi
    %p Bu yazı sitemizde gözükecektir
```
Artık resmimizi yerleştirdik ve üzerine yazımızıda yazmış olduk.
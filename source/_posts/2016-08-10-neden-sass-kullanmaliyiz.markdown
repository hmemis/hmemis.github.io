---
layout: post
title: "Neden Sass Kullanmalıyız?"
date: 2016-08-10 09:41:46 +0300
comments: true
categories: 
---


SASS Nedir?

Syntactically Awesome Style Sheets ifadesinin kısaltması olan SASS, en popüler CSS ön-işlemcilerinden (pre-processing) biridir.Kendi resmi sitesinde ki ifadeye göre olgun,istikrarlı ve güçlü profesyonel seviyedeki CSS uzantı dilidir.

Uzantı dilinden kasıt stil oluştururken CSS’de olmayan özellikleri kullanabiliyor olmamızdır.Kısaca Sass, CSS ile yaptığımız işleri daha kolay, hızlı ve düzenli hale getiren yardımcı bir araçtır.


SASS özellikleri nelerdir?

Sass genel olarak css derleyicisidir. Css sayesinde var olmuş fakat css’i teknik olarak geçmeyi başarmıştır.

Sass, kendi sözdizimi ile yazılmış kodları CSS’e çevirir. Sass tarafından oluşturulan bu CSS dosyası projeye dahil edilerek kullanılır. Sass compile edilen diller gibi ekstra bir derleme komutu beklemez, çalıştığınız proje dizinini takip ederek, kaydedilen her “*.sass” ve “*.scss” dosyasını otomatik olarak saniyeler içinde derler ve kullanıma hazırlar.

    Css’in değişken tanımlanılabilinen hali (Variables)
    Css’in tarayıcılar için yazdığımız ekstra kodları kendisi oluşturabilen hali(Mixins)
    Css’in girintileri fark ederek iç içe class’ları yazabilen hali (Nesting)
    Css dosyasında istediğimiz kodları istediğimiz yerde extend edebiliyoruz (Extend/Inheritance)
    Css dosyamızı parçalara ayırıp, ayırdığımız kısımları istediğimiz yerde çağırabiliyoruz (Import)
    Css dosyamızda çarpma,bölme toplama vs. yapabiliyorz. (Operators)

Şimdide yukarıda bahsettiğimiz özellikleri inceleyelim.

Ariables: Sass’ta değişkenleri tanımlıyoruz

    $header-font-style:  Helvetica, sans-serif
    $header-color: #000

Daha sonra değişkenleri aşağıdaki gibi çağırabiliyoruz.

    .header
      font: $header-font-style
      color: $header-color

Nesting: Nesne girintilerine göre kod yazmak.Yine bu sayede sass işimizi kolaylaştırıyor.

    #nav
      ul
       color: red
      li
       color: blue
      a
       color: green

Css çıktısı:

    #nav ul {
      color: red;
    }
    #nav li {
      color: blue;
    }
    #nav a {
      color: green;
    }


Partials ve @import: Kodlarımızı bölümleyip istediğimiz yerde import edebiliyoruz.

    /* _reset.sass */
    body
         margin: 0
         padding: 0

Bu dosyayı asıl stil dosyamıza dahil edebiliyoruz.

    /* base.sass */
    @import 'reset'

 

Mixins: Aşağıdaki komutu sass  dosyamızın üst kısmına tanımlıyoruz .

    @mixin border-radius($radius)
        -webkit-border-radius: $radius
        -moz-border-radius: $radius
        -ms-border-radius: $radius
        -o-border-radius: $radius
        border-radius: $radius


Mixin'i sass'da çağırıyoruz ve bu sayede üstteki komutu tekrar tekrar yazmayarak işimizi kolaylaştırmış oluyoruz.

    .box
        @include border-radius(10px)

Extend/Inheritance: class yada id'lerde kullandığımız özellikleri @extend özelliği ile bir sonraki class yada id mizin içinde kullanabiliyoruz.

message class'ı için kodlarımız bunlar.

    .message
          border: 1px solid #ccc
          padding: 10px
          color: #333


Şimdide diğer class yada id'mizde bu kodları extend edelim.

    .success
          @extend .message
          border-color: green
    .error
          @extend .message
          border-color: red


Operators: css özelliklerini yazarken operatorleri kullanabiliyoruz.

    aside
         float: right
         width: 300px / 960px * 100%
    Css çıktısı:

    aside {
        float: right;
        width: 31.25%;
    }


Neden Sass Kullanmalıyım?

Tanımını yaparken de açıkladığım gibi CSS’i daha elverişli hale getirir.Sass, programalama dillerinin sahip olduğu bazı özellikleri (değişkenler,fonksiyonlar), CSS de kullanabilmemizi sağlıyor ve bir nevi CSS’i basit bir dilden programlama diline çevirir.

Binlerce satırlık CSS kodlarını daha hızlı yazmamızı,daha düzenli bir stil dosyası oluşturmamıza olanak tanır.Bu şekilde daha önce yazdığımız kodları kolay bir şekilde bulabiliriz.

Kısacası CSS’i hantal bir yapıdan çıkarır ve daha dinamik bir yapıya döndürür.Sass’ın faydalarını esas olarak büyük projelerde farkedebiliriz.


---
layout: post
title: "Ruby on Rails ile ilgili genel bilgi"
date: 2016-07-31 21:11:14 +0300
comments: true
categories: 
---
 RUBY ON RAİLS İLE İLGİLİ GENEL BİLGİ

 Öncelikle bir süredir kullandığım Ruby dili ile yazılmış Ruby on Rails framework ünü tanımakla başlayalım.Daha sonra Rails'in tarihçesini, yapısını ve sonrasında Rails MVC (Model View Controller) yapısını inceleyelim.
 Ruby nesne tabanlı bir programlama dili olup oldukça sade ve kısa bir sözdizimine (syntax) sahiptir. Zaten Ruby’nin temelinde bu sadelik ve kısalık söz konusudur. Karmaşık kodlar yerine gelişmiş uygulamaları kısa yoldan gerçekleştirebilir.
 Ruby on Rails ise, David Heinemeir Hansson’un başını çektiği Ruby dili ile yazılmış open source frameworktür. Şu an 3.2.RC1 versiyonu ortalıkta dolaşmaktadır. Ancak en güvenilir versiyon şu an için 3.1.1 dir.
 Bizde kendi ruby versiyonumuzu terminal yardımıyla öğrenebiliriz.Aşağıdaki komutu terminale yazalım.
 -$ ruby -version
 Buradaki sayıların ne anlama geldiğine ve ne zamanlar değiştiğini inceleyelim.
 ruby 3.2.1 diye görüken ruby versiyonunda
 3 sayısı yapısal değişiklikleri gösterir ve yapısal değişiklik olunca versiyonumuz artık ruby 4.0.0 olarak gözükür.
 2 sayısı yeni özellik eklenince değişir.Örneğin ruby 3.3.1
 1 sayısı ise hataları gösterir.Hatalar düzelince sayı artmaya devam eder.

 Peki neden diğer programlama dilleri yerine Ruby On Rails’i tercih edeyim diyecek olursanız, bunun cevabı Ruby’nin sözdizimi. Düşünsenize diğer dillerle 50 satırda gerçekleştireceğiniz işlemleri bu dil sayesinde 10 satıra indirgeyebiliyorsunuz. Ayrıca bu 10 satır diğerlerine göre çok daha sade ve basit oluyor.
 Rails’in fark yaratan bir diğer özelliği ise, web’i gerçekten anlayan geliştiriciler tarafından yaratılmış olması.
 Ruby on Rails’in yaratıcısı David Heinemeier Hansson “agile software development” (çevik yazılım geliştirme) manifestosunda da imzası olan, DRY (Don’t Repeat Yourself), pragmatik programlama gibi felsefeleri takip eden yaratıcı ve ödüllü bir programcı.

Hansson’un railsde bir araya getirdiği teknik ve paradigmalardan bazıları:

    MVC – Model / View / Controller (JSP kullananlar bilirler)
    ORM – Object Relational Mapping veritabanı arabirimi (Rails’de ActiveRecord olarak geçiyor)
    REST – REpresentational State Transfer
    DRY – Don’t Repeat Yourself
    Agile Programming
    Pragmatic Programming
 
 Şimdi Rails ile yeni bir projeye nasıl başlanır onu görelim.Terminale aşağıdaki komutu yazalım.
 -$ rails new blog
 Komut sayesinde Rails projemize başlamış sayılıyoruz.Daha sonra aşağıdaki komut ile Rails projemizin içine giriyoruz.
 -$ cd blog
 Sonrasında aşağıdaki komut ile yazdığımız ve enterladığımız anda gerekli databaseler bizim için oluşmuş oluyor.
 -$ rake db:migrate
 Son olarak Rails projemizi görmek için aşağıdaki komutu terminale yazıyoruz
 -$ rails s
 Ve artık projemizi görebiliriz.Bunun için arama motoruna http://localhost:3000 yazarız.

 Şimdi projemizin dosyalarını inceleyelim.

    Gemfile => Proje içinde kullanılan gemlerin buludunğu dosyadır. Yüklemek istediğiniz gemleri buraya yazarsınız.
    README => Klasik Readme .txt dosyasıdır. Proje ile ilgili detayları buraya yazabilirsiniz.
    Rakefile => Konsolda rake işlemlerini gerçekleştirmek için gerekli olan dosyaların bulunduğu yerdir.
    app => Rails projesinin çekirdeği buradadır. Controller, Model, View, Helper, Assets ler burada saklanır. Bu klasörlerin ne işe yaradığına yeri geldikçe anlatacağım.
    config => Runtime, databasei ve daha fazla ayarların ve düzenlemelerin yapıldığı dosyadır.
    config.ru => Rack tabanlı serverlerin çalışması için gerekli dosyadır.
    db => Database şemalarının ve database yapısının tutulduğu yerdir.
    doc => Derinlemesine dökümantasyonların olduğu klasördür.
    lib => Daha fazla modulün bulunduğu klasördür.
    log => Uygulamanın loglarının tutulduğu dosyadır.
    public => Static dosyaların ve son kullanıcı ekranlarının bulunduğu klasördür.
    script => Adından anlaşılacağı gibi Rails scriptlerinin ve daha sonra bizlerin yazdığı scriptlerin bulunduğu klasördür.
    test => Test dosyalarının ve diğer test durumlarının bulunduğu bölümdür.
    tmp => Temporary dosyalarını barındırır.
    vendor => Ruby gemlerini ve Rails’in kaynak kodunu kapsayan bölümdür. Daha çok sonraki eklentileri içerir.
 Evet sonuç itibari ile temel bir Rails projesi dosya dizimi bu şekilde oluşur. Bu klasörlerin içinde genel dosyalar vardır
 
 Birazda Rails - MVC yapısını inceleyelim.Rails’te model katmanı veritabanı ile olan ilişkilerden sorumludur. Genellikle her bir model, bir veritabanı tablosu ile iletişim halindedir. Model, tablo üzerinde CRUD yani Create, Read, Update ve Delete işlerini yapar. Örneğin tabloda arama yapmak için şöyle bir sorgu kullanırız: 

  Model.where(:name => 'model_name').first


 Controller MVC modelinin en önemli kısmıdır. Rails’de controller, dış dünyadan yani kullanıcıdan istekleri kabul eder, gerekli işlemleri uygular ve sonuçları view katmanına gönderir. Web istekleri, değişkenlerin ve verilerin işlenmesi, çeşitli bilgiler için Model’e başvurulması, işlenen verilerin kayıt için tekrar Model’e yollanması gibi işlerin hepsi Controller sorumluluğundadır. Controller genellikle Model üzerindeki CRUD işlemlerini idare eder, view’da kullanılacak değişkenleri düzenler.

  def index
    # logic to list all recipes
  end
 
  def show
    # logic to show a particular recipe
  end
 
  def create
    # logic to create a new recipe
  end
 
  def update
    # logic to update a particular recipe
  end



 MVC yapısında View, uygulamanın kullanıcıya görünen yüzüdür. View’ın, Model ile yapacağı herhangi bir iletişim mutlaka Controller üzerinden gerçekleştirilmelidir! Bu sayede hem view temiz kalmış olur hemde MVC çatısından kopmamış oluruz.

View, bizim model nesnelerimizin kullanıcıya sunulması ve formatlanmasından sorumludur. Kullanıcıya sunduğu formlar, input kutuları, butonlar vb. ile kullanıcıyla iletişime girerler.

Rails yapısında birde Controller ve View’ı birbirine kolayca bağlamak için “helper”lar kullanılır. Helper’lar sayesinde örneğin bir kayıt validasyon kurallarından geçemediyse ve kullanıcıya hata göstermemiz gerekiyorsa Helper’lardan yararlanabiliriz.

 Son olarakta Rails'i oluşturan kütüphanelerden bahsedelim.
Active Record: Veritabanı ile iletişimi yönetir.

Action View: HTML dosyalarını oluşturan templating sistemidir ve kullanıcıdan aldığı girdileri Rails uygulamasına paslar.

Action Controller: Hem uygulama akışını hemde veritabanından gelerek view’da gösterilecek olan verileri yönetir.


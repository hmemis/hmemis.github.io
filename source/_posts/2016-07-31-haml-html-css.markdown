---
layout: post
title: "haml - html - css"
date: 2016-07-31 18:24:39 +0300
comments: true
categories: 
---

HAML-HTML-CSS-SASS-COMPASS

 HTML, Hyper Text Markup Language cümlesinin kısaltmasıdır ve hypertext işaret dili anlamınada gelir.

 HTML dosyası temelde bir text dosyası olmasına karşın işaretlenmiş kelimeler (tag'lar - Etiketler) sayesinde görsellik kazanır.

 Oluşturulan bu dosyanın tarayıcıda (browser) görsellik kazanabilmesi için uzantısının HTM veya HTML olması gereklidir.
 
 Basit bir Html sayfası oluşturmak kolaydır.Fakat yazılan kodlar uzadıkça html ile kod yazmakta zorlaşır.Html den daha kolay yazılan haml dili yardımımıza gelir.
 
 HAML, Rails uygulamaları için geliştirilmiş görüntüleme dili. Kendini tekrar etmeyen ve sadeliği ile öne çıkan bu dili okumakta öğrenmekte çok kolay. Felsefi olarak güzel olanın basit olması gerektiğine inanan HAML geliştircileri, HAML için gerçek sorunların gerçek çözümü olduğunu söylüyor.

 Basit bir HAML sayfası .haml uzantısı olarak karşımıza çıkıyor ve yazımı, içeriği HTML’den çok farklı. Bir kere tag olayı ortadan kalkıyor. Bir örnek ile görelim

HTML kodu :
```html
<div id=”profile”>
<div>
<div id=”date”><%= print_date %></div>
<div id=”address”><%= current_user.address %></div>
</div>
<div>
<div id=”email”><%= current_user.email %></div>
<div id=”bio”><%= current_user.bio %></div>
</div>
</div>
```
HAML kodu :
```haml
#profile
.left.column
#date= print_date
#address= current_user.address
.right.column
#email= current_user.email
#bio= current_user.bio
```
 Ayrıca https://html2haml.herokuapp.com/ sitesi sayesinde html kodlarımızı haml koduna çevirebiliyoruz.
 
 Şimdide html ve css farkını inceleyelim.Css yani 'Cascading Style Sheets' yani 'Basamaklı Stil Sayfası' HTML'in ihtiyaçlarımızı karşılamadığı noktada devreye girer. Html elementlerinin üzerinde düzenleme yapmamızı sağlar. CSS, HTML belgeleri düzenini tamamlayan bir stil dilidir.Örneğin,  yazı tipleri, renkler, kenar boşlukları, çizgiler, yükseklik, genişlik, arka plan görüntüleri, gelişmiş pozisyonları ve diğer pek çok özelliğin düzenlenmesini kapsar. HTML'den daha fazla seçenek sunuyor ve daha gelişmiş görünüyor.

 Css te en çok karıştırılan id ve class sorununa değinelim birazda ID, tek bir element için kullanılır. Genellikle header, footer, navbar, sidebar gibi tekrar etmeyen alanları tanımlamak için kullanılır. Her sayfada ortak olarak kullanılan ID olabilir (header, footer, ...) ancak tek sayfada aynı isimde birden fazla ID olmamalıdır. Çünkü hem W3C kurallarına uymaz hem de Javascript kullanacağımız zaman aynı isimde ID varsa karışıklığa yol açar.Class'larda ID'lere benzer lakin amaçları farklıdır. ID'nin aksine tek sayfa içerisinde birçok kez tanımlanabilir. Sayfa içerisinde aynı özellikleri taşıyan yerler varsa özellikle yazı stilleri gibi (örneğin; başlıkların aynı renkte ya da boyutta olduğu yerler) Class kullanılmalıdır.

CSS de ID # (diyez) işareti ile kullanılır.
```css
#idismi
{
    position:absolute;
    left:25px;
    top:25px;
    width:150px;
}

```
CSS de class .(nokta) işareti ile kullanılır.
```css
.menu
{
    font-size:14px;
    color:#ff0000;
}
```
 Nerede Class Nerede ID Kullanmalıyım?

Bunu örnekle açıklamak istiyorum. Varsayalım kütüphane açacağız. Öncelikle kitaplarımızı felsefe, psikoloji, polisiye ... gibi kategorilere bölmemiz gerekir ve kütüphanemizde bu kitaplara özel raflar oluşturmalıyız. İşte kitaplara özel oluşturulan bu raflara ID diyoruz. Her kitabın sayfa sayısı, yazı büyüklüğü, ebatları farklıdır. Değişik kitaplar aynı rafta toplanmıştır ve bu işleme de Class diyoruz.

 CSS’ de bulunmayan bazı özellikleride SASS te bulabiliriz örneğin değişken (variables) tanımlama, iç içe (nesting) olarak hazırlanmış seçiciler oluşturmak, css kodlarınızı yeniden kullanılabilir ve parametrik olarak çalışabilen parçalara bölmek (mixin), bir css tanımlamasının başka bir css tanımlamasından miras almasını sağlayan seçici kalıtımı (selector inheritance) yapmak için kullanılır. 
  
 Son olarakta Sass’ın araç kutusu gibi olan compassa değinelim. Önek sorununa çözüm oluşturan mixinleri, otomatik sprite yapma imkanı, dikey hizalama kolaylıkları, kolay ızgara sayfa planları sunan bir Sass araç kutusu olarak tanımlanabilir. Ayrıca eklenti desteği yardımı ile daha fazla geliştirilebilen bir araç kutusu.
 

---
layout: post
title: Jekyll Kurulumu
excerpt: "Jekyll Kurulumu"
categories: articles
comments: true
share: true
analytics: true
tags: [Jekyll, Jekyll Kurulumu, Pip, Python, Ruby, Devkit, Rouge, Pygments]
---

##Giriş

Merhaba,
Bugün benimde nacizane sitemi hazırladığım jekyll uygulamasını Windows'ta kullanabilmek için ortamı nasıl hazırlayacağımızı anlatacağım. 
Ama bilmeyenler için biraz jekyll nedir ondan bahsedelim.

---

####Jekyll Nedir?
Jekyll statik site oluşturabileceğimiz, Ruby dilinde yazılmış bir uygulama. Belli bir dizin yapısı var ve bu yapıya bağlı kalarak sitemizi oluşturabiliyoruz. 
Örnek dizin yapısı aşağıdaki gibidir;

![](../../images/2016-01-20-JekyllInstallation/1.png)

Tabii bu dizin yapısı projeye göre değişkenlik gösterebilir. Ekran görüntüsünde gördüğümüz dizin yapısı **jekyll new testblog** komutunu çalıştırarak
yeni bir jekyll projesi oluşturduktan sonra gördüğümüz ilk dizin yapısı. Bu konulara ve kullanıma daha sonra başka yazılarda değinmeye çalışacağım. Şimdilik
kuruluma geçelim.

---

#####1 - Ruby Kurulumu

-	<http://rubyinstaller.org/downloads/> web sitesinden işletim sistemimize uygun bir versiyonu seçip indiriyoruz(*Benim kurduğum versiyon - 2.0.0 | x64 bit*).
-	İndirdiğimiz dosyayı çalıştırıyoruz ve aşağıdaki adımları izliyoruz.

![](../../images/2016-01-20-JekyllInstallation/2.png)

-	Japonca’mız olmadığı için **English** seçeneğini seçip devam ediyoruz :)

![](../../images/2016-01-20-JekyllInstallation/3.png)

-	**I accept the Licence** seçeneğini seçerek devam ediyoruz.

![](../../images/2016-01-20-JekyllInstallation/4.png)

-	Kurulum klasörünü **C:\Ruby200-64** olarak ayarlıyoruz ve **Add Ruby executables to your PATH** seçeneğini seçerek devam ediyoruz.

![](../../images/2016-01-20-JekyllInstallation/5.png)

-	**Finish** butonuna tıklayarak kurulumumuzu tamamlıyoruz.

---

#####2 - Devkit Kurulumu

-	<http://rubyinstaller.org/downloads/>  sitesinden uygun devkit versiyonunu indiriyoruz(*Benim kurduğum versiyon - 4.7.2-20130224-1432 | x64 bit*).

![](../../images/2016-01-20-JekyllInstallation/6.png)

-	İndirdiğimiz dosyayı çalıştırıyoruz ve yolu **C:\Devkit** seçerek çıkarma işlemini başlatıyoruz.

![](../../images/2016-01-20-JekyllInstallation/7.png)


-	Komut satırını açıyoruz ve **DevKit** klasörüne gidiyoruz
-	Burada ilk olarak **ruby dk.rb init** komutunu çalıştırıp dosyayı initialize işlemini yapıyoruz.
-	**notepad config.yml** komutunu çalıştırarak dosyayı açıp aşağıdaki ekran görüntüsündeki gibi **– C:/Ruby200-x64** satırının eklenip eklenmediğini kontrol ediyoruz. 
Eklenmemişse ekliyoruz ve dosyayı kaydedip, kapatıyoruz.

![](../../images/2016-01-20-JekyllInstallation/8.png)

-	Son olarak sırasıyla **ruby dk.rb review** ve **ruby dk.rb install** komutlarını çalıştırıyoruz ve aşağıdaki ekran görüntüsünü elde ediyoruz.

![](../../images/2016-01-20-JekyllInstallation/9.png)

---

#####3 - Jekyll Kurulumu

-	**gem install jekyll** komutunu çalıştırıyoruz ve aşağıdaki ekran görüntüsündeki gibi gemlerin kurulduğunu görüyoruz.

![](../../images/2016-01-20-JekyllInstallation/10.png)

---

#####4 - Syntax Highlighter'ların Kurulumu

-	Syntax Highlighter’lar web sitemize eklediğimiz kodların renkli ve güzel bir şekilde görünmesini sağlarlar. 
Bunun için Rouge ya da pygments yükleyebiliriz. Fakat pygments desteklediği diller açısından daha avantajlı durumdadır. 
Bununla birlikte python ve pip kurulumunu zorunlu hale getiriyor.

######4.1 - Rouge Kurulumu

-	Gayet basit. **gem install rouge** komutunu çalıştırarak rouge gemini yüklüyoruz ve kullanıma hazır hale geliyor.
-	Projemizde _config.yml dosyasında *highlighter: rouge* satırını ekleyerek/düzenleyerek aktif hale getiriyoruz.

![](../../images/2016-01-20-JekyllInstallation/11.png)

######4.2 - Pygments Kurulumu

***- Python Kurulumu***

-	<http://www.python.org/download/> web sitesinden python kurulumunu indirip çalıştırıyoruz(*Benim kurduğum versiyon - 2.7.8 | x64 bit*).

![](../../images/2016-01-20-JekyllInstallation/12.png)

-	**Install for all users** seçeneğini seçip devam ediyoruz.

![](../../images/2016-01-20-JekyllInstallation/13.png)

-	Yükleme yolunu **C:\Python27** olarak seçip devam ediyoruz.

![](../../images/2016-01-20-JekyllInstallation/14.png)

-	**Add python.exe to Path** seçeneğini aktif edip devam ediyoruz.

![](../../images/2016-01-20-JekyllInstallation/15.png)

-	**Finish** butonuna tıklayıp yükleme işlemini tamamlıyoruz.

***- Pip Kurulumu***

-	C diski altında pip adında bir klasör oluşturuyoruz.
-	<https://bootstrap.pypa.io/get-pip.py> linkindeki yazıları kopyalayıp  oluşturduğumuz klasör altında **get-pip.py** adında dosya oluşturarak içine yapıştırıyoruz.
-	Komut satırında **C:\pip** yoluna geliyoruz.
-	Aşağıdaki ekran görüntüsündeki gibi **python get-pip.py** komutunu çalıştırıyoruz ve kurulumu yapıyoruz. 

![](../../images/2016-01-20-JekyllInstallation/16.png)

***- Pygments Kurulumu***

-	Aşağıdaki ekran görüntüsünde olduğu gibi **python -m pip install Pygments** komutunu çalıştırarak pygments’i kuruyoruz.

![](../../images/2016-01-20-JekyllInstallation/17.png)

---

####Jekyll Yeni Proje Oluşturma Ve Çalıştırma

-	**jekyll new testblog** komutunu çalıştırarak **testblog** adında yeni bir jekyll projesi oluşturuyoruz.

![](../../images/2016-01-20-JekyllInstallation/18.png)

-	Oluşturduğumuz projenin içine giriyoruz ve **jekyll serve** komutunu çalıştırarak sunucuyu ayağa kaldırıyoruz. 
Ekranda gördüğümüz gibi http://127.0.0.1:4000/ linkine girerek projemizi görüntüleyebiliriz. İlk ekran görüntümüz aşağıdaki gibidir.

![](../../images/2016-01-20-JekyllInstallation/19.png)

Şimdilik bu kadar. İyi çalışmalar. Sağlıcakla...

##Referanslar:

1.<http://jekyll-windows.juthilo.com/>  
2.<http://yizeng.me/>  

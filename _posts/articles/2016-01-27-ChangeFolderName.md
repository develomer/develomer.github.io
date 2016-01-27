---
layout: post
title: C# Klasör Adını Değiştirme
excerpt: "C# Klasör Adını Değiştirme"
categories: articles
comments: true
share: true
analytics: true
tags: [C#, Klasör adı değiştirme]
---

##C# İle Klasör Adı Değiştirme

Merhaba,

Bazen belli şartlara göre klasör adını değiştirmek isteyebiliriz. Eğer klasör sayısı fazlaysa ve belli şartlara göre değiştirilecekse aşağıdaki basit kod ile 
seçtiğimiz yol altındaki tüm klasör adlarını değiştirebiliyoruz.

```csharp

public void changeFolderName(string newName)
{
    DirectoryInfo dir = new DirectoryInfo("C:/Users/username/Desktop/testfolder/");

    foreach (var item in dir.GetDirectories())
    {
        item.MoveTo(Path.Combine(item.Parent.FullName, newName));
    }
}

```

İyi çalışmalar. Sağlıcakla...

##Referanslar:

1.<https://msdn.microsoft.com//>  

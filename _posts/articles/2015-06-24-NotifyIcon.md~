---
layout: post
title: NotifyIcon Karakter Sorunu
excerpt: "NotifyIcon 63 Karakter Sorunu"
categories: articles
comments: true
share: true
analytics: true
tags: [notifyicon sorunu, c# notify icon karakter]
---


#   NotifyIcon 63 Karakter Sorunu

Merhaba,
Bildirim çubuğunda görünmesini istedğimiz uygulamalara NotifyIcon nesnesini ekleriz. Bu aslında çok basit bir işlem. Fakat eklediğimiz NotifyIcon için karakter sayısının 64 karakteri geçmesini istediğimiz durumlarda aşağıdaki ekran görüntüsünde bulunan ArgumentOutOfRangeException hatasını alırız.

![](../../images/2015-06-25-NotifyIcon/4)
 
Bu durumu basit bir kod parçacığıyla aşabiliyoruz.
 
![](../../images/2015-06-25-NotifyIcon/1)
 
Visual Studio yu açıp ve New-Project  seçeneğini seçerek yeni bir proje açalım.
 
![](../../images/2015-06-25-NotifyIcon/2)

Form penceresi şekildeki gibi karşımıza gelir. Şimdi projemize Toolbox kısmından yeni bir NotifIcon ekleyelim.

![](../../images/2015-06-25-NotifyIcon/3)

Şimdi aşağıdaki kodları projemize ekliyoruz.

```csharp
using System.Reflection;
```

isim uzayını ekliyoruz.
 
```csharp
string text = "1111111111111111" +  
	"\n22222222222222222" +  
	"\n3333333333333333333" +  
	"\n4444444444444444444444" +  
	"\n\n55555555555555555555555" +  
	"\n\n666666666666666666666666666";
```
                      
Sıra işi yapacak kısmı eklemekte. Aşağıdaki kod satırlarını ekliyoruz.

```csharp
public static void SetNotifyIconText(NotifyIcon notifyTest, string text)
{
	if (text.Length >= 1000) throw 
		new ArgumentOutOfRangeException("Text limited to 127 characters");
	Type t = typeof(NotifyIcon);
	BindingFlags hidden = BindingFlags.NonPublic | BindingFlags.Instance;
	t.GetField("text", hidden).SetValue(notifyTest, text);
	if ((bool)t.GetField("added", hidden).GetValue(notifyTest))
	    t.GetMethod("UpdateIcon", hidden).Invoke(notifyTest, new object[] { true });
}
```
 
Son olarak sınıfı kullanarak foksiyonumuzu çağırıyoruz.

```csharp
Fixes.SetNotifyIconText(notifyTest, text);
```

![](../../images/2015-06-25-NotifyIcon/5)

Ekran görüntüsünde görebileceğimiz üzere karakter uzunluğu problemi ortadan kalkmış oluyor.

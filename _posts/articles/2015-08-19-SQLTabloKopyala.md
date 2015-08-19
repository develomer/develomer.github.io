---
layout: post
title: SQLde Tablo Kopyalama
excerpt: "SQLde Tablo Kopyalama"
categories: articles
comments: true
share: true
analytics: true
tags: [SQL, Tablo Kopyalama]
---


Merhaba,

SQL'de bir tabloyu kopyalamak istiyorsak yapmamız gereken şey oldukça basit. Basitçe eski tabloyu yeni bir tablo adının içine ***SELECT*** ediyoruz.


```csharp
SELECT * INTO KOPYATABLO FROM ORJINALTABLO
```

Bu basit SQL kodunu yazdığımızda tabloyu PRIMARY KEY ve INDEX gibi kısımları değil sadece veriyi aktarmış oluruz.

İyi çalışmalar...
---
layout: post
title: T-SQL While Döngüsü
excerpt: "T-SQL While Döngüsü"
categories: articles
comments: true
share: true
analytics: true
tags: [T-SQL, LOOP, While, Döngü]
---

Merhaba,

İşim gereği bazen PL/SQL bazende T-SQL kodu yazmam gerekebiliyor. Birkaç gün bir arkadaşım ***WHERE*** koşulunu eklemeyi unutarak bir UPDATE işlemi yaptı. 
Yedek alınmasına alınmıştı ama aradan birkaç gün geçtiği için arada oluşan veriler vardı. Dolayısıyla direkt olarak geriye dönülemiyordu. 
Bu sorunu çözmenin birçok yolu vardı ama ben aşağıdaki T-SQL kodunu yazarak eski ve yeni tabloyu karşılaştırıp ID’lerin uyuşması durumunda gerekli kolondaki değeri değiştirme yöntemini seçtim.  
Şimdi o kodu kolon vs isimlerini değiştirerek yazalım.

```sql
GO
DECLARE @maxValue INT = 0;
DECLARE @counter INT = 0;
DECLARE @value INT = 0;
SET @maxValue = (SELECT MAX(ID) FROM ORNEKTABLO_OLD);
SET @counter = (SELECT MIN(ID) FROM ORNEKTABLO_OLD);
WHILE @maxValue >= @counter
BEGIN
	SET @value = (SELECT ORNEKTABLO_OLD.DEGISMESIGEREKENKOLON FROM ORNEKTABLO_OLD WHERE ORNEKTABLO_OLD.ID = @counter);
	IF @value IS NULL
		IF @counter > @maxValue
			BREAK
		ELSE 
			BEGIN
				SET @counter = @counter + 1;
				CONTINUE
			END
	ELSE
		BEGIN
		UPDATE ORNEKTABLO
			SET ORNEKTABLO.DEGISMESIGEREKENKOLON = @value
		WHERE
			ORNEKTABLO.ID = @counter
		SET @counter = @counter + 1;
		END
END
```

Tablonun maksimum ve minimum ID değerlerini  değişkenlere atadıktan sonra minimum değerli değişkenin değerini artırarak her seferinde değişmesini istediğim kolonun değerini  farklı bir değişkene atadım. 
Daha sonra belli kolullara göre tabloyu güncelledim. Umarım işinize yarar.
İyi çalışmalar...

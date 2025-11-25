# Mobil Cihaz Fiyat Tahmini



# Projenin Amacı

Bu projenin temel amacı, mobil cihaz fiyatlarını (Launched Price (USA)) etkileyen özellikleri sırayla deneyerek en uygun özelliği seçip fiyatla  arasındaki ilişkiyi incelemek ve bu ilişkiye dayanarak bir Doğrusal Regresyon (Linear Regression) modeli oluşturmaktır.

# Kullanılan Dataset

Telefonlara ait:

Marka

Model

RAM

Ağırlık

Kamera çözünürlükleri

Ekran boyutu

Batarya kapasitesi

Farklı ülkelere göre fiyatlar

Çıkış yılı

gibi özellikleri içermektedir.

# Ortalama Hata ve Başarı

RMSE (Ortalama Hata): 388.94

R2 Skoru (Başarı): 0.18

Başarının düşük olmasının nedeni sadece RAM ile fiyat tahmini yapmaya çalışmaktır.Diğer özellikler eklenirse daha başarılı bir sonuç elde edilebilir.

Sırasıyla adımlar şu şekildedir :

# 1)Dataset'i Yükleme

```python
import pandas as pd 
import matplotlib.pyplot as plt 
import numpy as np
mobiles = pd.read_csv("mobiles_dataset.csv", encoding='latin-1') 
mobiles.head()

```
| Company Name | Model Name | Mobile Weight | RAM | Front Camera | Back Camera | Processor | Battery Capacity | Screen Size | Launched Price (Pakistan) | Launched Price (India) | Launched Price (China) | Launched Price (USA) | Launched Price (Dubai) | Launched Year |
|:-------------|:-----------|:--------------|:----|:-------------|:------------|:----------|:-----------------|:------------|:--------------------------|:-----------------------|:----------------------|:---------------------|:-----------------------|:--------------|
| Apple | iPhone 16 128GB | 174g | 6GB | 12MP | 48MP | A17 Bionic | 3,600mAh | 6.1 inches | PKR 224,999 | INR 79,999 | CNY 5,799 | USD 799 | AED 2,799 | 2024 |
| Apple | iPhone 16 256GB | 174g | 6GB | 12MP | 48MP | A17 Bionic | 3,600mAh | 6.1 inches | PKR 234,999 | INR 84,999 | CNY 6,099 | USD 849 | AED 2,999 | 2024 |
| Apple | iPhone 16 512GB | 174g | 6GB | 12MP | 48MP | A17 Bionic | 3,600mAh | 6.1 inches | PKR 244,999 | INR 89,999 | CNY 6,499 | USD 899 | AED 3,199 | 2024 |
| Apple | iPhone 16 Plus 128GB | 203g | 6GB | 12MP | 48MP | A17 Bionic | 4,200mAh | 6.7 inches | PKR 249,999 | INR 89,999 | CNY 6,199 | USD 899 | AED 3,199 | 2024 |
| Apple | iPhone 16 Plus 256GB | 203g | 6GB | 12MP | 48MP | A17 Bionic | 4,200mAh | 6.7 inches | PKR 259,999 | INR 94,999 | CNY 6,499 | USD 949 | AED 3,399 | 2024 |



# 2)Fiyat Temizleme

Fiyatlardaki USD,PKR gibi sayısal olmayan ifadeler temizlenir.

Ayrık değerler temizlenir ve bu şekilde daha doğru regresyon yapmak mümkün olur.


# 3)RAM ve Front Camera Temizleme

RAM'deki GB ifadesi çıkarılır.Front Cameradaki MB ifadesi çıkarılır.Sadece numerik ifadeler kalır.

# 4)Hedef Belirleme

Front Camera,Launched Year ve RAM özelliklerinin Launched Price(USA) ile özelliklerine nakılmıştır.En uygun olan RAM seçilmiştir.Fiyat olarak ABD lansman fiyatını seçilmesinin nedeni daha evrensel bir fiyat değeri olmasıdır.


# 5)Korelasyon Matrisi

RAM ile Launched Price (USA) arasındaki katsayı, diğerlerinden en yüksek ve +1'e en yakın olanıdır. Bu, RAM'in fiyattaki değişimi açıklamada en güçlü değişken olduğunu gösterir.


# 6)RAM miktarı ile telefonların ortalama lansman fiyatı arasındaki ilişkiyi gösteren bar grafiği

![Bar Grafiği](bar_grafik.png)

# 7)Linear regresyon modeli oluşturma

Hedef ve özellik tanımlanır.

Veri şekli düzenlenir.

Veri seti X_train %80 ve y_train %20 olmak üzere rastgele bölünür.

Model eğitimi ve tahmini yapılır.


# 8)Neden Linear Regresyon seçildi?

Kolay yorumlanabilirdir.

Basit ve hızlıdır.

Fiyat tahmini için uygundur .

Dataset ile uyumludur.


# 8)Neden Linear Regresyon seçildi?

Kolay yorumlanabilirdir.

Basit ve hızlıdır.

Fiyat tahmini için uygundur .

Dataset ile uyumludur.

# Diğer Regresyon Modelleri Neden Seçilmedi

# Lojistik Regression: 

Datasette 0-1 ,evet-hayır gib ifadeler bulunmadığı için lojitik regresyona uygun değildir.

# Polinomical Regression:

Veri setinde bariz bir polinomik ilişki gözlenmemiştir.

Yorumlanabilirliği düşüktür.

# Random Forest:

Çok karmaşık olacağı için seçilmemiştir.

Linear modele göre daha yavaştır.

# SVR

Karmaşıktır.Aykırı değerler için dirençlidir.Bu veri seti için gerekli değildir.

Yorumlaması zor.



# 9)Sonuç

Bu proje kapsamında yapılan analizler ve oluşturulan Lineer Regresyon modeli, mobil cihaz fiyatlarını etkileyen RAM özelliğinin rolünü açıkça göstermiştir.

Güçlü Eğilim: RAM miktarı ile ABD Lansman Fiyatı arasında net bir pozitif ilişki olduğu gözlemlenmiştir. Bar grafiği, RAM arttıkça ortalama fiyatın istikrarlı bir şekilde arttığını kanıtlamaktadır.

Model Seçimi: Korelasyon matrisi, RAM'in diğer incelenen özellikler (Launched Year, Front Camera) arasında Fiyat ile en belirgin ilişkiye sahip değişken olduğunu göstermiştir.

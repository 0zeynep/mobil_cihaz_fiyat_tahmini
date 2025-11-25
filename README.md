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

'''import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
mobiles=pd.read_csv("mobiles_dataset.csv",encoding='latin-1')
mobiles.head()'''

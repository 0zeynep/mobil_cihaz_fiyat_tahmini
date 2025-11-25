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
| Company Name | Model Name | Mobile Weight | RAM | Front Camera | Back Camera | Processor | Battery Capacity | Screen Size | Launched Price (Pakistan) | Launched Price (India) | Launched Price (China) | Launched Price (USA) | Launched Price (Dubai) | Launched Year |
|:-------------|:-----------|:--------------|:----|:-------------|:------------|:----------|:-----------------|:------------|:--------------------------|:-----------------------|:----------------------|:---------------------|:-----------------------|:--------------|
| Apple | iPhone 16 128GB | 174g | 6GB | 12MP | 48MP | A17 Bionic | 3,600mAh | 6.1 inches | PKR 224,999 | INR 79,999 | CNY 5,799 | USD 799 | AED 2,799 | 2024 |
| Apple | iPhone 16 256GB | 174g | 6GB | 12MP | 48MP | A17 Bionic | 3,600mAh | 6.1 inches | PKR 234,999 | INR 84,999 | CNY 6,099 | USD 849 | AED 2,999 | 2024 |
| Apple | iPhone 16 512GB | 174g | 6GB | 12MP | 48MP | A17 Bionic | 3,600mAh | 6.1 inches | PKR 244,999 | INR 89,999 | CNY 6,499 | USD 899 | AED 3,199 | 2024 |
| Apple | iPhone 16 Plus 128GB | 203g | 6GB | 12MP | 48MP | A17 Bionic | 4,200mAh | 6.7 inches | PKR 249,999 | INR 89,999 | CNY 6,199 | USD 899 | AED 3,199 | 2024 |
| Apple | iPhone 16 Plus 256GB | 203g | 6GB | 12MP | 48MP | A17 Bionic | 4,200mAh | 6.7 inches | PKR 259,999 | INR 94,999 | CNY 6,499 | USD 949 | AED 3,399 | 2024 |

# 🚢 Gemi Sınıflandırma CNN Projesi

Bu proje, **Global AI Hub & Akbank Derin Öğrenme Bootcamp** kapsamında geliştirilmiş olup, gemi türlerini sınıflandırmak için **Convolutional Neural Network (CNN)** modeli kullanmaktadır.

---

## 🔹 Proje Hakkında
Projenin amacı, CNN tabanlı bir model ile gemi türlerini sınıflandırmaktır.  

Başlıca adımlar:  
- **CNN Modeli:** Conv2D, BatchNormalization, MaxPooling, Dense ve Dropout katmanlarından oluşur.  
- **Veri Ön İşleme ve Artırma:** Eğitim seti rescaling, yatay çevirme ve parlaklık değişimleri ile zenginleştirilmiştir.  
- **Model Eğitimi:** EarlyStopping ve ReduceLROnPlateau callback’leri ile optimize edilmiş.  
- **Model Değerlendirme:** Test setinde doğruluk, confusion matrix ve classification report ile performans ölçümü yapılmıştır.
- **Doğru ve Yanlış Tahmin Örnekleri:** Test setindeki örnekler, tahmin ve gerçek sınıflarıyla birlikte görselleştirilmiştir.
- **Model Yorumlanabilirliği:** Grad-CAM görselleştirmeleri kullanılarak modelin hangi bölgelere dikkat ettiği analiz edilmiştir.  
- **Sonuçların Görselleştirilmesi:** Eğitim/validation accuracy ve loss grafikleri ile modelin öğrenme süreci görselleştirilmiştir.

---

## 📊 Veri Seti
Proje, Kaggle üzerinde bulunan **Ship Classification Dataset** kullanılarak gerçekleştirilmiştir.  
- Kullanılan veri seti: [Ship Classification Dataset (Kaggle)](https://www.kaggle.com/datasets/oleksandershevchenko/ship-classification-dataset/versions/3)   
- Eğitim (`train`), doğrulama (`valid`) ve test (`test`) setleri olarak ayrılmıştır.  
- 10 adet gemi türü içeren ~10.000 adet renkli görüntülerden oluşmaktadır.  
- Eğitim seti veri artırma (augmentation) teknikleri ile zenginleştirilmiştir: rescaling, yatay çevirme ve parlaklık değişimleri.  
- Bu sayede modelin genelleme yeteneği artırılmış ve overfitting riski azaltılmıştır.
---

## 📈 Performans Sonuçları
Modelin doğrulama seti üzerindeki performansı aşağıdaki dropout oranları için değerlendirilmiştir:  

| Dropout Rate | Validation Accuracy | Validation Loss | Test Accuracy | Test Loss |
|---------------|-------------------|-----------------|-----------------|-----------------|
| 0.4           | 89.11%            | 0.4210          | 72.34%          | 1.2526 
| 0.5           | 92.74%            | 0.2977          | 73.88%          | 1.1731 
| 0.6           | 88.39%            | 0.4303          | 72.34%          | 1.4724 

- En yüksek doğruluk **dropout=0.5** ile elde edilmiştir.  
- Test seti performansı da yüksek olup, modelin genelleme yeteneğini göstermektedir.  
- Confusion matrix ve classification report sınıf bazlı performansı özetlemektedir.  
- Grad-CAM görselleştirmeleri, modelin dikkat ettiği bölgeleri görselleştirerek karar mekanizmasını açıklamaktadır.

---

## ⚙️ Teknik Detaylar
- Model eğitimi sırasında GPU kullanılmıştır.  
- Eğitim süreci 20 epoch boyunca gerçekleştirilmiş ve en iyi model **EarlyStopping** ile kaydedilmiştir.  
- Hiperparametreler: learning rate = 0.001, batch size = 64, dropout = 0.5
- Optimizer: Adam (lr=0.001)
- Model, overfitting’i önlemek için **Dropout** ve **BatchNormalization** kullanmaktadır.  
- Kod ve notebooklar, proje reproducibility için tüm adımları içerir.

---

## 🚀 Gelecek Çalışmalar
- Veri setinin büyütülmesi veya daha fazla gemi türü eklenmesi.
- Daha ileriye gidip gemi türlerinin yanı sıra, gemilerin isim/kod tahmini için geliştirmeler.
- Daha gelişmiş CNN mimarilerinin (ResNet, EfficientNet) denenmesi.  
- Projenin web uygulaması olarak deploy edilmesi ve gerçek zamanlı kullanım.  
- Dinamik veri toplama ve artırma pipeline’larının entegrasyonu.

---

## 🔗 Linkler
- [Kaggle Notebook Linki](https://www.kaggle.com/code/dogukanozcelik/deeplearning-bootcamp-dozcelik/edit/run/263843247) 

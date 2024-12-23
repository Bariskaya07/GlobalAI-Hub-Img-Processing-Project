# GlobalAI-Hub-Img-Processing-Project

# CNN Tabanlı Görüntü Sınıflandırma Projesi

## Proje Açıklaması
Bu proje, **Convolutional Neural Networks (CNN)** kullanarak belirli hayvan türlerinin görüntülerini sınıflandırmayı amaçlamaktadır. Model, farklı manipülasyon ve renk düzeltme tekniklerini içeren test setleriyle değerlendirilmiştir.
## Veri Seti
https://www.kaggle.com/datasets/rrebirrth/animals-with-attributes-2
## Hedef
- Görüntü işleme ve veri artırma tekniklerini anlamak.
- CNN modellerinin temel çalışma prensiplerini öğrenmek.
- Farklı veri manipülasyonlarının ve renk sabitliği algoritmalarının model başarısı üzerindeki etkilerini incelemek.

---

## Kullanılan Teknolojiler
- **Python**
- **TensorFlow/Keras**
- **OpenCV**
- **NumPy**
- **Matplotlib**
- **Scikit-learn**

---

## Proje Adımları

### 1. Veri Seti Hazırlığı
- 10 farklı hayvan sınıfı (`collie`, `dolphin`, `elephant`, `fox`, `moose`, `rabbit`, `sheep`, `squirrel`, `giant panda`, `polar bear`) seçildi.
- Her sınıftan ilk 650 görsel kullanıldı ve eğitim/test setlerine ayrıldı (%70 eğitim, %30 test).
- Görseller, model giriş boyutlarına uygun şekilde yeniden boyutlandırıldı (128x128).

### 2. Veri Artırma (Data Augmentation)
- Aşağıdaki teknikler uygulandı:
  - Döndürme
  - Kaydırma (genişlik/yükseklik)
  - Yakınlaştırma
  - Yatay çevirme
  - **Eklenenler:** Bulanıklaştırma, kenar bulma, gürültü ekleme

### 3. CNN Model Tasarımı
- **Katmanlar:**
  - Convolutional Layer
  - MaxPooling Layer
  - Fully Connected Layer
  - Dropout
- **Optimizasyon ve Kayıp Fonksiyonu:**
  - Optimizer: Adam
  - Loss Function: Categorical Crossentropy

### 4. Manipüle Edilmiş Test Seti
- Test setine parlaklık ve kontrast değişiklikleri uygulandı.

### 5. Renk Sabitliği Algoritması
- Manipüle edilmiş test setine **Gray World** algoritması ile renk sabitliği uygulandı.

### 6. Sonuçların Karşılaştırılması
- Üç farklı test setindeki başarı oranları raporlandı:
  - Orijinal test seti
  - Manipüle edilmiş test seti
  - Renk sabitliği uygulanmış test seti

---

## Kullanım

### 1. Gereksinimler
Proje için aşağıdaki kütüphanelerin kurulu olduğundan emin olun:
- `tensorflow`
- `opencv-python`
- `numpy`
- `matplotlib`
- `scikit-learn`

Kurulum:
```bash
pip install tensorflow opencv-python numpy matplotlib scikit-learn
```

### 2. Projenin Çalıştırılması
- **Adım 1:** Projeyi klonlayın veya indirin.
- **Adım 2:** Veri setinizi `C:/Users/ACER/Desktop/Animals` konumuna yerleştirin.
- **Adım 3:** Aşağıdaki komutu çalıştırarak projeyi başlatın:
  ```bash
  python cnn_image_classification.py
  ```

### 3. Sonuçların Görselleştirilmesi
- Eğitim ve doğrulama doğruluğu ile kaybı görselleştirmek için `matplotlib` kullanılmıştır.
- Test seti sonuçları konsolda görüntülenecektir.

---

## Sonuçlar

| Test Seti Türü               | Başarı Oranı (%) |
|------------------------------|------------------|
| **Orijinal Test Seti**       | **67.28**         |
| **Manipüle Edilmiş Test Seti** | **59.54**         |
| **Renk Sabitliği Uygulanmış Set** | **42.56**         |

---

### **Sonuçların Analizi**
1. **Orijinal Test Seti:**
   - Modelin orijinal test setindeki başarısı değerlendirilecektir.
   
2. **Manipüle Edilmiş Test Seti:**
   - Manipüle edilmiş test setindeki model doğruluğu incelenmiştir.

3. **Renk Sabitliği Uygulanmış Set:**
   - Renk sabitliği uygulanmış test seti analiz edilmiştir.
## Daha Yüksek Başarı Oranı Almak için Çözüm Önerileri 
Orijinal Test Seti İçin:

Model Derinliğini Artırma: Daha fazla katman ekleyerek modelin özellik öğrenme kapasitesini artırılabilir.

Hyperparameter Optimization: learning rate ve batch size gibi parametreleri optimize edilebilir.

Manipüle Edilmiş Test Seti İçin:

Daha Fazla Veri Artırma: Parlaklık ve kontrast manipülasyonlarını artırarak modelin bu durumlara alışmasını sağlanabilir.

Renk Sabitliği Uygulanmış Test Seti İçin:

Grayscale Eğitim: Renk özelliklerine daha az bağımlı bir model için gri tonlama ile eğitim yapılabilir. 

Alternatif Renk Dengeleme Teknikleri kullanılabilir örneğin Histogram eşitleme veya CLAHE

---

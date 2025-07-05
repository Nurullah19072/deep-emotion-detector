# 😃 Duygu Tanıma Sistemi | Emotion Recognition System (CNN + Tkinter + OpenCV)

## 📌 Proje Açıklaması | Project Description

**TR:**  
Bu proje, Python ile geliştirilmiş bir gerçek zamanlı duygu tanıma sistemidir. Görsel veriler temizlenip kategorilere ayrıldıktan sonra bir Convolutional Neural Network (CNN) modeli eğitilir. Ardından model; görsel, webcam ve GUI destekli olarak duygu tahmini yapabilir. Arayüz Tkinter ile geliştirilmiş, yüz algılama ise OpenCV kullanılarak yapılmıştır.

**EN:**  
This is a real-time emotion recognition system built with Python. After preprocessing and organizing image data, a CNN model is trained to classify emotions. The trained model can predict emotions via images, webcam, and a user-friendly Tkinter GUI. Face detection is handled by OpenCV.

---
##   NOT
* TR:
  Bu projede kullanılan veri seti, yüz ifadelerine göre duyguları sınıflandırmak amacıyla hazırlanmış bir görüntü veri setidir. Ancak bu veri seti artık Kaggle platformundan kaldırıldığı ve boyutu oldukça büyük    olduğu için bu repoya doğrudan dahil edilememiştir.

  Projeyi çalıştırmak isteyen kullanıcılar, benzer bir veri setini aşağıdaki şekilde yapılandırabilir:

  Ana klasör adı: archive/

  Alt klasörler: happy/, sad/, angry/, neutral/, fear/, surprise/

  Her klasör içinde: ilgili duyguya ait .jpg veya .png görseller

* EN:
  The dataset used in this project was originally hosted on Kaggle and contained facial images categorized by emotion. However, since it has been removed from Kaggle and is also too large to include in this        repository, it is not directly shared here.

  If you'd like to run the project, you can use your own dataset organized as follows:

  Main folder: archive/

  Subfolders: happy/, sad/, angry/, neutral/, fear/, surprise/

  Each folder should contain images (.jpg / .png) representing that emotio

---


## 🧠 Kullanılan Teknolojiler | Technologies Used

- Python 3
- TensorFlow / Keras
- OpenCV
- PIL / ImageHash
- Tkinter (GUI)
- Scikit-learn
- tqdm

---

## 🧩 Proje Bileşenleri | Project Components

| Aşama | Açıklama |
|-------|----------|
| 🔍 Görsel Temizleme | Aynı hash'e sahip görseller silinir (`imagehash`) |
| 🗂 Veri Ayrımı | Eğitim/test klasörleri oluşturulur (`train_test_split`) |
| 🧠 Model Eğitimi | CNN modeli augmentasyon ile eğitilir (`ImageDataGenerator`) |
| 🖥️ GUI | Tkinter ile arayüz geliştirilmiştir |
| 📷 Canlı Kamera | OpenCV ile yüz algılama ve canlı tahmin yapılır |
| 📁 Fotoğraf Analizi | Kullanıcıdan fotoğraf seçilerek duygu tahmini yapılır |
| 📝 Loglama | 5 saniyede bir `duygu_cikti.txt` dosyasına çıktı kaydı yapılır |

---

## 🖥️ Kullanım Talimatı | How to Run

### 1. Ortam Kurulumu / Setup

```bash
pip install -r requirements.txt
```

> Alternatif olarak:  
`tensorflow`, `opencv-python`, `Pillow`, `imagehash`, `tqdm`, `scikit-learn`

---

### 2. Eğitim Verisi Hazırlığı / Dataset Prep

- Görseller `archive/` klasöründe olmalı. Alt klasörler: `happy`, `sad`, `angry`, vs.
- Kod ilk olarak `archive/` içindeki kopya görselleri temizler.
- Ardından `data/train/` ve `data/test/` klasörlerini oluşturur.

---

### 3. Model Eğitimi / Train Model

Kod içinde `model.fit(...)` bölümüyle CNN modeli eğitilir ve `best_model_augmented.h5` dosyası oluşturulur.

---

### 4. Uygulama Çalıştırma / Run GUI
-Run tuşuna bas.
- GUI açılır.
- "📁 Fotoğraf Seç" butonu ile görselden duygu tanıma yapılır.
- "📷 Kamerayla Analiz Et" butonu ile canlı analiz yapılır.
- Kamera açıkken her 5 saniyede bir `duygu_cikti.txt` dosyasına zaman damgalı tahminler kaydedilir.

---

## 📊 Eğitim Parametreleri | Training Params

- Görsel boyutu: `96x96`
- Epoch: `70`
- Batch size: `64`
- Data augmentation: ✔️
- Regularization: L2

---


## 📄 Lisans | License

MIT License

---

## 🎓 Not

Bu proje bireysel olarak geliştirilmiştir. Yapay zekâ, görüntü işleme ve arayüz geliştirme konularına ilgi duyanlar için güçlü bir örnek teşkil eder.

# Sınıflandırma Algoritmaları Performans Analizi ve Hiperparametre Optimizasyonu

Bu proje, farklı veri yapılarına sahip üç popüler veri seti üzerinde; k-En Yakın Komşu (KNN), Destek Vektör Makineleri (SVM) ve Rastgele Orman (Random Forest) algoritmalarının performansını karşılaştırmalı olarak incelemektedir.

## 📋 Proje Hakkında
Bu çalışma, bir uçtan uca makine öğrenmesi hattını (pipeline) temsil eder. Verilerin görselleştirilmesinden başlayarak, ön işleme, hiperparametre optimizasyonu ve model değerlendirme süreçlerini içerir.

### 🔍 Kullanılan Veri Setleri
* **Breast Cancer:** İkili sınıflandırma (Binary Classification) odaklı medikal veri seti.
* **Wine:** Çok sınıflı (Multi-class) kimyasal analiz veri seti.
* **Digits:** El yazısı rakamlardan oluşan yüksek boyutlu görüntü veri seti.

## 🚀 Temel Özellikler
* **Boyut İndirgeme:** `PCA` kullanılarak yüksek boyutlu verilerin 2B düzlemde görselleştirilmesi.
* **Otomatik Optimizasyon:** `GridSearchCV` ile her model için en iyi hiperparametrelerin (n_neighbors, C, kernel, n_estimators vb.) belirlenmesi.
* **Ölçeklendirme:** Mesafe tabanlı algoritmalar için `StandardScaler` ile veri normalizasyonu.
* **Görsel Analiz:** Her model için Confusion Matrix (Hata Matrisi) ve genel doğruluk (Accuracy) karşılaştırma grafikleri.

## 🛠️ Kurulum
Projeyi yerel makinenizde çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

1. Gerekli kütüphaneleri yükleyin:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn

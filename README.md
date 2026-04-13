# Sınıflandırma Algoritmalarının Karşılaştırmalı Analizi ve Optimizasyonu

Bu proje, makine öğrenmesi süreçlerinde model seçimi, veri ön işleme, boyut indirgeme ve hiperparametre optimizasyonu aşamalarını kapsamlı bir şekilde ele almaktadır. Çalışma kapsamında, farklı veri yapılarına sahip veri setleri üzerinde popüler sınıflandırma algoritmalarının performans metrikleri analiz edilmiştir.

## 📋 Proje Metodolojisi

Proje, Bilgisayar Mühendisliği yüksek lisans düzeyinde bir araştırma pipeline'ı izlemektedir:

### 1. Veri Keşfi ve Görselleştirme (EDA)
* **Boyut İndirgeme (PCA):** Yüksek boyutlu öznitelik uzayına sahip veri setleri (özellikle Digits ve Breast Cancer), varyansın en yüksek olduğu 2 bileşene indirgenerek görselleştirilmiştir. Bu, verilerin sınıfsal ayrılabilirliğini (linearly separable olup olmadıklarını) anlamak için kritik bir adımdır.
* **Korelasyon Analizi:** Öznitelikler arasındaki istatistiksel ilişkileri belirlemek amacıyla ısı haritaları (Heatmap) üzerinden analiz yapılmıştır.

### 2. Veri Ön İşleme (Preprocessing)
* **Standardizasyon:** Mesafe tabanlı algoritmaların (KNN ve SVM) büyük ölçekli özniteliklerden etkilenmemesi için `StandardScaler` (Z-score normalizasyonu) kullanılmıştır.
* **Veri Bölümleme:** Modelin genelleme başarısını (generalization error) ölçmek için veriler %75 Eğitim ve %25 Test olarak ayrılmıştır.

### 3. Model Eğitimi ve Hiperparametre Optimizasyonu
`GridSearchCV` kullanılarak 5-katlı çapraz doğrulama (5-Fold Cross-Validation) ile aşağıdaki parametre uzayları taranmıştır:
* **K-Nearest Neighbors (KNN):** Komşu sayısı (k), ağırlık fonksiyonları (uniform, distance) ve mesafe metrikleri (Euclidean, Manhattan).
* **Support Vector Machines (SVM):** Regularizasyon parametresi (C) ve çekirdek (Kernel) fonksiyonları (RBF, Linear).
* **Random Forest (RF):** Karar ağacı sayısı (n_estimators) ve maksimum ağaç derinliği (max_depth).

## 🛠️ Teknik Gereksinimler
Çalışmanın yürütülmesi için gerekli kütüphaneler:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn

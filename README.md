# Sınıflandırma Algoritmalarının Karşılaştırmalı Analizi ve Hiperparametre Optimizasyonu

Bu proje, bilgisayar mühendisliği prensipleri çerçevesinde; veri ön işleme, boyut indirgeme, model seçimi ve hiperparametre optimizasyonu süreçlerini kapsayan kapsamlı bir makine öğrenmesi (ML) pipeline'ıdır. Çalışma, farklı karakteristiklere sahip veri setleri üzerinde KNN, SVM ve Random Forest algoritmalarının performansını ampirik verilerle karşılaştırır.

## 📋 Proje Metodolojisi

Proje akışı, yüksek lisans düzeyinde bir araştırma metodolojisine dayanmaktadır:

### 1. Veri Keşfi ve Görselleştirme (EDA)
* **PCA (Principal Component Analysis):** Yüksek boyutlu öznitelik uzayları, varyansın en yüksek olduğu ilk iki bileşene indirgenerek 2D düzlemde görselleştirilmiştir. Bu, sınıfların geometrik dağılımı ve ayrılabilirliği hakkında kritik ön bilgi sağlar.
* **Korelasyon Analizi:** Öznitelikler arasındaki doğrusal ilişkilerin tespiti için korelasyon matrisleri kullanılmıştır.

### 2. Veri Ön İşleme (Preprocessing)
* **Feature Scaling:** Mesafe tabanlı modellerin (KNN, SVM) performansını stabilize etmek için `StandardScaler` (Z-score normalizasyonu) uygulanmıştır.
* **Train/Test Split:** Modellerin genelleme (generalization) yeteneğini ölçmek amacıyla veri setleri %75 eğitim ve %25 test olarak ayrılmıştır.

### 3. Hiperparametre Optimizasyonu (Grid Search)
Her algoritma, 5-katlı çapraz doğrulama (5-Fold Cross-Validation) kullanılarak en uygun hiperparametreler ile eğitilmiştir:
- **KNN:** k-komşu sayısı, ağırlıklandırma (uniform/distance) ve mesafe metrikleri.
- **SVM:** C (ceza parametresi) ve çekirdek fonksiyonları (RBF, Linear).
- **Random Forest:** Karar ağacı sayısı (n_estimators) ve maksimum derinlik (max_depth).

## 📊 Performans Değerlendirme Metrikleri

Modellerin başarısı, sadece ham doğruluk üzerinden değil, istatistiksel güvenilirliği temsil eden şu metriklerle ölçülmüştür:

* **Accuracy (Doğruluk):** Toplam tahminler içerisindeki doğru sınıflandırma oranı.
* **Weighted F1-Score:** Precision ve Recall değerlerinin harmonik ortalaması. Sınıf dağılımı dengesiz olsa dahi modelin gerçek başarısını yansıtır.
* **Confusion Matrix (Hata Matrisi):** Tip I ve Tip II hataların (yanlış pozitif/negatif) sınıf bazında dağılımı.

## 🚀 Önemli Bulgular ve Çıkarımlar

Yapılan analizler sonucunda elde edilen temel bulgular şunlardır:

1.  **Ölçeklendirme Hassasiyeti:** Standardizasyon işleminin SVM ve KNN modellerinde belirgin bir doğruluk artışı sağladığı, ancak ağaç tabanlı Random Forest modelinin ölçeklendirmeden bağımsız olarak kararlı çalıştığı gözlemlenmiştir.
2.  **Boyutun Etkisi:** `Digits` gibi yüksek boyutlu verilerde Random Forest'ın öznitelik seçimi yeteneği sayesinde daha iyi genelleme yaptığı tespit edilmiştir.
3.  **Optimizasyon Kazancı:** Grid Search ile belirlenen parametrelerin, varsayılan (default) parametrelere kıyasla test setindeki hata payını (error rate) ortalama %3-7 oranında azalttığı saptanmıştır.
4.  **PCA Analizi:** Görselleştirmeler, sınıfların iç içe geçtiği (over-lapping) bölgelerde modellerin hata yapma eğiliminin arttığını doğrulamaktadır.

## 🛠️ Teknik Gereksinimler
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```
## Hazırlayan:
Begüm Yaren ÖZTÜRK


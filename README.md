# Akciğer Kanseri Veri Analizi (Survey Lung Cancer) – Dönem Projesi

Bu proje, Kaggle üzerinde paylaşılan **Survey Lung Cancer** veri seti kullanılarak
**LUNG_CANCER (YES/NO)** hedef değişkeninin tahmin edilmesini amaçlayan bir **ikili sınıflandırma** çalışmasıdır.
Projede veri keşfi (EDA), ön işleme, modelleme ve değerlendirme adımları uygulanmıştır.

---

## Problem Tanımı
Amaç: Anket tabanlı özellikler (AGE, GENDER, SMOKING, COUGHING, WHEEZING vb.) kullanarak
kişinin **LUNG_CANCER** sınıfını (0=NO, 1=YES) tahmin etmek.

---

## Veri Seti
- Kaynak: Kaggle – *Survey Lung Cancer*
- Boyut: **309 satır, 16 sütun**
- Hedef (Target): **LUNG_CANCER** (YES/NO → 1/0)
- Not: Sınıf dağılımı dengesizdir (YES örnekleri daha fazladır).

---

## Kullanılan Yöntemler

### 1) EDA ve Ön İşleme
- Kolon adları düzenlendi
- `LUNG_CANCER`: YES/NO → 1/0
- `GENDER`: MALE/FEMALE → 1/0
- Pipeline içinde güvenlik amaçlı **median imputation** kullanıldı
- Logistic Regression için **StandardScaler** uygulandı
- Veri bölme: **%80 Train / %20 Test** (`stratify=y`)

### 2) Modeller
- **Logistic Regression** (baseline)
- **Random Forest** (feature importance analizi için de kullanıldı)

---

## Sonuçlar (Özet)
- **Logistic Regression**
  - Accuracy: **0.871**
  - ROC-AUC: **0.954**
- **Random Forest**
  - Accuracy: **0.887**
  - ROC-AUC: **0.946**

> Değerlendirmede Accuracy yanında Confusion Matrix ve ROC-AUC kullanılmıştır.

---

## Çalıştırma (Google Colab)

1. Bu repoyu indir (Download ZIP) veya `git clone` ile çek.
2. Aşağıdaki dosyaların aynı klasörde olduğundan emin ol:
   - `survey_lung_cancer.csv`
   - `lung_cancer.ipynb`
3. Notebook’u çalıştır:
   - Google Colab’da aç → `Runtime -> Run all` (Tümünü Çalıştır)

Opsiyonel kurulum:
```bash
pip install pandas numpy matplotlib scikit-learn

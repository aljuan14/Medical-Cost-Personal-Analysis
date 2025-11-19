
# 🏥 Medical Cost Prediction (Regression)

Project *Machine Learning* untuk memprediksi biaya tagihan medis (*medical insurance charges*) berdasarkan data demografis dan gaya hidup. Proyek ini membandingkan performa tiga algoritma regresi: **Linear Regression**, **Random Forest**, dan **XGBoost**.

## 📋 Daftar Isi

  - [Tentang Project](https://www.google.com/search?q=%23-tentang-project)
  - [Dataset](https://www.google.com/search?q=%23-dataset)
  - [Metodologi](https://www.google.com/search?q=%23-metodologi)
  - [Hasil Evaluasi Model](https://www.google.com/search?q=%23-hasil-evaluasi-model)
  - [Insight & Kesimpulan](https://www.google.com/search?q=%23-insight--kesimpulan)
  - [Cara Menjalankan](https://www.google.com/search?q=%23-cara-menjalankan)

## 🔍 Tentang Project

Tujuan utama proyek ini adalah membangun model prediksi untuk memperkirakan `charges` (biaya medis) seseorang. Analisis ini membantu memahami faktor risiko utama yang membebankan biaya asuransi.

## 📊 Dataset

Dataset `insurance.csv` terdiri dari **1.338 baris** dan **7 kolom**.

  * **Target:** `charges` (Kontinu/Numerik).
  * **Fitur:** `age`, `sex`, `bmi`, `children`, `smoker`, `region`.
  * **Kondisi Data:** Bersih (tidak ada *missing values*).

## ⚙️ Metodologi

1.  **EDA (Exploratory Data Analysis):**
      * Analisis distribusi biaya (Skewed distribution).
      * Analisis hubungan `smoker` vs `charges` (Perokok memiliki biaya jauh lebih tinggi).
      * Analisis korelasi (Heatmap).
2.  **Preprocessing:**
      * Encoding variabel kategorikal (`sex`, `smoker`, `region`) menggunakan Label Encoding.
3.  **Modeling:**
      * **Linear Regression** (Baseline).
      * **Random Forest Regressor** (Ensemble Bagging).
      * **XGBoost Regressor** (Ensemble Boosting) - *New\!*.
4.  **Evaluasi:**
      * Menggunakan MAE, RMSE, dan R-Squared ($R^2$).

## 🏆 Hasil Evaluasi Model

Berdasarkan pengujian pada 20% data testing (268 data), berikut adalah perbandingan performanya:

| Model | MAE (Error $) | RMSE (Error $) | Akurasi ($R^2$) |
| :--- | :--- | :--- | :--- |
| Linear Regression | $4,186.51 | $5,799.59 | 78.33% |
| Random Forest | $2,533.67 | $4,590.57 | 86.43% |
| **XGBoost** | **$2,365.86\*\* | **$4,368.01** | **87.71%** |

> **Pemenang:** 🏆 **XGBoost** adalah model terbaik dengan error terendah dan kemampuan menjelaskan variasi data sebesar **87.71%**.

## 💡 Insight & Kesimpulan

1.  **Faktor Terpenting:** Status **Perokok (`smoker`)** adalah fitur yang paling dominan mempengaruhi biaya asuransi, dengan *feature importance* mencapai **\>60%** pada model tree-based.
2.  **Model:** Algoritma non-linear (Random Forest & XGBoost) jauh mengungguli Linear Regression, menunjukkan bahwa pola kenaikan biaya medis tidak selalu berupa garis lurus (misalnya lonjakan biaya drastis pada perokok dengan BMI tinggi).

## 🚀 Cara Menjalankan

1.  **Clone Repository:**
    ```bash
    git clone https://github.com/username-kamu/medical-cost-prediction.git
    ```
2.  **Install Dependencies:**
    Pastikan kamu menginstall `xgboost` selain library standar.
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn xgboost
    ```
3.  **Jalankan Notebook:**
    Buka file `train.ipynb` di VS Code atau Jupyter Notebook.

-----

*Dibuat sebagai latihan Regression Analysis.*

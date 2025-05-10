# 📊 Analisis Attrition Karyawan dengan XGBoost & SHAP

## 1. 🧠 Business Understanding

Perusahaan Jaya Jaya Maju mengalami tingkat pengunduran diri (attrition) karyawan yang signifikan dalam beberapa tahun terakhir. Untuk menjaga stabilitas organisasi dan efisiensi operasional, penting untuk memahami faktor-faktor yang mendorong karyawan mengundurkan diri.

## 2. ❓ Permasalahan Bisnis

- Apa saja faktor utama yang menyebabkan karyawan resign?
- Bagaimana cara mengidentifikasi karyawan dengan risiko tinggi untuk mengundurkan diri?
- Bagaimana HR dapat mengambil langkah preventif berdasarkan data?

## 3. 🔎 Cakupan Proyek

Proyek ini berfokus pada:
- Membangun model prediksi attrition menggunakan algoritma XGBoost.
- Menganalisis interpretabilitas model menggunakan SHAP dan Feature Importance.
- Memberikan insight berbasis data untuk mendukung pengambilan keputusan strategis oleh tim HR.

## 4. ⚙️ Persiapan

### 📂 Sumber Data:
- Dataset internal perusahaan mengenai informasi karyawan (demografi, jabatan, pengalaman kerja, kepuasan kerja, dll).
- Fitur target: Attrition (Yes/No)

### 💻 Setup Environment:
- Python (Scikit-Learn, XGBoost, SHAP, Pandas, Matplotlib)
- Jupyter Notebook
- Streamlit (untuk visualisasi dashboard)

---

## 5. 📈 Analisis Model & Interpretabilitas

### A. Global Feature Importance (SHAP)

**Fitur paling dominan:**
- `StockOptionLevel`  
- `EnvironmentSatisfaction`  
- `OverTime_Yes`  
- `JobInvolvement`

🧠 Interpretasi:
- Opsi saham dan kondisi lingkungan kerja sangat memengaruhi keputusan resign.
- Lembur menjadi faktor risiko utama yang dapat dimitigasi oleh HR.

### B. SHAP Summary Plot (Multivariat)

**Insight utama:**
- `OverTime_Yes` → Karyawan yang sering lembur (nilai SHAP positif) lebih cenderung resign.
- `EnvironmentSatisfaction` → Semakin tidak puas, semakin besar kemungkinan resign.
- `MaritalStatus_Divorced` → Berhubungan positif dengan keputusan resign.
- `EducationField_Life Sciences / Medical` → Lebih stabil.

### C. Feature Importance dari Model

**Fitur penting yang konsisten:**
- `StockOptionLevel`, `EnvironmentSatisfaction`, `OverTime_Yes`

**Perbedaan:**
- `JobRole_Manufacturing Director` muncul signifikan di feature importance tapi tidak di SHAP → indikasi adanya interaksi kompleks dalam model.

---

## 6. 📊 Business Dashboard

Visualisasi interaktif disediakan untuk membantu tim HR:
- Menyaring dan menganalisis faktor penyebab attrition
- Memahami distribusi risiko resign per departemen/jabatan
- Menyusun strategi retention berbasis data

![Dashboard Overview](giansirait-dashboard.png)

---

## 7. 🧾 Kesimpulan

**Faktor-faktor utama penyebab attrition:**
1. 💰 Kompensasi  
   - `StockOptionLevel` & `JobLevel` rendah → merasa kurang dihargai.

2. ⚖️ Beban Kerja  
   - `OverTime` & `JobInvolvement` rendah → beban kerja tidak seimbang.

3. 🌱 Lingkungan Kerja  
   - `EnvironmentSatisfaction` & `JobSatisfaction` rendah → budaya kerja perlu evaluasi.

4. 👥 Demografi  
   - `MaritalStatus_Divorced` dan `Gender_Female` → cenderung lebih rentan resign *(tergantung konteks data)*.

---

## 8. ✅ Rekomendasi Action Items

1. **Tingkatkan Kepuasan Lingkungan Kerja**  
   - Laksanakan program feedback rutin dari karyawan.  
   - Lakukan perbaikan dan pemeliharaan fasilitas kerja secara berkala.

2. **Batasi Overtime**  
   - Evaluasi ulang distribusi beban kerja antar tim.  
   - Sediakan insentif yang adil untuk lembur.

3. **Review Kebijakan Kompensasi**  
   - Tawarkan opsi saham atau tunjangan tambahan, terutama untuk karyawan level junior.

4. **Fleksibilitas Kerja**  
   - Terapkan program kerja dari rumah (WFH) sebagian atau penuh waktu.  
   - Dorong keseimbangan kehidupan kerja (Work-Life Balance) untuk meningkatkan produktivitas.

# Sistem-Klasifikasi-Risiko-Kelayakan-Kredit-Berbasis-AI
Project for UAS AI

# 🚀 Panduan Setup & Run Proyek di Lokal

Selamat datang! Buat kamu yang mau nge-pull repo ini dan cobain langsung **Sistem Klasifikasi Risiko Kelayakan Kredit Berbasis AI** di komputer sendiri, panduan ini bakal ngebantu banget. 

Inti dari proyek ini lumayan seru: kita ngegabungin data angka biasa (kayak gaji dan tanggungan) sama sentimen teks dari catatan nasabah pakai NLP (IndoBERTa).

## 📋 Persiapan Awal
Biar prosesnya mulus, pastikan di laptop atau PC kamu udah ada:
1. **Python 3.8+**
2. **Git** (buat clone repo)
3. **Jupyter Notebook** atau bisa juga pakai **VS Code** yang udah dipasang ekstensi Jupyter.
4. Akun **Weights & Biases (WandB)**. Ini kepake banget buat ngeliat performa model (opsional sih, tapi sayang kalau dilewatin).

---

## ⚙️ Mulai Instalasi

**1. Clone Repositori**
Buka terminal favoritmu, lalu *clone* reponya ke folder lokal:
```bash
git clone <URL_REPOSITORI_ANDA>
cd <NAMA_FOLDER_REPOSITORI>
```

**2. Bikin Virtual Environment (Wajib Banget!)**
Biar *library* proyek ini nggak tabrakan sama *project* Python kamu yang lain, mending bikin *virtual environment* dulu.
*   Kalau pakai **Windows:**
    ```bash
    python -m venv env
    .\env\Scripts\activate
    ```
*   Kalau pakai **Mac/Linux:**
    ```bash
    python3 -m venv env
    source env/bin/activate
    ```

**3. Install Semua Kebutuhan (Dependencies)**
Sekarang tinggal install semua *library* pendukung yang dipakai di proyek ini. Tinggal ketik ini:
```bash
pip install transformers wandb scikit-learn pandas numpy joblib matplotlib seaborn jupyter
```

**4. Autentikasi WandB**
Karena kita pakai WandB buat nge-track eksperimen, login dulu ke akunmu:
```bash
wandb login
```
Nanti tinggal *paste* API key dari dashboard WandB kamu. Kalau lagi malas login, santai aja, kodenya udah diatur biar otomatis pindah ke mode *offline*.

---

## ▶️ Cara Jalanin Kodenya

**1. Buka Jupyter Notebook**
Di terminal yang sama, ketik perintah ini:
```bash
jupyter notebook
```

**2. Buka Notebook Utama**
Nanti browser bakal otomatis kebuka. Cari dan buka file yang namanya `Tugas_UAS_AI_Raki_Raihan.ipynb`.

**3. Eksekusi Kodenya**
Langsung aja jalankan (*run*) selnya satu-satu (Shift + Enter) atau pencet **"Run All"**. 
*   **Perhatian:** Pas pertama kali jalan, agak sabar dikit ya. Kodenya bakal *download* model NLP `w11wo/indonesian-roberta-base-sentiment-classifier` dari Hugging Face. Jadi pastikan koneksi internet kamu aman.
*   Setelah itu, sistem bakal nge-train model (Gradient Boosting & Random Forest) dan ngasih laporan evaluasinya.
*   Di bagian akhir, model terbaiknya bakal disave langsung ke folder kamu dengan nama `model_gbc_uas.joblib` dan `scaler_uas.joblib`. Ini model matang yang siap dipakai!

**4. Waktunya Eksperimen!**
Kalau semua sel udah beres jalan, kamu bisa nyobain nebak data baru. Scroll ke paling bawah, cari fungsi `prediksi_kandidat_baru()`. Silakan ubah angka pendapatan, jumlah tanggungan, atau iseng ganti kalimat catatannya buat lihat gimana si AI ngambil keputusan (Layak/Tidak Layak).

Selamat ngoprek! 💻🔥

# Sistem-Klasifikasi-Risiko-Kelayakan-Kredit-Berbasis-AI
Project for UAS AI

Analisis Proyek Kelayakan Kredit
File notebook ini memuat proyek "Sistem Klasifikasi Risiko Kelayakan Kredit Berbasis AI". Berikut adalah poin-poin utama dari analisis kode tersebut:  
IPYNB

Pengolahan Data: Proyek ini menggunakan simulasi data pendapatan, tanggungan, dan catatan nasabah, serta mengisi data kosong menggunakan nilai median dan modus.  
IPYNB

Integrasi NLP: Menggunakan model AI bahasa IndoBERTa untuk mengekstraksi skor sentimen dari catatan kondisi keuangan nasabah secara otomatis.  
IPYNB

Kinerja Model: Membandingkan algoritma Random Forest dan Gradient Boosting yang telah dioptimasi, di mana keduanya mendapatkan akurasi pengujian sebesar 30% karena keterbatasan ukuran data dummy.  
IPYNB

Pengaruh Fitur: Pendapatan bulanan menjadi penentu utama (66.34%), diikuti oleh jumlah tanggungan (26.75%), dan skor NLP (6.91%).  
IPYNB

Teks Presentasi (Panduan Lisan)
"Halo semuanya, hari ini saya akan mempresentasikan Sistem Klasifikasi Risiko Kelayakan Kredit berbasis AI. Sistem ini cukup inovatif karena tidak hanya mengevaluasi angka seperti pendapatan dan tanggungan, tetapi juga menganalisis sentimen dari catatan nasabah menggunakan NLP IndoBERTa.  
IPYNB
+ 1

Setelah melakukan hyperparameter tuning pada model Gradient Boosting, sistem memproses data melalui evaluasi otomatis. Meskipun diuji pada data simulasi skala kecil dengan akurasi 30%, analisis Feature Importance kami berhasil membuktikan bahwa pendapatan bulanan menyumbang bobot evaluasi terbesar, sementara skor teks memberikan lapisan konteks tambahan untuk keputusan akhir AI."  
IPYNB
+ 1

Draf Slide Presentasi (.md)
Berikut adalah struktur slide dalam format Markdown yang bisa Anda salin langsung ke file .md:

Markdown
# Sistem Klasifikasi Risiko Kredit Berbasis AI[cite: 1]

## 1. Pendekatan Utama[cite: 1]
* Integrasi data finansial numerik dan analisis teks[cite: 1].
* Menggunakan AI NLP IndoBERTa untuk membaca sentimen catatan nasabah[cite: 1].

## 2. Tahapan Pemodelan[cite: 1]
* **Algoritma**: Evaluasi menggunakan Random Forest dan Gradient Boosting[cite: 1].
* **Hyperparameter Tuning**: Menghasilkan akurasi validasi 55% dan akurasi uji 30% pada data dummy[cite: 1].

## 3. Fitur Paling Berpengaruh[cite: 1]
* **Pendapatan Bulanan**: 66.34%[cite: 1].
* **Jumlah Tanggungan**: 26.75%[cite: 1].
* **Skor Sentimen (NLP)**: 6.91%[cite: 1].
Apakah Anda ingin saya membantu merancang skenario pertanyaan audiens beserta jawaban teknisnya untuk persiapan presentasi Anda?

tolong buatkan alur dan penjelasan cara penginstalan dan merunning proyek apabila ada orang yang pull ke lokalnya

Untuk memudahkan siapa saja yang ingin melakukan pull dan menjalankan proyek ini di komputer lokal mereka, saya telah menyusun panduan langkah demi langkah. Panduan ini mencakup proses instalasi pustaka yang dibutuhkan hingga cara mengeksekusi kode berdasarkan file notebook aslinya.

Saya juga akan membuatkan file panduan ini dalam format Panduan_Instalasi_Proyek.md agar bisa langsung Anda gunakan sebagai README.md di repositori Anda.

2. Buat Virtual Environment (Sangat Direkomendasikan)
Agar dependencies proyek ini tidak bentrok dengan proyek lain di komputer Anda, buat virtual environment:

Windows:

Bash
python -m venv env
.\\env\\Scripts\\activate
Mac/Linux:

Bash
python3 -m venv env
source env/bin/activate
3. Instalasi Library yang Dibutuhkan
Instal seluruh pustaka Python yang digunakan dalam proyek ini. Anda bisa menginstalnya secara langsung melalui pip:

Bash
pip install transformers wandb scikit-learn pandas numpy joblib matplotlib seaborn jupyter
(Catatan: Pustaka ini sesuai dengan yang digunakan dalam notebook proyek).

4. Autentikasi Weights & Biases (WandB)
Proyek ini menggunakan WandB untuk memantau performa model. Lakukan login dengan menjalankan:

Bash
wandb login
Masukkan API key dari akun WandB Anda saat diminta. Jika Anda ingin menjalankannya tanpa sinkronisasi internet (offline), Anda bisa melewati langkah ini (kode sudah menangani mode offline).

▶️ Cara Menjalankan Proyek
1. Buka Jupyter Notebook
Jalankan perintah berikut di terminal Anda:

Bash
jupyter notebook
2. Buka File Notebook
Pada antarmuka Jupyter di browser, cari dan buka file bernama Tugas_UAS_AI_Raki_Raihan.ipynb.

3. Eksekusi Sel (Run Cells)
Jalankan setiap blok sel (cell) secara berurutan (Shift + Enter) atau klik tombol "Run All".

Notebook akan secara otomatis mengunduh model NLP w11wo/indonesian-roberta-base-sentiment-classifier dari Hugging Face pada run pertama. Pastikan Anda memiliki koneksi internet yang stabil.

Model Machine Learning akan dilatih (Gradient Boosting & Random Forest) dan dievaluasi.

Pada tahap akhir, sistem akan menyimpan model terbaik dan scaler ke dalam penyimpanan lokal Anda dengan nama:

model_gbc_uas.joblib

scaler_uas.joblib

4. Menguji Prediksi Kandidat Baru
Setelah seluruh sel selesai dieksekusi, Anda dapat menguji model dengan data baru menggunakan fungsi prediksi_kandidat_baru() di bagian paling bawah notebook dengan mengubah nilai pendapatan, jumlah tanggungan, dan catatan teks sesuai keinginan Anda.

Proyek ini merupakan implementasi dari klasifikasi risiko kredit AI.
"""

with open("Panduan_Instalasi_Proyek.md", "w", encoding="utf-8") as f:
f.write(content)

print("File Panduan_Instalasi_Proyek.md berhasil dibuat!")


```text?code_stdout&code_event_index=1
File Panduan_Instalasi_Proyek.md berhasil dibuat!

Your Markdown (.md) file is ready

Ikon MD
Panduan_Instalasi_Proyek
 MD 
Buka
Berikut adalah penjelasan alur untuk melakukan penyiapan (setup) dan menjalankan proyek ini di lokal:

Persiapan Lingkungan (Environment Setup)
Pertama, pengguna harus mengkloning repositori Anda. Sangat disarankan untuk membuat Virtual Environment (venv) agar library yang diinstal tidak mengganggu proyek Python lainnya di komputer pengguna.

Instalasi Library (Dependencies)
Pengguna perlu menginstal semua library yang tertera pada bagian awal notebook Anda. Berdasarkan file referensi, pustaka yang wajib diinstal adalah transformers, wandb, scikit-learn, pandas, numpy, joblib, matplotlib, dan seaborn.  
IPYNB

Konfigurasi Weights & Biases (WandB)
Karena proyek ini mengintegrasikan wandb untuk tracking eksperimen, pengguna disarankan untuk menjalankan perintah wandb login di terminal mereka dan memasukkan API key dari akun WandB. Meskipun notebook menunjukkan mode offline jika tidak login, performa tracking akan lebih optimal jika dilakukan login.  
IPYNB
+ 1

Menjalankan Jupyter Notebook
Pengguna kemudian membuka file Tugas_UAS_AI_Raki_Raihan.ipynb menggunakan Jupyter Notebook atau editor kode seperti VS Code.  
IPYNB

Eksekusi dan Ekspor Model
Saat kode dieksekusi (di-run), sistem akan mengunduh model IndoBERTa dari Hugging Face untuk fitur NLP, membuat dataset dummy, dan melatih model Machine Learning. Pada sel terakhir, model Gradient Boosting terbaik serta parameter StandardScaler akan otomatis disimpan ke dalam file lokal dengan nama model_gbc_uas.joblib dan scaler_uas.joblib. File artefak inilah yang nantinya bisa digunakan oleh pengguna untuk tahap deployment.  
IPYNB
+ 2

Anda dapat melampirkan file Panduan_Instalasi_Proyek.md di atas ke dalam repositori GitHub/GitLab Anda agar tim atau orang lain dapat membacanya dengan rapi!

Gemini adalah AI dan dapat membuat kesalahan.





Menganalisis
Explain
# Panduan Instalasi dan Menjalankan Proyek Lokal

Proyek ini adalah **Sistem Klasifikasi Risiko Kelayakan Kredit Berbasis AI** yang menggabungkan analisis data numerik tradisional dengan sentimen teks (NLP) menggunakan model IndoBERTa.

## 📋 Prasyarat
Sebelum memulai, pastikan komputer Anda telah menginstal:
1. **Python 3.8+**
2. **Git** (untuk melakukan pull/clone repositori)
3. **Jupyter Notebook** atau IDE seperti **VS Code** yang mendukung ekstensi `.ipynb`
4. Akun **Weights & Biases (WandB)** untuk tracking eksperimen (opsional namun direkomendasikan).

---

## ⚙️ Langkah-langkah Instalasi

**1. Clone Repositori**
Buka terminal/Command Prompt dan jalankan perintah berikut untuk mengunduh proyek ke lokal Anda:
```bash
git clone <URL_REPOSITORI_ANDA>
cd <NAMA_FOLDER_REPOSITORI>
```

**2. Buat Virtual Environment (Sangat Direkomendasikan)**
Agar *dependencies* proyek ini tidak bentrok dengan proyek lain di komputer Anda, buat *virtual environment*:
*   **Windows:**
    ```bash
    python -m venv env
    .\env\Scripts\activate
    ```
*   **Mac/Linux:**
    ```bash
    python3 -m venv env
    source env/bin/activate
    ```

**3. Instalasi Library yang Dibutuhkan**
Instal seluruh pustaka Python yang digunakan dalam proyek ini. Anda bisa menginstalnya secara langsung melalui `pip`:
```bash
pip install transformers wandb scikit-learn pandas numpy joblib matplotlib seaborn jupyter
```
*(Catatan: Pustaka ini sesuai dengan yang digunakan dalam notebook proyek).*

**4. Autentikasi Weights & Biases (WandB)**
Proyek ini menggunakan WandB untuk memantau performa model. Lakukan login dengan menjalankan:
```bash
wandb login
```
Masukkan API key dari akun WandB Anda saat diminta. Jika Anda ingin menjalankannya tanpa sinkronisasi internet (offline), Anda bisa melewati langkah ini (kode sudah menangani mode offline).

---

## ▶️ Cara Menjalankan Proyek

**1. Buka Jupyter Notebook**
Jalankan perintah berikut di terminal Anda:
```bash
jupyter notebook
```

**2. Buka File Notebook**
Pada antarmuka Jupyter di browser, cari dan buka file bernama `Tugas_UAS_AI_Raki_Raihan.ipynb`.

**3. Eksekusi Sel (Run Cells)**
Jalankan setiap blok sel (*cell*) secara berurutan (Shift + Enter) atau klik tombol **"Run All"**. 
*   Notebook akan secara otomatis mengunduh model NLP `w11wo/indonesian-roberta-base-sentiment-classifier` dari Hugging Face pada run pertama. Pastikan Anda memiliki koneksi internet yang stabil.
*   Model Machine Learning akan dilatih (Gradient Boosting & Random Forest) dan dievaluasi.
*   Pada tahap akhir, sistem akan menyimpan model terbaik dan *scaler* ke dalam penyimpanan lokal Anda dengan nama:
    *   `model_gbc_uas.joblib`
    *   `scaler_uas.joblib`

**4. Menguji Prediksi Kandidat Baru**
Setelah seluruh sel selesai dieksekusi, Anda dapat menguji model dengan data baru menggunakan fungsi `prediksi_kandidat_baru()` di bagian paling bawah notebook dengan mengubah nilai pendapatan, jumlah tanggungan, dan catatan teks sesuai keinginan Anda.

---
*Proyek ini merupakan implementasi dari klasifikasi risiko kredit AI.*
Panduan_Instalasi_Proyek.md
Menampilkan Panduan_Instalasi_Proyek.md.

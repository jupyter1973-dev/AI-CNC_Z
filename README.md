# 🏭 PROTOTYPE: AI-POWERED CNC VIRTUAL LEARNING

## Pendahuluan
Proyek ini adalah *Proof of Concept* (PoC) untuk platform pembelajaran virtual CNC dengan Kecerdasan Buatan. Tujuannya adalah untuk mendemonstrasikan bagaimana teknologi AI dan simulasi dapat digunakan untuk meningkatkan pendidikan dan pelatihan di bidang manufaktur CNC, khususnya untuk sekolah kejuruan (SMK).

## Fitur Utama
1.  **CNC Simulator 2D/3D**: Memvisualisasikan jalur alat (tool path) G-code secara interaktif dalam dua atau tiga dimensi.
2.  **AI G-code Generator**: Asisten AI untuk menghasilkan, mengoptimalkan, dan membantu debugging G-code untuk berbagai bentuk geometris.
3.  **Virtual Quality Control**: Mensimulasikan inspeksi kualitas benda kerja menggunakan teknik Computer Vision untuk mendeteksi cacat.
4.  **Predictive Maintenance Simulation**: Mensimulasikan pemantauan kesehatan mesin dan memprediksi potensi kegagalan berdasarkan data sensor, menggunakan algoritma pembelajaran mesin untuk deteksi anomali.

## Instalasi

### Lingkungan Python Lokal
Jika Anda ingin menjalankan proyek ini di lingkungan Python lokal (di luar Google Colab), pastikan Anda memiliki Python 3.8+ terinstal. Kemudian, Anda dapat menginstal semua dependensi menggunakan pip:

```bash
# Buat virtual environment (opsional, namun disarankan)
python -m venv venv
source venv/bin/activate # Untuk Linux/macOS
# venv\Scripts\activate   # Untuk Windows

# Instal semua library yang dibutuhkan
pip install numpy matplotlib plotly ipywidgets scikit-learn tensorflow gradio streamlit opencv-python
```

## Tujuan Proyek
*   **Meningkatkan Pemahaman Konsep CNC**: Memberikan alat visual dan interaktif untuk memahami prinsip-prinsip dasar CNC dan G-code.
*   **Aplikasi AI dalam Manufaktur**: Mendemonstrasikan potensi AI dalam otomasi pembuatan G-code, kontrol kualitas, dan pemeliharaan prediktif.
*   **Pembelajaran Aksesibel**: Menyediakan platform pembelajaran virtual yang dapat diakses melalui web browser, tanpa memerlukan perangkat keras CNC fisik yang mahal.
*   **Pengembangan Keterampilan**: Membantu siswa SMK dan profesional melatih keterampilan mereka dalam pemrograman CNC dan analisis data mesin.

## Penggunaan dan Reproduksi Proyek

### 1. Menyiapkan Lingkungan

#### Di Lingkungan Python Lokal
*   Setelah menginstal dependensi (lihat bagian Instalasi di atas), Anda bisa menjalankan skrip Python secara individual atau mengadaptasi kode sel ke dalam skrip `.py`.
*   Untuk antarmuka Gradio, simpan kode dari sel Gradio (`DHtHAInqTzqT`) ke dalam file `app_gradio.py` dan jalankan `python app_gradio.py`.
*   Untuk aplikasi Streamlit, simpan kode dari sel Streamlit (`6SKZmzncTznK`) ke dalam file `cnc_simulator_app.py` dan jalankan `streamlit run cnc_simulator_app.py`.

### 2. Fitur CNC Simulator
*   Kelas `SimpleCNCSimulator` memungkinkan Anda mengeksekusi G-code dan memvisualisasikan jalur alat.
*   Anda dapat memodifikasi `sample_gcode` di sel `VdaOTioDTz2n` dan menjalankan ulang untuk melihat visualisasi yang berbeda.
*   **Visualisasi**: Visualisasi 2D (menggunakan Matplotlib) dan 3D (menggunakan Plotly) , window Matplotlib akan muncul, dan plot Plotly akan terbuka di browser default Anda.
*   **Contoh Visualisasi**: ![Contoh Visualisasi CNC Simulator](https://i.imgur.com/example_cnc_sim.png)

### 3. Fitur AI G-code Assistant
*   Kelas `AICodeAssistant` di sel `XRZtmRWHTzzl` menyediakan metode untuk membuat G-code untuk bentuk dasar (persegi, lingkaran, segitiga, pocket).
*   Anda bisa memanggil fungsi-fungsi seperti `ai_assistant.generate_square(size=...)` untuk mendapatkan G-code yang dihasilkan.
*   **Visualisasi**: G-code yang dihasilkan akan ditampilkan sebagai teks. Untuk memvisualisasikannya, Anda bisa menyalin G-code ini ke dalam `SimpleCNCSimulator`.
*   **Contoh Visualisasi**: ![Contoh G-code Assistant](https://i.imgur.com/example_ai_gcode.png)

### 4. Fitur Virtual Quality Control
*   Kelas `VirtualQualityControl` di sel `E_uSZLb7Tzwe` mensimulasikan inspeksi benda kerja.
*   Fungsi `qc.simulate_workpiece(has_defect=True/False)` membuat gambar benda kerja.
*   Fungsi `qc.detect_defects()` akan mengidentifikasi cacat pada gambar yang disimulasikan, dan `qc.visualize_inspection()` akan menampilkan hasilnya.
*   **Visualisasi**: Gambar hasil inspeksi (benda kerja asli, deteksi tepi, dan cacat yang disorot), ini akan muncul di window Matplotlib.
*   **Contoh Visualisasi**: ![Contoh Virtual Quality Control](https://i.imgur.com/example_vqc.png)

### 5. Fitur Predictive Maintenance Simulation
*   Kelas `PredictiveMaintenanceSimulator` di sel `07283e14` mensimulasikan data sensor dan mendeteksi anomali. Ini sudah mencakup *hyperparameter tuning* untuk model OneClassSVM.
*   Fungsi `pm.generate_sensor_data()` membuat data sensor, dan `pm.detect_anomalies()` mengidentifikasi pola-pola aneh.
*   `pm.visualize_predictive_maintenance()` akan menampilkan grafik sensor dengan anomali yang disorot serta prediksi pemeliharaan.
*   **Visualisasi**: Grafik interaktif dari data sensor dengan anomali yang disorot (menggunakan Plotly) , plot ini akan terbuka di browser default Anda.
*   **Contoh Visualisasi**: ![Contoh Predictive Maintenance](https://i.imgur.com/example_pm.png)

### 6. Antarmuka Interaktif (Gradio)
*   Sel `DHtHAInqTzqT` akan meluncurkan antarmuka web Gradio.
*   Setelah sel ini dijalankan, akan muncul tautan publik (biasanya berakhir dengan `.gradio.live`). Buka tautan ini di browser Anda untuk berinteraksi dengan semua fitur proyek dalam satu antarmuka yang ramah pengguna.
*   **Visualisasi**: Semua visualisasi (CNC, QC, PM) akan terintegrasi dan ditampilkan langsung di antarmuka web Gradio.
*   **Contoh Visualisasi**: ![Contoh Gradio Interface](https://i.imgur.com/example_gradio.png)

### 7. Aplikasi Streamlit (Opsional)
*   Sel `6SKZmzncTznK` akan membuat file `cnc_simulator_app.py`.
*   Untuk menjalankan aplikasi Streamlit ini, Anda perlu mengunduh file `.py` tersebut dan menjalankannya secara lokal dengan `streamlit run cnc_simulator_app.py` atau menyebarkannya ke platform seperti Streamlit Cloud. Ini memberikan alternatif untuk akses seluler.
*   **Visualisasi**: Visualisasi akan ditampilkan langsung di antarmuka web Streamlit.
*   **Contoh Visualisasi**: ![Contoh Streamlit App](https://i.imgur.com/example_streamlit.png)

### 8. Pengujian Fungsionalitas Dasar
*   Sel `30vsjAIBTzkn` berisi fungsi `test_all_features()` yang dapat Anda jalankan untuk memverifikasi bahwa semua komponen utama proyek berfungsi dengan benar. Output akan berupa teks konfirmasi di output sel.

## Kontribusi
Proyek ini bersifat prototipe dan terbuka untuk pengembangan lebih lanjut. Ide-ide untuk kontribusi meliputi:
*   Ekspansi pada `AI G-code Assistant` (misalnya, menambahkan lebih banyak bentuk, optimasi jalur alat).
*   Peningkatan model `Virtual Quality Control` (misalnya, menggunakan model deep learning).
*   Penyempurnaan model `Predictive Maintenance` dengan algoritma yang lebih canggih atau data yang lebih kompleks.
*   Perbaikan UI/UX pada antarmuka Gradio atau Streamlit.
*   Implementasi lebih banyak standar industri dan metrik evaluasi.

Selamat mencoba dan berkreasi!

Z.Arif Gani

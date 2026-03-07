# Real-Time-Object-Detection-YOLO-
Otomatisasi Monitoring K3 (Keselamatan Kerja) dengan Computer Vision YOLOv8  

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-blue?style=for-the-badge)
![Computer Vision](https://img.shields.io/badge/Computer%20Vision-Inference-green?style=for-the-badge)

Proyek ini menggunakan algoritma **YOLOv8** untuk mendeteksi penggunaan Alat Pelindung Diri (APD) secara real-time di lingkungan konstruksi. Sistem ini mampu mengidentifikasi pekerja yang patuh maupun yang melanggar aturan keselamatan kerja (HSE).

## 📌 Masalah yang Diselesaikan
* **Monitoring Otomatis:** Menghilangkan ketergantungan pada pengawasan manual yang rentan terhadap kelalaian manusia.
* **Deteksi Pelanggaran Real-Time:** Mengidentifikasi pekerja tanpa helm (`NO-Hardhat`) atau rompi (`NO-Safety Vest`) secara instan.
* **Analisis Kepatuhan:** Menyediakan data objektif bagi manajemen HSE untuk evaluasi kepatuhan standar keselamatan lapangan.

## 🚀 Fitur Utama
* Deteksi multi-kelas: `Person`, `Hardhat`, `Safety Vest`, `Gloves`, dan `Mask`.
* Deteksi label negatif: Mengidentifikasi secara spesifik objek yang hilang/tidak dipakai.
* Inference cepat pada video resolusi tinggi menggunakan arsitektur YOLOv8.

## 📊 Hasil Pelatihan (Training Results)
Model dilatih selama **50 Epoch** dengan hasil yang stabil:
* **mAP50:** Menunjukkan tren kenaikan yang konsisten hingga mencapai ~0.55.
* **Loss:** Penurunan signifikan pada *Box Loss* dan *Class Loss*, menandakan model belajar dengan baik tanpa overfitting.

## 💻 Cara Penggunaan (Inference)

```python
from ultralytics import YOLO

# Load model terbaik hasil training
model = YOLO('weights/best.pt')

# Jalankan deteksi pada file video
results = model.predict(source='video_input.mp4', save=True, conf=0.25)

🛠️ Tech Stack
Language: Python

Framework: Ultralytics YOLOv8

Dataset: Roboflow Universe (PPE Dataset)

Tools: Google Colab (GPU Training), PyTorch, Matplotlib

📝 Kesimpulan
Proyek ini membuktikan potensi besar Computer Vision dalam mendukung target Zero Accident di sektor konstruksi dan manufaktur dengan sistem pemantauan yang efisien dan objektif.

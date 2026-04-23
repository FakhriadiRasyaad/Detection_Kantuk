🚗 Deteksi Kantuk Pengemudi (YOLOv8)
Proyek ini bertujuan untuk membangun sistem deteksi objek berbasis Deep Learning untuk mengenali tanda-tanda kantuk pada pengemudi secara real-time. Model ini dilatih menggunakan arsitektur YOLOv8 untuk mendeteksi berbagai kondisi wajah dan posisi kepala yang mengindikasikan kelelahan.

📊 Detail Dataset
Dataset yang digunakan dalam pelatihan ini mencakup 6 kelas klasifikasi:

kepala_miring (Indikasi tertidur)

kepala_tegak (Kondisi waspada)

mata_close (Mata tertutup)

mata_open (Mata terbuka)

mulut_close (Mulut tertutup)

mulut_open (Menguap)

Statistik Data:

Total Gambar Training: 1755 gambar

Total Gambar Validasi: 752 gambar

🛠️ Konfigurasi Pelatihan
Model dilatih menggunakan varian YOLOv8 Nano (yolov8n.pt) agar tetap ringan saat diimplementasikan pada perangkat CPU atau embedded device (seperti Raspberry Pi).

Parameter Training:

Epochs: 25

Image Size: 640x640

Batch Size: 16

Optimizer: AdamW

Augmentasi: Mosaic (1.0), Flip Horizontal (0.5), HSV Saturation/Value adjustments.

🚀 Alur Kerja (Workflow)
Instalasi & Persiapan: Instalasi ultralytics dan onnx, serta menghubungkan Google Drive untuk penyimpanan dataset.

Pre-processing: Skrip secara otomatis memperbaiki path pada file data.yaml agar sesuai dengan lingkungan runtime Google Colab.

Training: Menjalankan proses pelatihan dengan model YOLOv8n.

Evaluasi: Mengukur performa model menggunakan metrik mAP50, mAP50-95, serta visualisasi Confusion Matrix dan F1 Curve.

Inference: Pengujian model pada gambar validasi untuk memverifikasi hasil deteksi.

Export Model: Konversi model hasil pelatihan (best.pt) ke format lain untuk deployment.

📦 Hasil Akhir & Export
Model yang telah dilatih diekspor ke berbagai format untuk target perangkat yang berbeda:

ONNX: Laptop CPU / Mini PC / RPi

TFLite: Raspberry Pi 4/5

OpenVINO: Intel iGPU / Laptop Intel

TorchScript: Backup untuk Laptop/Desktop

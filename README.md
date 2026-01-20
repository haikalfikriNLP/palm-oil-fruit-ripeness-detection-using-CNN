# Palm Oil Fruit Ripeness Detection using CNN

Penelitian ini berfokus pada deteksi tingkat kematangan
buah kelapa sawit menggunakan **YOLOv5s**
yang dikombinasikan dengan
**Convolutional Block Attention Module (CBAM)**,
**Transformer Refinement (TR)**,
dan **Bidirectional Feature Pyramid Network (BiFPN)**.

Sistem dirancang untuk melakukan deteksi objek
secara **real-time**
serta mengklasifikasikan tingkat kematangan
buah kelapa sawit berdasarkan citra digital.

---

## Background

Penentuan tingkat kematangan buah kelapa sawit
secara manual sangat bergantung pada pengalaman manusia
dan berpotensi menimbulkan ketidakkonsistenan penilaian.

Dengan memanfaatkan teknologi **computer vision**
dan **deep learning**,
proses deteksi kematangan buah kelapa sawit
dapat dilakukan secara otomatis,
akurat, dan efisien
guna mendukung produktivitas sektor perkebunan.

---

## Research Objectives

Tujuan dari penelitian dan pengembangan sistem ini adalah:
- Mendeteksi objek buah kelapa sawit pada citra digital
- Mengklasifikasikan tingkat kematangan buah kelapa sawit
  ke dalam beberapa kelas kematangan
- Mengembangkan model deteksi objek berbasis **YOLOv5s**
  dengan integrasi **CBAM, BiFPN, dan Transformer Refinement (TR)**
- Meningkatkan akurasi dan kualitas ekstraksi fitur
  melalui mekanisme atensi dan penggabungan fitur multi-skala
- Menghasilkan sistem deteksi berbasis deep learning
  yang mampu berjalan secara **real-time**
  untuk mendukung proses monitoring dan evaluasi panen

---

## Dataset Description

Dataset yang digunakan berupa citra buah kelapa sawit
yang telah dianotasi dalam format **YOLO**.

### Fruit Ripeness Classes
- **Unripe** – Buah mentah
- **Underripe** – Kurang matang
- **Ripe** – Matang
- **Overripe** – Terlalu matang
- **Empty Bunch** – Janjang kosong
- **Abnormal** – Buah abnormal / cacat

---

### Dataset Split

#### Data Latih (Training)
<p align="center">
  <img src="assets/training.png" width="400"/>
  <img src="assets/trainingmetric.png" width="400"/>
</p>

#### Data Validasi (Validation)
<p align="center">
  <img src="assets/validation.png" width="400"/>
  <img src="assets/validationmetric.png" width="400"/>
</p>

#### Data Uji (Testing)
<p align="center">
  <img src="assets/testing.png" width="400"/>
  <img src="assets/testingconvidence.png" width="400"/>
</p>

---

## Methodology

Penelitian ini mengusulkan pengembangan model deteksi objek
berbasis **YOLOv5s**
dengan mengintegrasikan
**CBAM**, **BiFPN**, dan **Transformer Refinement (TR)**.

CBAM digunakan untuk meningkatkan kualitas ekstraksi fitur
melalui mekanisme atensi kanal dan spasial,
sehingga model mampu memfokuskan perhatian
pada area citra yang relevan.

BiFPN diterapkan pada bagian *neck*
untuk mengoptimalkan penggabungan fitur multi-skala
secara dua arah (*top-down* dan *bottom-up*),
sehingga aliran informasi fitur menjadi lebih efektif.

Transformer Refinement (TR) digunakan
untuk menangkap hubungan global antar fitur
dan memperbaiki representasi fitur tingkat lanjut,
khususnya pada objek dengan variasi ukuran
dan tingkat kematangan yang beragam.

---

## Model Architecture

Model deteksi objek yang digunakan adalah **YOLOv5s**
yang terdiri dari tiga komponen utama:
- **Backbone** – Ekstraksi fitur
- **Neck** – Penggabungan fitur multi-skala
- **Head** – Prediksi bounding box dan kelas objek

<p align="center">
  <img src="assets/architecture.png" width="650"/>
</p>

**YOLOv5s Standar:**
Input → Backbone → Neck (FPN + PAN) → Head

**YOLOv5s + CBAM + TR + BiFPN:**
Input
→ Backbone + CBAM
→ Neck (BiFPN + Transformer Refinement)
→ Head (Deteksi Objek)


---

## Evaluation Metrics

Performa model dievaluasi menggunakan metrik:
- Precision
- Recall
- mAP@0.5
- mAP@0.5:0.95

<p align="center">
  <img src="assets/metriccurve.png" width="600"/>
</p>

---

## Results and Discussion

Hasil pengujian menunjukkan bahwa
model YOLOv5s yang diusulkan
mampu mendeteksi dan mengklasifikasikan
tingkat kematangan buah kelapa sawit
dengan baik.

Integrasi CBAM, BiFPN, dan Transformer Refinement
membantu meningkatkan kualitas ekstraksi fitur
serta kestabilan deteksi
pada berbagai kondisi citra.

---

## Application Preview

### Contoh hasil deteksi tingkat kematangan buah kelapa sawit
<p align="center">
  <img src="assets/result1.png" width="400"/>
  <img src="assets/result2.png" width="400"/>
</p>

### Contoh penerapan aplikasi berbasis Python (Anaconda)
<p align="center">
  <img src="assets/app1.png" width="300"/>
  <img src="assets/app2.png" width="300"/>
  <img src="assets/app3.png" width="300"/>
</p>

---

## Research Novelty

Penelitian ini mengusulkan **model deteksi tingkat kematangan buah kelapa sawit**
dengan mengintegrasikan **YOLOv5s, CBAM, BiFPN, dan Transformer Refinement**,
yang memungkinkan peningkatan akurasi deteksi
melalui mekanisme atensi dan penggabungan fitur multi-skala
tanpa mengorbankan efisiensi komputasi real-time.



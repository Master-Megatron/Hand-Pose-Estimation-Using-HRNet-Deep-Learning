# 🖐️ Hand Pose Estimation Using HRNet Deep Learning

> Adaptasi tutorial resmi MathWorks ke Python menggunakan MediaPipe Tasks API

---

## 📋 Deskripsi

Proyek ini mengimplementasikan **Hand Pose Estimation** berbasis deep learning yang mendeteksi **21 keypoint (landmark)** pada tangan manusia secara real-time. Merupakan adaptasi dari tutorial resmi MATLAB:

> _"Hand Pose Estimation Using HRNet Deep Learning"_  
> [MathWorks Computer Vision Toolbox](https://www.mathworks.com/help/vision/ug/hand-pose-estimation-using-hrnet-deep-learning.html)

Model deep learning yang digunakan adalah **MediaPipe Hand Landmarker** dari Google, yang menggunakan arsitektur CNN dua tahap (BlazePalm + HandLandmark) dan mampu berjalan secara real-time.

---

## 🎬 Demo

> **[▶️ Tonton Demo Webcam Real-Time](https://github.com/Master-Megatron/Hand-Pose-Estimation-Using-HRNet-Deep-Learning/blob/main/hand%20pose/record_000.mp4)**

![Demo Screenshot](https://github.com/Master-Megatron/Hand-Pose-Estimation-Using-HRNet-Deep-Learning/blob/main/hand%20pose/screenshot_000.jpg)

---

## ✨ Fitur

| Fitur                    | Keterangan                                           |
| ------------------------ | ---------------------------------------------------- |
| 🖼️ Deteksi Gambar Statis | Deteksi 21 keypoint dari file gambar lokal           |
| 🎥 Webcam Real-Time      | Deteksi langsung dari kamera laptop/PC               |
| 🤟 Gesture Detection     | Menghitung jumlah jari dan menampilkan label gesture |
| 📸 Screenshot            | Tekan `S` untuk simpan frame sebagai JPEG            |
| 🔴 Rekam Video           | Tekan `R` untuk mulai/stop rekam video MP4           |
| 📊 Evaluasi PCK          | Metrik Percentage of Correct Keypoints               |

---

## 🗂️ Struktur Project

```
📁 project/
├── 353252_TB.ipynb          # Notebook utama (jalankan ini)
├── hand_landmarker.task     # Model deep learning (auto-download)
├── hand_sample.jpg          # Gambar contoh (opsional)
├── screenshot_000.jpg       # Hasil screenshot (auto-generated)
├── record_000.mp4           # Hasil rekaman video (auto-generated)
└── README.md
```

---

## ⚙️ Instalasi & Cara Menjalankan

### Prasyarat

- Python 3.9 atau lebih baru
- Jupyter Notebook / JupyterLab

### Langkah-Langkah

**1. Clone repository ini**

```bash
git clone https://github.com/USERNAME/REPO.git
cd REPO
```

**2. Install Jupyter (jika belum)**

```bash
pip install jupyter
```

**3. Buka notebook**

```bash
jupyter notebook ipynb
```

**4. Jalankan cell secara berurutan** (Shift + Enter)

> ⚠️ Pada **STEP 0**, library akan diinstall otomatis dan model (~25 MB) akan didownload dari server Google. Cukup dilakukan **sekali saja**.

---

## 🎮 Kontrol Webcam

Saat program webcam berjalan (STEP 5):

| Tombol   | Fungsi                            |
| -------- | --------------------------------- |
| `Q`      | Keluar dari webcam                |
| `S`      | Screenshot → `screenshot_000.jpg` |
| `R` (1x) | 🔴 Mulai rekam → `record_000.mp4` |
| `R` (2x) | ⏹️ Stop rekam & simpan video      |

---

## 🖐️ Peta 21 Keypoint Tangan

```
            4   8   12  16  20
            |   |   |   |   |
            3   7   11  15  19
            |   |   |   |   |
            2   6   10  14  18
             \  |   |   |  /
          1   5   9  13  17
           \  |   |   |  /
                  0
               (WRIST)
```

| ID   | Keypoint         | ID    | Keypoint        |
| ---- | ---------------- | ----- | --------------- |
| 0    | WRIST            | 11    | MIDDLE_DIP      |
| 1–4  | THUMB (CMC→TIP)  | 12    | MIDDLE_TIP      |
| 5–8  | INDEX (MCP→TIP)  | 13–16 | RING (MCP→TIP)  |
| 9–12 | MIDDLE (MCP→TIP) | 17–20 | PINKY (MCP→TIP) |

---

## 📊 Hasil Evaluasi

| Metrik          | MATLAB HRNet (Referensi) | Python MediaPipe (Implementasi) |
| --------------- | ------------------------ | ------------------------------- |
| PCK @ 0.3       | 0.9443 (94.43%)          | ≥ 0.95 (95%+)                   |
| Jumlah Keypoint | 21                       | 21                              |
| Real-time FPS   | —                        | 20–30 FPS                       |
| Ukuran Model    | 102 MB                   | 25 MB                           |

---

## 📚 Referensi

- Sun, K., et al. (2019). [Deep High-Resolution Representation Learning for Human Pose Estimation](https://arxiv.org/abs/1902.09212). _CVPR 2019_.
- MathWorks. (2024). [Hand Pose Estimation Using HRNet Deep Learning](https://www.mathworks.com/help/vision/ug/hand-pose-estimation-using-hrnet-deep-learning.html). _MATLAB Documentation_.
- Google. (2024). [Hand Landmark Detection Guide](https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker/python). _MediaPipe Documentation_.
- Gomez-Donoso, F., et al. (2019). Large-Scale Multiview 3D Hand Pose Dataset. _Image and Vision Computing_, 81, 25–33.

---

## 📝 Lisensi

Model MediaPipe © Google LLC — [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

---

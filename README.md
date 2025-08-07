# 🎩 ML-Hat-Detection-With-API-RoboFlow

Proyek ini menggunakan **kamera webcam** dan **Roboflow API** untuk mendeteksi penggunaan **helm (hard hat)** pada manusia, dengan model deteksi berbasis YOLO yang di-host di Roboflow Universe. Kamera akan menangkap gambar setiap 3 detik dan mengirimkannya ke Roboflow untuk dianalisis, lalu menampilkan hasil deteksi secara langsung dengan OpenCV.

---

## 📦 Dependencies

Pastikan kamu menginstal library berikut:

```bash
pip install opencv-python requests
```

---

## 🔧 Konfigurasi

1. **Buat akun di Roboflow** dan pilih model dari Universe. Misalnya:
   - https://universe.roboflow.com/roboflow-universe-projects/hard-hats-fhbh5/model/6

2. **Salin API Key** dari halaman Roboflow Dashboard:
   - [https://app.roboflow.com/settings/api](https://app.roboflow.com/settings/api)

3. Masukkan ke dalam variabel `API_KEY` di dalam script Python:

```python
API_KEY = "YOUR_API_KEY"
MODEL_ID = "hard-hats-fhbh5/6"
```

---

## 🚀 Cara Menjalankan

Jalankan script Python berikut:

```python
python detect_hard_hat.py
```

> Tekan `q` di jendela kamera untuk keluar dari program.

---

## 🎥 Alur Program

1. **Buka kamera dengan OpenCV** (`cv2.VideoCapture(0)`)
2. **Ambil 1 frame setiap 3 detik**
3. **Kompres frame ke format JPG dalam memory**
4. **Kirim ke Roboflow API**
5. **Terima hasil deteksi (bounding box, class, confidence)**
6. **Gambarkan hasil ke frame**
7. **Tampilkan live feed dengan anotasi**

---

## 🧪 Contoh Hasil Deteksi

Setiap prediksi akan memberikan:

```json
{
  "class": "hardhat",
  "confidence": 0.89,
  "x": 320,
  "y": 240,
  "width": 120,
  "height": 160
}
```

---

## 📌 Catatan

- Script ini menggunakan **API Roboflow versi serverless**: `https://detect.roboflow.com`.
- Diperlukan koneksi internet untuk mengirim frame ke API.
- Kamu bisa mengatur `INTERVAL` (dalam detik) sesuai kebutuhan.

---



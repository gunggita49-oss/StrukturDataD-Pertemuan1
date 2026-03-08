# 📊 Analisis Nilai Mahasiswa

### Penjelasan Logika & Fungsi

Dokumentasi ini disusun untuk memberikan pemahaman mengenai **alur logika** dan **implementasi struktur data Array** dalam program pengolahan nilai mahasiswa menggunakan **Python di Google Colab**.

Program ini mencakup proses:

* Input data nilai
* Validasi data
* Perhitungan statistik
* Analisis kelulusan
* Visualisasi data

---

# 🛠️ 1. Persiapan Library

Langkah awal melibatkan pemanggilan pustaka eksternal untuk **efisiensi komputasi** dan **visualisasi data**.

```python
import numpy as np
import matplotlib.pyplot as plt
```

### 📚 Penjelasan Library

**NumPy (`np`)**

* Tulang punggung pengolahan data numerik
* Mengubah list menjadi **array kontigu**
* Memungkinkan **vektorisasi** sehingga perhitungan statistik lebih cepat tanpa looping manual

**Matplotlib (`plt`)**

* Library untuk **visualisasi data**
* Mengubah data statistik menjadi **grafik informatif dan mudah dipahami**

---

# 🧠 2. Bedah Fungsi `program_nilai()`

Fungsi ini merupakan **inti dari aplikasi** yang mencakup seluruh siklus data dari **input hingga output**.

---

## 📥 A. Validasi Input Data

Kompleksitas: **O(n)**

```python
for i in range(10):
    while True:
        try:
            n = float(input(f"Masukkan nilai mahasiswa ke-{i+1}: "))
            if 0 <= n <= 100:
                data_nilai.append(n)
                break
```

### Logika Program

* `for` digunakan untuk mengambil **10 data nilai**
* `while True` memastikan input terus diminta hingga valid
* `try-except` menangani kesalahan input seperti:

  * memasukkan huruf
  * format angka salah
* validasi `0 <= n <= 100` memastikan nilai berada dalam rentang yang benar

---

## ⚡ B. Komputasi Statistik dengan NumPy

```python
arr_nilai = np.array(data_nilai)

n_max = np.max(arr_nilai)
n_min = np.min(arr_nilai)
rata_rata = np.mean(arr_nilai)
```

### Penjelasan

**Efisiensi Memori**

Data dikonversi menjadi `numpy.array` sehingga disimpan pada **memori kontigu**.

**Ekstraksi Statistik**

Program menghitung:

* Nilai **maksimum**
* Nilai **minimum**
* Nilai **rata-rata**

menggunakan fungsi NumPy yang sudah **teroptimasi secara matematis**.

---

## 🔍 C. Analisis Kelulusan (Filtering)

```python
lulus = arr_nilai[arr_nilai >= 60]
jml_lulus = len(lulus)
jml_gagal = len(arr_nilai) - jml_lulus
```

### Teknik yang Digunakan

**Boolean Indexing**

Teknik filtering array menggunakan kondisi logika.

Keunggulan:

* Lebih cepat dibanding loop manual
* Langsung menyaring nilai **≥ 60** sebagai nilai lulus

---

## 📈 D. Representasi Visual

```python
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 5))
```

### Konsep Visualisasi

**Subplots Layout**

Grafik dibagi menjadi **dua panel**:

1. Statistik nilai mahasiswa
2. Distribusi kelulusan

Tujuannya agar **perbandingan data dapat terlihat secara bersamaan**.

---

# 🔬 3. Analisis Performa (Big-O Complexity)

| Komponen          | Kompleksitas | Karakteristik Struktur Data                               |
| ----------------- | ------------ | --------------------------------------------------------- |
| Akses Data        | **O(1)**     | Memori kontigu memungkinkan akses langsung melalui indeks |
| Input & Statistik | **O(n)**     | Setiap elemen array diproses satu kali                    |
| Penyimpanan       | **O(n)**     | Data homogen menggunakan tipe data seragam                |

---

# 💡 Catatan Penggunaan di Google Colab

**Eksekusi**

Jalankan setiap sel kode secara **berurutan** agar variabel tetap tersimpan dalam memori runtime.

**Output Visualisasi**

Grafik akan otomatis muncul di bawah sel kode karena integrasi **Matplotlib dengan Google Colab**.

---

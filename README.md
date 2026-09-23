# Pertemuan 04 Seleksi Multi-Kondisi dan Validasi Input

**Nama:** Maila Andira Putri
**NIM:** 2225250126
**Kelas:** 3A

---

## Tujuan

Membangun program validasi dan klasifikasi nilai menggunakan struktur `if-elif-else`. Program dapat:

- Memvalidasi nilai ujian, nilai tugas, dan kehadiran.
- Menghitung nilai akhir mahasiswa.
- Menentukan predikat nilai (A–E).
- Menentukan status kelulusan berdasarkan nilai dan kehadiran.
- Menangani input yang tidak valid.

---

## Cara Menjalankan

Pastikan Python 3 telah terinstal.

Jalankan program dengan perintah:

```bash
python3 praktik/validasi_klasifikasi_nilai.py
```

atau

```bash
python validasi_klasifikasi_nilai.py
```

---

## Tabel Keputusan

| Kategori | Syarat | Contoh Masukan |
|-----------|---------|----------------|
| Error Nilai Ujian | Nilai ujian < 0 atau > 100 | 120 |
| Error Nilai Tugas | Nilai tugas < 0 atau > 100 | -5 |
| Error Kehadiran | Kehadiran < 0 atau > 100 | 150 |
| Error Input | Input bukan angka | abc |
| Predikat A | Nilai akhir ≥ 90 | Ujian 95, Tugas 90 |
| Predikat B | 80 ≤ Nilai akhir < 90 | Ujian 85, Tugas 80 |
| Predikat C | 70 ≤ Nilai akhir < 80 | Ujian 75, Tugas 70 |
| Predikat D | 60 ≤ Nilai akhir < 70 | Ujian 65, Tugas 60 |
| Predikat E | Nilai akhir < 60 | Ujian 50, Tugas 55 |
| Tidak Lulus | Kehadiran < 75% | Kehadiran 70 |
| Lulus | Nilai akhir ≥ 70 dan kehadiran ≥ 75% | Nilai akhir 83, Kehadiran 90 |

---

## Hasil Pengujian

| No | Masukan | Keluaran yang Diharapkan | Keluaran Aktual | Status |
|----|----------|-------------------------|----------------|---------|
| 1 | Ujian=95, Tugas=90, Hadir=90 | Predikat A, Lulus | Predikat A, Lulus | Berhasil |
| 2 | Ujian=85, Tugas=80, Hadir=90 | Predikat B, Lulus | Predikat B, Lulus | Berhasil |
| 3 | Ujian=75, Tugas=70, Hadir=80 | Predikat C, Lulus | Predikat C, Lulus | Berhasil |
| 4 | Ujian=65, Tugas=60, Hadir=85 | Predikat D, Tidak Lulus | Predikat D, Tidak Lulus | Berhasil |
| 5 | Ujian=50, Tugas=55, Hadir=90 | Predikat E, Tidak Lulus | Predikat E, Tidak Lulus | Berhasil |
| 6 | Ujian=90, Tugas=85, Hadir=70 | Tidak Lulus karena kehadiran | Tidak Lulus karena kehadiran | Berhasil |
| 7 | Ujian=120, Tugas=80, Hadir=90 | Pesan error validasi | Pesan error validasi | Berhasil |
| 8 | Ujian=abc, Tugas=80, Hadir=90 | Pesan error input angka | Pesan error input angka | Berhasil |

---

## Refleksi

Saat melakukan pengujian, ditemukan bahwa program belum menangani masukan berupa teks seperti:

```
abc
```

Jika langsung dikonversi ke tipe data numerik, program akan menghasilkan error. Untuk mengatasi masalah tersebut digunakan blok `try-except` sehingga program dapat menampilkan pesan kesalahan yang lebih jelas kepada pengguna.

Selain itu dilakukan validasi rentang nilai agar nilai ujian, nilai tugas, dan kehadiran hanya dapat berada pada rentang 0–100.

---

## Kesimpulan

Program berhasil menerapkan struktur `if-elif-else` untuk melakukan validasi data, menghitung nilai akhir, menentukan predikat, dan menentukan status kelulusan mahasiswa. Program juga mampu menangani berbagai masukan tidak valid sehingga lebih aman digunakan.
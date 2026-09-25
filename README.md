# Pertemuan 04 Seleksi Multi-Kondisi dan Validasi Input

Nama: Farid Ardiansah
NIM: 2225250125
Kelas: 3E

## Tujuan

Membangun program validasi dan klasifikasi menggunakan rantai `if-elif-else`, serta memahami penggunaan validasi tipe data, validasi rentang, dan kondisi multi-cabang dalam Python.

## Cara Menjalankan

Program dapat dijalankan melalui terminal dengan perintah:

```bash
python3 praktik/validasi_klasifikasi_nilai.py
```

## Tabel Keputusan

| Kategori                        | Syarat                               | Contoh Masukan                    |
| ------------------------------- | ------------------------------------ | --------------------------------- |
| Predikat A                      | Nilai akhir ≥ 85 dan kehadiran ≥ 80% | Ujian 90, Tugas 80, Kehadiran 95  |
| Predikat B                      | Nilai akhir ≥ 70 dan kehadiran ≥ 80% | Ujian 75, Tugas 70, Kehadiran 85  |
| Predikat C                      | Nilai akhir ≥ 60 dan kehadiran ≥ 80% | Ujian 60, Tugas 60, Kehadiran 80  |
| Predikat D                      | Nilai akhir ≥ 50 dan kehadiran ≥ 80% | Ujian 55, Tugas 50, Kehadiran 90  |
| Predikat E                      | Nilai akhir < 50 dan kehadiran ≥ 80% | Ujian 40, Tugas 30, Kehadiran 100 |
| Tidak memenuhi syarat kehadiran | Kehadiran < 80%                      | Ujian 90, Tugas 90, Kehadiran 75  |
| Penolakan nilai ujian           | Nilai ujian < 0 atau > 100           | Ujian 105                         |
| Penolakan nilai tugas           | Nilai tugas < 0 atau > 100           | Tugas -5                          |
| Penolakan tipe                  | Salah satu masukan bukan angka       | Kehadiran `abc`                   |

## Hasil Pengujian

| No. | Masukan     | Keluaran yang Diharapkan                           | Keluaran Aktual                                    | Status   |
| --- | ----------- | -------------------------------------------------- | -------------------------------------------------- | -------- |
| 1   | 90, 80, 95  | Nilai akhir 86.00, Predikat A, Lulus               | Nilai akhir 86.00, Predikat A, Lulus               | Berhasil |
| 2   | 75, 70, 85  | Nilai akhir 73.00, Predikat B, Lulus               | Nilai akhir 73.00, Predikat B, Lulus               | Berhasil |
| 3   | 60, 60, 80  | Nilai akhir 60.00, Predikat C, Lulus               | Nilai akhir 60.00, Predikat C, Lulus               | Berhasil |
| 4   | 55, 50, 90  | Nilai akhir 53.00, Predikat D, Belum lulus         | Nilai akhir 53.00, Predikat D, Belum lulus         | Berhasil |
| 5   | 40, 30, 100 | Nilai akhir 36.00, Predikat E, Belum lulus         | Nilai akhir 36.00, Predikat E, Belum lulus         | Berhasil |
| 6   | 90, 90, 75  | Nilai akhir 90.00, Tidak memenuhi syarat kehadiran | Nilai akhir 90.00, Tidak memenuhi syarat kehadiran | Berhasil |
| 7   | 105, 80, 90 | Penolakan rentang nilai ujian                      | Penolakan rentang nilai ujian                      | Berhasil |
| 8   | 80, -5, 90  | Penolakan rentang nilai tugas                      | Penolakan rentang nilai tugas                      | Berhasil |
| 9   | 80, 80, abc | Penolakan tipe                                     | Penolakan tipe                                     | Berhasil |

## Refleksi

Salah satu masukan tidak valid yang perlu diperhatikan adalah ketika pengguna memasukkan teks, misalnya `abc`, pada bagian nilai atau kehadiran. Jika langsung menggunakan `float()` tanpa penanganan, program akan mengalami error. Masukan tersebut ditangani menggunakan `try-except` sehingga program dapat menampilkan pesan **"Masukan ditolak: seluruh data harus berupa angka."** Selain itu, program juga memvalidasi rentang nilai agar data yang kurang dari 0 atau lebih dari 100 tidak diproses.

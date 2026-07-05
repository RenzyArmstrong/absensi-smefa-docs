# Peran & Hak Akses

Sistem memakai empat peran dengan hak bertingkat, mengikuti prinsip hak seminimal yang diperlukan: tiap peran hanya bisa melakukan yang jadi tugasnya.

```
siswa  ⊂  guru  ⊂  guru BK     — peran di aplikasi
Admin                          — pengelola panel web
```

## Matriks hak akses

| Kemampuan | Siswa | Guru | Guru BK | Admin |
|---|:---:|:---:|:---:|:---:|
| Absen wajah masuk/pulang | ✅ | — | — | — |
| Ajukan izin | ✅ | — | — | — |
| Lihat riwayat & telat sendiri | ✅ | — | — | — |
| Pantau kehadiran semua kelas | — | ✅ | ✅ | ✅ |
| Beri catatan pada absensi siswa | — | ✅ | ✅ | ✅ |
| Setujui / tolak izin | — | — | ✅ | ✅ |
| Reset data wajah siswa | — | — | ✅ | ✅ |
| Ekspor absensi & izin | — | — | ✅ | ✅ |
| Kelola data siswa & reset PIN | — | — | — | ✅ |
| Rekap bulanan & monitoring | — | — | — | ✅ |
| Atur aplikasi, geofence, jam | — | — | — | ✅ |
| Kelola akun guru (aplikasi) | — | — | — | ✅ |
| Rilis/upload versi aplikasi | — | — | — | ✅ |
| Pemeliharaan & audit log | — | — | — | ✅ |

## Siswa

Pengguna dasar, hanya melayani dirinya sendiri:

- Absen wajah masuk dan pulang (dengan liveness anti-foto dan geofence, atau mode PKL tanpa geofence).
- Mengajukan izin (sakit/keperluan) beserta foto bukti.
- Melihat riwayat kehadiran dan menit keterlambatan miliknya sendiri.

Siswa tidak bisa melihat data siswa lain.

## Guru (guru mapel)

Guru mata pelajaran tidak absen, hanya memantau:

- Dashboard daftar semua kelas dan siswa dengan dropdown kelas dan paginasi.
- Tab Hari Ini — status kehadiran tiap siswa (hadir/izin/alfa/belum) dan menit telat.
- Tab Rekap Bulan Ini — per siswa: jumlah hadir, telat (×N + total menit), izin, alfa.
- Memberi catatan bila siswa hadir tapi tidak masuk pelajaran, lewat preset ("Izin Ambil Barang", "Izin ke UKS", "Dipanggil Guru/BK", "Tugas/Kegiatan Sekolah") atau ketik sendiri.

Secara teknis guru hanya bisa menulis kolom catatan. Ia tidak bisa mengubah kehadiran, jam, status telat, membuat, atau menghapus data absensi — dijamin oleh aturan di server, bukan sekadar disembunyikan di UI.

## Guru BK

Semua yang guru bisa, ditambah wewenang bimbingan konseling:

- Setujui atau tolak pengajuan izin siswa.
- Reset data wajah siswa (ganti HP / wajah salah) supaya siswa daftar ulang.
- Ekspor rekap absensi dan izin (CSV).
- Peringatan otomatis bila siswa Alfa tiga hari berturut-turut.

## Admin (panel web)

Pengelola sistem lewat browser, dengan akses penuh ke panel:

- Kelola data siswa (tambah/hapus/reset PIN), lihat dan kelola absensi serta izin.
- Rekap bulanan per kelas dan monitoring layanan.
- Atur aplikasi dan geofence (jam masuk, batas alfa, titik/radius sekolah, mode pemeliharaan, versi).
- Kelola akun guru aplikasi, rilis versi aplikasi, pemeliharaan data, dan audit log.

Kredensial admin disimpan terpisah dari basis data.

---

[Kembali ke README](../README.md) · [Diagram alur](FLOWCHARTS.md)

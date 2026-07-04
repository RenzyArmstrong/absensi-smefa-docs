# 🔐 Peran & Hak Akses

Sistem memakai **5 peran** dengan hak yang bertingkat. Prinsipnya: **hak seminimal yang diperlukan** (least privilege), dan tiap peran hanya bisa melakukan yang menjadi tugasnya.

```
siswa  ⊂  guru  ⊂  guru_bk        (peran di APLIKASI)
                     admin  ⊂  super admin   (peran di PANEL WEB)
```

## 👤 Matriks Hak Akses

| Kemampuan | Siswa | Guru | Guru BK | Admin | Super Admin |
|---|:---:|:---:|:---:|:---:|:---:|
| Absen wajah masuk/pulang | ✅ | — | — | — | — |
| Ajukan izin | ✅ | — | — | — | — |
| Lihat riwayat & telat sendiri | ✅ | — | — | — | — |
| Pantau kehadiran semua kelas | — | ✅ | ✅ | ✅ | ✅ |
| Beri catatan pada absensi siswa | — | ✅ | ✅ | ✅ | ✅ |
| Setujui / tolak izin | — | — | ✅ | ✅ | ✅ |
| Reset data wajah siswa | — | — | ✅ | ✅ | ✅ |
| Ekspor absensi & izin | — | — | ✅ | ✅ | ✅ |
| Kelola data siswa & reset PIN | — | — | — | ✅ | ✅ |
| Rekap bulanan & monitoring | — | — | — | ✅ | ✅ |
| Atur aplikasi, geofence, jam | — | — | — | ✅ | ✅ |
| Kelola akun guru (aplikasi) | — | — | — | ✅ | ✅ |
| Rilis/upload versi aplikasi | — | — | — | ✅ | ✅ |
| Pemeliharaan & audit log | — | — | — | ✅ | ✅ |
| **Kelola akun panel (admin lain)** | — | — | — | **❌** | ✅ |

> Perbedaan **admin** vs **super admin** hanya satu: **hanya super admin** yang boleh membuat/menghapus akun panel lain. Ini mencegah seorang admin mengangkat dirinya atau orang lain menjadi admin (anti eskalasi hak).

## 🧑‍🎓 Siswa

Pengguna dasar. Hanya melayani dirinya sendiri:

- Absen wajah **masuk** dan **pulang** (dengan liveness anti-foto + geofence, atau mode PKL tanpa geofence).
- Mengajukan **izin** (sakit/keperluan) beserta foto bukti.
- Melihat **riwayat kehadiran** dan **menit keterlambatan** miliknya sendiri.

Siswa **tidak** bisa melihat data siswa lain.

## 🧑‍🏫 Guru (guru mapel)

Guru mata pelajaran. **Tidak absen** — hanya **memantau**:

- Dashboard **daftar semua kelas & siswa** dengan **dropdown kelas** dan **paginasi**.
- **Hari Ini** — **status kehadiran** tiap siswa (hadir/izin/alfa/belum) + **menit telat**.
- **Rekap Bulan Ini** — per siswa: jumlah hadir, telat (×N + total menit), izin, alfa — langsung di aplikasi.
- Memberi **catatan** bila siswa hadir tapi tidak masuk pelajaran — pilihan **preset** (mis. "Izin Ambil Barang", "Izin ke UKS", "Dipanggil Guru/BK", "Tugas/Kegiatan Sekolah") atau **ketik sendiri**.

> 🔒 Secara teknis, guru **hanya** dapat menulis kolom *catatan*. Ia **tidak bisa** mengubah kehadiran, jam, status telat, membuat, atau menghapus data absensi — dijamin oleh aturan di server, bukan sekadar disembunyikan di UI.

## 🧑‍⚕️ Guru BK

Semua yang guru bisa, **ditambah** wewenang bimbingan konseling:

- **Setujui / tolak** pengajuan izin siswa.
- **Reset data wajah** siswa (ganti HP / wajah salah) → siswa daftar ulang otomatis.
- **Ekspor** rekap absensi & izin (CSV).
- Peringatan otomatis bila siswa **Alfa 3 hari berturut-turut**.

## 🛠️ Admin (panel web)

Pengelola harian lewat browser. Hampir setara super admin:

- Kelola **data siswa** (tambah/hapus/reset PIN), lihat & kelola **absensi** dan **izin**.
- **Rekap bulanan** per kelas + **monitoring** layanan.
- Atur **aplikasi & geofence** (jam masuk, batas alfa, titik/radius sekolah, mode pemeliharaan, versi).
- Kelola **akun guru** aplikasi, **rilis** versi aplikasi, **pemeliharaan data** & **audit log**.

## 👑 Super Admin (panel web)

Pemegang tertinggi. Semua yang admin bisa **plus** satu-satunya yang boleh **mengelola akun panel** (membuat/menghapus admin lain). Kredensial super admin disimpan terpisah dari basis data.

---

[⬅️ Kembali ke README](../README.md) · [Lihat diagram alur ➡️](FLOWCHARTS.md)

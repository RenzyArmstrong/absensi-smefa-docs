# Diagram Alur

Panduan langkah demi langkah ada di [Panduan Penggunaan](PANDUAN.md). Halaman ini kumpulan diagram alur sistem.

## Alur absensi siswa

Proses absen harian, dari login sampai kehadiran tersimpan:

![Alur absen harian siswa: login, cek lokasi, verifikasi wajah, status Hadir/Telat/Alfa, tersimpan](assets/alur-absensi.svg)

Alur pertama kali, dilakukan sekali saat mulai pakai:

![Alur pertama kali siswa: login, lengkapi data dan ganti PIN, daftar wajah, absen masuk pertama](assets/alur-pertama-kali.svg)

---

## Diagram rinci

Diagram di bawah memakai Mermaid dan otomatis tampil sebagai gambar saat dibuka di GitHub.

---

## 1. Login & Pengarahan Peran

Saat login, sistem mengarahkan pengguna ke tampilan sesuai perannya. Guru & BK **tidak** melewati absen wajah.

```mermaid
flowchart TD
    A([Buka Aplikasi]) --> B[Masukkan Username/NISN + PIN]
    B --> C{Kredensial valid?}
    C -- Tidak --> B
    C -- Ya --> D{Peran?}
    D -- siswa --> E{Sudah absen hari ini?}
    E -- Belum --> F[Layar Absen Wajah]
    E -- Sudah --> G[Dashboard Siswa]
    D -- guru --> H[Dashboard Guru: pantau + catatan]
    D -- guru_bk --> I[Dashboard BK: pantau + catatan + izin + wajah + ekspor]
```

## 2. Absen Wajah (Masuk)

Absen hanya berhasil bila **wajah hidup terverifikasi** dan **posisi di area sekolah** (kecuali siswa PKL).

```mermaid
flowchart TD
    A([Mulai Absen]) --> B{Siswa PKL?}
    B -- Ya --> D[Lewati cek lokasi]
    B -- Tidak --> C{Di dalam area sekolah?}
    C -- Tidak --> X[Tolak: di luar area]
    C -- Ya --> D
    D --> E[Deteksi wajah + minta kedip/gerak]
    E --> F{Liveness lolos? Anti-foto}
    F -- Tidak --> X2[Tolak: wajah tidak hidup]
    F -- Ya --> G{Wajah cocok dgn data siswa?}
    G -- Tidak --> X3[Tolak: wajah tidak dikenal]
    G -- Ya --> H[Ambil foto bukti + waktu server]
    H --> I{Jam server vs jam masuk & batas alfa}
    I -- "sebelum jam masuk" --> J[Status: Hadir]
    I -- "antara jam masuk & batas alfa" --> K[Status: Hadir + Telat X menit]
    I -- "lewat batas alfa" --> L[Status: Alfa otomatis]
    J --> M[(Simpan absensi)]
    K --> M
    L --> M
```

## 3. Perhitungan Telat & Alfa

Waktu selalu diambil dari **jam server** (bukan jam HP) supaya tidak bisa dicurangi.

```mermaid
flowchart LR
    A[Waktu absen server] --> B{Bandingkan}
    B -- "≤ Jam Masuk (mis. 07:15)" --> H[Hadir]
    B -- "> Jam Masuk & ≤ Batas Alfa" --> T["Hadir + Telat<br/>(selisih menit dicatat)"]
    B -- "> Batas Alfa (mis. 08:00)" --> AL[Alfa otomatis]
    T --> R[Rekap: total menit telat<br/>dijumlah sebulan]
```

## 4. Alur Izin

Siswa mengajukan izin; Guru BK/Admin menyetujui atau menolak.

```mermaid
flowchart TD
    A([Siswa ajukan izin]) --> B[Isi alasan + foto bukti]
    B --> C[(Izin: status Pending)]
    C --> D{Guru BK / Admin}
    D -- Setujui --> E[Absensi hari itu jadi Izin]
    D -- Tolak --> F[Izin ditolak]
    E --> G[Notifikasi ke siswa]
    F --> G
```

## 5. Catatan Guru (siswa hadir tapi keluar kelas)

```mermaid
flowchart TD
    A([Guru buka dashboard]) --> B[Pilih kelas via dropdown]
    B --> C[Lihat daftar siswa + status hari ini]
    C --> D{Siswa hadir tapi tidak ikut pelajaran?}
    D -- Ya --> E[Ketuk Catatan]
    E --> F[Pilih preset atau ketik sendiri]
    F --> G[(Simpan ke kolom catatan absensi)]
    D -- Tidak --> C
```

## 6. Alfa Otomatis & Notifikasi WhatsApp

Di akhir hari, siswa yang tidak absen (dan tidak izin) otomatis ditandai Alfa; orang tua dikabari.

```mermaid
flowchart TD
    A([Jadwal akhir hari - server]) --> B[Cek tiap siswa]
    B --> C{Sudah ada absensi hari ini?}
    C -- Ya --> Z[Lewati]
    C -- Tidak --> D{Sedang izin?}
    D -- Ya --> Z
    D -- Tidak --> E{Siswa PKL?}
    E -- Ya --> Z
    E -- Tidak --> F[Tandai Alfa]
    F --> G[Kirim notifikasi WhatsApp ke wali]
    F --> H{Alfa 3 hari beruntun?}
    H -- Ya --> I[Peringatan ke Guru BK]
```

## 7. Hierarki Peran & Hak

```mermaid
flowchart TD
    S[Siswa<br/>absen · izin · lihat sendiri]
    G[Guru<br/>+ pantau kelas + catatan]
    BK[Guru BK<br/>+ approve izin + reset wajah + ekspor]
    AD[Admin<br/>kelola semua panel]
    SA[Super Admin<br/>+ kelola akun panel]

    S --> G --> BK
    AD --> SA
    BK -.->|peran aplikasi| S
    AD -.->|peran panel web| SA
```

---

[⬅️ Peran & Hak Akses](ROLES.md) · [Arsitektur ➡️](ARCHITECTURE.md)

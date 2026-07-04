# 🛡️ Keamanan (Tingkat Tinggi)

Ringkasan prinsip keamanan. **Tidak** memuat kunci, kredensial, URL, atau detail yang bisa disalahgunakan.

## Prinsip Utama

1. **Aturan ditegakkan di server, bukan di UI.** Menyembunyikan tombol tidaklah cukup — setiap peran dibatasi oleh aturan akses di basis data. Contoh: guru **hanya** bisa menulis kolom *catatan*; ia tak bisa mengubah kehadiran walau memakai alat lain.
2. **Hak seminimal mungkin (least privilege).** Tiap peran hanya diberi yang menjadi tugasnya. Lihat [Peran & Hak Akses](ROLES.md).
3. **Waktu tepercaya dari server.** Tanggal & jam absensi diambil dari server (WIB), bukan jam HP → mencegah backdate & manipulasi telat.

## Perlindungan Kecurangan Absen

- **Liveness wajah** (kedip/gerak) → menolak foto/gambar diam.
- **Geofence** → absen hanya di area sekolah (kecuali mode PKL yang memang jarak jauh).
- **Anti mock-GPS** → lokasi palsu terdeteksi & ditolak.
- **Pendaftaran wajah tersupervisi** → siswa hanya bisa mendaftarkan wajah saat guru membukanya (sekali pakai), mencegah pembajakan identitas.
- **Kunci field absensi** → siswa hanya boleh mengubah field yang wajar; sisanya terkunci.

## Perlindungan Data & Privasi

- **Koordinat lokasi tidak pernah disimpan/ditampilkan** — hanya label "di dalam/di luar area".
- **Wajah disimpan sebagai representasi matematis**, bukan foto untuk pencocokan; verifikasi di perangkat.
- **Foto bukti terlindungi** — hanya dapat diakses lewat proxy panel yang terautentikasi.
- **Penyimpanan terenkripsi** di perangkat (AES-256-GCM) untuk token sesi.

## Perlindungan Aplikasi & Panel

- **Anti-bongkar (anti-decrypt):** kode aplikasi rilis di-obfuscate (R8); URL/konfigurasi sensitif tidak tersimpan sebagai teks polos → tetap aman walau aplikasi dibongkar.
- **Anti-tangkap layar & anti-debug** pada layar sensitif.
- **Panel:** CSP ketat berbasis nonce, proteksi CSRF, rate-limiting, sesi aman (anti session-fixation), dan **audit log** aktivitas.
- **Pemisahan kredensial:** akun super admin disimpan terpisah dari basis data.
- **Infrastruktur disembunyikan** di balik terowongan aman (tanpa membuka port publik).

## Operasional

- **Backup terjadwal** (server harian + salinan offsite) dengan prosedur pemulihan.
- **Healthcheck** tiap 5 menit → peringatan otomatis bila layanan mati.

> Dokumen ini sengaja tidak menyebutkan endpoint, domain, path, nomor, atau kunci apa pun.

---

[⬅️ Fitur](FEATURES.md) · [Kembali ke README](../README.md)

# 📚 SMEFA Absence — Dokumentasi

Dokumentasi resmi **SMEFA Absence**, sistem absensi sekolah berbasis **pengenalan wajah + geofence**, dengan **panel admin web** dan **notifikasi WhatsApp**. Dibuat untuk **SMK YP Fatahillah 2 · Cilegon**.

> ⚠️ **Repo ini hanya DOKUMENTASI** — bukan kode sumber aplikasi. Tidak berisi kunci, kredensial, URL server, atau logika keamanan apa pun.

---

## 🎯 Ringkasan

SMEFA Absence menggantikan absensi manual dengan alur digital yang cepat, sulit dicurangi, dan mudah dipantau:

- Siswa **absen dengan wajah** (deteksi kedip/liveness → anti foto) hanya bila berada **di area sekolah** (geofence). Siswa **PKL** absen tanpa geofence.
- Absen **masuk & pulang** terekam beserta **foto bukti** dan **status telat** (dihitung dari jam server, anti ubah jam HP).
- **Guru** memantau kehadiran per kelas dan memberi **catatan**; **Guru BK** menyetujui izin, mengelola wajah, dan ekspor data.
- **Admin** mengelola semua lewat panel web; **notifikasi WhatsApp** otomatis mengabari orang tua saat anak Alfa.

## 🧩 Komponen Sistem

| Komponen | Peran | Teknologi |
|---|---|---|
| **Aplikasi Android** | Absen wajah siswa, dashboard guru & BK | Kotlin · Jetpack Compose |
| **Backend** | Basis data, aturan akses, hook otomatis | PocketBase (Go/SQLite) |
| **Panel Admin** | Kelola siswa, absensi, rekap, konfigurasi | Go + Vue 3 SPA (Vite · Naive UI) |
| **Gateway WhatsApp** | Kirim notifikasi otomatis | Node.js (Baileys) |

Semuanya **self-hosted** di server sekolah dan diakses lewat terowongan aman (Cloudflare Tunnel). Detail infrastruktur sengaja tidak dipublikasikan demi keamanan.

## 📖 Daftar Dokumen

| Dokumen | Isi |
|---|---|
| [Arsitektur](docs/ARCHITECTURE.md) | Gambaran komponen & aliran data |
| [Peran & Hak Akses](docs/ROLES.md) | Matriks lengkap siswa · guru · guru BK · admin · super admin |
| [Diagram Alur](docs/FLOWCHARTS.md) | Flowchart login, absen, izin, telat/alfa, hak akses |
| [Fitur](docs/FEATURES.md) | Daftar fitur per peran |
| [Keamanan](docs/SECURITY.md) | Prinsip & lapisan keamanan (tingkat tinggi) |

## 👥 Kredit

- **Sandi Maulana Akbar** — Software Developer · Administrator · UI/UX
- **Pa Angga** — Administrator · Konseptor
- **SMK YP Fatahillah 2** — © 2025–2026

---

<sub>Dokumentasi ini bebas dibaca. Kode sumber, kredensial, dan konfigurasi server tidak disertakan.</sub>

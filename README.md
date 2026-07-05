# SMEFA Absence — Dokumentasi

Dokumentasi SMEFA Absence, sistem absensi sekolah berbasis pengenalan wajah dan geofence, dengan panel admin web dan notifikasi WhatsApp. Dibuat untuk SMK YP Fatahillah 2 Cilegon.

Repo ini hanya berisi dokumentasi, bukan kode sumber aplikasi. Tidak ada kunci, kredensial, URL server, maupun logika keamanan di sini.

## Ringkasan

SMEFA Absence menggantikan absensi manual dengan alur digital yang cepat dan sulit dicurangi:

- Siswa absen dengan wajah (dengan deteksi kedip supaya foto tidak bisa dipakai) dan hanya bila berada di area sekolah. Siswa PKL absen tanpa geofence.
- Absen masuk dan pulang terekam beserta foto bukti dan status telat. Telat dihitung dari jam server, jadi jam HP tidak bisa diakali.
- Guru memantau kehadiran per kelas dan memberi catatan. Guru BK menyetujui izin, mengelola data wajah, dan mengekspor data.
- Admin mengelola semuanya lewat panel web. Orang tua otomatis dikabari lewat WhatsApp saat anaknya Alfa.

## Komponen sistem

| Komponen | Peran | Teknologi |
|---|---|---|
| Aplikasi Android | Absen wajah siswa, dashboard guru & BK | Kotlin, Jetpack Compose |
| Backend | Basis data, aturan akses, otomasi | PocketBase (Go/SQLite) |
| Panel admin | Kelola siswa, absensi, rekap, konfigurasi | Go + Vue 3 (Naive UI) |
| Gateway WhatsApp | Notifikasi otomatis | Node.js (Baileys) |

Semuanya self-hosted di server sekolah dan diakses lewat Cloudflare Tunnel. Detail infrastruktur sengaja tidak dipublikasikan.

## Daftar dokumen

| Dokumen | Isi |
|---|---|
| [Panduan Penggunaan](docs/PANDUAN.md) | Cara pakai dari nol untuk siswa, guru, dan guru BK |
| [Peran & Hak Akses](docs/ROLES.md) | Matriks hak akses siswa, guru, guru BK, admin, super admin |
| [Diagram Alur](docs/FLOWCHARTS.md) | Flowchart login, absen, izin, telat/alfa |
| [Fitur](docs/FEATURES.md) | Daftar fitur per peran |
| [Arsitektur](docs/ARCHITECTURE.md) | Gambaran komponen dan aliran data |
| [Keamanan](docs/SECURITY.md) | Prinsip dan lapisan keamanan |

## Kredit

- Sandi Maulana Akbar — Software Developer, Administrator, UI/UX
- Pa Angga — Administrator, Konseptor
- SMK YP Fatahillah 2 — © 2025–2026

---

<sub>Dokumentasi ini bebas dibaca. Kode sumber, kredensial, dan konfigurasi server tidak disertakan.</sub>

# ✨ Fitur

## Untuk Siswa
- **Absen wajah** masuk & pulang dengan **liveness** (kedip/gerak) → anti foto.
- **Geofence** — hanya bisa absen di area sekolah. **Siswa PKL** absen jarak jauh tanpa geofence.
- **Foto bukti** otomatis tiap absen masuk & pulang.
- **Pulang Izin** — absen pulang lebih awal dengan alasan + foto bukti.
- **Ajukan izin** (sakit/keperluan) langsung dari aplikasi.
- **Riwayat & keterlambatan** pribadi, lengkap dengan **menit telat** ("⏰ Telat 20 menit").
- **Pengingat** absen harian.

## Untuk Guru
- **Dashboard pantau** semua kelas & siswa dengan **dropdown kelas** + **paginasi**.
- Dua tampilan: **Hari Ini** (status tiap siswa + chip menit telat) dan **Rekap Bulan Ini** (per siswa: hadir, telat ×N + total menit, izin, alfa).
- **Catatan** cepat (preset) atau bebas untuk siswa yang hadir tapi keluar kelas.

## Untuk Guru BK
- Semua fitur guru, **plus**:
- **Setujui / tolak izin** siswa.
- **Reset data wajah** siswa.
- **Ekspor** absensi & izin (CSV).
- **Peringatan Alfa 3 hari** beruntun.

## Untuk Admin / Super Admin (Panel Web)
- **Dashboard** ringkasan kehadiran harian.
- **Data siswa** — tabel, cari, tambah/impor, hapus, reset PIN, kelola per kelas.
- **Absensi** — riwayat masuk & pulang + **foto** + status **telat/alfa** (muat otomatis hari ini).
- **Perizinan** — tinjau & setujui izin beserta bukti.
- **Rekap bulanan** per kelas — hadir, telat, **total menit telat**, izin, alfa; ekspor CSV.
- **Hari libur** — kalender libur sekolah.
- **Pengaturan** — jam masuk, **batas alfa**, geofence (titik/radius), ambang wajah, mode pemeliharaan, versi.
- **Akun guru** — kelola akun guru aplikasi.
- **Kelola wajah per kelas**, **pendaftaran wajah tersupervisi** (anti pembajakan identitas).
- **Rilis aplikasi** — unggah & publikasikan versi baru (opsional/wajib).
- **Monitoring** layanan + **audit log** aktivitas panel.
- **Akun panel** *(super admin saja)* — kelola admin lain.

## Otomatisasi Server
- **Telat & Alfa otomatis** dari jam server.
- **Auto-Alfa** akhir hari (mengecualikan yang izin & siswa PKL).
- **Notifikasi WhatsApp** otomatis ke wali.
- **Backup** terjadwal (server harian + offsite) & **healthcheck** tiap 5 menit.

---

[⬅️ Arsitektur](ARCHITECTURE.md) · [Keamanan ➡️](SECURITY.md)

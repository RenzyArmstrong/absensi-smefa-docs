# Panduan Penggunaan — SMEFA Absence

Panduan pemakaian aplikasi absensi SMEFA Absence di SMK YP Fatahillah 2 Cilegon. Aplikasi memakai verifikasi wajah dan penguncian lokasi sekolah supaya absensi tidak bisa dititipkan. Pilih bagian sesuai peran kamu:

- [Siswa](#siswa)
- [Guru](#guru)
- [Guru BK](#guru-bk)
- [Status kehadiran & istilah](#status-kehadiran--istilah)
- [Pertanyaan umum](#pertanyaan-umum)

## Alur singkat

Dua diagram di bawah: alur pertama kali (dilakukan sekali saat mulai pakai) dan alur absen harian.

![Alur pertama kali siswa: login, lengkapi data & ganti PIN, daftar wajah, absen masuk pertama](assets/alur-pertama-kali.svg)

![Alur absen harian siswa: login, cek lokasi, verifikasi wajah, status Hadir/Telat/Alfa, tersimpan](assets/alur-absensi.svg)

---

## Siswa

Kamu absen dengan wajah, dan hanya bisa absen saat berada di lingkungan sekolah. Bagian ini mengurutkan langkahnya dari pasang aplikasi sampai absen sehari-hari.

Yang perlu disiapkan: HP Android dengan kamera depan, NISN dan PIN awal dari sekolah, koneksi internet, dan GPS. Belum punya NISN atau PIN awal? Minta ke wali kelas atau admin.

### Pasang aplikasi

Pasang file APK yang dibagikan sekolah. Karena aplikasi tidak lewat Play Store, biasanya muncul peringatan "sumber tidak dikenal" — izinkan pemasangan untuk aplikasi yang kamu pakai membuka file (File Manager atau browser).

Saat pertama dibuka, aplikasi minta izin kamera, lokasi, dan notifikasi. Izinkan semuanya. Untuk lokasi, pilih "Saat aplikasi digunakan" dan "Lokasi presisi".

Satu hal yang paling sering bikin absen gagal adalah GPS kurang akurat. Buka Setelan HP → Lokasi, nyalakan, lalu set ke mode Akurasi Tinggi. Nama menunya beda-beda tiap merek HP.

### Login dan lengkapi data

Isi NISN dan PIN awal dari admin, lalu tekan Masuk. Saat login pertama, kamu diarahkan ke layar Lengkapi Data & Ganti PIN:

1. Periksa nama, NISN, dan kelas. Data ini tidak bisa diubah sendiri — kalau ada yang salah, lapor admin dan jangan lanjut.
2. Isi nomor WhatsApp kamu (wajib). Nomor ini dipakai untuk reset PIN kalau suatu saat lupa, jadi pastikan aktif.
3. Nomor WhatsApp orang tua dan email boleh diisi, tapi tidak wajib.
4. Buat PIN baru 4–6 digit (jangan pakai PIN default admin), lalu ketik ulang.
5. Tekan Simpan & Lanjut.

Mulai sekarang kamu login pakai PIN baru itu.

### Daftar wajah (sekali saja)

Sebelum bisa absen, wajah kamu didaftarkan dulu — cukup sekali. Pendaftaran harus dibuka lebih dulu oleh admin/guru lewat panel sekolah; kalau belum dibuka, minta dibukakan.

Di layar Absensi Wajah, taruh wajah di dalam bingkai oval di tempat terang tanpa masker, lalu kedipkan mata mengikuti perintah di layar. Aplikasi mengambil tiga sampel ("Mendaftarkan wajah 1/3", "2/3", "3/3") — kedip lagi tiap diminta. Setelah selesai, kamu langsung tercatat absen masuk. Daftarkan dengan penampilan sehari-hari (tanpa kacamata hitam) supaya gampang cocok nanti.

### Absen masuk

Setiap hari cukup buka aplikasi dan login. Kalau belum absen, aplikasi langsung membuka Absensi Wajah:

1. Aplikasi mengecek lokasi. Tunggu beberapa detik.
2. Kalau kamu di area sekolah, muncul tantangan gerak: palingkan wajah ke samping sebentar, lalu hadap depan dan kedipkan mata 2–3 kali sesuai perintah. Gerakan ini memastikan yang absen orang asli, bukan foto atau video.
3. Kalau wajah cocok, muncul "Absen berhasil" dan kamu masuk ke Dashboard.

Status kehadiran dihitung dari jam server, bukan jam HP: absen sebelum jam masuk berarti Hadir; antara jam masuk dan batas alfa berarti Hadir tapi dicatat telat sekian menit; lewat batas alfa atau tidak absen sama sekali berarti Alfa. Jamnya diatur admin. Karena pakai jam server, mengubah jam HP tidak ada gunanya — datang lebih awal satu-satunya cara.

### Absen pulang

Kartu Absen Pulang muncul di Dashboard setelah kamu Hadir. Ada dua pilihan:

- Pulang Normal — untuk pulang di jam biasa. Tekan, lalu verifikasi wajah (menoleh + kedip). Status tetap Hadir dan jam pulang tercatat.
- Pulang Izin — untuk pulang lebih awal karena sakit/keperluan. Isi alasan, lampirkan foto bukti (utamakan Foto Langsung), lalu Verifikasi Wajah & Kirim. Status hari itu berubah jadi Izin.

### Ajukan izin kalau tidak masuk

Kalau tidak bisa hadir (mis. sakit di rumah), ajukan izin dari layar Login tanpa perlu absen. Tekan Ajukan Izin, isi NISN, PIN, dan alasan, lampirkan foto bukti, lalu Kirim. Izin diperiksa dan disetujui atau ditolak oleh Guru BK. Ajukan sebelum batas alfa supaya tidak keburu tertandai Alfa.

### Lupa PIN

Di layar Login tekan Lupa PIN, masukkan NISN, tekan Kirim Kode. Kode OTP dikirim ke WhatsApp yang kamu daftarkan dan berlaku 5 menit. Masukkan kode itu bersama PIN baru, lalu Ganti PIN. Kalau nomor WhatsApp kamu sudah tidak aktif, hubungi admin untuk reset manual.

### Membaca Dashboard

Empat kotak di atas menunjukkan rekap kamu: Hadir, Izin, Alfa, dan Belum. Di bawahnya, Riwayat Absensi Saya menampilkan daftar absensi dari yang terbaru, lengkap dengan status tiap hari, catatan telat, dan catatan dari guru bila ada.

### Siswa PKL

Kalau kamu sedang PKL dan sudah didaftarkan admin, kamu bisa absen dari tempat PKL tanpa harus di sekolah. Prosesnya sama, hanya pengecekan lokasi yang dilewati — verifikasi wajah tetap wajib. Kalau aplikasi masih menuntut lokasi sekolah, berarti status PKL kamu belum diaktifkan; hubungi admin.

### Kalau absen bermasalah

- Di luar area sekolah / GPS tidak terbaca — pastikan kamu benar di lingkungan sekolah, GPS mode Akurasi Tinggi, keluar sebentar ke area terbuka, lalu tekan Coba Lagi.
- Wajah tidak cocok — cari tempat terang, lepas masker/topi/kacamata hitam, hadap lurus, pastikan hanya wajah kamu di kamera, lalu kedip lagi.
- Kamera hitam — cek izin Kamera di setelan aplikasi, pastikan tidak ada aplikasi lain memakai kamera, tutup lalu buka lagi.
- "Pendaftaran wajah belum dibuka" — minta guru atau admin membuka pendaftaran wajah kamu.
- Sudah tertandai Alfa padahal hadir/izin — hanya Guru BK yang bisa mengoreksi; laporkan ke beliau.

---

## Guru

Guru mata pelajaran tidak absen wajah. Setelah login kamu langsung masuk Dashboard untuk memantau kehadiran dan memberi catatan. Guru bisa melihat dan mencatat, tapi tidak bisa mengubah kehadiran, jam, atau status siswa — itu wewenang Guru BK dan admin.

### Login

Buka aplikasi, izinkan permintaan izin di awal (dibutuhkan aplikasi walau guru tidak absen wajah), masukkan akun guru dan PIN dari admin, lalu Masuk. Kamu langsung dibawa ke Dashboard.

### Memantau kehadiran

Di kartu Pantau Kehadiran Siswa, atur dua filter — Jurusan (Semua/TKJ/DKV/MPLB/AKL) dan Kelas (Semua/10/11/12) — untuk memilih kelas yang mau dilihat. Ada dua tab:

- Hari Ini — status tiap siswa hari ini (Hadir, Izin, Alfa, atau Belum) beserta menit telat bila ada. Di atasnya ada ringkasan jumlah per status.
- Rekap Bulan Ini — rekap sebulan per siswa, contohnya "Hadir 18 · Telat 3× (1 jam 15 menit) · Izin 2 · Alfa 1".

Kalau siswa banyak, daftar dibagi per halaman lewat tombol Sebelumnya dan Berikutnya.

### Memberi catatan

Catatan dipakai untuk siswa yang sudah hadir tapi keluar atau izin saat pelajaran (mis. ke UKS, dipanggil BK). Di tab Hari Ini, tekan Catatan pada baris siswa, pilih salah satu preset (Izin Ambil Barang, Izin ke UKS / Sakit, Dipanggil Guru/BK, Tugas/Kegiatan Sekolah) atau ketik sendiri, lalu Simpan. Catatan hanya bisa diberikan ke siswa yang sudah hadir hari itu.

### Yang tidak bisa diubah guru

Guru hanya bisa menambah atau mengubah catatan. Status kehadiran, jam, menit telat, persetujuan izin, reset wajah, dan export bukan wewenang guru — semua ini dikunci di server, jadi kamu tidak akan tidak sengaja mengubah data siswa. Kalau ada data yang keliru, laporkan ke Guru BK atau admin.

Layar guru tidak bisa di-screenshot karena menampilkan data banyak siswa. Ini disengaja, bukan kerusakan.

---

## Guru BK

Guru BK punya semua kemampuan guru mapel (memantau kehadiran, filter, catatan) ditambah wewenang di bawah ini. Untuk cara memantau dan mengisi catatan, lihat bagian [Guru](#guru). Layar BK menampilkan data semua siswa, jadi jaga kerahasiaannya.

### Menyetujui atau menolak izin

Di kartu Riwayat Izin Siswa, tiap pengajuan punya status Pending, Disetujui, atau Ditolak. Untuk yang masih Pending, tekan Setuju atau Tolak.

- Setuju membuat kehadiran siswa hari itu menjadi Izin dan melindunginya dari Alfa otomatis. Menyetujui izin tidak menimpa hari yang sudah tercatat Hadir.
- Tolak menandai pengajuan sebagai ditolak tanpa mengubah kehadiran.

Sebaiknya periksa foto bukti dan alasannya dulu, dan proses di hari yang sama supaya siswa tidak keburu ditandai Alfa di akhir hari.

### Reset wajah

Pakai ini kalau data wajah siswa perlu didaftarkan ulang — ganti HP, wajah tidak pernah cocok, atau salah daftar. Buka kartu Kelola Wajah Siswa, masukkan NISN, tekan Reset Wajah. Ini hanya menghapus data wajah lama; riwayat absensi tetap aman. Supaya siswa bisa daftar ulang, pendaftaran wajahnya juga harus dibuka dari panel admin. Pastikan NISN benar sebelum menekan.

### Export data

Export Absensi mengunduh rekap kehadiran bulan berjalan, Export Izin mengunduh seluruh pengajuan izin. Keduanya berupa file CSV yang tersimpan di folder Downloads dan bisa dibuka di Excel atau Google Sheets untuk laporan.

### Peringatan alfa beruntun

Kalau ada siswa Alfa tiga hari berturut-turut, Guru BK mendapat peringatan otomatis saat data termuat di Dashboard. Alfa berarti tidak absen dan tidak izin — belum tentu membolos, bisa saja lupa absen atau HP bermasalah. Cek Rekap Bulan Ini siswa itu, lalu konfirmasi ke siswa atau orang tuanya.

### Menjaga data

Layar BK memuat data pribadi semua siswa, termasuk alasan sakit dan foto bukti. Gunakan hanya untuk keperluan sekolah, kunci HP, dan simpan file export di tempat aman. Layar BK tidak bisa di-screenshot — pakai Export untuk data resmi. Reset wajah dan proses izin berpengaruh langsung ke catatan siswa, jadi lakukan dengan cermat.

---

## Status kehadiran & istilah

| Status | Arti |
|---|---|
| Hadir | Sudah absen masuk dengan wajah di area sekolah. |
| Izin | Tidak masuk karena sakit/keperluan dan izinnya sudah disetujui Guru BK. |
| Alfa | Tanpa keterangan — tidak absen dan tidak izin sampai akhir hari. Siswa PKL dikecualikan. |
| Telat | Tetap Hadir, tapi absen setelah jam masuk; menit telatnya dicatat. |
| Belum | Belum ada catatan hari itu (belum absen, belum izin, belum lewat batas). |

Telat dan alfa dihitung dari jam server, bukan jam HP. Jam masuk dan batas alfa diatur admin.

| Istilah | Arti |
|---|---|
| Geofence | Batas lokasi di sekitar sekolah. Absen hanya bisa di dalam area sekolah, kecuali siswa PKL. |
| Liveness | Uji wajah hidup lewat gerakan kecil (menoleh lalu kedip) supaya foto atau video tidak bisa menipu. |
| Enroll / pendaftaran wajah | Perekaman wajah pertama kali (3 sampel). Harus dibuka guru atau admin dulu. |
| PKL | Praktik Kerja Lapangan. Siswa PKL absen dari luar sekolah dan tidak kena Alfa otomatis. |
| NISN & PIN | Identitas untuk login. PIN awal dari admin, wajib diganti saat setup pertama. |
| OTP | Kode sekali pakai lewat WhatsApp untuk reset PIN. |

---

## Pertanyaan umum

**Tidak bisa absen, "di luar area sekolah".** Pastikan kamu benar berada di lingkungan sekolah, GPS mode Akurasi Tinggi, tunggu lokasi mengunci, lalu Coba Lagi. Siswa PKL yang masih diminta ke sekolah: minta admin mengaktifkan status PKL.

**"Wajah tidak cocok".** Cari tempat terang, lepas masker/topi/kacamata gelap, hadap lurus, dan pastikan hanya wajah kamu di kamera. Kalau berkali-kali gagal, minta Guru BK reset wajah supaya bisa daftar ulang.

**Kamera hitam.** Cek izin Kamera di setelan aplikasi, pastikan tidak ada aplikasi lain memakai kamera, lalu tutup dan buka lagi aplikasinya.

**Lupa PIN.** Login → Lupa PIN → masukkan NISN → Kirim Kode → masukkan OTP dari WhatsApp bersama PIN baru → Ganti PIN. Kalau nomor WhatsApp sudah ganti, hubungi admin.

**OTP tidak masuk.** Pastikan ada sinyal dan WhatsApp aktif, cek nomor yang terdaftar sudah benar, tunggu satu dua menit, dan jangan tekan Kirim Kode berulang terlalu cepat.

**Data nama atau kelas salah.** Data ini read-only; laporkan ke admin untuk diperbaiki.

**Terlanjur Alfa padahal sakit/izin.** Ajukan izin dengan foto bukti. Kalau sudah lewat harinya, hubungi Guru BK dengan bukti agar statusnya dikoreksi.

**Datang pagi tapi tercatat telat.** Telat dihitung dari jam server. Absen segera setiba di sekolah, jangan ditunda. Kalau yakin keliru, lapor Guru BK.

**Ganti HP baru.** Data wajah tersimpan di server, bukan di HP. Kalau verifikasi selalu gagal di HP baru, minta Guru BK reset wajah lalu daftar ulang.

**Aplikasi minta update.** Ikuti dan pasang versi terbaru. Update biasanya wajib supaya fitur dan keamanan tetap jalan.

**(Guru/BK) Tidak bisa screenshot Dashboard.** Ini disengaja untuk melindungi data siswa. Gunakan Export (khusus Guru BK) untuk mendapatkan data resmi.

**(Guru) Daftar siswa kosong.** Atur filter Jurusan dan Kelas dulu; longgarkan ke Semua kalau perlu.

**(Guru/BK) Tidak diminta absen wajah saat login.** Benar — guru dan guru BK tidak absen wajah, langsung masuk Dashboard. Absen wajah hanya untuk siswa.

---

[Kembali ke README](../README.md)

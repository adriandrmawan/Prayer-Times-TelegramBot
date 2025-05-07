# Bot Jadwal Sholat Telegram

![Node.js Version](https://img.shields.io/badge/Node.js-v16%2B-brightgreen.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

Bot Telegram yang mengingatkan waktu sholat secara otomatis dengan menggunakan lokasi atau nama kota. Dirancang untuk membantu umat Muslim mendapatkan jadwal sholat akurat dan pengingat otomatis sebelum waktu sholat.

## 🚀 Fitur

- ✅ Jadwal sholat untuk berbagai kota atau berdasarkan lokasi GPS
- ✅ Pengingat otomatis sebelum waktu sholat
- ✅ Mengatur lokasi secara manual atau menggunakan GPS
- ✅ Menyimpan pengaturan lokasi dan notifikasi untuk penggunaan selanjutnya
- ✅ Antarmuka Telegram yang sederhana dan mudah digunakan
- ✅ Mendukung perintah yang mudah dipahami

## 📋 Persyaratan

- [Telegram Bot Token](https://core.telegram.org/bots#botfather)
- [Cloudflare Workers](https://workers.cloudflare.com/) atau layanan serverless lainnya
- Node.js v16 atau lebih baru

## 🛠️ Panduan Instalasi

### 1. Persiapan Bot Telegram
1. Buat bot baru menggunakan [BotFather](https://core.telegram.org/bots#botfather) di Telegram.
2. Salin token bot yang diberikan oleh BotFather.

### 2. Setup Cloudflare Worker
1. Buat akun Cloudflare dan akses [Cloudflare Workers](https://workers.cloudflare.com/).
2. Deploy aplikasi dengan mengunggah kode ke Cloudflare Worker.
3. Pastikan untuk mengatur environment variables berikut:
    - `TELEGRAM_TOKEN`: Token bot yang didapat dari BotFather.
    - `NOTIFICATION_MINUTES`: Waktu pengingat sebelum waktu sholat (default: 15 menit).
    - `PRAYER_CACHE`: Penyimpanan cache untuk jadwal sholat.
    - `USER_PREFERENCES`: Penyimpanan pengaturan pengguna.

### 3. Konfigurasi Bot
1. Pastikan bot dapat menerima webhook dengan menggunakan endpoint `/webhook` yang sudah disediakan dalam aplikasi.
2. Atur waktu cron job untuk pengecekan pengingat otomatis setiap 5 menit.

## 🗂️ Struktur Proyek
```

📦bot-jadwal-sholat
├── 📄worker.js - file utama bot
├── 📄Wrangler.toml- Pengaturan dan variabel lingkungan

```

## 🖥️ Cara Penggunaan
1. Akses bot Telegram dan mulai interaksi dengan mengirimkan perintah:
    - `/start` - Memulai bot dan melihat panduan penggunaan.
    - `/sholat [kota]` - Melihat jadwal sholat untuk kota tertentu.
    - `/setlokasi [kota]` - Mengatur lokasi default.
    - `/notifikasi` - Mengaktifkan pengingat otomatis.
    - `/matikan_notifikasi` - Menonaktifkan pengingat otomatis.
    - `/help` - Melihat bantuan.

2. Bot akan memberikan jadwal sholat berdasarkan kota atau lokasi yang ditentukan.

## 🔒 Keamanan
- Pengingat menggunakan sistem notifikasi berbasis waktu yang disesuaikan.
- Semua data lokasi dan preferensi pengguna disimpan di penyimpanan aman.
- Penggunaan API Telegram dengan token yang diatur secara terpisah.

## ⚠️ Batasan
- Membutuhkan Cloudflare Worker atau platform serverless lain.
- Menggunakan API Aladhan untuk jadwal sholat yang mungkin tidak tersedia di beberapa daerah.
- Fitur pengingat otomatis hanya berfungsi pada server yang berjalan terus-menerus.

## 🤝 Kontribusi
1. Fork repositori ini.
2. Buat branch baru: `git checkout -b fitur-baru`.
3. Lakukan perubahan dan commit: `git commit -m 'Tambahkan fitur baru'`.
4. Push perubahan ke branch: `git push origin fitur-baru`.
5. Buat Pull Request untuk di-review.

## 📝 Lisensi
MIT License - Lihat [LICENSE](LICENSE) untuk detail.

---

Dikembangkan dengan ❤️ oleh Tim Developer.

Terima kasih kepada:
- [Aladhan API](https://aladhan.com/prayer-times-api) - Sumber jadwal sholat.
- [Telegram](https://core.telegram.org/) - Platform komunikasi.

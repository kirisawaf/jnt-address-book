# J&T Courier Address Book — starter

Ini adalah kerangka awal aplikasi web yang dapat dipasang di Android (PWA). Aplikasi menyimpan data ke Cloud Firestore di bawah akun Google yang login.

## Fitur awal
- Login Google
- Tambah nama, alamat, patokan
- Ambil koordinat GPS perangkat
- Cari nama/alamat/patokan
- Navigasi ke koordinat melalui Google Maps
- Edit dan hapus data

## Langkah konfigurasi Firebase
1. Buat project di https://console.firebase.google.com/
2. Tambahkan aplikasi Web (ikon `</>`), beri nama misalnya `Courier Address Book`.
3. Salin konfigurasi Firebase yang ditampilkan.
4. Buka `index.html`, cari `const firebaseConfig` lalu ganti:
   - `ISI_API_KEY` dengan `apiKey`
   - `ISI_PROJECT_ID` dengan `projectId`
   - `ISI_APP_ID` dengan `appId`
   - Pastikan `authDomain` menggunakan `<projectId>.firebaseapp.com`.
5. Firebase Console > Authentication > Get started > Sign-in method > aktifkan Google.
6. Firebase Console > Firestore Database > Create database.
7. Pilih production mode, lalu tab Rules dan tempel isi `firestore.rules`, kemudian Publish.
8. Hosting harus menggunakan HTTPS agar GPS berfungsi. Deploy folder ini ke Firebase Hosting (misalnya melalui Firebase CLI dari komputer) atau layanan hosting HTTPS yang kamu kendalikan.
9. Setelah situs online, buka URL-nya di Chrome Android > menu titik tiga > Tambahkan ke layar utama / Install app.

## Penting
- Jangan kirim API key rahasia, password, atau kode verifikasi ke siapa pun. Firebase web config memang digunakan di sisi aplikasi, tetapi keamanan data bergantung pada Authentication dan Firestore Rules.
- Aturan Firestore di file ini membatasi setiap pengguna hanya membaca/menulis data di folder UID miliknya.
- Jangan simpan data pribadi yang tidak dibutuhkan untuk pengantaran. Gunakan hanya untuk tujuan kerja yang sah dan sesuai kebijakan J&T.
- GPS harus diambil saat kamu berada di alamat yang benar; akurasi bisa berubah tergantung sinyal dan lingkungan.
- Kerangka ini belum dipublikasikan dan belum terhubung ke project Firebase milikmu.

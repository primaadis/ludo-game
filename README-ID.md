# LUDOVERSE Multiplayer P2P (maks. 4 pemain)

Versi ini mempertahankan tampilan sinematik dan mekanik ular tangga dari HTML asli, dengan multiplayer melalui WebRTC DataChannel menggunakan PeerJS.

## File
- `index.html` — aplikasi lengkap (HTML, CSS, JS)

## Cara menjalankan gratis
1. Buat repository GitHub baru atau gunakan repository proyekmu.
2. Unggah `index.html` ke root repository.
3. Aktifkan **Settings → Pages → Deploy from a branch → main / root**.
4. Buka URL HTTPS GitHub Pages. Host pilih world, isi nama, tekan **CREATE ROOM**, lalu bagikan kode 6 karakter.
5. Teman membuka URL yang sama, memasukkan nama dan kode, lalu menekan **JOIN ROOM**. Host menekan **START GAME** setelah minimal ada 2 pemain. Maksimal 4 pemain.

## Biaya dan batasan
- Tidak memerlukan Firebase, database, Cloud Functions, server yang kamu deploy, atau kartu pembayaran.
- PeerJS menggunakan layanan signaling cloud publik gratis untuk membantu menemukan peer dan bertukar informasi awal koneksi. Setelah koneksi berhasil, data permainan dikirim langsung antarbrowser melalui WebRTC. Dokumentasi: https://peerjs.com/client/faq dan https://peerjs.com/server/cloud
- Layanan cloud publik bukan jaminan uptime/SLA; ID room bisa bentrok, layanan dapat berubah, dan koneksi bisa gagal pada jaringan tertentu. WebRTC membutuhkan signaling untuk membangun koneksi, serta STUN/TURN untuk traversal NAT; koneksi langsung tidak dijamin di semua jaringan.
- Host harus tetap membuka halaman selama permainan. Jika host menutup tab atau koneksinya terputus, room berakhir.
- Karena tanpa backend tepercaya, host adalah sumber kebenaran game. Jangan anggap versi ini anti-cheat/kompetitif. Pemain yang mengontrol host/browser host dapat memanipulasi state.
- `PeerJS` dimuat dari CDN `unpkg.com`; diperlukan internet saat membuka game.

## Uji sebelum dibagikan
Uji dengan 2–4 perangkat/browser berbeda, termasuk satu ponsel pada jaringan seluler. Pastikan room bisa dibuat, pemain bergabung, game mulai, dadu bergilir, ular/tangga tersinkron, dan kemenangan muncul di semua perangkat. Ini adalah implementasi awal; konektivitas WebRTC bergantung pada jaringan dan layanan signaling pihak ketiga.

# 🎬 Video Invitation — Deploy ke Vercel

Halaman web minimalis yang langsung memutar video undangan portrait (1080×1920)
saat dibuka. Auto-play muted pertama, lalu user bisa tap untuk aktifkan suara.

---

## 📁 Struktur Folder

```
video-invitation/
├── index.html          ← halaman utama (tidak perlu diubah)
├── vercel.json         ← konfigurasi Vercel
├── public/
│   └── invitation.mp4  ← ⚠️  LETAKKAN VIDEO KAMU DI SINI
└── README.md
```

---

## 🚀 Cara Deploy

### 1. Siapkan video
Letakkan file video undangan kamu di folder `public/` dengan nama **`invitation.mp4`**.

> Format yang direkomendasikan: **MP4 (H.264)**, resolusi **1080×1920**, ukuran maks ~50MB.

Kalau nama file video kamu berbeda, edit baris ini di `index.html`:
```html
<source src="./public/invitation.mp4" type="video/mp4" />
```

### 2. Deploy ke Vercel

**Cara A — via Vercel CLI (terminal):**
```bash
npm i -g vercel
cd video-invitation
vercel
```
Ikuti instruksi, pilih deploy as static site.

**Cara B — via GitHub:**
1. Push folder ini ke repo GitHub kamu
2. Buka [vercel.com](https://vercel.com) → New Project → Import repo
3. Vercel otomatis detect sebagai static site → klik Deploy

### 3. Buka link
Setelah deploy selesai, Vercel kasih link seperti:
```
https://nama-project.vercel.app
```
Buka link itu → video langsung auto-play! 🎉

---

## 🎛️ Fitur

| Fitur | Keterangan |
|---|---|
| Auto-play (muted) | Langsung play saat halaman dibuka |
| Tap untuk suara | Klik/tap overlay untuk aktifkan audio |
| Tombol mute/unmute | Pojok kanan bawah |
| Loop | Video diputar berulang |
| Responsif | Pas di HP maupun desktop |
| Fallback | Pesan error jika video tidak ditemukan |

---

## 💡 Tips

- Gunakan video **MP4 H.264** untuk kompatibilitas terluas
- Kompres video dengan [HandBrake](https://handbrake.fr/) atau [Squoosh](https://squoosh.app/) agar loading cepat
- Kalau video >50MB, upload ke CDN (Google Drive, Cloudinary, dll) dan ganti `src` dengan URL langsung ke file MP4
- Untuk video dari Google Drive: gunakan format `https://drive.google.com/uc?export=download&id=FILE_ID`

---

## 📝 Ubah Video URL Eksternal

Edit `index.html`, cari baris:
```html
<source src="./public/invitation.mp4" type="video/mp4" />
```
Ganti dengan URL video kamu:
```html
<source src="https://cdn.kamu.com/undangan.mp4" type="video/mp4" />
```
# invitation

# beliagenerasiterengganu

Laman web rasmi **Parti Belia GENERASI Rakyat Terengganu** (Parlimen Belia Malaysia 2026).

Laman statik — HTML, CSS dan JavaScript sahaja. Tiada build step.

## Struktur

```
index.html                  # laman utama (semua seksyen)
assets/img/                 # logo, gambar penaung, halaman Profile Book
assets/audio/               # letak kita-generasi.mp3 di sini (lagu rasmi)
.github/workflows/pages.yml # deploy automatik ke GitHub Pages
```

## Ubah tetapan

Semua pautan dan tarikh ada dalam blok `CONFIG` di bahagian bawah `index.html`:
ID Jotform, pautan WhatsApp, media sosial, aplikasi MyDigital ID / ePBMy,
tarikh tutup daftar dan tarikh mengundi, serta lokasi fail lagu.

## Lagu rasmi

Letak fail MP3 di `assets/audio/kita-generasi.mp3`. Tanpa fail ini, pemain lagu
akan papar mesej "Fail lagu belum ditemui"; bahagian lain laman tetap berfungsi.

## Lihat secara lokal

```sh
python3 -m http.server 8000
# buka http://localhost:8000
```

## Deploy (GitHub Pages)

1. Gabungkan (merge) ke branch `main`.
2. Di GitHub: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Workflow `Deploy ke GitHub Pages` akan berjalan setiap kali ada push ke `main`.

## Sambung domain (kemudian)

1. Di **Settings → Pages → Custom domain**, masukkan domain anda
   (contoh `beliagenerasiterengganu.com`) dan tandakan **Enforce HTTPS**.
2. Di panel DNS pendaftar domain:
   - Domain utama (apex): rekod `A` ke `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`.
   - `www`: rekod `CNAME` ke `<nama-pengguna-github>.github.io`.
3. Selepas domain aktif, tukar `og:image` dalam `index.html` kepada URL penuh
   (contoh `https://beliagenerasiterengganu.com/assets/img/logo-generasi.png`)
   supaya pratonton pautan di WhatsApp/Facebook memaparkan logo.

Laman ini juga boleh di-deploy ke Netlify, Vercel atau Cloudflare Pages —
pilih folder root, tiada arahan build.

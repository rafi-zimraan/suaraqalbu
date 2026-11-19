# SuaraQalbu

Website channel dakwah **SuaraQalbu**: nasihat dan kajian singkat dari para
ustadz, donasi operasional lewat Saweria, dan info langganan member YouTube.

**Alamat:** https://rafi-zimraan.github.io/suaraqalbu/

- YouTube: https://www.youtube.com/@Suaraqalbu.channel
- Facebook: https://www.facebook.com/suaraqalbu.channel
- Saweria: https://saweria.co/suaraQalbu

## Isi repo

```
index.html      satu halaman, tanpa build step
img/            logo, potret ustadz (dipotong dari thumbnail channel), thumbnail video, og.jpg
sumber/og.html  sumber gambar pratinjau og.jpg (render 1200×630 dengan Chrome headless)
```

## Mengubah halaman

Edit `index.html`, commit, lalu push ke `main`. GitHub Pages memperbarui
situs dalam 1–2 menit.

| Saat | Ubah |
|---|---|
| Memberships sudah di-Launch | `const MEMBERSHIP_AKTIF = false;` → `true` (tombol "Segera dibuka" menjadi "Gabung di YouTube") |
| Nominal Saweria berubah | blok `.nominal` di kartu Saweria |
| Angka subscriber / jumlah video | `.angka` dan `.gelembung` di hero |
| Playlist baru | kartu di `#ustadz`, potret 480×600 di `img/` |

## Aturan isi

- Gambar ustadz diambil dari **thumbnail video channel SuaraQalbu sendiri**.
  Thumbnail bertema politik tidak dipakai.
- Donasi untuk **operasional channel**, tidak wajib, tanpa janji pahala.
  Halaman menyatakan para ustadz tidak menerima donasi lewat halaman ini.
- Kajian ustadz tetap gratis. Yang khusus member hanya e-book dan rangkuman
  susunan SuaraQalbu.
- Ayat diambil dari quran.com (terjemah Kementerian Agama RI). Jangan
  mengetik ulang teks Arab.
- Disclaimer "Channel ini bukan channel resmi…" wajib ada di footer.

## Panduan kajian (`artikel/`) dan SEO

`artikel/*.html`, `artikel/index.html`, `artikel/artikel.css`, dan
`sitemap.xml` **dihasilkan oleh skrip** — jangan diedit tangan. Isinya ada di
project induk: `konten/artikel/<video_id>.json` (+ `_video.json` untuk tanggal,
durasi, dan frame gambar). Untuk menambah halaman:

1. Ambil transkrip: `yt-dlp --skip-download --write-auto-subs --sub-langs id --sub-format json3 <url>`
2. Tulis `konten/artikel/<id>.json` mengikuti format file yang sudah ada
   (panduan isi video, bukan transkrip; tanpa teks ayat/hadits).
3. Tambah entri di `_video.json`, lalu `python3 -I tools/build_artikel.py`
   dari project induk.
4. Commit + push dari folder ini.

Beranda memuat JSON-LD `Organization` + `WebSite`; tiap artikel memuat
`VideoObject` (dengan `Clip` = momen penting) dan `BreadcrumbList`.

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

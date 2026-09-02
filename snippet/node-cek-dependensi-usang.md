# Melihat dependensi Node yang sudah usang

**Masalah:** ingin tahu paket mana yang tertinggal, tanpa langsung memperbarui semuanya.

```bash
npm outdated
```

Kolom yang penting:

| Kolom | Artinya |
|---|---|
| `Current` | yang benar-benar terpasang di `node_modules` |
| `Wanted` | versi tertinggi yang masih cocok dengan rentang di `package.json` |
| `Latest` | versi terbaru di registry, bisa jadi versi mayor yang memutus kompatibilitas |

Naikkan hanya sampai `Wanted` (aman, tidak mengubah `package.json`):

```bash
npm update
```

Naik ke `Latest` harus disengaja, satu per satu, lalu jalankan ujinya:

```bash
npm install react@latest
npm test
```

> Perbedaan `Current` dan `Wanted` yang jauh biasanya berarti `package-lock.json`
> sudah lama tidak disegarkan — bukan berarti paketnya rusak.

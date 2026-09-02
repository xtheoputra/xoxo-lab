# Mengecilkan ukuran video dengan ffmpeg

**Masalah:** rekaman layar 200 MB, sementara batas unggah 25 MB.

Pengaturan yang hampir selalu cukup — H.264, CRF 28:

```bash
ffmpeg -i masukan.mp4 -vcodec libx264 -crf 28 keluaran.mp4
```

`-crf` adalah tombol kualitas. Makin **besar** angkanya, makin kecil berkasnya:

| CRF | Hasil |
|---|---|
| 18 | nyaris tanpa kehilangan kualitas, berkas besar |
| 23 | bawaan ffmpeg, aman untuk umum |
| 28 | jelas lebih kecil, masih layak ditonton |
| 32+ | mulai terlihat rusak |

Rekaman layar tanpa suara — buang jalur audionya, lumayan hemat:

```bash
ffmpeg -i masukan.mp4 -an -vcodec libx264 -crf 28 keluaran.mp4
```

Turunkan resolusi ke 720p sambil menjaga rasio:

```bash
ffmpeg -i masukan.mp4 -vf scale=-2:720 -crf 28 keluaran.mp4
```

> Pakai `scale=-2:720`, bukan `-1:720`. H.264 menuntut lebar berkelipatan dua,
> dan `-1` bisa menghasilkan angka ganjil yang membuat ffmpeg gagal.

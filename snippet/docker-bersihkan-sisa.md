# Docker memakan puluhan giga — membersihkannya

**Masalah:** disk penuh, dan `docker` diam-diam menyimpan image, kontainer mati,
volume yatim, serta cache build.

Lihat dulu apa yang memakan tempat:

```bash
docker system df
```

Tambahkan `-v` untuk rincian per image dan per volume:

```bash
docker system df -v
```

Bersihkan yang jelas tidak terpakai — kontainer berhenti, jaringan menganggur,
image menggantung, cache build:

```bash
docker system prune
```

Cache build biasanya pelakunya. Khusus itu saja:

```bash
docker builder prune
```

> ⚠️ `docker system prune -a --volumes` memang paling lega, tetapi ikut menghapus
> **volume** — artinya basis data pengembangan di dalamnya hilang permanen.
> Jangan dijalankan reflek. Periksa `docker volume ls` dulu.

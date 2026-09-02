# Mencadangkan SQLite selagi aplikasi berjalan

**Masalah:** menyalin berkas `.db` dengan `cp` saat aplikasi masih menulis bisa
menghasilkan cadangan yang rusak — separuh transaksi ikut tersalin.

Pakai perintah bawaan SQLite yang sadar penguncian:

```bash
sqlite3 data.db ".backup cadangan.db"
```

Dari dalam Python, tanpa proses terpisah:

```python
import sqlite3

sumber = sqlite3.connect("data.db")
tujuan = sqlite3.connect("cadangan.db")
with tujuan:
    sumber.backup(tujuan)
tujuan.close()
sumber.close()
```

Cadangan berbentuk teks SQL, berguna untuk diperiksa mata:

```bash
sqlite3 data.db .dump > cadangan.sql
```

Periksa berkasnya sehat sebelum dipercaya:

```bash
sqlite3 cadangan.db "PRAGMA integrity_check;"
```

Jawaban yang benar hanya satu kata: `ok`.

> Kalau memakai mode WAL, jangan lupa `data.db-wal` dan `data.db-shm` saat menyalin
> manual. `.backup` sudah mengurusnya sendiri — itu sebabnya ia lebih dianjurkan.

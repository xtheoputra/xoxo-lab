# Mencari berkas raksasa di riwayat Git

**Masalah:** `git clone` lambat sekali padahal isi repo kelihatan kecil. Biasanya ada
berkas besar yang pernah ter-commit lalu dihapus — objeknya tetap tersimpan.

Urutkan objek terbesar di dalam basis data Git:

```bash
git rev-list --objects --all |
  git cat-file --batch-check='%(objecttype) %(objectname) %(objectsize) %(rest)' |
  awk '$1=="blob" {print $3, $4}' |
  sort -nr | head -20
```

Kolom pertama adalah ukuran dalam byte, kolom kedua nama berkasnya.

Lihat ukuran total repo:

```bash
git count-objects -vH
```

Kalau ternyata berkasnya memang harus dibuang dari riwayat, lihat
[git-hapus-rahasia-dari-riwayat.md](git-hapus-rahasia-dari-riwayat.md) — caranya sama.

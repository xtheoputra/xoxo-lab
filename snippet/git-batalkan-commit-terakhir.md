# Membatalkan commit terakhir

**Masalah:** sudah `git commit`, ternyata ada berkas yang belum siap ikut.

Batalkan commit-nya tapi **pertahankan semua perubahan** di staging:

```bash
git reset --soft HEAD~1
```

Kalau mau perubahannya kembali jadi belum di-`add`:

```bash
git reset HEAD~1
```

> ⚠️ `git reset --hard HEAD~1` juga membatalkan commit, tetapi **menghapus perubahannya**.
> Jangan dipakai kalau belum yakin. Kalau sudah terlanjur, commit-nya masih bisa dicari
> lewat `git reflog` selama ~90 hari.

Kalau commit-nya sudah terlanjur ter-`push`, jangan `reset` — pakai commit pembalik
supaya riwayat orang lain tidak rusak:

```bash
git revert HEAD
```

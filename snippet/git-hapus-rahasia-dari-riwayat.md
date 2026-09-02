# Sandi terlanjur ter-commit — menghapusnya dari riwayat

**Masalah:** `.env` atau berkas berisi sandi sudah ter-push. Menghapus berkasnya lewat
commit baru **tidak cukup** — isinya tetap bisa dibaca dari riwayat.

## Langkah nol, sebelum apa pun

**Cabut dan ganti kredensialnya sekarang juga.** Anggap sandi itu sudah bocor.
Membersihkan riwayat hanya merapikan; ia tidak menarik kembali data yang sudah terbaca
orang lain, bot pemindai, atau cache GitHub.

## Membersihkan riwayat

Dengan [`git-filter-repo`](https://github.com/newren/git-filter-repo) (dianjurkan resmi,
menggantikan `filter-branch`):

```bash
pip install git-filter-repo
git filter-repo --invert-paths --path .env
```

Lalu paksa perbarui remote:

```bash
git push --force --all
git push --force --tags
```

> ⚠️ Ini menulis ulang **semua SHA commit**. Setiap salinan repo milik orang lain
> jadi tidak sinkron dan harus di-clone ulang. Beri tahu tim dulu.

## Supaya tidak terulang

```bash
echo ".env" >> .gitignore
git rm --cached .env
```

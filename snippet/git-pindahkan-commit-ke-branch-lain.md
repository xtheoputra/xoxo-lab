# Salah branch — memindahkan commit ke tempat yang benar

**Masalah:** commit sudah jadi, baru sadar masih di `main` padahal seharusnya di branch fitur.

Selama **belum di-push**, cukup tiga perintah:

```bash
git branch fitur-baru          # tandai posisi sekarang
git reset --hard HEAD~1        # kembalikan main ke sebelum commit
git switch fitur-baru          # lanjut bekerja di tempat yang benar
```

Ganti `HEAD~1` dengan `HEAD~3` kalau yang salah tempat ada tiga commit.

Kalau branch tujuannya sudah ada, ambil commit-nya satu per satu:

```bash
git switch fitur-lama
git cherry-pick <sha>
git switch main
git reset --hard HEAD~1
```

> ⚠️ `git reset --hard` membuang perubahan yang belum di-commit di direktori kerja.
> Simpan dulu dengan `git stash` kalau ada.

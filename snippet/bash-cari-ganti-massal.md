# Cari-dan-ganti di banyak berkas sekaligus

**Masalah:** satu nama fungsi berubah, dan ia tersebar di puluhan berkas.

## Lihat dulu, jangan langsung ganti

```bash
grep -rn "namaLama" --include="*.ts" .
```

`-n` menampilkan nomor baris, jadi hasilnya bisa langsung diklik di terminal editor.

## Baru ganti

```bash
grep -rl "namaLama" --include="*.ts" . | xargs sed -i 's/namaLama/namaBaru/g'
```

- `-rl` hanya mencetak **nama berkas** yang cocok, bukan barisnya.
- `sed -i` menyunting berkas di tempat.

> ⚠️ Pada macOS, `sed -i` menuntut argumen cadangan — `sed -i ''` lalu polanya.
> Di Git Bash Windows dan Linux, `sed -i` saja sudah benar.

> ⚠️ `sed` tidak paham batas kata. `namaLama` juga akan mengenai `namaLamaSekali`.
> Kunci batasnya kalau perlu: `s/\bnamaLama\b/namaBaru/g`.

Jaring pengamannya: kerjakan di direktori kerja yang bersih, supaya `git diff` bisa
memperlihatkan persis apa yang berubah, dan `git checkout .` membatalkan semuanya.

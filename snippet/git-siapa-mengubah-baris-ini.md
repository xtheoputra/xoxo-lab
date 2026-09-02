# Mencari tahu siapa dan kenapa baris ini berubah

**Masalah:** ada satu baris ganjil, dan tidak ada yang ingat kenapa ia ditulis begitu.

```bash
git blame -L 40,60 src/berkas.ts
```

`-L` membatasi ke rentang baris, jadi keluarannya tidak sepanjang berkasnya.

Abaikan commit yang cuma merapikan format, supaya yang muncul penulis aslinya:

```bash
git blame -w -M -C -L 40,60 src/berkas.ts
```

| Bendera | Gunanya |
|---|---|
| `-w` | abaikan perubahan spasi belaka |
| `-M` | lacak baris yang dipindahkan di dalam berkas yang sama |
| `-C` | lacak baris yang disalin dari berkas lain |

Sudah dapat SHA-nya? Baca alasan lengkapnya di pesan commit:

```bash
git show <sha>
```

Melacak riwayat satu fungsi, bahkan menembus penggantian nama berkas:

```bash
git log -L :namaFungsi:src/berkas.ts
```

> Kalau satu commit besar berisi perapian format menutupi semua hasil `blame`, catat
> SHA-nya di `.git-blame-ignore-revs`, lalu jalankan:

```bash
git config blame.ignoreRevsFile .git-blame-ignore-revs
```

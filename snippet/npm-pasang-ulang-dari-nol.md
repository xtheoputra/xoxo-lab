# Memasang ulang dependensi Node dari nol

**Masalah:** galat aneh yang tidak masuk akal — modul katanya tidak ditemukan padahal
jelas ada di `package.json`. Biasanya `node_modules` yang sudah tidak sinkron.

```bash
rm -rf node_modules package-lock.json
npm install
```

Di PowerShell:

```powershell
Remove-Item -Recurse -Force node_modules, package-lock.json
npm install
```

## Sebelum menghapus lock file, pikir dulu

`package-lock.json` adalah yang menjamin rekan tim mendapat versi yang sama persis.
Menghapusnya berarti versi bisa bergeser diam-diam.

Untuk sekadar menyegarkan `node_modules` **tanpa** menggeser versi apa pun:

```bash
rm -rf node_modules
npm ci
```

`npm ci` memasang tepat seperti isi lock file dan menolak jalan kalau lock file-nya
tidak cocok dengan `package.json`. Itu juga yang sebaiknya dipakai di CI.

Cache npm jarang jadi biang masalah, tapi kalau curiga:

```bash
npm cache verify
```

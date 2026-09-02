# tsconfig ketat, versi paling ringkas

**Masalah:** TypeScript dipasang, tapi diam saja saat ada `undefined` nyasar — karena
`strict` belum menyala.

```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "ESNext",
    "moduleResolution": "bundler",
    "strict": true,
    "noUncheckedIndexedAccess": true,
    "noImplicitOverride": true,
    "verbatimModuleSyntax": true,
    "skipLibCheck": true,
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true
  },
  "include": ["src"]
}
```

Yang perlu dipahami:

- `strict: true` sudah mencakup `noImplicitAny`, `strictNullChecks`, dan kawan-kawannya.
  Tidak perlu menulisnya satu per satu.
- `noUncheckedIndexedAccess` **tidak** ikut di dalam `strict`. Ia membuat `arr[0]`
  bertipe `T | undefined` — merepotkan di awal, tetapi justru di situ bug indeks tertangkap.
- `forceConsistentCasingInFileNames` penting kalau bekerja di Windows lalu di-deploy ke
  Linux: `./Utils` dan `./utils` sama saja di Windows, dan gagal di server.
- `skipLibCheck` melewati pemeriksaan berkas `.d.ts` pihak ketiga. Ia menyembunyikan
  masalah tipe di dependensi, tapi memangkas waktu kompilasi banyak sekali.

Menyalakan `strict` di proyek lama sebaiknya bertahap: nyalakan, hitung galatnya
dengan `npx tsc --noEmit`, lalu cicil per folder.

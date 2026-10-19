# xoxo-lab

## English summary

**xoxo-lab** is a collection of short snippets and notes: commands that get used often but are easy to forget.

**What it is**

- 16 standalone notes in [`snippet/`](snippet/), one problem per file, short enough to read with the terminal still open.
- Git: undo the last commit, move commits to the right branch, find huge files in history, remove a committed secret from history, find who changed a line and why.
- CLI and dev tools: bulk search-and-replace, testing JSON endpoints with curl, cleaning up Docker disk usage, compressing video with ffmpeg, outdated Node dependencies, a clean npm reinstall, a quick Python virtual environment, backing up SQLite while the app runs, a minimal strict `tsconfig`.
- Windows: find which process holds a port, create symlinks without Administrator rights.
- Writing rules: the problem comes first, then the command; destructive commands carry a warning; commands the author has not run personally are not included.

**Status:** reference notes, no dependencies and nothing to install. Licensed [MIT](LICENSE).

Built by [xTheo Labs](https://xtheo-labs.vercel.app) · [@xtheoputra](https://github.com/xtheoputra)

> The notes and the documentation below are in Indonesian. *Dokumentasi lengkap di bawah ini dalam Bahasa Indonesia.*

---

Kumpulan snippet dan catatan singkat: perintah yang sering kepakai tapi selalu lupa.

Setiap catatan berdiri sendiri di dalam folder [`snippet/`](snippet/), ditulis pendek
supaya bisa dibaca sambil terminal masih terbuka. Tidak ada dependensi, tidak ada
langkah pemasangan — tinggal salin perintahnya.

## Isi

| Berkas | Untuk apa |
|---|---|
| [`bash-cari-ganti-massal.md`](snippet/bash-cari-ganti-massal.md) | Cari-dan-ganti di banyak berkas sekaligus |
| [`curl-uji-endpoint-json.md`](snippet/curl-uji-endpoint-json.md) | Menguji endpoint JSON dengan curl |
| [`docker-bersihkan-sisa.md`](snippet/docker-bersihkan-sisa.md) | Docker memakan puluhan giga — membersihkannya |
| [`ffmpeg-kompres-video.md`](snippet/ffmpeg-kompres-video.md) | Mengecilkan ukuran video dengan ffmpeg |
| [`git-batalkan-commit-terakhir.md`](snippet/git-batalkan-commit-terakhir.md) | Membatalkan commit terakhir |
| [`git-cari-berkas-raksasa-di-riwayat.md`](snippet/git-cari-berkas-raksasa-di-riwayat.md) | Mencari berkas raksasa di riwayat Git |
| [`git-hapus-rahasia-dari-riwayat.md`](snippet/git-hapus-rahasia-dari-riwayat.md) | Sandi terlanjur ter-commit — menghapusnya dari riwayat |
| [`git-pindahkan-commit-ke-branch-lain.md`](snippet/git-pindahkan-commit-ke-branch-lain.md) | Salah branch — memindahkan commit ke tempat yang benar |
| [`git-siapa-mengubah-baris-ini.md`](snippet/git-siapa-mengubah-baris-ini.md) | Mencari tahu siapa dan kenapa baris ini berubah |
| [`node-cek-dependensi-usang.md`](snippet/node-cek-dependensi-usang.md) | Melihat dependensi Node yang sudah usang |
| [`npm-pasang-ulang-dari-nol.md`](snippet/npm-pasang-ulang-dari-nol.md) | Memasang ulang dependensi Node dari nol |
| [`python-venv-cepat.md`](snippet/python-venv-cepat.md) | Lingkungan virtual Python, versi cepat |
| [`sqlite-backup-tanpa-menghentikan-aplikasi.md`](snippet/sqlite-backup-tanpa-menghentikan-aplikasi.md) | Mencadangkan SQLite selagi aplikasi berjalan |
| [`tsconfig-strict-minimal.md`](snippet/tsconfig-strict-minimal.md) | tsconfig ketat, versi paling ringkas |
| [`windows-siapa-yang-pakai-port.md`](snippet/windows-siapa-yang-pakai-port.md) | Port sudah dipakai — siapa pelakunya? (Windows) |
| [`windows-symlink-tanpa-admin.md`](snippet/windows-symlink-tanpa-admin.md) | Membuat symlink di Windows tanpa jadi Administrator |

## Aturan menulis catatan

1. Satu berkas = satu masalah.
2. Tulis **masalahnya dulu**, baru perintahnya.
3. Sertakan peringatan kalau perintahnya merusak (menulis ulang riwayat, menghapus berkas).
4. Perintah yang belum pernah dijalankan sendiri tidak masuk.

## Lisensi

[MIT](LICENSE).

# xoxo-lab

Short, tested notes for commands that are used often and forgotten just as often.

[![Docs check](https://github.com/xtheoputra/xoxo-lab/actions/workflows/docs-check.yml/badge.svg)](https://github.com/xtheoputra/xoxo-lab/actions/workflows/docs-check.yml)

**Status:** Maintained · 16 notes · MIT licensed

## Overview

Each note covers one problem: the situation comes first, then the command that fixes it, with a warning wherever the command is destructive. Every command has been run by the author before it is written down. There is nothing to install; read the note and copy the command.

The notes are written in Indonesian. The table below gives an English title for each one.

## Contents

| Note | Topic |
|---|---|
| [`bash-cari-ganti-massal.md`](snippet/bash-cari-ganti-massal.md) | Search and replace across many files |
| [`curl-uji-endpoint-json.md`](snippet/curl-uji-endpoint-json.md) | Test a JSON endpoint with curl |
| [`docker-bersihkan-sisa.md`](snippet/docker-bersihkan-sisa.md) | Reclaim disk space used by Docker |
| [`ffmpeg-kompres-video.md`](snippet/ffmpeg-kompres-video.md) | Compress a video with ffmpeg |
| [`git-batalkan-commit-terakhir.md`](snippet/git-batalkan-commit-terakhir.md) | Undo the last commit |
| [`git-cari-berkas-raksasa-di-riwayat.md`](snippet/git-cari-berkas-raksasa-di-riwayat.md) | Find very large files in Git history |
| [`git-hapus-rahasia-dari-riwayat.md`](snippet/git-hapus-rahasia-dari-riwayat.md) | Remove a committed secret from history |
| [`git-pindahkan-commit-ke-branch-lain.md`](snippet/git-pindahkan-commit-ke-branch-lain.md) | Move commits to the right branch |
| [`git-siapa-mengubah-baris-ini.md`](snippet/git-siapa-mengubah-baris-ini.md) | Find who changed a line, and why |
| [`node-cek-dependensi-usang.md`](snippet/node-cek-dependensi-usang.md) | List outdated Node dependencies |
| [`npm-pasang-ulang-dari-nol.md`](snippet/npm-pasang-ulang-dari-nol.md) | Reinstall Node dependencies from scratch |
| [`python-venv-cepat.md`](snippet/python-venv-cepat.md) | Create a Python virtual environment quickly |
| [`sqlite-backup-tanpa-menghentikan-aplikasi.md`](snippet/sqlite-backup-tanpa-menghentikan-aplikasi.md) | Back up SQLite while the application runs |
| [`tsconfig-strict-minimal.md`](snippet/tsconfig-strict-minimal.md) | A minimal strict `tsconfig.json` |
| [`windows-siapa-yang-pakai-port.md`](snippet/windows-siapa-yang-pakai-port.md) | Find which process holds a port on Windows |
| [`windows-symlink-tanpa-admin.md`](snippet/windows-symlink-tanpa-admin.md) | Create symlinks on Windows without Administrator rights |

## Writing rules

1. One file, one problem.
2. State the problem first, then the command.
3. Warn before anything destructive, such as rewriting history or deleting files.
4. Only commands the author has run personally are included.

## Quality checks

A GitHub Actions workflow lints every Markdown file and checks that every link resolves.

## Documentation

Indonesian version of this page: [`docs/README.id.md`](docs/README.id.md).

## License

[MIT](LICENSE) © 2026 Harasta Rahman Tri Putra

---

Built by [xTheo Labs](https://xtheo-labs.vercel.app) · [@xtheoputra](https://github.com/xtheoputra)

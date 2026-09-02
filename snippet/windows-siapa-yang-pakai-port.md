# Port sudah dipakai — siapa pelakunya? (Windows)

**Masalah:** `EADDRINUSE: address already in use :::5173`, padahal merasa tidak
menjalankan apa pun.

Cari PID yang memegang port itu:

```powershell
netstat -ano | findstr :5173
```

Kolom terakhir adalah PID. Cari tahu proses apa itu **sebelum** dimatikan:

```powershell
Get-Process -Id 12345
```

Kalau memang proses nyasar milik sendiri:

```powershell
Stop-Process -Id 12345
```

Cara satu baris, tanpa menyalin PID manual:

```powershell
Get-NetTCPConnection -LocalPort 5173 -State Listen |
  ForEach-Object { Get-Process -Id $_.OwningProcess }
```

> ⚠️ Jangan `Stop-Process` sebelum melihat nama prosesnya. Beberapa port dipegang
> layanan sistem, dan mematikannya bisa memutus koneksi lain.

Lebih aman lagi: jalankan saja di port lain, mis. `PORT=5273 npm run dev`.

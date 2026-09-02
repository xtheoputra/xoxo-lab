# Membuat symlink di Windows tanpa jadi Administrator

**Masalah:** `New-Item -ItemType SymbolicLink` gagal dengan
*A required privilege is not held by the client*.

Windows menuntut hak khusus untuk symlink — kecuali **Developer Mode** dinyalakan.

## Nyalakan sekali saja

Settings → System → For developers → **Developer Mode** → On.

Sesudah itu, sebagai pengguna biasa:

```powershell
New-Item -ItemType SymbolicLink -Path C:\kerja\pintasan -Target C:\proyek\asli
```

## Kalau Developer Mode tidak boleh dinyalakan

*Junction* untuk direktori tidak menuntut hak istimewa sama sekali:

```
mklink /J C:\kerja\pintasan C:\proyek\asli
```

| Bentuk | Sasaran | Butuh hak khusus |
|---|---|---|
| `mklink /J` (junction) | direktori, hanya lokal | tidak |
| `mklink /D` (symlink dir) | direktori, boleh UNC | ya, atau Developer Mode |
| `mklink` (symlink berkas) | berkas | ya, atau Developer Mode |

> Git di Windows bawaannya tidak membuat symlink saat checkout. Nyalakan dengan
> `git config core.symlinks true` — dan itu pun tetap menuntut syarat di atas.

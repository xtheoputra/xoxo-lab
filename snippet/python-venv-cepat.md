# Lingkungan virtual Python, versi cepat

**Masalah:** `pip install` mengotori Python sistem, lalu dua proyek bertengkar
memperebutkan versi paket yang sama.

```bash
python -m venv .venv
```

Mengaktifkan — perintahnya berbeda per shell:

```bash
source .venv/bin/activate      # Linux / macOS / Git Bash
.venv\Scripts\Activate.ps1     # PowerShell
.venv\Scripts\activate.bat     # cmd.exe
```

Pastikan yang aktif benar sebelum memasang apa pun:

```bash
python -c "import sys; print(sys.prefix)"
```

Membekukan dan memulihkan daftar paket:

```bash
pip freeze > requirements.txt
pip install -r requirements.txt
```

> Masukkan `.venv/` ke `.gitignore`. Isinya besar, khusus mesin ini, dan tidak
> bisa dipakai ulang di sistem operasi lain.

Kalau PowerShell menolak dengan *running scripts is disabled*, sekali saja:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

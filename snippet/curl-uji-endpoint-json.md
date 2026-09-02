# Menguji endpoint JSON dengan curl

**Masalah:** ingin memastikan API hidup dan bentuk responsnya benar, tanpa membuka Postman.

GET biasa, dengan hasil yang enak dibaca:

```bash
curl -s https://api.contoh.id/v1/status | jq
```

POST dengan badan JSON:

```bash
curl -s -X POST https://api.contoh.id/v1/masuk \
  -H 'Content-Type: application/json' \
  -d '{"email":"a@b.id","sandi":"rahasia"}' | jq
```

Kalau yang dicari status HTTP-nya, bukan isinya:

```bash
curl -s -o /dev/null -w '%{http_code} %{time_total}s\n' https://api.contoh.id/v1/status
```

Melihat header respons juga:

```bash
curl -sD - -o /dev/null https://api.contoh.id/v1/status
```

> Jangan menaruh token asli langsung di baris perintah — ia tersimpan di riwayat shell.
> Pakai variabel lingkungan: `-H "Authorization: Bearer $TOKEN"`.

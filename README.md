# Praktik 1 — Persiapan Environment (Modul 0)

> **Tugas asli di silabus:** buat project kosong `dotnet new webapp -n HelloWorld`, jalankan, ubah teks di halaman utama.

Tujuan latihan ini cuma satu: **membuktikan environment .NET 8 SDK kamu sudah siap** untuk membuat & menjalankan project ASP.NET Core, sebelum masuk ke materi yang lebih serius di Modul 1 dan seterusnya.

## Apa yang sudah dikerjakan di folder ini

- Project dibuat dengan `dotnet new webapp -n HelloWorld` (template Razor Pages kosong).
- Teks default "Welcome" di halaman utama sudah diganti — buka `Pages/Index.cshtml` untuk lihat perubahannya.

## Prasyarat

- .NET 8 SDK sudah terinstall (`dotnet --version` harus menampilkan versi 8.x). Kalau belum, lihat `README.md` di root repo bagian instalasi.

## Langkah-langkah (step by step)

### 1. Buka terminal di folder project ini
```powershell
cd example/praktik1/HelloWorld
```

### 2. (Opsional) Restore package
Biasanya tidak perlu manual karena `dotnet run` otomatis melakukan restore, tapi kalau mau eksplisit:
```powershell
dotnet restore
```

### 3. Jalankan aplikasi
```powershell
dotnet run
```

Tunggu sampai muncul tulisan seperti ini di terminal:
```
Now listening on: http://localhost:5xxx
Application started. Press Ctrl+C to shut down.
```

### 4. Buka di browser
Salin URL yang muncul (`http://localhost:5xxx`) dan buka di browser. Harusnya kamu melihat:
> "Halo, ini praktik pertama saya belajar ASP.NET Core! 👋"

Kalau teks ini yang muncul (bukan teks default "Welcome"), berarti:
- ✅ .NET SDK sudah terinstall dengan benar
- ✅ Kamu berhasil membuat & menjalankan project ASP.NET Core pertamamu
- ✅ Kamu berhasil mengedit file `.cshtml` dan perubahannya benar-benar ter-apply

### 5. (Opsional) Coba mode hot reload
Hentikan dulu (lihat langkah stop di bawah), lalu jalankan dengan:
```powershell
dotnet watch run
```
Sambil aplikasi berjalan, coba ubah lagi teks di `Pages/Index.cshtml`, simpan filenya, dan lihat browser — harusnya otomatis refresh tanpa kamu perlu restart manual.

## Cara menghentikan aplikasi (stop)

Aplikasi ASP.NET Core yang dijalankan lewat `dotnet run` / `dotnet watch run` berjalan terus di terminal (foreground process) sampai dihentikan manual:

1. Klik ke jendela terminal tempat `dotnet run` berjalan.
2. Tekan **`Ctrl + C`**.
3. Tunggu sampai muncul tulisan `Application is shutting down...` lalu kembali ke prompt terminal biasa.

Kalau `Ctrl+C` tidak merespons (jarang terjadi), tutup saja jendela terminalnya — proses `dotnet` akan ikut berhenti.

## Troubleshooting singkat

| Masalah | Solusi |
|---|---|
| `dotnet` tidak dikenali | SDK belum terinstall / belum ada di PATH — buka terminal baru setelah install SDK |
| Port sudah dipakai (`address already in use`) | Ada instance `dotnet run` lain yang masih jalan di port yang sama — stop dulu (`Ctrl+C`) di terminal lain, atau jalankan dengan port berbeda: `dotnet run --urls http://localhost:5100` |
| Browser tidak otomatis kebuka | Buka manual URL yang tertulis di terminal |

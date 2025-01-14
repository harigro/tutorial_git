
# Langkah-langkah Menggabungkan Repo Lokal dengan Repo GitHub

## 1. Pastikan Repo di Lokal adalah Git Repo
Pastikan folder lokal Anda sudah diinisialisasi sebagai repository Git. Jika belum, jalankan perintah ini di folder lokal:

```
git init
```

## 2. Tambahkan Remote Repository dari GitHub
Sambungkan repo lokal Anda ke repo di GitHub menggunakan perintah berikut. Ganti `URL_REPO_GITHUB` dengan URL repo GitHub Anda:

```
git remote add origin URL_REPO_GITHUB
```

## 3. Periksa Remote Repository
Cek apakah remote repository sudah ditambahkan dengan benar:

```
git remote -v
```

Output-nya seharusnya menunjukkan URL dari repo GitHub Anda.

## 4. Sinkronisasi dengan Repo GitHub
Jalankan perintah berikut untuk mengambil (fetch) semua data dari GitHub ke repo lokal:

```
git fetch origin
```

Setelah itu, lakukan merge atau checkout branch sesuai kebutuhan.

## 5. Menggabungkan (Merge) Repo Lokal dengan Repo GitHub
Jika Anda ingin menggabungkan branch utama (`master` atau `main`) dari GitHub ke branch lokal, gunakan:

```
git pull origin master
```

Atau jika repo Anda menggunakan `main` sebagai branch utama:

```
git pull origin main
```

## Catatan Penting
- Jika terdapat konflik saat penggabungan, Anda perlu menyelesaikannya secara manual.
- Pastikan file lokal yang belum dikomit tidak akan hilang. Gunakan `git status` untuk memeriksa status repo Anda.

Jika Anda membutuhkan bantuan lebih lanjut, beri tahu saya struktur atau masalah spesifik repo Anda!

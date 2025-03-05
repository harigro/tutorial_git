# Tutorial Perintah Git dan GitHub

Repo ini berisi tutorial dan panduan penggunaan perintah dasar hingga lanjutan dalam Git dan GitHub.

## Pendahuluan
Git adalah sistem kontrol versi terdistribusi yang digunakan untuk melacak perubahan kode. GitHub adalah layanan hosting untuk repositori Git yang memungkinkan kolaborasi dan pengelolaan proyek secara online.

## Instalasi Git
Unduh dan instal Git sesuai dengan sistem operasi Anda:
- **Windows**: [Git for Windows](https://git-scm.com/download/win)
- **Mac**: Menggunakan Homebrew: `brew install git`
- **Linux**: `sudo apt install git` (Debian/Ubuntu) atau `sudo dnf install git` (Fedora)

## Konfigurasi Awal
Setelah menginstal Git, konfigurasikan identitas Anda:
```sh
git config --global user.name "Nama Anda"
git config --global user.email "email@example.com"
```

## Perintah Dasar Git
Beberapa perintah dasar dalam Git:
```sh
# Inisialisasi repositori Git
git init

# Menambahkan perubahan ke staging area
git add .

# Membuat commit dengan pesan
git commit -m "Pesan commit"

# Melihat status repositori
git status

# Melihat riwayat commit
git log
```

## Menghubungkan ke GitHub
Untuk menghubungkan repositori lokal ke GitHub:
```sh
# Menambahkan remote repository
git remote add origin https://github.com/username/repository.git

# Mengunggah perubahan ke GitHub
git push -u origin main
```

## Berkontribusi ke Proyek Open Source
Untuk berkontribusi ke repositori open source:
1. **Fork** repositori.
2. **Clone** repositori ke lokal.
3. Buat **branch** baru dan lakukan perubahan.
4. **Commit** dan **push** perubahan.
5. Buat **Pull Request** ke repositori utama.

## Referensi Tambahan
- [Memasukkan Repo Eksternal ke Repo Internal](gabungan/Memasukkan%20Repo%20C%20ke%20dalam%20Repo%20A%20pada%20Cabang%20B.md)
- [Memasukkan Repo Eksternal ke Repo Internal Tanpa Kehilangan Sejarah Komit](gabungan/Menggabungkan%20Repo%20C%20ke%20dalam%20Repo%20Utama%20Tanpa%20Kehilangan%20Sejarah%20Commit.md)
- [Repo GitHub Ke Repo Lokal](gabungan/Menggabungkan_Repo_Lokal_dengan_GitHub.md)
- **Perintah:**
  - [Git SubTree](gabungan/perintah/Menambahkan%20Repository%20Eksternal%20ke%20dalam%20Repository%20Internal.md)
  - [Perbedaan Perintah Pada Git Fetch](gabungan/perintah/Perbedaan%20Perintah.md)
- [Menghapus dan Membatalkan Commit dengan Git](komit/Menghapus%20dan%20Membatalkan%20Commit%20dengan%20Git.md)
- [Panduan Lengkap Membuat Pull Request di GitHub untuk Kontributor Pemula](kontributor/Panduan%20Lengkap%20Membuat%20Pull%20Request%20di%20GitHub%20untuk%20Kontributor%20Pemula.md)
- [Mengunggah Repo ke GitHub](mengunggah/upload_repo_to_github.md)
- [Memperbarui Repo Lokal A' dengan Repo A di GitHub](Perbahrui/Memperbahrui%20Repo%20A'%20Lokal%20Dari%20Repo%20A%20di%20Github.md)

## Lisensi
Proyek ini menggunakan `lisensi GPL`. Silakan gunakan dan modifikasi sesuai kebutuhan Anda.

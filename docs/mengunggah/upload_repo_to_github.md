# Cara Mengunggah Repository Lokal ke GitHub

Panduan ini menjelaskan langkah-langkah untuk mengunggah repository lokal ke GitHub.

---

## 1. Persiapan di GitHub
1. Login ke akun GitHub Anda.
2. Buat **repository baru** di GitHub:
   - Masukkan nama repository, misalnya `belajar_php`.
   - Jangan tambahkan file seperti README, `.gitignore`, atau LICENSE jika Anda sudah memiliki repo lokal.
3. Salin URL repository yang telah dibuat.

---

## 2. Konfigurasi di Lokal
### Langkah-langkah:
1. **Masuk ke direktori repo lokal Anda:**
   ```bash
   cd path/to/repo
   ```
   Contoh:
   ```bash
   cd belajar_php
   ```

2. **Inisialisasi git (jika belum):**
   Jika repo belum diinisialisasi sebagai git, jalankan:
   ```bash
   git init
   ```

3. **Tambahkan semua file ke staging area:**
   ```bash
   git add .
   ```

4. **Commit perubahan:**
   ```bash
   git commit -m "Initial commit"
   ```

---

## 3. Hubungkan ke Repository GitHub
1. **Tambahkan remote origin:**
   Ganti `<URL-REPO-GITHUB>` dengan URL repo GitHub Anda. Contoh:
   ```bash
   git remote add origin https://github.com/username/belajar_php.git
   ```

2. **Push ke GitHub:**
   Untuk cabang `main`:
   ```bash
   git branch -M main
   git push -u origin main
   ```
   Untuk cabang `master`:
   ```bash
   git push -u origin master
   ```

---

## 4. Verifikasi
1. Buka repository di GitHub Anda.
2. Pastikan semua file dari repo lokal telah terunggah.

---

## Catatan Tambahan
- Jika Anda mengalami kendala dengan autentikasi, pastikan Anda menggunakan **Personal Access Token** untuk otentikasi, bukan kata sandi.
- Anda dapat membuat **Personal Access Token** di [GitHub Settings](https://github.com/settings/tokens).

# Panduan Lengkap Membuat Pull Request di GitHub untuk Kontributor Pemula

### 1. **Fork Repository**

- **Tujuan**: Membuat salinan dari repository utama ke akun GitHub Anda.
- **Langkah-langkah**:
  1. Buka halaman repository yang ingin Anda kontribusikan.
  2. Klik tombol **Fork** di pojok kanan atas halaman.
  3. Tunggu proses fork selesai, maka repository akan muncul di akun GitHub Anda.

---

### 2. **Clone Repository Fork**

- **Tujuan**: Mendownload repository fork ke komputer lokal untuk diedit.

- **Langkah-langkah**:
  
  1. Salin URL repository fork Anda. Klik tombol **Code**, lalu salin link HTTPS.
  
  2. Jalankan perintah di terminal:
     
     ```bash
     git clone https://github.com/username/repository-name.git
     ```
     
     > Ganti `username` dengan nama akun GitHub Anda, dan `repository-name` dengan nama repository.

---

### 3. **Buat Branch Baru**

- **Tujuan**: Memisahkan perubahan dari branch utama agar lebih terorganisir.

- **Langkah-langkah**:
  
  1. Masuk ke folder repository:
     
     ```bash
     cd repository-name
     ```
  
  2. Buat branch baru dengan nama deskriptif:
     
     ```bash
     git checkout -b fitur-login
     ```
     
     > Ganti `fitur-login` dengan nama branch sesuai perubahan yang Anda lakukan.

---

### 4. **Lakukan Perubahan**

- **Tujuan**: Mengedit file sesuai kebutuhan.
- **Langkah-langkah**:
  1. Buka file yang ingin Anda ubah menggunakan editor teks favorit (misalnya, VSCode).
  2. Lakukan perubahan seperti menambahkan fitur baru, memperbaiki bug, atau memperbarui dokumentasi.
  3. Setelah selesai, simpan file.

---

### 5. **Commit Perubahan**

- **Tujuan**: Menyimpan catatan perubahan pada branch lokal.

- **Langkah-langkah**:
  
  1. Tambahkan perubahan ke staging area:
     
     ```bash
     git add .
     ```
  
  2. Commit perubahan dengan pesan deskriptif:
     
     ```bash
     git commit -m "Menambahkan fitur login"
     ```

---

### 6. **Push Branch ke GitHub**

- **Tujuan**: Mengirim branch ke repository fork di GitHub.

- **Langkah-langkah**:
  
  1. Push branch ke repository:
     
     ```bash
     git push origin fitur-login
     ```
  
  2. Setelah push, GitHub akan memberikan link ke branch Anda.

---

### 7. **Ajukan Pull Request**

- **Tujuan**: Mengajukan perubahan untuk ditinjau oleh maintainer repository utama.
- **Langkah-langkah**:
  1. Buka repository fork Anda di GitHub.
  2. Klik tombol **Compare & pull request**.
  3. Pastikan:
     - Branch sumber adalah `username/fitur-login`.
     - Branch target adalah branch utama repository asal, misalnya `main` atau `master`.
  4. Isi deskripsi pull request, misalnya:
     - Apa yang diubah?
     - Mengapa perubahan ini penting?
     - Instruksi tambahan jika ada.
  5. Klik tombol **Create pull request**.

---

### 8. **Review dan Diskusi**

- **Tujuan**: Memastikan perubahan Anda diterima tanpa konflik.

- **Langkah-langkah**:
  
  1. Maintainer akan meninjau perubahan.
  
  2. Jika ada masalah, mereka akan memberikan komentar atau meminta revisi.
  
  3. Perbaiki masalah jika ada, lalu commit ulang dan push:
     
     ```bash
     git add .
     git commit -m "Memperbaiki validasi form login"
     git push origin fitur-login
     ```

---

### 9. **Merge Pull Request**

- **Tujuan**: Menggabungkan perubahan ke branch utama.
- **Langkah-langkah**:
  1. Jika pull request disetujui, maintainer akan mengklik **Merge**.
  2. Anda akan menerima notifikasi bahwa pull request berhasil digabungkan.

---

### Catatan Tambahan

- **Selalu Sinkronisasi dengan Repository Utama**:  
  Jika repository utama berubah saat Anda bekerja, sinkronisasi perubahan dengan:
  
  ```bash
  git remote add upstream https://github.com/original-owner/repository-name.git
  git fetch upstream
  git merge upstream/main
  ```
  
  > Ganti `main` dengan branch utama yang digunakan di repository.

- **Ikuti Pedoman Kontribusi**:  
  Periksa file `CONTRIBUTING.md` di repository untuk panduan kontribusi spesifik.

Dengan langkah ini, Anda dapat berkontribusi ke proyek GitHub dengan rapi dan profesional! 🎉

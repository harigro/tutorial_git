## **Tutorial Menggabungkan Repo GitHub ke Repo Lokal dan Mengirimnya Kembali ke GitHub**  

## **Kata Pengantar**  
Git adalah alat yang sangat berguna untuk mengelola versi kode dalam pengembangan perangkat lunak. Sering kali, kita memiliki repo GitHub yang ingin digabungkan dengan repo lokal yang telah kita buat menggunakan `git init`. Tutorial ini akan membahas langkah-langkah untuk mengambil repo GitHub, menggabungkannya dengan repo lokal, dan mengirimkannya kembali ke GitHub.  

---

## **1. Inisialisasi Repo Lokal**  
Jika belum memiliki repo lokal, buatlah dengan perintah berikut:  

```bash
mkdir repository
cd repository
git init
```

---

## **2. Tambahkan Repo GitHub sebagai Remote**  
Tambahkan repo GitHub ke repo lokal agar dapat mengambil data dari sana:  

```bash
git remote add origin https://github.com/username/repository.git
```

Pastikan remote sudah ditambahkan dengan menjalankan:  

```bash
git remote -v
```

---

## **3. Ambil Repo dari GitHub Tanpa Overwrite**  
Karena repo lokal sudah ada, **jangan langsung `git pull`** karena mungkin akan terjadi konflik. Sebagai gantinya, gunakan perintah berikut:  

```bash
git fetch origin
```

Perintah ini hanya mengambil perubahan dari repo GitHub tanpa menerapkannya langsung ke repo lokal.  

Lihat daftar branch yang tersedia di repo GitHub:  

```bash
git branch -a
```

Jika branch `main` sudah ada di GitHub, buat branch baru di lokal berdasarkan branch tersebut:  

```bash
git checkout -b main origin/main
```

Jika branch `main` belum ada, buat dan pindah ke branch tersebut:  

```bash
git branch main
git checkout main
```

### **Memperbarui Repo Lokal dari GitHub**
Jika repo GitHub diperbarui dan ingin memperbarui repo lokal, gunakan perintah berikut:  

```bash
git pull origin main
```

Perintah ini akan mengambil perubahan terbaru dari GitHub dan menggabungkannya ke repo lokal.  

---

## **4. Gabungkan Repo GitHub ke Repo Lokal**  
Gunakan perintah berikut untuk menggabungkan repo dari GitHub ke repo lokal:  

```bash
git merge origin/main
```

Jika ingin mengambil semua perubahan dari repo GitHub ke repo lokal tanpa perlu merge manual, gunakan perintah:

```bash
git checkout nama_cabang .
```

Namun, jika hanya ingin mengambil bagian tertentu dari repo GitHub, misalnya file atau commit tertentu, gunakan:

```bash
git checkout nama_cabang -- bagian_yang_ingin_diambil
```

Misalnya, jika hanya ingin mengambil file `config.php` dari branch `main`, jalankan:

```bash
git checkout main -- config.php
```

Jika terjadi konflik, edit file yang bermasalah, lalu jalankan:  

```bash
git add .
git commit -m "Resolve merge conflict"
```

Jika muncul error seperti:  

```
fatal: refusing to merge unrelated histories
```

Gunakan opsi `--allow-unrelated-histories` saat merge:  

```bash
git merge origin/main --allow-unrelated-histories -m "sesuiakan sesuka hati"
```

---

## **5. Kirim Repo yang Sudah Digabung ke GitHub**  
Setelah penggabungan selesai, kirim perubahan ke GitHub dengan perintah berikut:  

```bash
git push -u origin main
```

---

### **Kata Penutup**  
Selamat! 🎉 Anda telah berhasil menggabungkan repo GitHub dengan repo lokal dan mengirimkannya kembali ke GitHub. Dengan mengikuti tutorial ini, Anda dapat mengelola proyek Git lebih baik dan bekerja secara kolaboratif dengan lebih efisien. Jika Anda mengalami kendala, pastikan untuk membaca pesan error dengan seksama atau bertanya kepada komunitas developer. 🚀
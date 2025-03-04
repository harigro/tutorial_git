# Cara Memperbarui Repo Lokal A' dengan Repo A di GitHub

Dalam pengembangan perangkat lunak dengan Git, sering kali kita memiliki salinan (fork atau clone) dari sebuah repository utama. Ketika repository utama diperbarui, kita mungkin ingin menarik perubahan tersebut ke dalam repository lokal kita tanpa harus mengkloning ulang. Artikel ini akan membahas cara memperbarui repo lokal **A'** agar sesuai dengan repo **A** di GitHub.

---

## **1. Menambahkan Remote Repo A ke Repo A'**

Jika kamu belum menambahkan **repo A** sebagai remote di **repo A'**, jalankan perintah berikut di dalam direktori repo A':

```sh
git remote add upstream https://github.com/username/repo-A.git
```

Gantilah `https://github.com/username/repo-A.git` dengan URL repo A di GitHub.

Untuk memastikan remote telah ditambahkan, jalankan:

```sh
git remote -v
```

Outputnya akan menunjukkan daftar remote, misalnya:

```
origin    https://github.com/username/repo-A-prime.git (fetch)
origin    https://github.com/username/repo-A-prime.git (push)
upstream  https://github.com/username/repo-A.git (fetch)
upstream  https://github.com/username/repo-A.git (push)
```

---

## **2. Mengambil Perubahan Terbaru dari Repo A**

Untuk mengambil pembaruan terbaru dari repo A tanpa menggabungkannya ke repo A', jalankan:

```sh
git fetch upstream
```

Perintah ini akan mengambil pembaruan dari repo A tetapi tidak akan langsung mengubah branch lokal.

---

## **3A. Menyamakan Repo A' dengan Repo A (Reset Hard)**

Jika kamu ingin **repo A' benar-benar sama persis** dengan repo A, gunakan:

```sh
git reset --hard upstream/main
```

Gantilah `main` dengan nama branch utama repo A jika berbeda (misalnya, `master`).

> ⚠️ **Peringatan:** Semua perubahan lokal yang belum di-commit akan hilang.

---

## **3B. Menggabungkan Perubahan Repo A ke Repo A' Tanpa Kehilangan Perubahan Lokal**

Jika kamu ingin memperbarui repo A' tanpa menghapus perubahan lokal, gunakan salah satu metode berikut:

### **1. Merge (Gabung Perubahan)**

```sh
git merge upstream/main
```

Ini akan menggabungkan perubahan dari repo A ke repo A', tetapi jika ada konflik, kamu harus menyelesaikannya secara manual.

### **2. Rebase (Riwayat Commit yang Lebih Bersih)**

```sh
git rebase upstream/main
```

Ini akan menerapkan perubahan dari repo A di atas commit lokal repo A'. Jika ada konflik, kamu harus menyelesaikannya satu per satu.

---

## **4. Mengunggah Perubahan ke Repo A' (Opsional)**

Jika repo A' juga ada di GitHub dan ingin diperbarui dengan hasil dari repo A, jalankan:

```sh
git push origin main --force
```

Ini akan menggantikan isi repo A' di GitHub dengan versi terbaru dari repo A.

---

## **Penutup**

Dengan mengikuti langkah-langkah di atas, kamu dapat memperbarui repo lokal A' agar selalu sinkron dengan repo A tanpa harus mengkloning ulang. Metode yang digunakan dapat disesuaikan dengan kebutuhan, apakah ingin menyalin secara langsung atau menggabungkan perubahan tanpa kehilangan modifikasi lokal.

💡 **Motivasi**: *Belajar Git itu seperti belajar mengelola waktu—semakin kamu menguasainya, semakin efisien dan teratur proses kerja kamu! Teruslah belajar dan berlatih, karena setiap commit adalah langkah menuju keahlian!* 🚀

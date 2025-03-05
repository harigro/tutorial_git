# Menggunakan Git Subtree: Menambahkan Repository Eksternal ke dalam Repository Internal

## Kata Pengantar

Dalam pengembangan perangkat lunak, sering kali kita ingin menyertakan pustaka atau modul dari repository lain ke dalam proyek utama kita. Salah satu cara untuk melakukannya adalah dengan menggunakan **Git Subtree**. Dengan `git subtree`, kita dapat menyertakan repository eksternal ke dalam repository internal tanpa perlu menjadikannya submodule, yang sering kali lebih kompleks dalam pengelolaannya.

Pada tutorial ini, kita akan membahas langkah-langkah menggunakan `git subtree`, perbedaan antara menggunakan opsi `--squash` dan tidak, serta bagaimana mengontrol apakah tag dari repository eksternal ikut terbawa atau tidak.

---

## 1. Menambahkan Repository Eksternal sebagai Subtree

Kita akan menambahkan repository eksternal sebagai subtree di dalam repository internal.

### **Langkah 1: Clone Repository Internal**

Pastikan kita berada di dalam repository internal yang akan menerima subtree.

```sh
# Clone repository internal jika belum ada
git clone https://github.com/user/my-project.git
cd my-project
```

### **Langkah 2: Tambahkan Repository Eksternal**

Tambahkan repository eksternal sebagai remote, misalnya:

```sh
git remote add lib-example https://github.com/example/lib-example.git
```

### **Langkah 3: Tambahkan Subtree dengan atau tanpa `--squash`**

#### **Tanpa `--squash` (Menjaga Riwayat Commit)**

```sh
git subtree add --prefix=vendor/lib-example lib-example main
```

- Semua commit dari repository eksternal akan disertakan dalam repository internal.
- Riwayat commit lengkap dari subtree tetap ada.

#### **Dengan `--squash` (Menggabungkan Commit Menjadi Satu)**

```sh
git subtree add --prefix=vendor/lib-example lib-example main --squash
```

- Semua commit dari repository eksternal akan digabung menjadi satu commit baru.
- Riwayat commit tidak ditampilkan secara terpisah dalam repository internal.

---

## 2. Memperbarui Repository Subtree

Jika repository eksternal mendapatkan pembaruan, kita dapat menarik perubahan ke repository internal.

#### **Tanpa `--squash`**

```sh
git subtree pull --prefix=vendor/lib-example lib-example main
```

#### **Dengan `--squash`**

```sh
git subtree pull --prefix=vendor/lib-example lib-example main --squash
```

---

## 3. Perbedaan Menggunakan `--squash` dan Tidak

| Fitur                              | Tanpa `--squash`                   | Dengan `--squash`                    |
| ---------------------------------- | ---------------------------------- | ------------------------------------ |
| Riwayat commit subtree             | Semua commit tetap ada             | Hanya satu commit gabungan           |
| Ukuran riwayat commit              | Bisa menjadi sangat panjang        | Lebih ringkas                        |
| Mudah melihat perubahan?           | Ya, commit terpisah terlihat jelas | Tidak, hanya ada satu commit         |
| Kompatibilitas dengan subtree push | Ya                                 | Tidak, harus menggunakan metode lain |

### **Kapan Menggunakan `--squash`?**

- Jika ingin menjaga riwayat commit di repository utama tetap bersih.
- Jika tidak terlalu peduli dengan riwayat commit subtree.

### **Kapan Tidak Menggunakan `--squash`?**

- Jika ingin melihat seluruh riwayat commit dari subtree.
- Jika ingin lebih mudah melakukan kontribusi kembali (`push`) ke repository eksternal.

---

## 4. Mengontrol Tag dari Repository Eksternal

Saat kita menambahkan subtree tanpa `--squash`, tag dari repository eksternal juga bisa ikut terbawa. Berikut adalah cara menghindari atau membawanya sesuai kebutuhan.

### **4.1 Menghindari Tag dari Repository Eksternal**

Secara default, `git subtree` akan menyertakan tag yang ada di repository eksternal. Untuk menghindari hal ini, gunakan opsi `--no-tags` saat menarik perubahan:

```sh
git fetch lib-example --no-tags
git subtree add --prefix=vendor/lib-example lib-example main
```

Saat memperbarui subtree tanpa membawa tag:

```sh
git fetch lib-example --no-tags
git subtree pull --prefix=vendor/lib-example lib-example main
```

### **4.2 Membawa Tag dari Repository Eksternal**

Jika kita ingin menyertakan tag dari repository eksternal saat menambahkan subtree, gunakan perintah:

```sh
git fetch lib-example --tags
git subtree add --prefix=vendor/lib-example lib-example main
```

Saat memperbarui subtree dengan menyertakan tag:

```sh
git fetch lib-example --tags
git subtree pull --prefix=vendor/lib-example lib-example main
```

---

## 5. Menghapus Repository Subtree

Jika ingin menghapus subtree, cukup gunakan perintah berikut:

```sh
git rm -r vendor/lib-example
```

Kemudian hapus remote repository jika tidak diperlukan:

```sh
git remote remove lib-example
```

---

## Kata Penutup

Menggunakan `git subtree` memberikan fleksibilitas dalam mengelola repository eksternal di dalam proyek internal. Dengan pemahaman yang baik, kita dapat memilih apakah akan menggunakan opsi `--squash` atau tidak, serta mengontrol apakah tag dari repository eksternal ikut terbawa atau tidak.

Jangan pernah takut untuk mencoba sesuatu yang baru dalam pengelolaan kode sumber. Koding itu seperti seni, semakin sering kita berlatih, semakin indah hasil yang kita buat. Semangat belajar dan terus eksplorasi! 🚀

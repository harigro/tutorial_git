# **Menggabungkan Repo C ke dalam Repo Utama Tanpa Kehilangan Sejarah Commit**

## **Pendahuluan**

Dalam pengembangan perangkat lunak, sering kali kita perlu menggabungkan beberapa repository menjadi satu tanpa kehilangan sejarah commit. Salah satu kasus yang umum adalah memindahkan repo `jumpers/main` ke dalam folder `jumpers/` di dalam repo utama.

Bagaimana cara melakukannya dengan benar? Artikel ini akan membahas **dua metode efektif** untuk memindahkan repo tanpa kehilangan sejarah commit: **Git Subtree** dan **Git Filter-Repo**. Pilihlah metode yang sesuai dengan kebutuhanmu!

---

## **Metode 1: Menggunakan `git subtree` (Cara Termudah)**

`git subtree` memungkinkan kita **memasukkan** repo lain sebagai subdirektori **tanpa kehilangan sejarah commit**.

### **Langkah-langkahnya:**

1. **Tambahkan repo `jumpers` sebagai remote**
   
   ```sh
   git remote add jumpers https://github.com/user/jumpers.git
   ```

2. **Ambil data dari repo `jumpers`**
   
   ```sh
   git fetch jumpers main
   ```

3. **Masukkan repo `jumpers/main` ke dalam folder `jumpers/` dengan subtree**
   
   ```sh
   git subtree add --prefix=jumpers jumpers main --squash
   ```
   
   - `--prefix=jumpers` → Menempatkan isi repo `jumpers/main` ke dalam folder `jumpers/`.
   - `--squash` → Menggabungkan commit menjadi satu commit besar (jika ingin tetap rapi).

4. **(Opsional) Untuk update di masa depan jika repo `jumpers` berubah**  
   Jika repo `jumpers` mendapat update dan ingin menarik perubahan ke repo utama, gunakan:
   
   ```sh
   git subtree pull --prefix=jumpers jumpers main --squash
   ```

---

## **Metode 2: Menggunakan `git filter-repo` (Jika Perlu Memindahkan dengan Seluruh Commit Asli)**

Jika kamu ingin **memindahkan isi repo `jumpers/main` ke folder `jumpers/` sambil tetap mempertahankan sejarah commit aslinya**, gunakan `git filter-repo`.

### **Langkah-langkahnya:**

1. **Clone repo `jumpers/main` secara terpisah**
   
   ```sh
   git clone https://github.com/user/jumpers.git jumpers-tmp
   cd jumpers-tmp
   ```

2. **Gunakan `git filter-repo` untuk memindahkan semua isi repo ke dalam subfolder `jumpers/`**
   
   ```sh
   git filter-repo --to-subdirectory-filter jumpers
   ```

3. **Tambahkan repo utama sebagai remote**
   
   ```sh
   git remote add repo-utama https://github.com/user/repo-utama.git
   git fetch repo-utama
   ```

4. **Merge perubahan ke repo utama**
   
   ```sh
   git checkout main
   git merge repo-utama/main --allow-unrelated-histories
   ```

5. **Push perubahan ke repo utama**
   
   ```sh
   git push origin main
   ```

---

## **Mana yang Harus Dipilih?**

| Metode              | Kelebihan                                                                              | Kekurangan                                                                                                         |
| ------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Git Subtree**     | Mudah, hanya beberapa perintah, bisa update dengan `subtree pull`                      | Menggunakan `--squash` menggabungkan semua commit menjadi satu (tapi bisa tanpa `--squash` jika mau semua commit). |
| **Git Filter-Repo** | Memindahkan repo secara penuh dengan seluruh sejarah commit tanpa kehilangan informasi | Lebih kompleks, memerlukan `git filter-repo` yang harus diinstal terlebih dahulu.                                  |

### **Kesimpulan**

- **Gunakan `git subtree`** jika ingin cara yang simpel tanpa kehilangan fungsi Git.
- **Gunakan `git filter-repo`** jika benar-benar ingin mempertahankan semua commit asli dari `jumpers/main` dalam subfolder `jumpers/`.

---

## **Penutup**

Memindahkan repository ke dalam struktur yang lebih rapi sangat penting untuk menjaga keteraturan dan skalabilitas proyek. Dengan memahami dua metode di atas, kamu bisa memilih cara terbaik sesuai kebutuhanmu. Jangan ragu untuk bereksperimen dan mencoba metode yang paling cocok!

## **Motivasi**

*"Setiap langkah kecil dalam pengelolaan kode adalah investasi besar untuk masa depan proyekmu. Teruslah belajar dan eksplorasi, karena ilmu tidak ada batasnya!"* 🚀💡

Berikut adalah cheat sheet Git lengkap dengan contoh perintah:

### **Konfigurasi Git:**

- `git config --global user.name "Nama Anda"`  
  Menetapkan nama pengguna Git global.  
  **Contoh**:
  
  ```bash
  git config --global user.name "John Doe"
  ```

- `git config --global user.email "email@example.com"`  
  Menetapkan email Git global.  
  **Contoh**:
  
  ```bash
  git config --global user.email "john.doe@example.com"
  ```

- `git config --list`  
  Menampilkan konfigurasi Git saat ini.  
  **Contoh**:
  
  ```bash
  git config --list
  ```

### **Membuat Repository Baru:**

- `git init`  
  Membuat repository Git baru.  
  **Contoh**:
  
  ```bash
  git init
  ```

- `git clone <url>`  
  Mengkloning repository dari URL.  
  **Contoh**:
  
  ```bash
  git clone https://github.com/username/repo.git
  ```

### **Mengecek Status:**

- `git status`  
  Menampilkan status perubahan file dalam repository.  
  **Contoh**:
  
  ```bash
  git status
  ```

- `git diff`  
  Menampilkan perbedaan antara file yang dimodifikasi dan versi terakhir yang disimpan.  
  **Contoh**:
  
  ```bash
  git diff
  ```

### **Menambahkan Perubahan:**

- `git add <file>`  
  Menambahkan file tertentu ke staging area.  
  **Contoh**:
  
  ```bash
  git add index.html
  ```

- `git add .`  
  Menambahkan semua perubahan di direktori ke staging area.  
  **Contoh**:
  
  ```bash
  git add .
  ```

### **Membuat Commit:**

- `git commit -m "Pesan commit"`  
  Membuat commit dengan pesan.  
  **Contoh**:
  
  ```bash
  git commit -m "Menambahkan halaman index"
  ```

- `git commit -a`  
  Commit semua perubahan yang sudah dilacak.  
  **Contoh**:
  
  ```bash
  git commit -a
  ```

### **Melihat Riwayat Commit:**

- `git log`  
  Menampilkan riwayat commit.  
  **Contoh**:
  
  ```bash
  git log
  ```

- `git log --oneline`  
  Menampilkan riwayat commit dalam format satu baris.  
  **Contoh**:
  
  ```bash
  git log --oneline
  ```

### **Mengelola Cabang (Branch):**

- `git branch`  
  Menampilkan semua cabang yang ada.  
  **Contoh**:
  
  ```bash
  git branch
  ```

- `git branch <nama_cabang>`  
  Membuat cabang baru.  
  **Contoh**:
  
  ```bash
  git branch fitur-1
  ```

- `git checkout <nama_cabang>`  
  Berpindah ke cabang tertentu.  
  **Contoh**:
  
  ```bash
  git checkout fitur-1
  ```

- `git checkout -b <nama_cabang>`  
  Membuat dan langsung berpindah ke cabang baru.  
  **Contoh**:
  
  ```bash
  git checkout -b fitur-2
  ```

- `git merge <nama_cabang>`  
  Menggabungkan perubahan dari cabang lain.  
  **Contoh**:
  
  ```bash
  git merge fitur-1
  ```

- `git branch -d <nama_cabang>`  
  Menghapus cabang lokal.  
  **Contoh**:
  
  ```bash
  git branch -d fitur-2
  ```

### **Mengatur Remote Repository:**

- `git remote add <nama_remote> <url>`  
  Menambahkan remote repository.  
  **Contoh**:
  
  ```bash
  git remote add origin https://github.com/username/repo.git
  ```

- `git remote -v`  
  Menampilkan daftar remote repository.  
  **Contoh**:
  
  ```bash
  git remote -v
  ```

- `git fetch`  
  Mengambil perubahan terbaru dari remote repository.  
  **Contoh**:
  
  ```bash
  git fetch
  ```

- `git pull`  
  Mengambil dan menggabungkan perubahan dari remote.  
  **Contoh**:
  
  ```bash
  git pull origin main
  ```

- `git push`  
  Mengirim perubahan ke remote repository.  
  **Contoh**:
  
  ```bash
  git push
  ```

- `git push <remote> <branch>`  
  Mengirim cabang tertentu ke remote repository.  
  **Contoh**:
  
  ```bash
  git push origin fitur-1
  ```

### **Mengatasi Konflik dan Revert:**

- `git revert <commit_id>`  
  Membalikkan perubahan yang dilakukan oleh commit tertentu.  
  **Contoh**:
  
  ```bash
  git revert 3a2b1c4
  ```

- `git reset <commit_id>`  
  Mengatur ulang HEAD ke commit tertentu (menghapus commit yang lebih baru).  
  **Contoh**:
  
  ```bash
  git reset 3a2b1c4
  ```

- `git reset --hard <commit_id>`  
  Menghapus semua perubahan lokal dan mengatur ulang ke commit tertentu.  
  **Contoh**:
  
  ```bash
  git reset --hard 3a2b1c4
  ```

### **Mengelola Tag:**

- `git tag`  
  Menampilkan semua tag.  
  **Contoh**:
  
  ```bash
  git tag
  ```

- `git tag <tag_name>`  
  Membuat tag baru.  
  **Contoh**:
  
  ```bash
  git tag v1.0
  ```

- `git push origin <tag_name>`  
  Mengirim tag ke remote repository.  
  **Contoh**:
  
  ```bash
  git push origin v1.0
  ```

### **Perintah Lainnya:**

- `git stash`  
  Menyimpan perubahan yang belum di-commit sementara.  
  **Contoh**:
  
  ```bash
  git stash
  ```

- `git stash pop`  
  Mengembalikan perubahan yang disimpan oleh stash.  
  **Contoh**:
  
  ```bash
  git stash pop
  ```

- `git show <commit_id>`  
  Menampilkan detail commit tertentu.  
  **Contoh**:
  
  ```bash
  git show 3a2b1c4
  ```

Itulah contoh penggunaan perintah Git yang sering digunakan dalam berbagai situasi.

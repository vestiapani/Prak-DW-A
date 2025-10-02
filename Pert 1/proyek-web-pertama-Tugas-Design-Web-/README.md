# 🚀 Panduan Lengkap Git & GitHub
Selamat datang di dokumentasi Git & GitHub saya! Panduan ini dirancang untuk membantumu menguasai dasar-dasar Git serta sebagai laporan tugas matakuliah saya, mulai dari instalasi hingga berkolaborasi dengan tim menggunakan GitHub.

Disusun oleh:

Nama: Ivan Wirahadi Permana

NPM: 4524210045

# 🎯 Apa yang Saya Pelajari?
Dokumentasi ini memiliki tiga tahap utama:

⚙️ Instalasi & Konfigurasi: Menyiapkan Git di komputermu.

💻 Alur Kerja Lokal: Menggunakan Git untuk mengelola proyek secara mandiri.

🤝 Kolaborasi Tim: Mengintegrasikan proyekmu dengan GitHub untuk kerja kelompok yang efisien.


# Bagian 1: ⚙️ Instalasi & Konfigurasi Awal Git
Langkah pertama adalah memasang Git di sistem operasimu.

1. Instalasi Git

💻 Untuk Pengguna Windows
Unduh Installer: Dapatkan versi terbaru dari [git-scm.com/download/win.
](https://git-scm.com/download/win)

Jalankan File .exe : Buka file yang sudah diunduh.

Ikuti Proses Instalasi: Biarkan semua pengaturan pada posisi default, cukup klik Next hingga proses instalasi selesai.

Verifikasi Instalasi: Buka Command Prompt (CMD) dan ketik perintah berikut:

```
git --version
```
Jika versi Git muncul, selamat, instalasi berhasil!

🍎 Untuk Pengguna macOS
Install Homebrew: Jika belum punya, buka Terminal dan jalankan perintah ini:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Install Git via Homebrew: Setelah Homebrew terpasang, jalankan:
```
brew install git
```
Verifikasi Instalasi: Pastikan Git sudah terpasang dengan benar.
```
git --version
```
2. Konfigurasi Awal (Wajib Dilakukan!)
Sebelum mulai, kenalkan dirimu pada Git. Buka terminal dan atur nama serta emailmu. Informasi ini akan dicatat pada setiap perubahan yang kamu buat (commit).

Ganti "vestiapani" dengan namamu
```
git config --global user.name "vestiapani"
```

Ganti "ivan131335@gmail.com" dengan email GitHub-mu
```
git config --global user.email "ivan131335@gmail.com"
```
# Bagian 2: 💻 Alur Kerja Dasar Git (Lokal)
Sekarang kita akan mencoba siklus dasar penggunaan Git pada sebuah proyek.

Buat Proyek & Inisialisasi Git
Buat folder baru untuk proyekmu dan "aktifkan" Git di dalamnya.

```
mkdir proyek-web
cd proyek-web
git init
```
Buat Beberapa File Awal
Mari kita tambahkan beberapa file contoh ke dalam proyek.

## Membuat file HTML utama
```
echo "<h1>Selamat Datang di Proyek Saya</h1>" > index.html
```

## Membuat folder untuk CSS dan filenya
```
mkdir css
echo "body { font-family: sans-serif; }" > css/style.css
```
## Cek Status & Tambahkan ke Staging Area
Lihat file mana saja yang berubah dan siapkan untuk disimpan.
Melihat status file (untracked, modified, staged)
```
git status
```

## Menambahkan semua file baru/berubah ke staging area
```
git add .
```
## Simpan Perubahan (Commit)
Simpan semua file yang ada di staging area ke dalam riwayat proyek dengan pesan yang jelas.
```
git commit -m "feat: Inisialisasi proyek dengan file index dan css"
```
## Buat Branch Baru untuk Fitur
Branch memungkinkan kita mengerjakan fitur baru tanpa mengganggu kode utama (main).
```
git checkout -b fitur-kontak
```
## Kerjakan Fitur di Branch Baru
Tambahkan file kontak.html di branch fitur-kontak.
```
echo "<h1>Halaman Kontak</h1>" > kontak.html
```
## Staging & Commit di Branch
Simpan pekerjaan yang telah kamu lakukan di branch ini.
```
git add .
git commit -m "feat: Menambahkan halaman kontak"
```
## Gabungkan Branch (Merge)
Setelah fitur selesai, gabungkan kembali ke branch utama (main).

### Pindah kembali ke branch utama
```
git checkout main
```

### Gabungkan semua perubahan dari 'fitur-kontak' ke 'main'
```
git merge fitur-kontak
```
Sekarang, semua kodemu (termasuk halaman kontak) sudah ada di branch main!

# Bagian 3: ☁️ Integrasi dengan GitHub
Saatnya mempublikasikan proyek lokalmu ke GitHub.

1. Buat Akun & Repository Baru di GitHub
2. Buka GitHub dan masuk ke akunmu.
3. Klik ikon + di pojok kanan atas, lalu pilih New repository.
4. Beri nama repository (contoh: proyek-web-pertama).
#### Penting: Jangan centang "Add a README file", karena kita sudah punya proyek lokal.
5. Klik Create repository.
6. Hubungkan & Unggah (Push) Proyek Lokal ke GitHub, GitHub akan memberimu beberapa perintah. 

Gunakan yang ini di terminalmu:

## Ganti URL dengan URL repository-mu
```
git remote add origin https://github.com/vestiapani/proyek-web-pertama-Tugas-Design-Web-.git
```

## Ubah nama branch utama menjadi 'main' (standar industri)
```
git branch -M main
```

## Kirim semua commit dari lokal ke repository GitHub
```
git push -u origin main
```
Refresh halaman GitHub-mu, dan lihatlah, kodemu sudah online!

# Bagian 4: 🤝 Alur Kerja Kolaborasi di GitHub (Feature Branch Workflow)
Ini adalah alur kerja standar saat kamu bekerja dalam sebuah tim.

## Clone Repository (Hanya sekali di awal)
Unduh salinan proyek dari GitHub ke komputermu.
```
git clone <URL_REPOSITORY_DARI_GITHUB>
```
## Selalu Mulai dari main yang Terbaru
Sebelum mulai mengerjakan fitur baru, pastikan kodemu adalah versi yang paling mutakhir.
```
git checkout main
git pull origin main
```
## Buat Branch Baru untuk Setiap Tugas/Fitur
Beri nama yang deskriptif untuk branch-mu.
```
git checkout -b fitur-login
```
Bekerja, Add, dan Commit di Branch-mu
Lakukan perubahan kode, lalu simpan secara berkala.

## Setelah melakukan perubahan pada file...
```
git add .
git commit -m "feat: Membuat struktur dasar form login"
```
## Unggah Branch Fitur ke GitHub
Bagikan branch-mu agar bisa dilihat oleh anggota tim lain.
```
git push origin fitur-login
```
1. Buat Pull Request (PR)
2. Buka halaman repository di GitHub.
3. Kamu akan melihat notifikasi untuk branch-mu. Klik Compare & pull request.
4. Isi judul dan deskripsi PR dengan jelas. Jelaskan apa yang kamu kerjakan.
5. Tetapkan Reviewers (anggota tim yang akan memeriksa kodemu).
6. Klik Create pull request.
7. Review, Diskusi, dan Merge
8. Reviewer akan memberikan masukan atau persetujuan pada kodemu.
9. Setelah disetujui, ketua tim atau pemilik repository akan menekan tombol Merge pull request.
10. Sinkronisasi Ulang Setelah Merge
11. Setelah PR-mu (atau PR orang lain) di-merge, semua anggota tim harus memperbarui branch main lokal mereka.
```
git checkout main
git pull origin main
```
12. Dan siklus ini berulang untuk setiap fitur baru! Selamat, kamu telah menyelesaikan panduan dasar Git & GitHub! 🎉

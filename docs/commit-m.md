# Pedoman Commit Message

**Commit message** adalah pesan atau deskripsi yang menjelaskan perubahan kode yang dilakukan dalam sebuah commit pada sistem version control seperti Git. Pesan ini berfungsi sebagai dokumentasi untuk melacak riwayat perubahan dalam proyek.


Sumber note ini diambil dari <a href="https://github.com/angular/angular/blob/main/contributing-docs/commit-message-guidelines.md" target="_blank">sini</a>.

!!! info "Apa ini?"
    Rekomendasi commit message untuk git supaya lebih terorganisir

## Format Commit Message
Setiap pesan komit terdiri dari header, konten, dan catatan kaki. Judul memiliki format khusus yang mencakup jenis, cakupan, dan subjek:

    ```
    <type>(<scope>): <subject> -> Header
    <BLANK LINE>
    <body>
    <BLANK LINE>
    <footer>
    ```

Bagian header berupa (type) dan (subject) wajib diisi namun  bagian (scope) opsional.

Setiap baris ***commit message*** tidak boleh lebih dari 100 karakter! Pembatasan karakter ini memungkinkan pesan menjadi lebih mudah dibaca di GitHub serta di berbagai alat git.

Footer harus berisi referensi penutup untuk issue jika ada.

Contoh penuh:

```
feat(auth): tambahkan login dengan Google OAuth

- Implementasi OAuth2 flow untuk login Google
- Tambah validasi token JWT
- Perbaiki bug session expiry

Closes #123
```

Contoh sederhana:
```
fix: adjust reset button positioning and padding
```


## Tipe Commit Message Header
Commit message yang umum digunakan:

<li><b>feat</b>: Fitur baru </li>
<li><b>fix</b>: Perbaikan bug </li>
<li><b>docs</b>: Perubahan Dokumentasi </li>
<li><b>perf</b>: Perubahan kode yang meningkatkan kinerja </li>
<li><b>test</b>: Menambahkan tes yang hilang atau mengoreksi tes yang ada </li>
<li><b>refactor</b>: Perubahan kode yang tidak memperbaiki bug atau menambahkan fitur </li>
<li><b>build</b>: Perubahan yang memengaruhi sistem build atau dependensi eksternal (contoh cakupan (scope): gulp, broccoli, npm) </li>
<li><b>style</b>: Perubahan yang tidak memengaruhi makna kode (white-space, pemformatan, tidak ada titik koma, etc) </li>
<li><b>ci</b>: Perubahan pada file konfigurasi dan skrip CI kami (contoh cakupan: Circle, BrowserStack, SauceLabs) </li>

### 1. feat - Fitur baru
```
feat(payment): tambahkan metode pembayaran QRIS

- Integrasi dengan API QRIS dari Xendit
- Tambah tabel `payment_methods` untuk menyimpan data QR
- Buat UI component untuk menampilkan kode QR

Resolves #45
```

### 2. fix - Perbaikan bug
```
fix(login): perbaiki validasi password yang selalu gagal

- Perbaiki regex validation untuk special characters
- Tambah error message yang lebih informatif
- Perbaiki unit test yang terkait

Fixes #78
```
### 3. docs - Perubahan dokumentasi
```
docs(readme): update panduan instalasi Docker

- Tambah langkah-langkah setup environment
- Perbaiki contoh konfigurasi .env
- Tambah troubleshooting section

No issue
```
### 4. style - Format kode (tanpa mengubah logika)
```
style(components): format kode dengan Prettier

- Sesuaikan indentasi di semua file .jsx
- Perbaiki formatting pada JSX attributes
- Tambah trailing commas konsisten

Ref #12
```
### 5. refactor - Restrukturisasi kode
```
refactor(api): ekstrak fungsi database ke module terpisah

- Pindahkan koneksi database ke `lib/db.js`
- Buat helper functions untuk query umum
- Perbaiki error handling pattern

No functional changes
```
### 6. test - Penambahan/modifikasi test
```
test(calculator): tambah unit test untuk fungsi divide

- Test pembagian dengan angka positif/negatif
- Test pembagian dengan nol (error case)
- Test edge cases dengan decimal numbers

Closes #33
```
### 7. chore - Tugas maintenance
```
chore(deps): update dependency react-router-dom ke v6.4

- Update package.json dan package-lock.json
- Hapus dependency yang tidak terpakai
- Update security patches

BREAKING CHANGE: Route configuration syntax changed
```
### 8. perf - Perbaikan performa (bonus)
```
perf(images): optimasi loading gambar dengan lazy loading

- Implementasi Intersection Observer untuk gambar
- Kompresi gambar statis dengan WebP format
- Tambah placeholder loading skeleton

Improves #90
```
### 9. ci - Konfigurasi CI/CD
```
ci(github): setup GitHub Actions untuk automated testing

- Tambah workflow untuk run unit tests
- Setup code coverage reporting
- Tambah linting check sebelum merge

Related to #56
```
### 10. build - Perubahan build system
```
build(webpack): upgrade ke Webpack 5 untuk better tree-shaking

- Update webpack.config.js
- Optimasi bundle splitting
- Tambah cache configuration

Reduces bundle size by ~15%
```

## Huh?
!!! question "Pertanyaan"
    Apa maksudnya Resolves #45, Fixes #78, Ref #12, Closes #33, Improves #90, dan Related to #56 pada footer?

Angka-angka yang ada di samping \# merupakan **issue tracker**. <br>
Misalnya **Resolves \#45**. Resolves berarti menyelesaikan atau mengatasi, sementara \#45 artinya issue atau masalah nomor 45. Jadi dapat disimpulkan footer yang diberikan pada commit message tersebut berarti issue nomor 45 telah diatasi pada commit ini.

Contoh dari kasus tersebut:
```
# Issue #45: "Login page shows error for valid passwords"
# Seseorang membuat commit:
```
```
git commit -m "fix(login): perbaiki validasi password

- Perbaiki regex validation yang salah
- Tambah test case untuk special characters

Fixes #45"
```


Setelah push & merge → Issue #45 otomatis:
<ol> 1. Status berubah menjadi "Closed" </ol>
<ol> 2. Muncul komentar: "Closed by commit abc123" </ol>
<ol> 3. Label mungkin ditambahkan "bug-fixed" </ol>


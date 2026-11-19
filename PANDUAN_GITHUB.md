# PANDUAN LENGKAP — WEBSITE HVC DI GITHUB

## A. Yang harus disiapkan
- Akun GitHub di https://github.com/
- Link **Aplikasi Web Google Apps Script** HVC yang telah berjalan: bentuknya `https://script.google.com/macros/s/.../exec`.
- File dari ZIP **HVC_GitHub_Pages_Siap_Upload.zip** ini. **Ekstrak ZIP dulu** sebelum upload.

> **Perbedaan:** GitHub Pages menampilkan portal Home HVC; fitur input surat, database, PDF, penomoran, dan arsip tetap di Google Apps Script. Jangan mengunggah `Index.html` Apps Script sebagai `index.html` GitHub Pages karena membutuhkan `google.script.run` yang tidak tersedia di GitHub Pages.

## B. Membuat repository untuk website
1. Login ke https://github.com/.
2. Klik tanda **+** di kanan atas → **New repository**, atau buka https://github.com/new.
3. Isi **Repository name:** `hvc-surat-menyurat` (contoh; bisa diganti).
4. Pilih **Public**, karena yang diunggah *hanya* paket portal publik, bukan kode admin/data internal.
5. Klik **Create repository**.

## C. Mengunggah file website
1. Ekstrak file ZIP website ke folder di komputer/HP Anda.
2. Di repository GitHub yang baru, pilih **uploading an existing file** atau **Add file → Upload files**.
3. Unggah file `index.html`, `config.js`, `.nojekyll`, `README.md`, `PANDUAN_GITHUB.md`. Jangan unggah ZIP tanpa diekstrak.
4. Klik **Commit changes**.
5. Pastikan `index.html` berada **di bagian utama repository**, bukan tersembunyi dalam folder ZIP.

## D. Menghubungkan tombol Buka Aplikasi
1. Buka Google Apps Script proyek Anda → **Terapkan → Kelola penerapan** → salin **URL Aplikasi web** dengan akhiran `/exec`.
2. Kembali ke GitHub → buka file **config.js** → klik ikon pensil (Edit this file).
3. Ubah baris `appUrl: ""` menjadi seperti ini:

```js
window.HVC_CONFIG = {
  appUrl: "https://script.google.com/macros/s/PASTE-ID-ANDA/exec"
};
```

4. Ganti seluruh URL contoh dengan URL Apps Script Anda sendiri. **Jangan tempel tautan Google Sheets atau editor Apps Script.**
5. Klik **Commit changes**.

## E. Mengaktifkan GitHub Pages
1. Buka tab **Settings** dari repository.
2. Pilih **Pages** pada menu di kiri.
3. Di **Build and deployment**, pilih **Source → Deploy from a branch**.
4. **Branch:** `main`; **Folder:** `/ (root)` → **Save**.
5. Setelah GitHub menyelesaikan penerbitan, buka alamat yang tercantum pada **Settings → Pages**.
6. Umumnya alamatnya `https://USERNAME.github.io/hvc-surat-menyurat/`.

## F. Pengujian
1. Buka URL GitHub Pages. Pastikan ada logo hiu HVC tanpa simbol 1% dan MC.
2. Coba tombol **Buka Aplikasi Pengurus**. Harus membuka web app Apps Script pada tab baru.
3. Masuk menggunakan akun Google pengurus yang sudah diizinkan.
4. Buat satu surat uji, pastikan Google Docs dan PDF tersimpan di Google Drive.
5. Jika tombol menampilkan "Link aplikasi belum diatur", periksa `config.js` dan URL `/exec`.
6. Jika Google menolak akses, periksa konfigurasi akun pengurus dan akses penerapan Apps Script; GitHub Pages tidak dapat melewati pembatasan akses Google.

## G. Cara memperbarui tampilan
- Di GitHub, buka file `index.html`, klik **Edit**, ubah sesuai kebutuhan, lalu **Commit changes**.
- Untuk mengubah logo, edit gambar yang tertanam di `index.html` (lebih mudah gunakan paket pembaruan berikutnya); tidak perlu mengubah backend.
- Jika ingin memperbarui fitur surat, edit file di Apps Script secara terpisah. Perubahan repository publik **tidak otomatis** mengubah Apps Script.

## H. Privasi dan keamanan
- Jangan pernah mengunggah Google Sheets berisi data anggota, tanda tangan, tautan Drive privat, password, token, atau kunci layanan ke repository Public.
- Simpan backup `Code.gs`, `Index.html`, `Media.gs` pada **repository Private** terpisah.
- Pastikan Google Apps Script tetap membatasi akses pengurus. Link web app yang tertulis di `config.js` akan dapat dilihat publik; keamanan harus ditentukan oleh konfigurasi akses Apps Script, bukan kerahasiaan URL.
- GitHub Pages adalah website publik; jangan gunakan untuk mengelola data anggota langsung tanpa arsitektur login/backend yang aman.

## I. Jika gagal membuka website
- Periksa file `index.html` ada di root.
- Pastikan branch `main`, folder `/(root)`.
- Cek tab **Actions** atau menu **Settings → Pages** untuk status deploy.
- Tunggu sampai GitHub Pages menampilkan alamat website, lalu muat ulang halaman.

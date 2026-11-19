# Portal Surat Menyurat Honda Vario Club Jakarta

Website publik (landing page) yang bisa diterbitkan melalui **GitHub Pages**.

## Penting
Website ini **bukan** aplikasi admin surat yang berjalan langsung di GitHub. Aplikasi surat, Google Sheets, Google Docs, dan PDF tetap berjalan di **Google Apps Script**. Tombol pada portal mengarahkan pengurus ke web app tersebut.

## Cara cepat
1. Buat **repository Public** di GitHub (khusus file paket website publik ini).
2. Unggah `index.html`, `config.js`, `.nojekyll`, serta file README dan panduan ini ke root repository.
3. Buka `config.js` → klik pensil Edit → isi `appUrl` dengan URL web app Apps Script yang sudah berakhiran `/exec` → `Commit changes`.
4. Buka `Settings` → `Pages` → `Build and deployment` → `Deploy from a branch` → Branch `main`, folder `/(root)` → `Save`.
5. Alamat website: `https://USERNAME.github.io/NAMA-REPOSITORY/`.

Jangan unggah `Code.gs`, `Media.gs`, Google Sheet, surat anggota, tanda tangan, atau ID sensitif ke repository publik. Untuk backup kode Apps Script gunakan paket terpisah dengan repository **Private**.

Lihat [PANDUAN_GITHUB.md](PANDUAN_GITHUB.md) untuk tutorial rinci.

# Dashboard Lapi 2 & Hormon — GitHub satu klik (projectgrafik)

Repository sudah ditetapkan dalam dashboard menjadi **smartlab738-max/projectgrafik**. File data yang diperbarui hanya **data.json** pada branch default. Tidak ada input path, PHP, MySQL, atau cPanel.

## Sangat penting: Token lama sudah dibagikan

1. Hapus/revoke token lama dari https://github.com/settings/personal-access-tokens.
2. Buat token baru: https://github.com/settings/personal-access-tokens/new.
3. Pengaturan token: **Resource owner = smartlab738-max**, **Repository access = Only select repositories -> projectgrafik**, **Repository permissions -> Contents = Read and write**. Pastikan akun yang membuat token mempunyai akses tulis repo. Jangan kirim token ke siapa pun, jangan unggah di GitHub, dan jangan menaruhnya dalam `index.html`.

## Pemasangan di GitHub

1. Buka https://github.com/smartlab738-max/projectgrafik.
2. Ganti **index.html** pada branch `main` dengan file yang ada di paket ini (menu Add file -> Upload files, atau buka file dan edit/replace). Commit changes.
3. **Jangan mengganti `data.json` yang sudah ada di GitHub dengan paket ini**, karena bisa menimpa data yang mungkin sudah Anda edit. `data.json` di paket hanya contoh awal jika di repo belum ada sama sekali. Saat diperiksa, `data.json` sudah ada di repo Anda.
4. Website GitHub Pages: `https://smartlab738-max.github.io/projectgrafik/` (hanya jika Pages sudah aktif).

## Pemakaian

1. Buka website > **Kelola Data**.
2. Saat pertama membuka halaman, buka **Pengaturan akses admin GitHub**, tempel token **baru**, klik **Aktifkan Akses Simpan**. Token hanya disimpan dalam memori halaman; akses hilang setelah tutup/reload.
3. Edit data/tabel/judul grafik dan klik **Simpan Perubahan**. Ini otomatis menulis ke `data.json` di repository yang sudah ditentukan.
4. Untuk penyimpanan berikutnya selama halaman masih terbuka, cukup klik **Simpan Perubahan** lagi. Tidak perlu input repository atau token ulang.
5. Jika status gagal, data disimpan di browser sebagai cadangan, **belum online**. Klik **Backup JSON** sebelum memuat ulang halaman, untuk mengamankan angka yang sudah diedit.

## Kenapa token tidak bisa otomatis selamanya?

GitHub Pages adalah halaman statis dan bukan backend autentikasi. Menaruh token tetap di JavaScript membuatnya bisa dicuri oleh siapa pun yang membuka situs. Versi ini menyimpan token sementara dalam memori halaman saja. Untuk benar-benar login sekali dan menyimpan tanpa token berulang setelah reload, perlu autentikasi OAuth/GitHub App dengan layanan backend aman (misalnya Cloudflare Worker). Jangan simpan token di kode atau repository publik.

## Error HTTP 403

403 bukan berarti repository/path salah. Periksa **Resource owner**, **Only select repositories**, **Contents: Read and write**, akun Anda mempunyai izin tulis, token masih berlaku, aturan proteksi branch `main`, atau rate limit. Dashboard baru menampilkan detail pesan GitHub daripada hanya pesan generik.

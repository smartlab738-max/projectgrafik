# Dashboard Monitoring Listrik Lapi 2 & Hormon — GitHub Only

Tidak perlu hosting PHP, cPanel, atau database MySQL. Repository GitHub digunakan sebagai website sekaligus arsip data dalam `data.json`.

## Setup sekali saja

1. Buat repository **Public**, misalnya `lapi-monitoring-listrik`, di GitHub.
2. Upload `index.html`, `data.json`, dan `README.md` ke root repository. **Jangan upload** folder `server/` dari paket versi lama.
3. Buka **Settings > Pages > Build and deployment**; set Source = **Deploy from a branch**, Branch = `main`, folder = `/(root)`, lalu Save.
4. Website menjadi `https://USERNAME.github.io/lapi-monitoring-listrik/`. Jika Anda memakai alamat GitHub Pages ini, aplikasi mendeteksi repository otomatis, tidak perlu mengedit kode.
5. Buka website. Jika ada status **Data terbaru dari GitHub**, koneksi baca sudah berhasil.

## Menyimpan setiap bulan

1. Buka **Settings GitHub > Developer settings > Personal access tokens > Fine-grained tokens**, atau gunakan https://github.com/settings/personal-access-tokens/new.
2. Atur **Repository access** = **Only select repositories**; pilih repository dashboard ini saja. Atur **Repository permissions > Contents** = **Read and write**. Pilih masa berlaku yang pendek dan simpan token di password manager, **bukan** di repository/chat publik.
3. Buka dashboard, **Kelola Data**, pilih area, tahun, bulan; edit angka, nama panel, dan judul grafik.
4. Buka **Penyimpanan online langsung di GitHub** (sudah terbuka secara default). Pastikan repository terbaca sesuai `USERNAME/NAMA-REPOSITORY`.
5. Tempel fine-grained token ke kolom **Token GitHub**, klik **Simpan ke GitHub**.
6. Tunggu status **Tersimpan di GitHub**. Sistem otomatis mengosongkan kolom token setelah berhasil. Data sudah menjadi commit baru pada `data.json`.
7. Buka halaman dari perangkat lain atau klik **Ambil Data Terbaru** untuk memeriksa pembaruan.

## Penting

- **GitHub bukan database konvensional.** Cocok untuk catatan bulanan berukuran kecil dan pembaruan sesekali, bukan data sensor real-time atau banyak orang yang mengedit bersamaan.
- `data.json` pada repository **Public** dapat dilihat siapa saja. Jangan masukkan data pribadi atau rahasia.
- Token memberi hak tulis pada repository yang dipilih. **Jangan pernah tulis token ke HTML/JSON/commit**. Aplikasi tidak menyimpannya ke localStorage atau sessionStorage.
- Jika GitHub gagal, perubahan tetap disimpan di browser yang digunakan dan ditandai **belum tersinkron**. Unduh **Backup JSON** bila muncul konflik; jangan menimpa data dari perangkat lain begitu saja.
- Jika halaman GitHub Pages menggunakan domain kustom, isi `const DEFAULT_REPOSITORY='USERNAME/NAMA-REPOSITORY';` dalam HTML sebelum mengunggah atau masukkan repository manual pada setiap browser.
- Akun GitHub yang membuat token harus memiliki hak menulis ke repository tersebut. Token harus diganti setelah kedaluwarsa.
- Riwayat perubahan `data.json` bisa diperiksa di tab **Commits** pada GitHub.

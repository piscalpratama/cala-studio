# CALA Studio Public Policy Hub

Situs statis resmi CALA Studio untuk profil publisher dan dokumen aplikasi Katahari.

## Halaman

- Halaman utama: `index.html`
- Kebijakan Privasi Katahari: `katahari/privacy-policy.html`
- Syarat dan Ketentuan Katahari: `katahari/terms-of-service.html`

Target URL GitHub Pages:

`https://piscalpratama.github.io/cala-studio/`

## Menjalankan secara lokal

Karena situs ini tidak membutuhkan backend, file dapat dibuka langsung di browser. Untuk simulasi yang lebih dekat dengan GitHub Pages, jalankan static server apa pun dari root repository, misalnya:

```bash
python -m http.server 8000
```

Lalu buka `http://localhost:8000/`.

## Deployment

### VPS

Workflow `.github/workflows/deploy-vps.yml` berjalan saat push ke `master` atau melalui **Run workflow**. File statis dikirim menggunakan akun `calaadmin` ke `/srv/apps/cala-studio`, direktori yang dilayani Caddy untuk `https://calastudio.tech`. Setelah upload, workflow membandingkan halaman publik dengan `index.html` commit yang sedang dideploy.

Workflow menggunakan repository secrets `CALA_DEPLOY_SSH_KEY` (private key untuk masuk ke server sebagai `calaadmin`) dan `CALA_VPS_KNOWN_HOSTS` (host key server yang sudah diverifikasi). Public key Actions harus ada dalam `/home/calaadmin/.ssh/authorized_keys`. Key deploy server ke GitHub berbeda dari key ini.

Direktori situs harus dapat ditulis oleh `calaadmin`. Arsip tiap deployment disiapkan di `/home/calaadmin/.cache/cala-studio/releases/`.

Deploy menimpa file statis tanpa menghapus file lain atau checkout `.git`. File yang dihapus dari repository tidak otomatis dihapus dari server. Upload langsung ke direktori aktif tidak menjamin pergantian versi atomik.

### GitHub Pages

Workflow `.github/workflows/deploy-pages.yml` mengunggah seluruh isi repository ke GitHub Pages saat perubahan didorong ke branch `master` atau saat workflow dijalankan manual.

Di repository GitHub, pastikan Pages menggunakan **GitHub Actions** sebagai source. Tidak ada secret, AdMob App ID, atau kredensial pembayaran di repository ini.

## Catatan konten

Tanggal berlaku dan pembaruan saat ini adalah 19 Agustus 2026. Kebijakan privasi dan syarat penggunaan perlu ditinjau ulang jika Katahari menambah login, cloud save, personalisasi iklan, langganan, atau bentuk pemrosesan data baru. Dokumen ini adalah informasi umum dan bukan pengganti konsultasi hukum profesional.

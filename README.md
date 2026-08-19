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

Workflow `.github/workflows/deploy-pages.yml` mengunggah seluruh isi repository ke GitHub Pages saat perubahan didorong ke branch `master` atau saat workflow dijalankan manual.

Di repository GitHub, pastikan Pages menggunakan **GitHub Actions** sebagai source. Tidak ada secret, AdMob App ID, atau kredensial pembayaran di repository ini.

## Catatan konten

Tanggal berlaku dan pembaruan saat ini adalah 19 Agustus 2026. Kebijakan privasi dan syarat penggunaan perlu ditinjau ulang jika Katahari menambah login, cloud save, personalisasi iklan, langganan, atau bentuk pemrosesan data baru. Dokumen ini adalah informasi umum dan bukan pengganti konsultasi hukum profesional.

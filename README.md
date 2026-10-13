# RIDA-AFAEK NTT

Penghimpunan Isu Strategis dan Kebutuhan Riset Perangkat Daerah NTT — Bapperida Provinsi NTT.

Situs statis satu berkas (`index.html`): tanpa build, tanpa instalasi. Logo dan foto latar sudah tertanam di dalam berkas.

## Deploy ke GitHub Pages
1. Buat repositori baru di GitHub, lalu unggah seluruh isi folder ini (`index.html`, `.nojekyll`, `README.md`).
2. Buka **Settings → Pages**.
3. Pada **Build and deployment**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.
4. Situs aktif di `https://<username>.github.io/<nama-repo>/` dalam beberapa menit.

## Sumber data
Data dibaca langsung dari Google Sheets saat halaman dibuka:
- Usulan riset: ID `1rmPQ51ULpwJIHMGLwGDK0GP29jRq-_p2UTE-4ukBfVc` (konstanta `SHEET`)
- Umpan balik: ID `1DsbCO4RVjS1LsmbaNUHoYuWFPgTRhndLrGjEnXAs4Jc` (konstanta `FSHEET`)

Kedua spreadsheet harus dibagikan sebagai **"Siapa saja yang memiliki tautan → Pelihat"**. Hanya tab pertama yang dibaca.
Kolom dicocokkan lewat kata kunci pada judul kolom (tahun/timestamp, perangkat daerah, kelompok, isu, output, skor). Jika berbeda, sesuaikan pencocokan di bagian `try{const L=await gs(SHEET)...` pada `index.html`.

## Catatan penting
- **Login admin.** Kata sandi (`PASS`, bawaan `admin123`).
- Edit skor, data permohonan mitra, dan umpan balik dari widget tersimpan di browser masing-masing pengguna (`localStorage`), tidak dibagikan antarpengguna.
- Statistik pengunjung adalah penghitung lokal di browser, bukan hitungan sungguhan.
- Tailwind dimuat dari CDN (`cdn.tailwindcss.com`) dan ikon MDI dari jsDelivr, jadi perlu koneksi internet. Untuk produksi, disarankan memakai build Tailwind sendiri.

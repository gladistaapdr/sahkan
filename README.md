# Sahkan: paket deploy prototipe

Isi folder:
- `index.html`: aplikasi Sahkan versi 31 sebagai halaman mandiri, dengan pita "Prototipe · semua data adalah data contoh" dan tag noindex.
- `_headers`: header keamanan dan noindex untuk Cloudflare Pages atau Netlify.

## 1. Pilih domain

Cek ulang ketersediaan di registrar sebelum membeli. Status di bawah diambil dari data RDAP registri.

| Domain | Status |
| --- | --- |
| sahkan.com | Terdaftar sejak 2014, nameserver Afternic (biasanya tanda domain dijual) |
| sahkan.id | Terdaftar sejak 2021, status client hold |
| sahkan.co.id | Terdaftar 30 Juni 2026. Kalau ini milik Anda, langsung ke langkah 3 |
| sahkan.my.id | Terdaftar sejak Maret 2026 |
| sahkan.app, sahkanapp.com, sahkanapp.id | Registri tidak mengembalikan data. Kemungkinan masih tersedia |

Syarat .co.id: dokumen badan usaha (akta pendirian atau NIB) dan KTP penanggung jawab. Syarat .id: KTP.

## 2. Unggah ke hosting statis (gratis)

Cloudflare Pages:
1. Masuk ke dash.cloudflare.com, buka Workers & Pages, lalu Create, lalu Pages, lalu Upload assets.
2. Unggah folder ini (index.html dan _headers).
3. Situs langsung aktif di alamat `nama-proyek.pages.dev`.

Netlify juga bisa: seret folder ini ke app.netlify.com/drop.

## 3. Hubungkan domain

1. Di proyek Pages, buka Custom domains, lalu tambahkan domain Anda.
2. Bila DNS domain dikelola di Cloudflare, rekaman dibuat otomatis.
3. Bila DNS ada di registrar Indonesia, buat rekaman CNAME `www` ke `nama-proyek.pages.dev`, lalu arahkan domain utama ke `www`.
4. HTTPS aktif otomatis setelah DNS tersebar (biasanya beberapa menit sampai 24 jam).

## 4. Yang berbeda di luar claude.ai

- Chat AI memakai Claude hanya di dalam artefak claude.ai. Di domain sendiri, Asisten AI otomatis memakai jawaban terbatas. Untuk AI penuh perlu server kecil yang memanggil Anthropic API. Kunci API tidak boleh ditaruh di index.html.
- Tombol unduh CSV dan dokumen siap cetak menyalin isi file ke clipboard sebagai gantinya.
- Pilihan tema, bahasa, dan domisili tetap tersimpan di browser pengguna.

## 5. Sebelum dibuka ke publik

- Cek merek "Sahkan" di PDKI DJKI (pdki-indonesia.dgip.go.id) sebelum membeli domain atau membuat materi pemasaran.
- Pertahankan noindex dan pita prototipe selama data masih data contoh, agar nama dan nomor SK fiktif tidak dikira notaris sungguhan.
- Saat layanan sungguhan berjalan: daftar PSE Lingkup Privat di Komdigi, siapkan kebijakan privasi sesuai UU 27/2022 (PDP), dan hapus data contoh.

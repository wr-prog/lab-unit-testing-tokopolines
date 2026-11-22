# Lab Unit Testing — TokoPolines

Praktikum Pertemuan 10 · Mata Kuliah Uji Produk IT
Cezar Nareswara R — 43324205

Repo ini berisi dua pendamping praktikum Unit Testing untuk studi kasus marketplace **TokoPolines**:

## 1. Web Lab (`index.html`)

Halaman web interaktif yang mengimplementasikan empat fungsi bisnis TokoPolines
(`validasi_jumlah`, `hitung_subtotal`, `hitung_diskon`, `validasi_checkout`) dan
menjalankan pengujian langsung di browser dengan empat teknik desain test case:

1. **Equivalence Partitioning** — lima partisi input `validasi_jumlah` beserta wakilnya.
2. **Boundary Value Analysis** — nilai batas 0, 1, 2, 9, 10, 11 dan batas stok 5/6.
3. **Decision Table** — delapan kombinasi syarat voucher POLINES10 (login × subtotal × voucher).
4. **State Transition** — mesin status pesanan (Menunggu Pembayaran → Diproses → Dikirim → Selesai,
   Batalkan hanya dari Menunggu Pembayaran), lengkap dengan pengujian transisi yang ditolak.

Dilengkapi **runner 28 test utama + 6 test tambahan** (semua PASS) serta demonstrasi
**defect BUG-01** (`validasi_jumlah_bug` menerima 11 unit → FAIL) dan regression test
setelah perbaikan (≤ 11 menjadi ≤ 10 → PASS).

Buka `index.html` langsung di browser, atau aktifkan GitHub Pages dari repo ini.

## 2. Notebook Python (`Unit_Testing_TokoPolines.ipynb`)

Notebook Google Colab berisi kode persis modul: SEL 1 fungsi bisnis, SEL 1B percobaan
manual, SEL 2 suite utama 28 test, SEL 3 demonstrasi defect, SEL 4 pembuktian perbaikan,
SEL 5 enam test tambahan — lengkap dengan output eksekusi aktual
(28 + 6 test PASS; demonstrasi defect 1 FAIL sesuai desain).

Hasil web (JavaScript) dan hasil notebook (Python `unittest`) setara satu sama lain.

# GGTopUp — Website Top Up Game & Unit Testing

Praktikum Pertemuan 10 · Mata Kuliah Uji Produk IT
Cezar Nareswara R — 43324205

Repo ini berisi website **GGTopUp** (aplikasi pendamping yang dibangun sendiri
sebagai objek uji) beserta notebook unit test untuk studi kasus TokoPolines.

## 1. Website GGTopUp (`index.html`)

Toko top up game online simulasi yang benar-benar berjalan di browser (satu
file HTML, tanpa dependensi server; data tersimpan di localStorage):

- **Katalog** — 8 produk top up (diamond Mobile Legends, UC PUBG Mobile,
  diamond Free Fire, Genesis Crystal Genshin Impact, Valorant Points, Steam
  Wallet, gift card Roblox dan PlayStation) dengan pencarian dan filter.
- **Login** — akun simulasi `mahasiswa@tokopolines.test` / `Polines123!` (REQ-01).
- **Keranjang** — jumlah pembelian divalidasi: bilangan bulat 1–10 dan tidak
  melebihi stok (REQ-02); subtotal = harga × jumlah (REQ-03). Tersedia field
  ID Pemain sebagai tujuan pengiriman item.
- **Voucher POLINES10** — diskon 10% hanya bila sudah login, subtotal
  ≥ Rp100.000, dan kode valid (REQ-04).
- **Checkout** — ditolak bila keranjang kosong (REQ-05).
- **Pesanan** — status bergerak Menunggu Pembayaran → Diproses → Dikirim →
  Selesai; pembatalan hanya dari Menunggu Pembayaran dan transisi yang tidak
  sesuai ditolak (REQ-06).
- **Panduan** — daftar aturan bisnis serta mode bug (batas jumlah menjadi 11)
  untuk latihan menemukan defect.

Fungsi bisnis di dalam website (`validasiJumlah`, `hitungSubtotal`,
`hitungDiskon`, `validasiCheckout`, `statusBerikut`) menerapkan aturan yang
sama persis dengan fungsi Python pada notebook, sehingga perilaku website dan
hasil unit test saling setara.

Buka `index.html` langsung di browser, atau aktifkan GitHub Pages dari repo ini.

## 2. Notebook Python (`Unit_Testing_TokoPolines.ipynb`)

Notebook Google Colab berisi kode persis modul: SEL 1 fungsi bisnis, SEL 1B
percobaan manual, SEL 2 suite utama 28 test, SEL 3 demonstrasi defect
(`validasi_jumlah_bug` menerima 11 unit → FAIL), SEL 4 pembuktian perbaikan,
SEL 5 enam test tambahan — lengkap dengan output eksekusi aktual
(28 + 6 test PASS; demonstrasi defect 1 FAIL sesuai desain).

Perancangan kasus ujinya memakai empat teknik: **Equivalence Partitioning**
dan **Boundary Value Analysis** untuk aturan jumlah (REQ-02), **Decision
Table** untuk kombinasi syarat voucher (REQ-04), dan **State Transition**
untuk status pesanan (REQ-06).

## Sumber Gambar Produk

Seluruh gambar pada etalase adalah **gambar asli produk game** (kartu voucher,
banner resmi, dan tangkapan layar dalam game — bukan hasil generate AI),
diambil dari halaman produk/penerbit berikut dan disematkan ke dalam file
`index.html` (diperkecil seperlunya):

- Mobile Legends — 172 Diamond: banner top up kazukiofficialstore.com
- PUBG Mobile — 120 UC: gambar kartu produk arektastore (Netlify)
- Free Fire — 70 Diamond: ilustrasi top up dari blog (Googleusercontent)
- Genshin Impact — 60 Genesis Crystal: tangkapan layar toko dalam game via bittopup.com
- Valorant — 475 Points: gambar kartu produk jumbosouq.com
- Steam Wallet — 25.000 IDR: gambar kartu produk kinguin.net
- Roblox — Gift Card 10.000 Robux: foto produk di Amazon (m.media-amazon.com)
- PlayStation Store — Gift Card $100: gambar kartu produk giftncode.com

# SAYYIDILPRO RETAIL — v2.0 PWA

Aplikasi web responsif dengan ikon khusus, tema hijau tua–putih–oranye, dan dukungan pemasangan PWA di Android/desktop.

## Cara menjalankan
1. Ekstrak ZIP.
2. Unggah isi folder `SAYYIDILPRO_RITEL` ke hosting yang menyediakan HTTPS (misalnya GitHub Pages).
3. Buka URL `index.html` melalui Chrome.
4. Login dengan akun demo di bawah.
5. Android: menu Chrome (⋮) → **Tambahkan ke layar utama / Install app**.
6. Komputer: ikon Install di address bar Chrome/Edge jika tersedia.

Untuk uji lokal di komputer, jalankan server statis dari folder ini, misalnya `python -m http.server 8000`, lalu buka `http://localhost:8000`.

## Akun demo awal
| Role | Username | PIN demo |
|---|---|---|
| Pemilik aplikasi | `admin` | `admin123` |
| Perusahaan | `perusahaan` | `company123` |
| Kepala toko | `manager` | `manager123` |
| Kasir | `kasir` | `kasir123` |
| Karyawan | `staff` | `staff123` |

## Fitur yang dapat diuji
- Login demo dengan lima role tampilan (owner, company, manager, cashier, employee).
- Dashboard, POS, scan/ketik barcode, keranjang, pembayaran tunai/QRIS/debit/transfer (pencatatan), stok otomatis berkurang, riwayat penjualan.
- Produk, harga beli/jual, stok minimum, mutasi, pembelian, cabang.
- Stock Opname terpisah sebagai halaman khusus (`?mode=opname`), sesi opname, penugasan karyawan, mode area mandiri, input stok fisik, kirim untuk persetujuan, persetujuan kepala toko, dan penyesuaian stok setelah disetujui.
- Akun karyawan demo, laporan, ekspor CSV, backup dan restore JSON.
- Service worker untuk cache dasar/offline shell.

## Batasan penting — sebelum dipakai operasional multi-perangkat
Versi ini adalah **PWA frontend mode lokal**. Data disimpan di `localStorage` browser/perangkat. Artinya data tidak otomatis tersinkron antar HP/komputer, belum ada database server, autentikasi server, isolasi data perusahaan/cabang di backend, audit log terpusat, atau pembayaran QRIS/bank sungguhan. Login dan pembatasan role pada versi ini hanya simulasi antarmuka dan bukan kontrol keamanan produksi. Offline cache bukan sinkronisasi transaksi offline.

Jangan gunakan akun demo dan jangan jadikan versi lokal ini sebagai satu-satunya pembukuan toko. Untuk operasional sungguhan sesuai spesifikasi multi-perusahaan/multi-cabang, tahap berikutnya wajib memasang backend + database terpusat, autentikasi aman, API, backup server, dan pengujian hak akses. QRIS/EDC/transfer hanya dicatat sebagai metode pembayaran, bukan diproses oleh aplikasi.

# Buku Kas Kios 📱💼
> **Aplikasi Kasir Pintar & Pembukuan Keuangan Digital UMKM Papua**

Aplikasi **Buku Kas Kios** dirancang khusus untuk mempermudah pelaku UMKM, mama-mama pedagang di Papua, serta pengelola unit usaha Kios **BUMKam (Badan Usaha Milik Kampung) / BUMDes** dalam mengelola pencatatan penjualan, inventaris barang, pengeluaran operasional, piutang usaha (kasbon), hingga penyusunan laporan keuangan terstandarisasi secara digital, sederhana, dan 100% offline-first.

Aplikasi ini merupakan bagian dari luaran program pengabdian masyarakat/KKN oleh **Fakultas Ekonomi dan Bisnis (FEB) Universitas Cenderawasih (UNCEN)** untuk mendorong digitalisasi ekonomi daerah.

---

## 🌟 Fitur Utama Aplikasi

### 1. 🛒 Kasir (Point of Sale - POS)
* Pencarian produk secara instan berdasarkan nama.
* Tambah produk baru langsung melalui modal popup tanpa menutup halaman kasir.
* Keranjang belanja interaktif dengan tombol kuantitas `+`/`-` dan opsi hapus item atau hapus semua.
* Tombol pembayaran nominal cepat (Rp 20.000, Rp 50.000, Rp 100.000, dan Uang Pas) untuk mempercepat proses transaksi.
* Cetak struk belanja fisik atau **Bagikan Gambar Struk Belanja** sebagai berkas gambar media di WhatsApp.

### 2. 📦 Katalog Produk & Stok Ulang (Restock)
* Pengelolaan inventaris lengkap: nama produk, Harga Pokok Penunualan (HPP / modal), harga jual, sisa stok, satuan (pcs, kg, renteng, dll), serta foto produk.
* Modul **Restock** terintegrasi untuk menambah kuantitas barang secara otomatis berdasarkan HPP.

### 3. 💸 Buku Pengeluaran (Beban Kios)
* Pencatatan pengeluaran operasional (Beban Umum) berdasarkan kategori: *Transportasi*, *Listrik & Air*, *Sewa Tempat*, *Gaji / Upah*, *Konsumsi*, dan *Lain-lain*.
* Catatan pengeluaran langsung mengurangi akun Kas/Uang Tunai (Neraca) dan terhitung ke dalam Beban Operasional Umum (Laba Rugi) secara real-time.

### 4. 📕 Buku Hutang (Piutang Usaha)
* Pencatatan daftar pelanggan kasbon: nama, nomor WhatsApp, jumlah hutang, keterangan belanja, dan tanggal transaksi.
* Tombol **WA Tagih** otomatis untuk mengirimkan pesan pengingat tagihan instan ke WhatsApp pelanggan.
* Fitur pelunasan sekali klik dan ekspor daftar hutang ke dalam berkas laporan PDF ringkas.

### 5. 📊 Laporan Keuangan Standar BUMKam/BUMDes
* **Filter Waktu**: Hari Ini, 7 Hari Terakhir, 30 Hari Terakhir, dan Semua Waktu.
* **Ringkasan Keuangan (Dashboard Visual)**: Panel indikator grafis yang menampilkan 4 metrik utama (Total Penjualan, Total Transaksi, Barang Terjual, Laba Bersih).
* **Laporan Laba Rugi**: Menghitung Pendapatan Penjualan, HPP (modal barang), Laba Kotor, Beban Operasional, dan Laba Bersih.
* **Laporan Neraca Keuangan**: Menyajikan neraca seimbang antara Aktiva (Kas Kios, Piutang Dagang, Persediaan Barang) dan Pasiva (Hutang Usaha, Modal Awal, Laba Berjalan).
* **Laporan Arus Kas (Cash Flow)**: Rekapitulasi kas masuk/keluar dari aktivitas Operasional, Investasi (Restock), dan Pendanaan (Modal Awal).

### 6. 📷 Capture & Share Image (WhatsApp Share)
* Fitur ekspor visual untuk membagikan rekap **Laporan Keuangan** lengkap atau rekap **Buku Hutang** ke dalam format file gambar PNG berlatar belakang putih bersih langsung ke nomor WhatsApp pengurus kampung/BUMDes.

### 7. 🔒 Keamanan & Utilitas Data
* **Keamanan PIN**: Mengunci akses aplikasi dengan username dan PIN guna menghindari penyalahgunaan data.
* **Backup & Restore**: Cadangkan seluruh basis data lokal ke dalam file JSON ke HP, atau pulihkan kembali kapan saja secara offline.
* **Reset Data**: Bersihkan seluruh database untuk memulai pembukuan periode baru.

---

## 🛠️ Arsitektur Teknologi & Pembuatan

Aplikasi ini dibungkus menggunakan arsitektur hybrid WebView yang ringan dengan performa tinggi untuk mendukung perangkat Android dengan spesifikasi rendah:

1. **Frontend (Klien Web)**:
   - **HTML5 & Vanilla CSS**: Desain visual premium modern dengan dukungan adaptif mode terang dan gelap (*Dark/Light Mode*).
   - **Vanilla Javascript**: Pengolahan logika state, pencarian produk, kalkulasi laporan akuntansi, dan rendering grafis canvas.
2. **Android Wrapper (Native)**:
   - **Kotlin (Android SDK)**: WebView client yang dikonfigurasi khusus dengan jembatan komunikasi Javascript Interface (`AndroidStorage`).
   - **Native Storage**: Integrasi `SharedPreferences` Android guna menyimpan data lokal agar tidak terhapus meskipun cache browser dibersihkan.
   - **FileProvider**: Manajemen hak akses dan URI aman untuk melampirkan berkas gambar hasil ekspor langsung ke WhatsApp.

### ⚙️ Konfigurasi Rilis Android
* **SDK Minimum**: API Level 21 (Android 5.0 Lollipop) - memastikan kompatibilitas tinggi pada HP lama.
* **SDK Target**: API Level 34 (Android 14).
* **Sertifikat APK**: Signed release menggunakan keystore produksi (`release_key.jks`, alias: `kioskey`).

---

## 📂 Struktur Repositori

* `/app` - Kode sumber proyek Android Studio (Kotlin, Manifest, Aset Gradle).
* `/app/src/main/assets/index.html` - Sumber kode frontend utama aplikasi (HTML/CSS/JS).
* `/BukuKasKios.apk` - Berkas aplikasi Android rilis final siap pasang.
* `/buku-kas-kios (4).html` - Berkas salinan HTML cadangan untuk pengujian di browser.

---

## ✒️ Hak Cipta & Kontributor

* **Konsep & Perancang Ide**: Yulianti Karoma (KKN FEB UNCEN Papua)
* **Pengembang Aplikasi**: Enterdie ([LinkedIn](https://www.linkedin.com/in/papedatimur))
* **Afiliasi**: KKN FEB Universitas Cenderawasih, Papua - 2026.
* **Slogan**: *"Hen wani Kami Membumi"*

Aplikasi ini didedikasikan secara gratis untuk memajukan perekonomian kampung dan digitalisasi UMKM di Papua.

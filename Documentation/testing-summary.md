# QA Testing Summary - Website Perpanjangan Kartu IoT

## 1. Executive Summary
Laporan ini merupakan ringkasan dari hasil pengujian manual (*manual testing*) pada aplikasi **Autotronic Web (Website Perpanjangan Kartu IoT)**. Berdasarkan hasil pengujian, ditemukan beberapa masalah kritis pada modul *Order* dan validasi *Login* yang memerlukan perbaikan sebelum aplikasi dapat dirilis ke tahap produksi.
*   **Status Keseluruhan:** 🔴 **NO-GO** (Membutuhkan Perbaikan Bug Kritis)
*   **Nama Proyek:** Website Perpanjangan Kartu IoT (Autotronic Web)
*   **Versi Aplikasi:** 1.0.0
*   **Lingkungan (Environment):** Development
*   **Penguji (QA):** Iskandar Zulkarnaen
*   **Tanggal Pengujian Utama:** 21 Januari 2026 - 25 Mei 2026

## 2. Test Execution Metrics (Metrik Pengujian)
Pengujian mencakup skenario Login, Dashboard, Invoice, dan Order Perdana M2M. Berikut adalah metrik hasil eksekusinya:

*   **Total Skenario Uji (Test Cases):** 19
*   **✅ Passed (Berhasil):** 16 (84.2%)
*   **❌ Failed (Gagal):** 3 (15.8%)

## 3. Key Findings & Bug Reports (Temuan Utama)
Terdapat 3 temuan *bug* dari pengujian ini, dengan rincian *severity* mulai dari *Major* hingga *Critical*.

### 🚨 [CRITICAL] TC-ORD-004: Gagal Validasi Order Perdana M2M (Data Quality Kosong)
*   **Deskripsi:** Sistem tidak menampilkan pesan peringatan saat data Quality dikosongkan pada proses Order Perdana M2M. Sistem malah langsung memproses pengiriman data hingga memicu kegagalan sistem (*Server Error*).
*   **Langkah Reproduksi:** 
    1. Buka menu Order Perdana M2M.
    2. Klik tombol Submit tanpa mengisi data *Quality*.
*   **Ekspektasi:** Muncul *pop-up alert* "Data harus diisi".
*   **Aktual:** Sistem tetap memproses submit dan menampilkan *screen server error*.
*   **Status Bug:** New (Assigned to: Emile C.) | **Prioritas:** High

### ⚠️ [MAJOR] TC-LG-003: Login Tanpa Mengisi Password
*   **Deskripsi:** Sistem tetap memproses *login* saat *password* dikosongkan dan tidak menampilkan pesan validasi.
*   **Aktual:** Sistem melakukan proses *loading*, kemudian *user* dikembalikan ke halaman *login* tanpa pesan *error* apa pun (harusnya muncul "Password harus diisi").
*   **Prioritas:** Low

### ⚠️ [UNCLASSIFIED] TC-ORD-003: Order Perdana M2M dengan Semua Data Kosong
*   **Deskripsi:** Saat menekan tombol *Submit* dengan seluruh form kosong, sistem terjebak dalam status *loading* tanpa henti. Tidak ada perpindahan halaman maupun kemunculan *pop-up alert*.

## 4. Test Environment (Lingkungan Pengujian)
Spesifikasi perangkat yang digunakan untuk proses pelaporan *bug* (*Bug Report* TC-ORD-004):
*   **Platform:** PC Desktop
*   **Sistem Operasi:** Windows 11
*   **Browser:** Brave

# FISH Prestasi v6 — versi diperbaiki dan dapat dijalankan

## A. Uji langsung tanpa Google
1. Ekstrak ZIP.
2. Buka `index.html` di Chrome/Edge/Firefox.
3. Isi formulir **Input Data Prestasi**.
4. Centang konfirmasi dan klik **Simpan Data**.
5. Data langsung muncul pada tabel dan tersimpan di `localStorage` browser.

Mode ini cocok untuk pengujian fungsi. File bukti tidak disalin ke Drive; hanya nama file yang dicatat.

## B. Penyimpanan nyata ke Google Sheets + Drive
1. Buka https://script.google.com dan buat project baru.
2. Buat file `Code.gs` dan salin isi `gas/Code.gs`.
3. Buat file HTML bernama `Index` dan salin isi `gas/Index.html`.
4. Jalankan fungsi `initializeSystem()` sekali dari editor Apps Script dan berikan izin.
5. Fungsi tersebut otomatis membuat:
   - Spreadsheet `SISTEM_PRESTASI_FISH`
   - Sheet `Prestasi`
   - Sheet `AuditLog`
   - Folder Drive `BUKTI_PRESTASI_FISH`
6. Pilih **Deploy > New deployment > Web app**.
7. Execute as: akun pemilik sistem. Pilih akses pengguna sesuai kebijakan institusi.
8. Buka URL `/exec` hasil deployment.

Dalam mode Apps Script, tombol **Simpan Data** akan menyimpan record ke Google Sheets dan mengunggah PDF/JPG/PNG ke Google Drive.

## Model data v6
Tidak ada prasyarat master mahasiswa. Setiap rekaman prestasi menyimpan identitas mahasiswa yang diinput manual bersama data prestasi. NIM dapat muncul pada lebih dari satu prestasi. Analisis mahasiswa unik dilakukan dari NIM.

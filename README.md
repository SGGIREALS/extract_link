SGI Extract Link

Tools Ekstraksi Link Brutal untuk Termux & Linux

```
███████╗ ██████╗ ██╗
██╔════╝██╔════╝ ██║
███████╗██║  ███╗██║
╚════██║██║   ██║██║
███████║╚██████╔╝██║
╚══════╝ ╚═════╝ ╚═╝
```

<div align="center">

https://img.shields.io/badge/Python-3.8%2B-blue
https://img.shields.io/badge/License-MIT-green
https://img.shields.io/badge/Platform-Termux%20%7C%20Linux-orange
https://img.shields.io/badge/Version-2.1-red

SGI Extract Link adalah tools ekstraksi link paling brutal yang dioptimalkan untuk Termux dan Linux. Tools ini mampu mengekstrak berbagai jenis link dari website target secara cepat dengan sistem multi-threading.

</div>

---

📋 Daftar Isi

· Fitur Utama
· Tangkapan Layar
· Persyaratan Sistem
· Instalasi
· Cara Penggunaan
· Contoh Penggunaan
· Struktur Output
· Interpretasi Hasil
· Tips & Trik
· Troubleshooting
· Kontribusi
· Lisensi
· Kontak

---

🔥 Fitur Utama

Kategori Fitur Deskripsi
🔗 Link Ekstraksi Link Mengambil semua link dari tag <a>
 Internal/External Memisahkan link internal dan external
 Bruteforce Direktori Mencari direktori tersembunyi (admin, api, dll)
🖼️ Media Gambar Mengekstrak semua URL gambar
 CSS & JavaScript Mengambil semua file stylesheet dan script
 Video & Audio Mendeteksi file media (mp4, mp3, dll)
📧 Kontak Email Mendeteksi alamat email
 Telepon Mengekstrak nomor telepon/WhatsApp
🌐 Social Social Media Menemukan link Facebook, Twitter, Instagram, dll
⚙️ API API Endpoints Mendeteksi endpoint API dari JavaScript
📁 Files Dokumen Mengekstrak PDF, DOC, XLS, PPT, ZIP
 Executable Mendeteksi file EXE, APK, MSI
⚡ Performa Multi-threading Proses parallel dengan thread yang bisa diatur
 Color Output Tampilan berwarna di terminal
 Save to File Menyimpan hasil lengkap ke file teks

---

📸 Tangkapan Layar

```
[12.5s] [INFO] Target: https://csi-india.org
[12.5s] [INFO] Memulai ekstraksi...
[13.2s] [OK] Status: 200 OK
[13.5s] [INFO] Mengekstrak link dari tag <a>...
[14.0s] [OK] Ditemukan 45 link dari tag <a>
[14.5s] [INFO] Mengekstrak gambar...
[15.2s] [OK] Ditemukan 23 gambar
...

============================================================
HASIL EKSTRAKSI SGI
============================================================

STATISTIK UTAMA:
  Total Link: 127
  Internal  : 89
  External  : 38
  Gambar    : 23
  CSS       : 12
  JavaScript: 15
  Forms     : 3
  Iframes   : 2
  Media     : 5
  Dokumen   : 8
  Direktori : 3
```

---

💻 Persyaratan Sistem

Untuk Termux (Android)

Komponen Spesifikasi Minimal
OS Termux (Android 7+)
Python 3.8 atau lebih baru
Storage 50 MB free space
RAM 2 GB (rekomendasi)
Internet Koneksi stabil

Untuk Linux

Komponen Spesifikasi Minimal
OS Ubuntu/Debian/CentOS
Python 3.8 atau lebih baru
Storage 50 MB free space
RAM 1 GB

---

⚙️ Instalasi

Instalasi di Termux

```bash
# 1. Update Termux
pkg update && pkg upgrade -y

# 2. Install Python dan dependencies
pkg install python clang libffi openssl -y

# 3. Clone repository
git clone https://github.com/SGGIREALS/extract_link.git

# 4. Masuk ke direktori
cd extract_link

# 5. Install module Python
pip install requests beautifulsoup4 lxml

# 6. Beri permission
chmod +x sgi.py

# 7. Test instalasi
python sgi.py --help
```

Instalasi di Linux

```bash
# 1. Clone repository
git clone https://github.com/SGGIREALS/extract_link.git

# 2. Masuk ke direktori
cd extract_link

# 3. Install Python dan pip (jika belum ada)
sudo apt update
sudo apt install python3 python3-pip -y

# 4. Install module Python
pip3 install requests beautifulsoup4 lxml

# 5. Beri permission
chmod +x sgi.py

# 6. Test instalasi
python3 sgi.py --help
```

---

🚀 Cara Penggunaan

Format Dasar

```bash
python sgi.py <url> [options]
```

Parameter Options

Option Kepanjangan Deskripsi Default
-t --threads Jumlah thread untuk parallel processing 10
-to --timeout Timeout per request dalam detik 15
-s --save Menyimpan hasil ke file False
-o --output Nama file output kustom Auto
-v --verbose Menampilkan semua link di terminal False
-d --depth Jumlah direktori bruteforce 20
-h --help Menampilkan help -

---

📝 Contoh Penggunaan

1. Scan Basic

```bash
python sgi.py https://csi-india.org
```

2. Scan dengan Thread Tinggi (Lebih Cepat)

```bash
python sgi.py https://csi-india.org -t 30
```

3. Scan dan Simpan Hasil

```bash
python sgi.py https://csi-india.org -s
```

Hasil tersimpan: SGI_csi-india_org_20241225_143022.txt

4. Scan Lengkap dengan Semua Fitur

```bash
python sgi.py https://csi-india.org -t 30 -s -v -d 30
```

5. Custom Output File

```bash
python sgi.py https://csi-india.org -s -o hasil_scan_csi.txt
```

6. Scan Website Lain

```bash
python sgi.py https://example.com -t 20 -s
```

7. Scan dengan Timeout Lebih Lama (Website Lambat)

```bash
python sgi.py https://website-lambat.com -to 30 -t 10
```

---

📁 Struktur Output

Output Terminal

```
[12.5s] [INFO] Target: https://csi-india.org
[12.5s] [INFO] Memulai ekstraksi...
[13.2s] [OK] Status: 200 OK
...
============================================================
HASIL EKSTRAKSI SGI
============================================================

STATISTIK UTAMA:
  Total Link: 127
  Internal  : 89
  External  : 38
  Gambar    : 23
  CSS       : 12
  JavaScript: 15
  Forms     : 3
  Iframes   : 2
  Media     : 5
  Dokumen   : 8
  Direktori : 3

EMAIL DITEMUKAN (2):
  1. info@csi-india.org
  2. contact@csi-india.org

NOMOR TELEPON (1):
  1. +62218888888

SOCIAL MEDIA (3):
  1. https://facebook.com/csindia
  2. https://twitter.com/csindia
  3. https://linkedin.com/company/csi

API ENDPOINTS (2):
  1. https://csi-india.org/api/v1/users
  2. https://csi-india.org/api/members

WAKTU SCAN: 45.23 detik
REQUESTS  : 156 total (142 sukses, 14 gagal)

============================================================
```

Output File (SGI_domain_timestamp.txt)

```
============================================================
SGI EXTRACT LINK - HASIL SCAN
============================================================
Target : https://csi-india.org
Waktu  : 2024-12-25T14:30:22.123456
============================================================

STATISTIK:
  total_links: 127
  internal: 89
  external: 38
  images: 23
  css: 12
  js: 15
  forms: 3
  iframes: 2
  media: 5
  emails: 2
  phones: 1
  social: 3
  apis: 2
  documents: 8
  directories: 3
  scan_duration: 45.23
  requests: 156
  success: 142
  failed: 14

SEMUA LINK (127):
    1. https://csi-india.org/
    2. https://csi-india.org/about
    3. https://csi-india.org/contact
    ...

EMAIL (2):
  • info@csi-india.org
  • contact@csi-india.org

NOMOR TELEPON (1):
  • +62218888888

SOCIAL MEDIA (3):
  • https://facebook.com/csindia
  • https://twitter.com/csindia
  • https://linkedin.com/company/csi

API ENDPOINTS (2):
  • https://csi-india.org/api/v1/users
  • https://csi-india.org/api/members

FILE DOKUMEN:
  PDF (3):
    • https://csi-india.org/docs/annual-report.pdf
    • https://csi-india.org/docs/brochure.pdf
    ...
```

---

📊 Interpretasi Hasil

Kolom Arti
Total Link Semua link yang ditemukan (termasuk duplikat)
Internal Link yang mengarah ke domain yang sama
External Link yang mengarah ke domain lain
Gambar URL file gambar (jpg, png, gif, dll)
CSS File stylesheet
JavaScript File script
Forms Action URL dari form
Iframes Sumber iframe
Media File video/audio
Email Alamat email yang ditemukan
Telepon Nomor telepon
Social Media Link ke platform social media
API Endpoints Endpoint API dari JavaScript
Dokumen File PDF, DOC, XLS, dll
Direktori Direktori tersembunyi yang ditemukan


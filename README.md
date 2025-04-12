# Alphageometry

Panduan berikut ini ditujukan untuk menggunakan Alphageometry. Ikuti langkah-langkah di bawah ini secara berurutan:

## 1. Install Windows Subsystem for Linux (WSL)

Untuk menjalankan perintah dan skrip berbasis Linux pada Windows, Anda perlu menginstall WSL.  
Ikuti panduan instalasi WSL yang tersedia di situs berikut:  
[Install WSL di Windows 11](https://pureinfotech.com/install-wsl-windows-11/)

AlphaGeometry membutuhkan lingkungan Linux karena alat ini dikembangkan untuk berjalan di atas sistem operasi Unix-like. Beberapa dependensi, skrip, dan toolchain yang digunakan dalam AlphaGeometry hanya tersedia atau lebih stabil di Linux. Dengan menggunakan WSL (Windows Subsystem for Linux), Anda dapat menjalankan AlphaGeometry secara langsung di dalam sistem Windows tanpa harus dual-boot atau menggunakan mesin virtual.

## 2. Download dan Install Miniconda pada WSL
 
Setelah proses instalasi WSL selesai, buka terminal WSL, lalu unduh dan install Miniconda dengan mengikuti langkah-langkah pada tautan berikut:

[Install Miniconda di Ubuntu 22.04](https://www.rosehosting.com/blog/how-to-install-miniconda-on-ubuntu-22-04/)  
> **Catatan:** Langkah update juga tersedia secara opsional pada halaman tersebut.

## 3. Membuat Environment Python pada WSL

Setelah Miniconda terpasang, buat environment baru dengan Python versi 3.10.  
Buka terminal (di dalam WSL) dan jalankan perintah berikut:

```bash
conda create -n deepmind python=3.10
```

Setelah proses pembuatan environment selesai, aktifkan environment tersebut:

```bash
conda activate deepmind
```

## 4. Instalasi Dependensi

Pastikan Anda berada di direktori utama proyek (tempat file requirements.txt berada), kemudian jalankan perintah berikut untuk menginstall semua paket yang diperlukan:

```
pip install -r requirements.txt
```

> **Catatan:** Jika file requirements.txt berada di direktori lain, ganti /path/to/requirements.txt dengan path yang sesuai.


## 5. Unzip Meliad

Silahkan unzip meliad sehingga struktur direktori akan terlihat seperti berikut:
```
alphageometry/
├── ag_ckpt_vocab/
│   ├── file1.ext
│   ├── file2.ext
│   └── file3.ext
├── inference.ipynb
├── requirements.txt
└── meliad_lib/
    └── meliad/
```

## 6. Persiapan Berkas Model

Download checkpoint, bobot, dan vocabulary dari link berikut :

https://drive.google.com/drive/u/0/folders/1ZLaZ2ajtOcILDWa5ePPLX1bmaf_BNRZV

Kemudian buat folder bernama ag_ckpt_vocab di dalam direktori utama proyek alphageometry dan pindahkan file yang telah didownload ke dalam folder ag_ckpt_vocab.

Contoh struktur direktori:

```
alphageometry/
├── ag_ckpt_vocab/
│   ├── file1.ext
│   ├── file2.ext
│   └── file3.ext
├── inference.ipynb
└── requirements.txt
```

## 7. Menjalankan Notebook

Buka file inference.ipynb (misalnya menggunakan Jupyter Notebook atau VS Code) dan jalankan perintah-perintah di dalamnya untuk melakukan inferensi menggunakan model.

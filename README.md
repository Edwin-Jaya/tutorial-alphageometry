# Alphageometry

Panduan berikut ini ditujukan untuk pengguna yang baru memulai. Ikuti langkah-langkah di bawah ini secara berurutan:

## 1. Install Windows Subsystem for Linux (WSL)

Untuk menjalankan perintah dan skrip berbasis Linux pada Windows, Anda perlu menginstall WSL.  
Ikuti panduan instalasi WSL yang tersedia di situs berikut:  
[Install WSL di Windows 11](https://pureinfotech.com/install-wsl-windows-11/)

## 2. Download dan Install Miniconda pada WSL

Miniconda merupakan paket manajer yang ringan untuk mengelola environment Python.  
Setelah menginstall, jalankan bash lalu unduh dan install Miniconda dengan mengikuti petunjuk pada tautan berikut:  
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

## 4. Download dan Konfigurasi Meliad

Untuk meng-clone repository meliad dari Google Research dan menambahkan lokasinya ke variabel lingkungan PYTHONPATH, ikuti langkah-langkah berikut:
Jalankan perintah-perintah ini di terminal (dalam WSL) di folder alphageometry:
```
MELIAD_PATH=meliad_lib/meliad

mkdir -p $MELIAD_PATH

git clone https://github.com/google-research/meliad $MELIAD_PATH

export PYTHONPATH=$PYTHONPATH:$MELIAD_PATH
```
Setelah menjalankan perintah-perintah di atas, struktur direktori akan terlihat seperti berikut:
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

## 5. Persiapan Berkas Model

Download ketiga file berikut dari link :

https://drive.google.com/drive/u/0/folders/1ZLaZ2ajtOcILDWa5ePPLX1bmaf_BNRZV

Kemudian buat folder bernama ag_ckpt_vocab di dalam direktori utama proyek alphageometry.
Pindahkan file yang telah didownload ke dalam folder ag_ckpt_vocab.

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

## 6. Instalasi Dependensi

Pastikan Anda berada di direktori utama proyek (tempat file requirements.txt berada), kemudian jalankan perintah berikut untuk menginstall semua paket yang diperlukan:

```
pip install -r requirements.txt
```

> **Catatan:** Jika file requirements.txt berada di direktori lain, ganti /path/to/requirements.txt dengan path yang sesuai.

## 7. Menjalankan Notebook

Buka file inference.ipynb (misalnya menggunakan Jupyter Notebook atau VS Code) dan jalankan perintah-perintah di dalamnya untuk melakukan inferensi menggunakan model.

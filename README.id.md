# Gitea

[![](https://github.com/go-gitea/gitea/actions/workflows/release-nightly.yml/badge.svg?branch=main)](https://github.com/go-gitea/gitea/actions/workflows/release-nightly.yml?query=branch%3Amain "Release Nightly")
[![](https://img.shields.io/discord/322538954119184384.svg?logo=discord&logoColor=white&label=Discord&color=5865F2)](https://discord.gg/Gitea "Join the Discord chat at https://discord.gg/Gitea")
[![](https://goreportcard.com/badge/code.gitea.io/gitea)](https://goreportcard.com/report/code.gitea.io/gitea "Go Report Card")
[![](https://pkg.go.dev/badge/code.gitea.io/gitea?status.svg)](https://pkg.go.dev/code.gitea.io/gitea "GoDoc")
[![](https://img.shields.io/github/release/go-gitea/gitea.svg)](https://github.com/go-gitea/gitea/releases/latest "GitHub release")
[![](https://www.codetriage.com/go-gitea/gitea/badges/users.svg)](https://www.codetriage.com/go-gitea/gitea "Help Contribute to Open Source")
[![](https://opencollective.com/gitea/tiers/backers/badge.svg?label=backers&color=brightgreen)](https://opencollective.com/gitea "Become a backer/sponsor of gitea")
[![](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT "License: MIT")
[![Contribute with Gitpod](https://img.shields.io/badge/Contribute%20with-Gitpod-908a85?logo=gitpod&color=green)](https://gitpod.io/#https://github.com/go-gitea/gitea)
[![](https://badges.crowdin.net/gitea/localized.svg)](https://translate.gitea.com "Crowdin")

[English](./README.md) | [繁體中文](./README.zh-tw.md) | [简体中文](./README.zh-cn.md)

## Tujuan

Tujuan proyek ini adalah menyediakan cara termudah, tercepat, dan tanpa hambatan untuk menyiapkan layanan Git yang di-host sendiri.

Karena Gitea ditulis dalam Go, aplikasi ini berjalan di **semua** platform dan arsitektur yang didukung oleh Go, termasuk Linux, macOS, dan Windows pada arsitektur x86, amd64, ARM, dan PowerPC.
Proyek ini telah [di-fork](https://blog.gitea.com/welcome-to-gitea/) dari [Gogs](https://gogs.io) sejak November 2016, dan banyak hal telah berubah.

Untuk demo online, kunjungi [demo.gitea.com](https://demo.gitea.com).

Untuk mengakses layanan Gitea gratis (dengan jumlah repositori terbatas), kunjungi [gitea.com](https://gitea.com/user/login).

Untuk menerapkan instans Gitea pribadi Anda dengan cepat di Gitea Cloud, mulai uji coba gratis di [cloud.gitea.com](https://cloud.gitea.com).

## Dokumentasi

Dokumentasi lengkap tersedia di [situs dokumentasi resmi](https://docs.gitea.com/) kami.

Mencakup panduan instalasi, administrasi, penggunaan, pengembangan, dan kontribusi untuk membantu Anda memulai dan menjelajahi semua fitur secara efektif.

## Cara Build (Kompilasi)

Dari direktori root kode sumber, jalankan:

    TAGS="bindata" make build

Atau jika diperlukan dukungan SQLite:

    TAGS="bindata sqlite sqlite_unlock_notify" make build

Target `build` dibagi menjadi dua sub-target:

- `make backend` — memerlukan [Go Stable](https://go.dev/dl/), versi yang diperlukan didefinisikan di [go.mod](/go.mod).
- `make frontend` — memerlukan [Node.js LTS](https://nodejs.org/en/download/) atau lebih baru dan [pnpm](https://pnpm.io/installation).

Koneksi internet diperlukan untuk mengunduh modul go dan npm. Saat membangun dari tarbal sumber resmi yang sudah menyertakan file frontend yang telah di-build sebelumnya, target `frontend` tidak akan dipicu, sehingga memungkinkan build tanpa Node.js.

Info lebih lanjut: https://docs.gitea.com/installation/install-from-source

## Cara Menjalankan

Setelah proses build selesai, file biner bernama `gitea` akan dibuat di direktori root kode sumber. Untuk menjalankannya:

    ./gitea web

Aplikasi akan berjalan dan dapat diakses melalui browser di alamat `http://localhost:3000` (secara default).

### Langkah-langkah Cepat

1. **Instal prasyarat:**
   - [Go](https://go.dev/dl/) (versi stabil terbaru)
   - [Node.js LTS](https://nodejs.org/en/download/) dan [pnpm](https://pnpm.io/installation)
   - Git

2. **Clone repositori:**

   ```bash
   git clone https://github.com/go-gitea/gitea.git
   cd gitea
   ```

3. **Build aplikasi:**

   ```bash
   TAGS="bindata" make build
   ```

4. **Jalankan aplikasi:**

   ```bash
   ./gitea web
   ```

5. **Buka browser** dan kunjungi `http://localhost:3000` untuk menyelesaikan pengaturan awal.

> [!NOTE]
> Jika Anda tertarik menggunakan API kami, kami memiliki dukungan eksperimental dengan [dokumentasi](https://docs.gitea.com/api).

## Berkontribusi

Alur kerja yang diharapkan: Fork → Patch → Push → Pull Request

> [!NOTE]
>
> 1. **ANDA HARUS MEMBACA [PANDUAN KONTRIBUTOR](CONTRIBUTING.md) SEBELUM MULAI MENGERJAKAN PULL REQUEST.**
> 2. Jika Anda menemukan kerentanan dalam proyek ini, silakan tulis secara pribadi ke **security@gitea.io**. Terima kasih!

## Lisensi

Proyek ini dilisensikan di bawah Lisensi MIT.
Lihat file [LICENSE](https://github.com/go-gitea/gitea/blob/main/LICENSE) untuk teks lisensi lengkap.

# 🚀 gohttpinjector linux

[![Go Version](https://img.shields.io/badge/Go-v1.21.5%2B-00ADD8?style=flat&logo=go)](https://go.dev)
[![Platform](https://img.shields.io/badge/Platform-Linux%20%2F%20Debian-red?style=flat&logo=debian)](https://www.debian.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

`gohttpinjector` adalah tool proxy HTTP ringan yang ditulis menggunakan bahasa pemrograman Go (Golang). Tool ini dirancang khusus untuk kebutuhan injeksi HTTP header, debugging jaringan, analisis penetrasi ringan, serta pengujian protokol transmisi.

---

## 📌 Ringkasan Proyek

* **Nama Aplikasi:** gohttpinjector
* **Bahasa Pemrograman:** Go (Golang)
* **Fungsi Utama:** HTTP Proxy, Header Injection, & Network Debugging

---

## ✨ Fitur Utama

* 🪶 **Sangat Ringan & Cepat:** Dibangun dengan Go, menghasilkan binary tunggal yang efisien tanpa memerlukan *runtime* tambahan.
* ⚙️ **Konfigurasi :** TLS (SNI>SSH) .
* ⚙️ **Konfigurasi :** TLSMODE (TLS>PROXY>PAYLOAD>SSH) .
* ⚙️ **Konfigurasi :** PAYLOAD (PROXY>PAYLOAD>SSH) .

---

## 🛠️ Prasyarat Sistem

Sebelum melakukan instalasi, pastikan sistem Anda memenuhi persyaratan berikut:

Pasang dependensi awal dengan perintah berikut:
```bash
debian  = sudo apt update && sudo apt install -y sshpas
./main or sudo ./main

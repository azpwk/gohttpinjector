gohttpinjector

Simple HTTP injector written in Go.
Ringkasan

gohttpinjector adalah tool sederhana untuk melakukan HTTP injection, ditulis dengan Go. Cocok untuk debugging jaringan dan pengujian protokol.
Fitur

    HTTP proxy/injector ringan
    Konfigurasi via file YAML
    Opsi baris perintah untuk override konfigurasi
    Build mudah dengan Go (Linux/Debian)

Prasyarat (Debian)

    Debian 10+ atau turunan
    Akses root/sudo untuk instalasi paket

Instalasi Go (Debian)

    Perbarui paket:

sudo apt update

Instal dependensi:

sudo apt install -y curl wget tar git build-essential

Pasang Go (contoh v1.21.5):

    GO_VERSION=1.21.5wget https://go.dev/dl/go${GO_VERSION}.linux-amd64.tar.gzsudo tar -C /usr/local -xzf go${GO_VERSION}.linux-amd64.tar.gzecho 'export PATH=$PATH:/usr/local/go/bin' >> ~/.profilesource ~/.profilego version

Instalasi sshpass (Debian)

sudo apt updatesudo apt install -y sshpass

Catatan: sshpass menyimpan password di command line — gunakan dengan hati-hati. Gunakan SSH key-based auth jika memungkinkan.
Instalasi dan build proyek

    Clone repo:

git clone <URL_REPO>cd <NAMA_REPO>

Bangun:

    go build -o gohttpinjector ./...

Contoh konfigurasi (config.yaml)
yaml

listen: "0.0.0.0:8080"target: "http://example.com"inject_headers:  X-Inject: "true"timeout_seconds: 10

Opsi baris perintah

    -config string Path ke file konfigurasi (default: ./config.yaml)
    -port int Port listen (menimpa konfigurasi)
    -verbose Aktifkan log verbose

(Catatan: sesuaikan nama opsi dengan implementasi di kode.)
Contoh penggunaan

Menjalankan dengan file konfigurasi:

./gohttpinjector -config ./config.yaml

Menjalankan di port 9090:

./gohttpinjector -port 9090

systemd service (contoh)

Buat file /etc/systemd/system/gohttpinjector.service:

[Unit]Description=gohttpinjector serviceAfter=network.target
[Service]Type=simpleUser=rootExecStart=/usr/local/bin/gohttpinjector -config /etc/gohttpinjector/config.yamlRestart=on-failure
[Install]WantedBy=multi-user.target

Aktifkan:

sudo systemctl daemon-reloadsudo systemctl enable --now gohttpinjector

Keamanan

    Jangan simpan kredensial sensitif di file konfigurasi tanpa enkripsi.
    Hindari menyimpan password di skrip; gunakan SSH key untuk otomatisasi.
    Batasi akses jaringan ke service jika perlu.

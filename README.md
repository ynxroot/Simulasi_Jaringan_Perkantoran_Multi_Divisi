# Simulasi Topologi Jaringan Perkantoran Multi-Divisi

Dokumentasi proyek portofolio jaringan komputer ini disusun guna memenuhi standar *Network Fundamentals* menggunakan perangkat lunak **Cisco Packet Tracer**. Proyek ini merancang dan mengimplementasikan jaringan lokal (*Local Area Network* / LAN) skala perkantoran yang terbagi ke dalam beberapa divisi dengan menerapkan teknik *Subnetting* dan *Routing* antar-subnetwork.

---

## 📐 Skema Topologi Jaringan
Berikut adalah gambaran keseluruhan topologi jaringan yang telah dirancang dan diimplementasikan untuk menghubungkan seluruh divisi:

![Topologi Jaringan Keseluruhan](nama-file-gambar-topologi.png)
*(Keterangan: Menampilkan keseluruhan arsitektur jaringan yang terdiri dari 1 unit Router, 3 unit Switch, serta perangkat PC yang terbagi ke dalam Divisi IT, Divisi HR, dan Divisi Finance).*

---

## 📋 Alokasi Pengalamatan IP (Subnetting)
Proyek ini menggunakan blok alamat IP privat kelas C dengan network utama **`192.168.1.0/26`** (`255.255.255.192`) yang dibagi secara terstruktur menjadi tiga subnetwork terisolasi:

| Divisi | Range Alokasi IP (Usable) | IP Default Gateway (Router) | Subnet Mask |
| :--- | :--- | :--- | :--- |
| **Divisi IT** | `192.168.1.2` - `192.168.1.62` | `192.168.1.1` | `255.255.255.192` |
| **Divisi HR** | `192.168.1.66` - `192.168.1.126` | `192.168.1.65` | `255.255.255.192` |
| **Divisi Finance** | `192.168.1.130` - `192.168.1.190` | `192.168.1.129` | `255.255.255.192` |

---

## ⚙️ Konfigurasi Perangkat & Pengujian

### 1. Konfigurasi Antarmuka Router (Gateway)
Router dikonfigurasi menggunakan antarmuka fisik (*Physical Interface*) pada tiap port (*GigabitEthernet*) yang bertindak sebagai pintu gerbang (*Default Gateway*) bagi masing-masing subnetwork divisi.

![Konfigurasi Router](nama-file-gambar-konfigurasi-router.png)
*(Keterangan: Screenshot tampilan konfigurasi IP Address dan status port pada perangkat Router).*

### 2. Pengujian Koneksi Lintas Divisi (Ping Test)
Pengujian komunikasi antar-divisi dilakukan untuk memastikan bahwa proses *routing* berjalan dengan baik dan paket data dapat diteruskan secara akurat setelah proses resolusi ARP selesai.

![Uji Koneksi Berhasil](nama-file-gambar-hasil-ping.png)
*(Keterangan: Screenshot bukti pengujian komunikasi atau status pengiriman paket yang berhasil).*

---

## 🚀 Panduan Penggunaan
1. Pastikan aplikasi **Cisco Packet Tracer** telah terinstal pada perangkat Anda.
2. Unduh berkas proyek berformat **`.pkt`** yang tersedia pada repository ini.
3. Buka berkas tersebut melalui aplikasi Cisco Packet Tracer untuk meninjau detail konfigurasi secara langsung dan melakukan pengujian ulang.

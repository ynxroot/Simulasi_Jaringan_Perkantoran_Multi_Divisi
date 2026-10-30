# Simulasi Topologi Jaringan Perkantoran Multi-Divisi

Proyek portofolio pertama dalam bidang *Network Fundamentals* menggunakan **Cisco Packet Tracer**. Simulasi ini merancang jaringan lokal (LAN) untuk sebuah perkantoran yang dibagi ke dalam beberapa divisi dengan menerapkan konsep *Subnetting* dan *Routing* antar-subnetwork.

---

## 📋 Detail Topologi & Alokasi IP
Proyek ini menggunakan network utama **`192.168.1.0/26`** (`255.255.255.192`) yang dipecah menjadi beberapa subnet terisolasi:

| Divisi | Range IP PC (Usable) | IP Default Gateway (Router) | Subnet Mask |
| :--- | :--- | :--- | :--- |
| **Divisi IT** | `192.168.1.2` - `192.168.1.62` | `192.168.1.1` | `255.255.255.192` |
| **Divisi HR** | `192.168.1.66` - `192.168.1.126` | `192.168.1.65` | `255.255.255.192` |
| **Divisi Finance** | `192.168.1.130` - `192.168.1.190` | `192.168.1.129` | `255.255.255.192` |

---

## 🛠️ Poin Konfigurasi Teknis
* **Router:** Menggunakan port interface fisik (`GigabitEthernet0/0`, `0/1`, `0/2`) yang bertindak sebagai *Default Gateway* untuk masing-masing divisi.
* **Switch:** Menggunakan Switch Layer 2 untuk mendistribusikan koneksi lokal di tiap divisi.
* **Routing Antar-Subnet:** Berhasil menghubungkan komunikasi lintas divisi yang berbeda network secara *seamless* setelah melalui proses *ARP resolution*.

---

## 🚀 Cara Menjalankan Proyek
1. Pastikan komputer lo sudah terinstal aplikasi **Cisco Packet Tracer**.
2. Download file proyek berformat **`.pkt`** dari repository ini.
3. Buka file tersebut menggunakan Cisco Packet Tracer untuk melihat skema topologi dan menguji koneksi (*ping* / kirim amplop antar divisi).

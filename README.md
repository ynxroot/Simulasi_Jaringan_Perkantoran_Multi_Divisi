# Simulasi Topologi Jaringan Perkantoran Multi-Divisi

Dokumentasi proyek portofolio jaringan komputer ini disusun guna memenuhi standar *Network Fundamentals* menggunakan perangkat lunak **Cisco Packet Tracer**. Proyek ini merancang dan mengimplementasikan jaringan lokal (*Local Area Network* / LAN) skala perkantoran yang terbagi ke dalam beberapa divisi dengan menerapkan teknik *Subnetting* dan *Routing* antar-subnetwork.

---

## 📐 Skema Topologi Jaringan
Berikut adalah gambaran keseluruhan topologi jaringan yang telah dirancang dan diimplementasikan untuk menghubungkan seluruh divisi:

<p align="center">
  <img src="https://github.com/user-attachments/assets/dbd85ca7-248e-4848-b5d2-3e6b6646984f" alt="Topologi Jaringan Keseluruhan" width="850">
  <br>
  <em>(Keterangan: Menampilkan keseluruhan arsitektur jaringan yang terdiri dari 1 unit Router, 3 unit Switch, serta perangkat PC yang terbagi ke dalam Divisi IT, Divisi HR, dan Divisi Finance).</em>
</p>


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

<p align="center">
  <img src="https://github.com/user-attachments/assets/e4f4255c-ab56-471f-ac1f-599de8ff4fc6" alt="Konfigurasi Router IT" width="260" style="margin: 5px;">
  <img src="https://github.com/user-attachments/assets/7c9961a2-91dc-4781-ac50-6a589917985b" alt="Konfigurasi Router HR" width="260" style="margin: 5px;">
  <img src="https://github.com/user-attachments/assets/db7e75dc-834b-4199-b647-355372d3e694" alt="Konfigurasi Router Finance" width="260" style="margin: 5px;">
  <br>
  <em>(Keterangan: Screenshot tampilan konfigurasi IP Address dan status port pada perangkat Router untuk masing-masing divisi).</em>
</p>



### 2. Pengujian Koneksi Lintas Divisi (Ping Test)
Pengujian komunikasi antar-divisi dilakukan untuk memastikan bahwa proses *routing* berjalan dengan baik dan paket data dapat diteruskan secara akurat setelah proses resolusi ARP selesai.

| Asal Perangkat (IP) | Tujuan Perangkat (IP) | Jenis Pengujian | Status Hasil |
| :--- | :--- | :--- | :--- |
| **PC Divisi IT** (`192.168.1.2`) | **PC Divisi HR** (`192.168.1.66`) | ICMP (Ping Test) | **Berhasil (Success)** |

<p align="center">
  <br>
  <strong>Opsi 1: Pengujian Via Paket (PDU Realtime Status)</strong>
  <br>
  <img src="https://github.com/user-attachments/assets/a31f5020-c336-4f3a-b8bb-dd89465a33c7" alt="Status Ping Sukses" width="600" style="margin-top: 5px; margin-bottom: 20px;">
  <br>
  <br>
  <strong>Opsi 2: Pengujian Via CLI (Command Prompt ICMP Ping)</strong>
  <br>
  <img src="https://github.com/user-attachments/assets/944f8e0b-387f-499b-ad5f-7705f82540d9" alt="Detail Command Prompt Ping" width="550" style="margin-top: 5px; margin-bottom: 15px;">
  <br>
  <em>(Keterangan: Screenshot bukti pengujian komunikasi lintas divisi menggunakan metode kirim paket data PDU dan perintah ping berbasis teks).</em>
</p>



---

## 🚀 Panduan Penggunaan
1. Pastikan aplikasi **Cisco Packet Tracer** telah terinstal pada perangkat Anda.
2. Unduh berkas proyek berformat **`.pkt`** yang tersedia pada repository ini.
3. Buka berkas tersebut melalui aplikasi Cisco Packet Tracer untuk meninjau detail konfigurasi secara langsung dan melakukan pengujian ulang.

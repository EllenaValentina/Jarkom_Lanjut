# SOAL ESSAY
## 1. Jelaskan menurut anda apa itu Routing Static?
Routing static adalah sebuah rute jaringan yang harus di konfigurasi secara manual oleh seorang teknisi
**- Lakukan Konfigurasi IP Address pada mikrotik 1**
- Buka Winbox64.exe -> login mikrotik
- Sambungkan laptop ke ether3, set IP Address -> tambahkan (+) 192.168.10.3/24 -> Apply -> OK
- Sambungkan ke mikrotik 2 di ether1, set IP Address -> tambahkan (+) 192.168.1.1/24 -> Apply -> OK
**- Lakukan Konfigurasi IP Address pada mikrotik 2**
- Buka Winbox64.exe -> login mikrotik
- Sambungkan laptop ke ether3, set IP Address -> tambahkan (+)  192.168.20.3/24 -> Apply -> OK
- Sambungkan ke mikrotik 1 di ether1, set IP Address -> tambahkan (+) 192.168.1.2/24 -> Apply -> OK
**- Lakukan Konfigurasi DHCP Server** 
### DHCP Server pada Mikrotik 1
- Buka IP -> DHCP Server -> DHCP Setup (Interface ether3)
### DHCP Server pada mikrotik 2
- Buka IP -> DHCP Server -> DHCP Setup (Interface ether 3)
**- Lakukan Setting Route**
### Routing di mikrotik 1
- Buka IP -> Routes
    - tambah (+) -> masukan Destination Address dengan IP 192.168.20.0/24 **(network di mikrotik 2)** -> masukan Gateway dengan IP 192.168.100.10 **(IP mikrotik 2 yang terhubung ke mikrotik 1)**
**Tes Koneksi**
- Setelah laptop dan mikrotik telah terhubung pastikan juga laptop mendapatkan IP Address DHCP Server yang sudah dikonfigurasi
- **Laptop yang terhubung pada mikrotik 1**
    - Buka terminal dan ping IP laptop yang terhubung ke mikrotik 2
- Ping akan muncul 
### Note: pastikan firewawll pada laptop dan internet mati, pastikan kedua DHCP reachable. Jika masih belum bisa lakukan disable/unable pada ether di control panel pada bagian internet dan ether.

## 2. Jelaskan menurut anda apa itu Routing Dynamic?
Berbeda dengan routing static, routing dynamic ini qdalah rute jaringan yang terisi otomatis tanpa harus di konfigurasi
**Pada mikrotik 1**
- Set IP Address:
    - Mikrotik 1 di ether 1 (192.168.1.1/24)
    - Laptop 1 di ether 2 (192.168.10.1/24)
- Set DHCP Server
- Ke terminal laptop -> ipconfig pada root
- Di Winbox ke routing -> RIP
    - set interface ether 1 dan 2
    - set networks:
        - 192,168,1.0/24
        - 192.168.10.0/24
- Cek route
**Pada mikrotik 2**
-Set IP Address:
    - Mikrotik 1 di ether 1 (192.168.2.1/24)
    - Laptop 1 di ether 2 (192.168.20.1/24)
- Set DHCP Server
- Ke terminal laptop -> ipconfig pada root
- Di Winbox ke routing -> RIP
    - set interface ether 1 dan 2
    - set networks:
        - 192,168,2.0/24
        - 192.168.20.0/24
- Cek route

## 3. Jelaskan menurut anda apa itu Firewall?
Seperti namanya, Firewall adalah sebuh dinding pertahanan/keamanan jaringan pada laptop untuk memantau dan mengontrol lalu lintas data yang masuk dan keluar dan melindungi laptop dari berbagai ancaman yang datang dari luar

## 4. Jelaskan menurut anda apa itu NAT?
NAT (Network Address Translation) adalah suatu jaringan komputer yang berfungsi untuk memudahkan perangkat-perangkat yang ada untuk terhubung ke internet


### Penjelasan Cased
Topologi ini menghubungkan router di kampus CR, KHI, dan KJ menggunakan VLAN untuk komunikasi antar kampus. Setiap kampus menggunakan router sebagai pengelola LAN, dan koneksi antar kampus diasumsikan terhubung melalui jalur fiber optik.
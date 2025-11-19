### Implementasi Socket Programming pada Protokol TCP dan UDP Menggunakan Python
## 1. Pendahuluan

Dua jenis protokol yang digunakan adalah Transmission Control Protocol (TCP) dan User Datagram Protocol (UDP).
Tujuan utama proyek ini adalah memberikan pemahaman dasar mengenai mekanisme komunikasi antara client dan server melalui jaringan lokal dengan menggunakan kedua protokol tersebut.

## 2. Ruang Lingkup

Proyek ini mencakup:

Implementasi server dan client menggunakan protokol TCP

Implementasi server dan client menggunakan protokol UDP

Pengujian komunikasi antar program dalam satu perangkat (localhost)

Analisis sederhana mengenai perbedaan karakteristik TCP dan UDP

## 3. Struktur Direktori
Python/

├── tcpServer.py      
├── tcpSocket.py      
├── udpServer.py      
└── udpSocket.py      

## 4. Deskripsi Program
# 4.1 Implementasi TCP

TCP merupakan protokol komunikasi yang bersifat connection-oriented. Sebelum terjadi pertukaran data, server dan client harus membangun koneksi terlebih dahulu. Protokol ini menjamin data dikirim secara berurutan, utuh, dan tanpa kehilangan paket.

# 4.1.1 tcpServer.py

Fungsi utama:

Mengaktifkan server pada alamat 127.0.0.1 dengan port 12345

Menunggu client melakukan koneksi

Menerima pesan dari client

Mengubah pesan menjadi huruf kapital

Mengirim kembali hasil pemrosesan ke client

Contoh keluaran server:

Koneksi dari 127.0.0.1:54321 Telah dibangun!

# 4.1.2 tcpSocket.py

Fungsi utama:

Menghubungkan client ke server TCP

Mengirim data yang diinput oleh pengguna

Menerima respon dari server

Menampilkan data hasil pemrosesan

Contoh keluaran client:

masukkan pesan untuk dikirim ke server: hello world
Server response: HELLO WORLD

# 4.2 Implementasi UDP

UDP merupakan protokol komunikasi yang bersifat connectionless. Protokol ini tidak memerlukan proses handshake sebelum pengiriman data. Karakteristiknya yang ringan membuat UDP cocok untuk aplikasi yang membutuhkan kecepatan tinggi, meskipun tidak menjamin keutuhan data.

# 4.2.1 udpServer.py

Fungsi utama:

Mengaktifkan server pada alamat 127.0.0.1 dengan port 9997

Menerima pesan dari client tanpa membangun koneksi

Menampilkan isi pesan serta alamat pengirim

Mengirimkan balasan berupa teks tetap

Contoh keluaran server:

UDP server menyala
Pesan dari Client: b'Lampu makan'
IP Client: ('127.0.0.1', 52431)

# 4.2.2 udpSocket.py

Fungsi utama:

Mengirim pesan ke server UDP

Menerima balasan server

Menampilkan respon yang diterima

Contoh keluaran client:

Pesan dari server: "Selamat datang di UDP Server"

# 5. Cara Menjalankan Program
# 5.1 Prasyarat

Python 3.x telah terinstal

Sistem operasi Windows, Linux, atau macOS

Terminal atau Command Prompt

#  5.2 Langkah Menjalankan TCP

Buka terminal pertama dan jalankan:

python tcpServer.py

<img width="753" height="108" alt="tcpServer" src="https://github.com/user-attachments/assets/9bf6e9d4-af50-4e47-bce8-a0f6e015263a" />




Buka terminal kedua dan jalankan:

python tcpSocket.py

<img width="740" height="141" alt="tcpSocket" src="https://github.com/user-attachments/assets/06441ec2-4589-4704-82f1-2c3865c45090" />




# 5.3 Langkah Menjalankan UDP

Jalankan server UDP:

python udpServer.py

<img width="726" height="130" alt="udpServer" src="https://github.com/user-attachments/assets/87987a3c-3db8-42f1-a98d-4f7606007c33" />



Jalankan client UDP:

python udpSocket.py

<img width="762" height="117" alt="udpSocked" src="https://github.com/user-attachments/assets/284de9e6-c969-44a7-859b-e359676c99d0" />




# 6. Analisis dan Hasil
# 6.1 Hasil Implementasi TCP

Pada saat pengujian, client berhasil mengirimkan pesan teks ke server, kemudian server memproses pesan tersebut menjadi huruf kapital dan mengirimkannya kembali.
Hal ini menunjukkan bahwa komunikasi dua arah berjalan dengan baik dan alur TCP telah bekerja sesuai konsep protokolnya: membangun koneksi, mentransfer data, dan menutup koneksi.

# 6.2 Hasil Implementasi UDP

Client mengirimkan pesan sederhana kepada server UDP, kemudian server mengembalikan pesan balasan tanpa perlu melakukan proses koneksi.
Hasil pengujian mengonfirmasi bahwa UDP bekerja dengan mekanisme pengiriman cepat dan sederhana tanpa jaminan keutuhan data. Namun dalam pengujian lokal, data diterima dengan baik.

# 7. Kesimpulan

Proyek ini berhasil menunjukkan:

Cara kerja TCP dan UDP melalui implementasi server-client sederhana

Perbedaanperilaku antara protokol yang bersifat connection-oriented (TCP) dan connectionless (UDP)

Penggunaan socket Python sebagai dasar komunikasi jaringan

Implementasi ini dapat dijadikan dasar untuk pengembangan aplikasi jaringan yang lebih kompleks seperti chat system, file transfer, atau real-time communication.

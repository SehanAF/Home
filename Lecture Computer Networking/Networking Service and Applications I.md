# ⭐️ Course Contents ⭐️ 

⌨️ ([0:15:12](https://www.youtube.com/watch?v=qiQR5rTSshw&t=912s)) Networking Services and Applications (part 1)

## Membahas Tentang

![[Pasted image 20230404131318.png]]

## The Basics of The Virtual Private Network

Jaringan pribadi virtual atau VPN digunakan oleh host jarak jauh untuk mengakses jaringan pribadi melalui terowongan terenkripsi melalui jaringan publik. Setelah koneksi VPN dibuat, host jarak jauh tidak lagi dianggap sebagai host jarak jauh, tetapi dianggap sebagai host lokal oleh jaringan privat.

Ada banyak keuntungannya, tetapi saya tidak akan membahasnya sekarang. Meskipun lalu lintas jaringan mungkin melewati banyak rute atau sistem yang berbeda, namun kedua ujungnya terlihat sebagai koneksi langsung. Penggunaan VPN dapat membantu mengurangi biaya jaringan, untuk organisasi dan bisnis.

Pengurangan biaya sebagian tercapai, karena VPN tidak memerlukan penggunaan jalur leased line khusus untuk membuat koneksi langsung tersebut. Ada beberapa jenis VPN yang berbeda, yaitu VPN situs ke situs, yang memungkinkan jaringan situs jarak jauh untuk terhubung ke jaringan situs utama dan dilihat sebagai segmen jaringan lokal. Konsentrator VPN di kedua ujung VPN akan mengelola koneksi tersebut.

![[Pasted image 20230404131453.png]]

Lebih detail tentang [[TB VPN]].

### VPN Types

ada beberapa tipe VPN yang dapat digunakan tergantung pada kebutuhan pengguna. VPN Remote Access digunakan oleh karyawan yang bekerja dari jarak jauh atau bepergian, VPN Site-to-Site digunakan oleh perusahaan yang membutuhkan akses ke sumber daya dari jaringan lain, dan VPN SSL/TLS digunakan oleh perusahaan yang membutuhkan akses jarak jauh ke sumber daya korporat tanpa memerlukan software khusus. Selain itu, VPN IPSec, VPN MPLS, dan VPN PPTP juga dapat digunakan tergantung pada kebutuhan pengguna. 

#### VPN Site-to-Site 

Memungkinkan dua atau lebih jaringan terhubung ke jaringan korporat melalui internet. Dalam tipe ini, koneksi diatur antara dua titik akhir yang berbeda, sehingga memungkinkan pengguna mengakses sumber daya yang berada di jaringan lain.

![[Pasted image 20230404132348.png]]

Lebih detail tentang [[VPN Site-to-Site]].

#### VPN Remote Access

Memungkinkan pengguna untuk terhubung dengan jaringan korporat dari luar jaringan menggunakan internet publik. Tipe ini umumnya digunakan oleh karyawan yang bekerja dari jarak jauh atau bepergian.

![[Pasted image 20230404133307.png]]

Lebih detail tentang [[VPN Remote Access]].

#### VPN SSL/TLS

Menggunakan teknologi Secure Socket Layer (SSL) atau Transport Layer Security (TLS) untuk mengenkripsi data pengguna. Tipe ini biasanya digunakan oleh perusahaan yang membutuhkan akses jarak jauh ke sumber daya korporat tanpa memerlukan software khusus.

![[Pasted image 20230404133529.png]]

Lebih detail tentang [[VPN SSL dan TLS]].

### [[Summary VPN Types]]  

## Protocol Used by The Virtual Private Network

Protocol Used by The Virtual Private Network adalah protokol atau standar yang digunakan untuk mengamankan koneksi internet dan data yang ditransmisikan melalui jaringan publik seperti internet. Protokol ini memungkinkan pengguna untuk terhubung ke jaringan pribadi melalui koneksi internet, sehingga membuat pengguna dapat mengakses sumber daya jaringan pribadi dengan aman dari mana saja di dunia. Protokol ini dapat berbeda-beda tergantung pada jenis dan tujuan VPN yang digunakan. Protokol VPN umumnya menggunakan enkripsi yang kuat dan teknologi keamanan lainnya untuk melindungi data dari ancaman cyber dan hacker.

### Internet Protocol Security ( IPsec )

Internet Protocol Security (IPsec) adalah protokol keamanan yang digunakan untuk melindungi komunikasi data yang terjadi di atas jaringan internet. IPsec menggunakan teknologi enkripsi untuk mengamankan data dari ancaman peretasan dan penyadapan. Dengan menggunakan IPsec, pengguna dapat membuat jaringan pribadi virtual (Virtual Private Network/VPN) yang aman dan terlindungi dari ancaman cyber. IPsec dapat digunakan untuk mengamankan berbagai jenis protokol jaringan, termasuk protokol TCP (Transmission Control Protocol) dan UDP (User Datagram Protocol). IPsec juga mendukung berbagai jenis metode enkripsi dan otorisasi, sehingga pengguna dapat memilih metode yang paling sesuai dengan kebutuhan mereka. IPsec juga dapat digunakan dengan mudah dan fleksibel, sehingga cocok digunakan oleh perusahaan atau organisasi dengan skala besar.

![[Pasted image 20230404135103.png]]

Lebih detail tentang [[IPsec]].

### Generic Routing Encapsulation ( GRE )

Generic Routing Encapsulation (GRE) adalah sebuah protokol jaringan yang digunakan untuk mengirimkan data melalui jaringan IP. GRE memungkinkan pengguna untuk mengirimkan paket data yang telah dienkapsulasi ke dalam sebuah paket IP. Dengan menggunakan GRE, pengguna dapat membuat sebuah jalur virtual (tunnel) di atas jaringan IP yang dapat digunakan untuk mengirimkan data dari satu jaringan ke jaringan lainnya. GRE sangat berguna dalam situasi di mana pengguna perlu mengirimkan data melalui jaringan publik, seperti internet, dengan aman dan terlindungi dari ancaman peretasan dan penyadapan. GRE juga dapat digunakan untuk mengatasi masalah dengan jaringan yang tidak kompatibel, misalnya dalam kasus di mana pengguna perlu menghubungkan jaringan yang berbeda jenis, atau ketika terjadi masalah dengan protokol jaringan yang digunakan. GRE dapat diintegrasikan dengan berbagai jenis protokol jaringan, termasuk IPsec, sehingga memungkinkan pengguna untuk membuat jalur virtual yang aman dan terlindungi dari ancaman cyber.

Lebih detail tentang [[GRE]].

### Point-to-Point Tunneling Protocol ( PPTP )

PPTP adalah protokol VPN yang paling umum digunakan. Protokol ini bekerja dengan mengenkripsi data yang dikirim melalui tunnel antara server VPN dan klien VPN. Meskipun mudah digunakan dan cepat, PPTP dianggap kurang aman karena enkripsi yang digunakan tidak terlalu kuat.

Lebih detail tentang [[PPTP]].

![[Pasted image 20230404141033.png]]

### Transport Layer Security ( TLS ) Protocol

TLS adalah singkatan dari "Transport Layer Security". Ini adalah protokol keamanan yang digunakan untuk melindungi privasi dan integritas data yang ditransmisikan melalui jaringan komputer, seperti internet. TLS digunakan untuk mengenkripsi data antara server dan client, sehingga mencegah pihak yang tidak berwenang untuk mengakses atau mengubah data tersebut. TLS sering digunakan dalam aplikasi web, seperti situs web e-commerce dan perbankan online, di mana privasi dan keamanan data sangat penting.

Lebih detail tentang [[TLS]].

### Secure Socket Layer ( SSL ) Protocol

SSL adalah singkatan dari "Secure Sockets Layer". Ini adalah protokol keamanan kuno yang digunakan untuk melindungi privasi dan integritas data yang ditransmisikan melalui jaringan komputer, seperti internet. SSL digunakan untuk mengenkripsi data antara server dan client, sehingga mencegah pihak yang tidak berwenang untuk mengakses atau mengubah data tersebut. Namun, saat ini SSL telah digantikan oleh TLS (Transport Layer Security) yang lebih aman dan efektif. TLS menggantikan SSL karena beberapa kelemahan keamanan yang ditemukan pada SSL. Oleh karena itu, disarankan untuk tidak menggunakan SSL dan beralih ke TLS untuk keamanan dan privasi yang lebih baik.

Lebih detail tentang [[SSL]].

![[Pasted image 20230404142304.png]]



### [[Summary Protocol VPN]]

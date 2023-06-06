# ⭐️ Course Contents ⭐️ 

[41:06](https://www.youtube.com/watch?v=3FNYvj2U0HM&t=2466s) - IP Addresses
[54:18](https://www.youtube.com/watch?v=3FNYvj2U0HM&t=3258s) - MAC Addresses
[57:35](https://www.youtube.com/watch?v=3FNYvj2U0HM&t=3455s) - TCP, UDP, & the Three-Way Handshake
[1:02:51](https://www.youtube.com/watch?v=3FNYvj2U0HM&t=3771s) - Common Ports & Protocols
[1:09:04](https://www.youtube.com/watch?v=3FNYvj2U0HM&t=4144s) - The OSI Model
[1:14:39](https://www.youtube.com/watch?v=3FNYvj2U0HM&t=4479s) - Subnetting, Part 1
[1:41:42](https://www.youtube.com/watch?v=3FNYvj2U0HM&t=6102s) - Subnetting, Part 2

# IP Addresses

Alamat IP adalah identifikasi numerik unik untuk setiap perangkat yang terhubung ke internet, terdiri dari alamat jaringan dan alamat host.  IP adalah singkatan dari “Internet Protocol”, alamat IP memungkinkan perangkat untuk berkomunikasi antar jaringan dan juga digunakan untuk menentukan lokasi geografis perangkat. Ada dua versi alamat IP yang umum digunakan saat ini, yaitu IPv4 dan IPv6. Alamat IP juga berperan dalam keamanan jaringan dan harus diperhatikan untuk menjaga privasi online.

Lebih detail tentang [[IP Addresses]] (https://en.wikipedia.org/wiki/IP_address).

- Cara melihat IP Addresses di terminal.
![[Pasted image 20230408204600.png]]

## Private IP Addresses

Alamat IP privat adalah alamat IP yang digunakan dalam jaringan lokal dan tidak dapat diakses dari internet. Alamat IP privat tidak unik secara global, artinya beberapa perangkat di jaringan lokal yang berbeda dapat menggunakan alamat IP yang sama tanpa menimbulkan konflik. 

Lebih detail tentang [[Private IP Addresses]] (https://en.wikipedia.org/wiki/Private_network).

![[Pasted image 20230408204953.png]]

# MAC Addresses

Alamat MAC (Media Access Control) adalah alamat unik yang diberikan kepada setiap perangkat jaringan seperti komputer atau printer. Alamat MAC terdiri dari 48 bit biner, yang biasanya dinyatakan dalam notasi heksadesimal dengan dua digit untuk setiap byte. Alamat MAC terintegrasi dalam hardware perangkat jaringan dan tidak dapat diubah atau diubah secara manual. Alamat MAC digunakan dalam jaringan Ethernet untuk mengatur akses ke media jaringan dan mengidentifikasi perangkat di dalam jaringan. Alamat MAC penting dalam pengaturan jaringan dan dapat digunakan untuk menetapkan akses jaringan tertentu atau mengamankan jaringan dengan mengizinkan hanya perangkat yang diizinkan yang dapat terhubung ke jaringan.

Lebih detail tentang [[MAC Addresses]] (https://en.wikipedia.org/wiki/MAC_address).

![[Pasted image 20230408205920.png]]

# TCP

TCP atau Transmission Control Protocol adalah protokol yang sangat penting dalam dunia jaringan komputer. Ia memastikan koneksi yang handal antara perangkat dengan memastikan bahwa data yang dikirimkan tiba dengan aman dan benar. TCP juga memungkinkan pengiriman data yang diprioritaskan, sehingga data yang lebih penting dapat dikirimkan lebih cepat. Selain itu, TCP memiliki kemampuan untuk mengatur aliran data, sehingga data tidak mengalir terlalu cepat atau terlalu lambat. TCP sangat penting dalam pengaturan jaringan dan digunakan pada banyak protokol jaringan seperti HTTP, FTP, dan SMTP. Dengan menggunakan TCP, Anda dapat memast
ikan bahwa data Anda dikirim dengan aman dan efisien melalui jaringan.

Lebih detail tentang [[TCP]] (https://en.wikipedia.org/wiki/Transmission_Control_Protocol).

![[Pasted image 20230408210719.png]]

# UDP

UDP atau User Datagram Protocol adalah protokol jaringan yang tidak andal, artinya ia tidak memastikan pengiriman data yang sempurna dan tidak memiliki mekanisme pemulihan kesalahan. UDP dikembangkan pada tahun 1980-an oleh David P. Reed dan digunakan pada hampir semua aplikasi jaringan di internet. UDP sangat cocok digunakan dalam aplikasi real-time seperti video streaming atau game online, di mana kecepatan pengiriman data lebih penting daripada keandalan pengiriman data. Meskipun tidak andal, UDP memiliki kecepatan pengiriman data yang lebih cepat dan lebih efisien daripada protokol TCP. Walaupun demikian, penggunaan UDP yang tepat dapat meningkatkan efisiensi dan performa jaringan.

Lebih detail tentang [[UDP]] (https://id.wikipedia.org/wiki/Protokol_Datagram_Pengguna).

![[Pasted image 20230408211256.png]]

# The Three-Way Handshake

The Three-Way Handshake adalah proses yang digunakan untuk membentuk koneksi TCP antara dua perangkat. Proses ini terdiri dari tiga tahap, yaitu SYN, SYN-ACK, dan ACK. Pada tahap pertama, perangkat pengirim mengirimkan pesan SYN ke perangkat tujuan. Kemudian pada tahap kedua, perangkat tujuan merespon dengan mengirimkan pesan SYN-ACK sebagai tanda bahwa ia siap untuk membentuk koneksi. Pada tahap terakhir, perangkat pengirim merespon dengan mengirimkan pesan ACK sebagai tanda bahwa koneksi telah berhasil dibentuk. The Three-Way Handshake sangat penting karena ia memastikan bahwa koneksi antara dua perangkat dapat dibentuk dengan aman dan terjamin, sehingga memastikan bahwa data yang dikirimkan dapat sampai ke tujuan dengan aman dan terjamin.

Lebih detail tentang [[Handshake]] (https://en.wikipedia.org/wiki/Handshake_(computing)).

![[Pasted image 20230408213127.png]]

# Common Ports

Common ports atau port umum adalah nomor yang digunakan untuk mengidentifikasi layanan atau protokol tertentu yang berjalan pada perangkat dalam jaringan komputer. Contoh dari common ports adalah port 80 yang digunakan untuk HTTP (Hypertext Transfer Protocol), port 443 untuk HTTPS (Hypertext Transfer Protocol Secure), port 25 untuk SMTP (Simple Mail Transfer Protocol), dan port 22 untuk SSH (Secure Shell). Setiap layanan atau protokol memiliki nomor port yang unik untuk memudahkan pengiriman data ke layanan atau protokol tersebut. Penggunaan common ports sangat penting dalam memastikan komunikasi yang efisien dan efektif antara perangkat dalam jaringan.

Lebih detail tentang [[Common Ports]] (https://en.wikipedia.org/wiki/Port_(computer_networking)).

![[Pasted image 20230408230133.png]]

# Protocols

Protokol adalah seperangkat aturan atau format yang digunakan untuk mengatur dan mengirim data dalam jaringan komputer. Protokol memastikan komunikasi yang efisien dan efektif antara perangkat dalam jaringan, serta mempertahankan keamanan dan privasi data dalam jaringan. Beberapa contoh protokol yang umum digunakan adalah TCP, IP, HTTP, FTP, dan DNS. Protokol TCP/IP merupakan protokol yang paling umum digunakan pada saat ini. Protokol sangat penting dalam memastikan komunikasi yang efektif antara perangkat dalam jaringan.

Lebih detail tentang [[Protocols]] (https://en.wikipedia.org/wiki/Lists_of_network_protocols).

![[Pasted image 20230408230920.png]]

# The OSI Model

OSI atau Open Systems Interconnection adalah sebuah model referensi untuk jaringan komputer yang terdiri dari tujuh lapisan. Model ini diciptakan oleh ISO pada tahun 1984 untuk memudahkan interkomunikasi antar sistem yang berbeda-beda. Setiap lapisan memiliki tugas dan fungsi masing-masing, yang membentuk sebuah sistem yang terintegrasi dan efektif, serta memudahkan interoperabilitas antar sistem yang berbeda-beda. Model OSI merupakan standar internasional yang diakui secara luas oleh industri dan organisasi di seluruh dunia.

Lebih detail tentang [[OSI]] (https://id.wikipedia.org/wiki/Model_OSI).

![[Pasted image 20230402071540.png]]

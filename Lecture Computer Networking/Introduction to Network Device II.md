# ⭐️ Course Contents ⭐️ 

⌨️ ([0:07:24](https://www.youtube.com/watch?v=qiQR5rTSshw&t=444s)) Intro to Network Devices (part 2)

Membahas tentang: 
- Security Device
- Optimization and Performance Devices

## Security Device

Security device dalam jaringan komputer adalah perangkat atau perangkat lunak yang dirancang untuk melindungi jaringan komputer dari ancaman keamanan seperti virus, malware, serangan DoS, serangan DDoS, dan serangan siber lainnya. Beberapa contoh perangkat keamanan jaringan adalah firewall, IDS (intrusion detection system), IPS (intrusion prevention system), VPN (virtual private network), dan antivirus.

Lebih detail tentang [[Security Device]] ([What is Device Security? Device Security Strategies - Citrix](https://www.citrix.com/solutions/secure-access/what-is-device-security.html)).

![[Pasted image 20230410105350.png]]

## Optimization and Performance Devices

Optimization and Performance Devices adalah perangkat keras atau lunak yang dirancang untuk meningkatkan kinerja jaringan komputer dan aplikasi. Tujuannya adalah untuk memaksimalkan penggunaan sumber daya jaringan dan memastikan aplikasi berjalan dengan lancar dan efisien. Jenis perangkat ini termasuk load balancer, wan optimizer, network analyzer, content delivery network, dan application delivery controller. Perangkat ini membantu meningkatkan kinerja jaringan dan aplikasi sehingga organisasi dapat meningkatkan efisiensi dan produktivitas.

Lebih detail tentang [[Optimization and Performance Devices]].

### Firewall

Pertama adalah firewall. Sekarang firewall dapat ditempatkan pada router atau host yang bisa berbasis perangkat lunak atau bisa juga perangkatnya sendiri.

Firewall berfungsi pada beberapa lapisan model OSI, khususnya pada lapisan 2, 3, 4 dan 7. Firewall dapat memblokir paket yang masuk atau keluar dari jaringan. Dan ini dilakukan melalui salah satu dari dua metode yang dapat dilakukannya melalui inspeksi tanpa kewarganegaraan, di mana firewall akan memeriksa setiap paket yang masuk atau keluar dari jaringan terhadap seperangkat aturan.

Setelah paket cocok dengan sebuah aturan, aturan tersebut akan diberlakukan dengan tindakan yang ditentukan, atau mungkin menggunakan inspeksi penuh status. Ini adalah saat firewall hanya akan memeriksa status koneksi antar jaringan. Secara khusus, ketika koneksi dibuat dari jaringan internal ke jaringan eksternal. Firewall tidak akan memeriksa paket apa pun yang kembali dari koneksi eksternal. Ia hanya peduli dengan status koneksi.

Sebagai aturan umum, sambungan eksternal tidak diizinkan untuk dimulai dengan jaringan internal. Sekarang firewall adalah garis pertahanan pertama dalam melindungi jaringan internal dari ancaman luar. Anda bisa menganggap firewall sebagai polisi dalam jaringan.

![[Pasted image 20230403104458.png]]

Lebih detail tentang [[Firewall]] (https://en.wikipedia.org/wiki/Firewall_(computing).

### Intrusion detection system (IDS)

IDS dan IDS adalah sistem pasif yang dirancang untuk mengidentifikasi ketika pelanggaran jaringan atau serangan terhadap jaringan terjadi. Mereka biasanya dirancang untuk memberi tahu administrator jaringan ketika pelanggaran atau serangan terjadi. Dan hal ini dilakukan melalui file log, pesan teks, dan melalui pemberitahuan email Teman, dan IDS tidak dapat mencegah atau menghentikan pelanggaran atau serangan dengan sendirinya.

IDS menerima salinan semua lalu lintas dan mengevaluasinya terhadap seperangkat standar. Standar yang digunakannya mungkin berbasis tanda tangan. Ini adalah saat IDS mengevaluasi lalu lintas jaringan untuk mengetahui adanya malware atau tanda tangan serangan, atau standar yang digunakan mungkin berbasis anomali. Di sinilah ia mengevaluasi lalu lintas jaringan untuk perubahan yang mencurigakan, atau mungkin berbasis kebijakan.

Di sinilah ia mengevaluasi lalu lintas jaringan terhadap kebijakan keamanan tertentu yang dinyatakan. Sebuah IDS dapat digunakan di tingkat host ketika digunakan di tingkat host. Ini disebut sistem deteksi intrusi berbasis host, kami menyembunyikan lebih kuat daripada sistem deteksi intrusi adalah sistem pencegahan intrusi.

![[Pasted image 20230403105423.png]]

Lebih detail tentang [[IDS]] (https://en.wikipedia.org/wiki/Intrusion_detection_system).

### Intrusion Prevention System (IPS)

IPS adalah sistem aktif yang dirancang untuk menghentikan pelanggaran atau serangan agar tidak berhasil dan merusak jaringan. Mereka biasanya dirancang untuk melakukan sebuah tindakan atau serangkaian tindakan untuk menghentikan aktivitas jahat. Mereka juga akan memberi tahu administrator jaringan melalui penggunaan file log, SMS, pesan teks, dan atau melalui notifikasi email. Agar IPS dapat bekerja.

Semua trafik di segmen jaringan harus mengalir melalui IPS saat memasuki dan meninggalkan segmen jaringan. Seperti IDS, semua trafik dievaluasi terhadap seperangkat standar dan mereka adalah standar yang sama yang digunakan pada ID. Penempatan terbaik di segmen jaringan adalah antara router dengan firewall yang diharapkan, dan segmen jaringan tujuan. Dengan begitu semua trafik mengalir melalui IPS.

IPS diprogram untuk membuat respons aktif terhadap situasi, mereka dapat memblokir alamat IP yang menyinggung, mereka dapat menutup antarmuka yang rentan, mereka dapat mengakhiri sesi jaringan, mereka dapat mengalihkan serangan. Ditambah lagi, masih banyak lagi tindakan yang bisa dilakukan oleh IPS. Yang paling utama adalah bahwa mereka dirancang untuk aktif untuk menghentikan pelanggaran atau serangan agar tidak berhasil dan merusak jaringan Anda. Mari kita beralih ke konsentrator jaringan pribadi virtual konsentrator VPN.

![[Pasted image 20230403112147.png]]

Lebih detail tentang [[IPS]].

### Virtual Private Network  (VPN)

Sekarang ini akan memungkinkan banyak koneksi VPN yang aman ke jaringan. Konsentrator akan menyediakan kanalisasi dan enkripsi yang tepat tergantung pada jenis koneksi VPN yang diizinkan ke jaringan. Sebagian besar konsentrator dapat berfungsi pada beberapa lapisan model OSI. Secara khusus, mereka dapat beroperasi pada lapisan dua, lapisan tiga dan lapisan tujuh.

Sekarang di luar transaksi internet, yang menggunakan koneksi SSL VPN pada lapisan tujuh, sebagian besar konsentrator akan berfungsi pada lapisan jaringan atau lapisan tiga dari model OSI, menyediakan enkripsi IPsec melalui terowongan yang aman.

![[Pasted image 20230403112659.png]]

Lebih detail tentang [[VPN]] (https://id.wikipedia.org/wiki/Jaringan_pribadi_maya)

### Load Balancer 

Sekarang mari kita bahas tentang optimasi dan kinerja perangkat. Kita akan mulai dengan membicarakan tentang penyeimbang beban. penyeimbang beban juga bisa disebut sebagai pengalih konten atau penyaring konten.

Ini adalah alat jaringan yang digunakan untuk menyeimbangkan beban di antara beberapa host yang berisi data yang sama. Hal ini menyebarkan beban kerja untuk efisiensi yang lebih besar. Biasanya digunakan untuk mendistribusikan permintaan atau beban kerja ke server farm di antara berbagai server dalam farm, sehingga membantu memastikan tidak ada satu server pun yang dibebani permintaan kerja yang berlebihan.

![[Pasted image 20230403132006.png]]

Lebih detail tentang [[Load Balancer]] (https://en.wikipedia.org/wiki/Load_balancing_(computing)).

### Proxy Server

Server proxy adalah alat yang meminta sumber daya atas nama mesin klien. Server ini sering digunakan untuk mengambil sumber daya dari luar jaringan yang tidak terpercaya atas nama klien yang meminta. Alat ini menyembunyikan dan melindungi klien yang meminta dari jaringan luar yang tidak terpercaya.

Ini juga dapat digunakan untuk menyaring konten yang diizinkan kembali ke jaringan tepercaya. Hal ini juga dapat meningkatkan kinerja jaringan dengan melakukan caching atau menyimpan halaman web yang sering diminta. Nah, itulah kesimpulan dari sesi pengenalan perangkat jaringan ini, bagian kedua Kita telah membahas beberapa perangkat keamanan yang mungkin Anda temukan di jaringan Anda. Dan kami menyimpulkan dengan perangkat pengoptimalan dan kinerja yang mungkin juga ada.

![[Pasted image 20230403133110.png]]

lebih detail tentang [[Proxy Server]] (https://en.wikipedia.org/wiki/Proxy_server).

### Summary

![[Pasted image 20230404130159.png]]

# ⭐️ Course Contents ⭐️ 

⌨️ ([0:22:49](https://www.youtube.com/watch?v=qiQR5rTSshw&t=1369s)) Networking Services and Applications (part 2)

## Membahas Tentang

![[Pasted image 20230407144057.png]]

# Network Access Services

## Network Interface Controller ( NIC )

Layanan akses jaringan pertama yang akan saya bahas sebenarnya adalah sebuah perangkat keras, pengontrol antarmuka jaringan atau Nic, bisa juga disebut kartu antarmuka jaringan. Nic adalah cara perangkat terhubung ke jaringan. Network interface controller bekerja pada dua lapisan model OSI pada lapisan dua yang merupakan lapisan data link.

Ini menyediakan sarana fungsional komunikasi jaringan dengan menentukan protokol jaringan mana yang akan digunakan seperti pada Nic yang akan menyediakan komunikasi Ethernet atau Nic yang akan menyediakan protokol Point to Point. Ini juga menyediakan alamat simpul jaringan lokal melalui alamat kontrol akses media fisik yang dibakar di lapisan satu lapisan fisik, pengontrol antarmuka jaringan menentukan bagaimana lalu lintas data jaringan akan dikonversi sedikit demi sedikit menjadi sinyal listrik yang dapat melintasi media jaringan yang sedang digunakan, yaitu menyediakan koneksi ke jaringan. 

Sebagian besar komputer modern dilengkapi dengan setidaknya satu router Ethernet Nic bawaan dan perangkat jaringan lainnya dapat menggunakan modul terpisah yang dapat dimasukkan ke dalam perangkat untuk menyediakan pengontrol antarmuka jaringan yang tepat untuk jenis media yang mereka sambungkan dalam protokol jaringan yang digunakan.

Lebih detail tentang [[NIC]] (https://en.wikipedia.org/wiki/Network_interface_controller).

![[Pasted image 20230407140411.png]]

## RADIUS ( Remote Authentication Dial In User Service. )

Layanan akses jaringan lainnya adalah radius remote, panggilan otentik dalam radius layanan pengguna adalah layanan akses jarak jauh yang digunakan untuk mengautentikasi pengguna jarak jauh dan memberi mereka akses ke sumber daya jaringan yang sah. Ini adalah protokol triple A yang populer yaitu protokol otentikasi, otorisasi dan akuntansi. Protokol ini digunakan untuk membantu memastikan bahwa hanya pengguna akhir yang diautentikasi yang menggunakan sumber daya jaringan yang diizinkan untuk mereka gunakan. Layanan akuntansi radius sangat kuat.

Satu-satunya kekurangan radius adalah hanya peminta kata sandi pengguna akhir yang dienkripsi.

Lebih detail tentang [[RADIUS]] (https://en.wikipedia.org/wiki/RADIUS).

## TACACS+ ( Terminal Access Controller Access-Control System Plus )

Segala sesuatu yang lain dikirim dalam sistem kontrol akses pengontrol akses terminal yang jelas plus atau TAC x plus sistem kontrol akses pengontrol akses terminal plus titik yang sangat jelas, tentu lebih mudah untuk dikatakan.

TAC x plus adalah layanan akses jarak jauh yang digunakan untuk mengautentikasi perangkat jarak jauh dan memberikan akses ke sumber daya jaringan yang sah. Ini juga merupakan protokol triple A populer yang digunakan untuk membantu memastikan bahwa hanya perangkat jaringan jarak jauh yang diautentikasi yang menggunakan sumber daya jaringan yang diizinkan untuk mereka gunakan. Dengan TAC x plus, fitur akuntansi tidak sekuat yang ada di radius.

Tetapi semua transmisi jaringan antar perangkat dienkripsi dengan TAC x plus, mari kita beralih ke layanan dan aplikasi lain. 

Lebih detail tenteng [[TACACS+]] (https://en.wikipedia.org/wiki/TACACS).

![[Pasted image 20230407141139.png]]

# Other Service and Apllications 

## RAS ( Remote Access Services )

Yang pertama adalah Layanan Akses Jarak Jauh AAS kami. Sekarang, RS bukanlah protokol, tetapi peta jalan. RS adalah deskripsi kombinasi perangkat lunak dan perangkat keras yang diperlukan untuk koneksi akses jarak jauh. Klien meminta akses dari server RS, yang akan memberikan atau menolak akses tersebut.

Lebih detail tentang [[RAS]] (https://en.wikipedia.org/wiki/Remote_access_service).

![[Pasted image 20230407144252.png]]

## Web Services

Kemudian kita memiliki layanan web, menciptakan sarana komunikasi silang. Layanan Web menyediakan sarana untuk komunikasi antara paket perangkat lunak atau platform yang berbeda. Hal ini biasanya dicapai dengan menerjemahkan komunikasi ke dalam format XML, atau format Extensible Markup Language. Hal ini menjadi lebih populer seiring dengan semakin beragamnya sistem.

Lebih detail tentang [[Web Services]] (https://id.wikipedia.org/wiki/Layanan_web).

![[Pasted image 20230407145003.png]]

## Unified Voice Services

Ini menciptakan sistem komunikasi suara yang lebih baik. Ini adalah deskripsi kombinasi perangkat lunak dan perangkat keras yang diperlukan untuk mengintegrasikan saluran komunikasi suara ke dalam jaringan seperti dalam Voice over IP.

Lebih detail tentang [[UVS]] (https://en.wikipedia.org/wiki/Unified_communications)

![[Pasted image 20230407145535.png]]

# Summary

![[Pasted image 20230408073213.png]]
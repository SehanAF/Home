# ⭐️ Course Contents ⭐️ 

⌨️ ([1:17:20](https://www.youtube.com/watch?v=qiQR5rTSshw&list=PLUcC-GwJC7M4bq1J4_jSLOjg3jmbD7sp2&index=1&t=4640s)) WAN Technologies (part 4)

![[Pasted image 20230512153246.png]]

# Circuit Switched VS Packet Switched Networks

### Perbedaan Circuit Switched dan Packet Switched Network

Circuit Switched Network adalah jenis jaringan yang membangun jalur komunikasi langsung antara pengirim dan penerima. Pada saat pengguna memulai percakapan, jaringan akan menciptakan sambungan khusus yang akan digunakan selama percakapan. Sambungan ini akan terus terbuka sampai salah satu pengguna menutupnya. Circuit Switched Network lebih cocok untuk aplikasi yang membutuhkan kecepatan transmisi data yang stabil seperti panggilan suara dan video call.

Sementara itu, Packet Switched Network adalah jaringan yang memecah pesan yang dikirim menjadi beberapa paket data sebelum dikirimkan ke alamat tujuan. Setiap paket data akan dikirim melalui jalan tercepat yang tersedia di jaringan. Di sisi tujuan, paket-paket tersebut akan disatukan kembali menjadi satu pesan lengkap. Packet Switched Network lebih cocok untuk aplikasi yang membutuhkan kapasitas bandwidth yang besar seperti internet browsing dan pengiriman email.

### Perbedaan Utama:

- Circuit Switched Network membangun sambungan langsung antara pengirim dan penerima, sedangkan Packet Switched Network memecah pesan menjadi paket data yang dikirim melalui jalur tercepat yang tersedia di jaringan.
- Circuit Switched Network cocok untuk aplikasi yang membutuhkan kecepatan transmisi data yang stabil seperti panggilan suara dan video call, sedangkan Packet Switched Network lebih cocok untuk aplikasi yang membutuhkan kapasitas bandwidth yang besar seperti internet browsing dan pengiriman email.
- Circuit Switched Network menggunakan seluruh bandwidth selama percakapan, sedangkan Packet Switched Network menggunakan bandwidth yang tersedia secara dinamis.

### Cheatsheet:

- Circuit Switched Network: jalur komunikasi langsung, stabil, cocok untuk panggilan suara dan video call.
- Packet Switched Network: pesan dipisah, dikirim melalui jalur tercepat, cocok untuk internet browsing dan pengiriman email.
- Perbedaan utama: cara jaringan membangun sambungan dan memproses data, jenis aplikasi yang cocok, penggunaan bandwidth.

## Circuit Switched Networks

Jaringan Circuit Switched adalah tipe jaringan telekomunikasi yang mengirimkan data melalui jalur yang telah ditentukan dan didedikasikan secara eksklusif untuk suatu panggilan. Setiap panggilan memiliki jalur tersendiri yang hanya digunakan selama panggilan itu aktif. Sistem ini biasanya digunakan dalam jaringan telepon yang menggunakan sirkuit analog.

Jaringan Circuit Switched memiliki tiga tahapan: pengaturan panggilan, pengiriman data, dan pemutusan panggilan. Saat sebuah panggilan dibuat, jaringan mencari jalur yang tersedia dan menghubungkan panggilan tersebut. Setelah panggilan selesai, jalur tersebut akan dilepaskan dan tersedia kembali untuk panggilan lain.

### Cheatsheet Jaringan Circuit Switched:

1. Tipe jaringan telekomunikasi yang mengirimkan data melalui jalur yang telah ditentukan dan didedikasikan secara eksklusif untuk suatu panggilan.
2. Setiap panggilan memiliki jalur tersendiri yang hanya digunakan selama panggilan itu aktif.
3. Jaringan Circuit Switched digunakan dalam jaringan telepon yang menggunakan sirkuit analog.

### Ringkasan:

- Jaringan Circuit Switched adalah tipe jaringan telekomunikasi yang khusus digunakan untuk panggilan suara dan menggunakan jalur yang didedikasikan secara eksklusif untuk suatu panggilan.
- Sistem ini terdiri dari tiga tahapan: pengaturan panggilan, pengiriman data, dan pemutusan panggilan.
- Cheatsheet Jaringan Circuit Switched terdiri dari tiga poin penting untuk memahami konsep dasar jaringan ini.

Lebih detail tentang [Circuit Switched](https://id.wikipedia.org/wiki/Circuit_switching).

## Packet Switched Networks

Jaringan Packet Switched adalah tipe jaringan yang mengirimkan data dalam bentuk paket kecil melalui berbagai jalur. Setiap paket data mengandung informasi alamat tujuan, sehingga dapat diarahkan melalui jalur yang paling efisien ke tujuan yang diinginkan. Setiap paket dapat mengikuti jalur yang berbeda-beda, dan dapat diterima dalam urutan yang berbeda-beda pula. Hal ini berbeda dengan jaringan circuit switched, yang memerlukan jalur khusus untuk setiap percakapan.

Keuntungan utama dari jaringan Packet Switched adalah efisiensi dalam penggunaan bandwidth jaringan. Karena setiap paket data mengikuti jalur yang berbeda-beda, maka jaringan dapat memanfaatkan kapasitas bandwidth yang lebih besar secara efektif. Hal ini memungkinkan jaringan untuk mengirimkan lebih banyak data dalam waktu yang sama. Namun, jaringan Packet Switched juga memiliki beberapa kelemahan, seperti overhead yang lebih besar karena adanya header pada setiap paket data, serta kemungkinan terjadinya delay (penundaan) yang lebih besar.

### Cheatsheet Jaringan Packet Switched:

- Mengirimkan data dalam bentuk paket kecil
- Setiap paket data mengandung informasi alamat tujuan
- Efisien dalam penggunaan bandwidth jaringan

Lebih detail tentang [Packet Switched](https://en.wikipedia.org/wiki/Packet_switching).

![[Pasted image 20230512153303.png]]

# Frame Relay VS Asynchronous Transfer Mode

### Perbedaan Frame Relay dan Asynchronous Transfer Mode

Frame Relay dan Asynchronous Transfer Mode (ATM) adalah dua teknologi jaringan yang berbeda. Frame Relay adalah sebuah protokol jaringan yang digunakan untuk menghubungkan beberapa jaringan lokal bersama-sama. Sedangkan ATM adalah sebuah teknologi jaringan yang mengirimkan data dalam bentuk sel atau paket kecil.

Frame Relay bekerja pada layer dua dari model OSI (Open Systems Interconnection) sedangkan ATM bekerja pada layer tiga. Frame Relay mengirimkan data dalam bentuk frame, sementara ATM mengirimkan data dalam bentuk sel.

Frame Relay memiliki kecepatan transfer data yang rendah dan biaya yang murah, sementara ATM memiliki kecepatan transfer data yang tinggi dan biaya yang mahal.

### Cheatsheet:

- Frame Relay: protokol jaringan untuk menghubungkan beberapa jaringan lokal bersama-sama
- ATM: teknologi jaringan yang mengirimkan data dalam bentuk sel atau paket kecil
- Frame Relay bekerja pada layer dua, sedangkan ATM bekerja pada layer tiga dari model OSI. Frame Relay mengirimkan data dalam bentuk frame, sementara ATM mengirimkan data dalam bentuk sel. Frame Relay memiliki kecepatan transfer data yang rendah dan biaya yang murah, sementara ATM memiliki kecepatan transfer data yang tinggi dan biaya yang mahal.

## Frame Relay

Frame Relay adalah teknologi jaringan komputer yang digunakan untuk mengirim data antara perangkat dalam jaringan yang berbeda. Teknologi ini digunakan untuk menghubungkan beberapa lokasi jaringan komputer dengan bandwidth yang lebih tinggi dan biaya yang lebih rendah daripada teknologi lain seperti leased line.

Frame Relay menggunakan konsep virtual circuit untuk mengirim data, yang berarti bahwa data dikirim melalui sirkuit virtual yang dibuat di atas jaringan fisik. Hal ini memungkinkan pengguna untuk membagi bandwidth yang tersedia dan mengirim data dengan cepat dan efisien.

### Cheatsheet Frame Relay

- Frame Relay adalah teknologi jaringan komputer untuk mengirim data antara perangkat dalam jaringan yang berbeda.
- Frame Relay menggunakan konsep virtual circuit untuk mengirim data melalui sirkuit virtual di atas jaringan fisik.
- Frame Relay memberikan keuntungan dengan biaya lebih rendah dan bandwidth yang lebih tinggi daripada teknologi lain seperti leased line.

Lebih detail tentang [Frame Relay](https://en.wikipedia.org/wiki/Frame_Relay).

![[Pasted image 20230512154631.png]]

## Asynchronous Transfer Mode

ATM adalah teknologi jaringan komputer yang digunakan untuk mengirim data dalam jumlah besar dan dengan kecepatan tinggi melalui jaringan. Teknologi ini membagi data menjadi paket kecil yang disebut sel dan mengirim sel-sel tersebut melalui jaringan dengan kecepatan yang sangat tinggi.

![[Pasted image 20230512155119.png]]

### Cara Kerja ATM

ATM mengambil data yang akan dikirim dan membaginya menjadi sel-sel kecil dengan ukuran tetap. Setiap sel diberi label untuk memastikan bahwa data yang dikirim sampai ke tujuannya dengan aman dan efisien. Sel-sel tersebut kemudian dikirim ke jaringan dan diatur sedemikian rupa sehingga sel-sel tersebut dapat mencapai tujuan mereka dengan kecepatan yang tinggi.

### Keuntungan ATM

ATM memiliki beberapa keuntungan, antara lain:

- Kecepatan Tinggi: Dibandingkan dengan teknologi jaringan komputer lainnya, ATM menawarkan kecepatan transfer data yang sangat tinggi.
- Scalability: ATM dapat dengan mudah disesuaikan dengan kebutuhan jaringan komputer yang berubah-ubah, baik dalam hal kecepatan maupun kapasitas.
- Quality of Service (QoS): ATM memungkinkan pengaturan kualitas layanan jaringan sehingga memastikan bahwa data yang dikirim melalui jaringan diterima dengan benar dan dengan kecepatan yang diinginkan.

### Cheatsheet ATM

- ATM adalah teknologi jaringan komputer yang digunakan untuk mengirim data dalam jumlah besar dan dengan kecepatan tinggi.
- Cara kerja ATM adalah dengan membagi data menjadi sel-sel kecil dan mengirim sel-sel tersebut melalui jaringan dengan kecepatan tinggi.
- Keuntungan ATM antara lain kecepatan tinggi, skalabilitas, dan quality of service (QoS).

Lebih detail tentang [Asynchoronous Transfer Mode](https://en.wikipedia.org/wiki/Asynchronous_Transfer_Mode).

![[Pasted image 20230512153331.png]]

# Multiprotocol Label Switching

Multiprotocol Label Switching (MPLS) adalah sebuah teknologi jaringan yang digunakan untuk mengirimkan data melalui jalur yang tepat dengan cepat dan efisien. MPLS bekerja dengan cara memberikan label pada paket data dan mengarahkannya melalui jalur yang sudah ditentukan sebelumnya. 

![[Pasted image 20230512155603.png]]

### Cara Kerja MPLS

MPLS bekerja dengan memberikan label pada setiap paket data yang diterima. Label ini digunakan untuk mengarahkan paket data ke jalur yang tepat di jaringan. Label MPLS memiliki informasi tentang alamat IP tujuan dan informasi lainnya yang dibutuhkan untuk mengirimkan data ke tempat yang dituju. 

### Cheatsheet MPLS

- MPLS adalah teknologi jaringan untuk mengirimkan data dengan cepat dan efisien.
- MPLS bekerja dengan memberikan label pada setiap paket data dan mengarahkannya melalui jalur yang sudah ditentukan sebelumnya.
- Label MPLS memiliki informasi tentang alamat IP tujuan dan informasi lainnya yang dibutuhkan untuk mengirimkan data ke tempat yang dituju.

Lebih detail tentang [MPLS](https://en.wikipedia.org/wiki/Multiprotocol_Label_Switching).

![[Pasted image 20230512153350.png]]

# Summary

![[Pasted image 20230512153420.png]]
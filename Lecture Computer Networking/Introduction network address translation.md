# ⭐️ Course Contents ⭐️ 

⌨️ ([0:46:01](https://www.youtube.com/watch?v=qiQR5rTSshw&list=PLUcC-GwJC7M4bq1J4_jSLOjg3jmbD7sp2&index=1&t=2761s)) Introducing Network Address Translation

## Membahas 

![[Pasted image 20230424112801.png]]

# The purpose of network address translation

Network Address Translation (NAT) adalah teknologi untuk menyembunyikan alamat IP internal dari jaringan agar hanya alamat IP publik yang dapat dilihat oleh komputer luar jaringan. Jenis NAT antara lain Static NAT, Dynamic NAT, Port Address Translation (PAT), Twice NAT, dan Policy NAT. NAT membantu meningkatkan keamanan jaringan, mengurangi jumlah alamat IP publik yang dibutuhkan, dan memungkinkan penggunaan alamat IP yang tidak valid secara publik.

Lebih detail tentang [[NAT]], [Wiki NAT](https://en.wikipedia.org/wiki/Network_address_translation).

![[Pasted image 20230424112942.png]] 
![[Pasted image 20230424114052.png]]

# How network address translation works

## The two categories of NAT

NAT (Network Address Translation) membagi menjadi dua jenis yaitu Static NAT dan Dynamic NAT. Static NAT mengalokasikan satu IP publik untuk satu IP pribadi, digunakan untuk server, dan lebih aman. Dynamic NAT membagi beberapa perangkat dengan satu IP publik secara bergantian, digunakan untuk jaringan dengan banyak perangkat, dan alamat IP publik dialokasikan secara dinamis. NAT digunakan untuk mengatasi keterbatasan alamat IP publik dan meningkatkan keamanan jaringan. NAT dapat mempengaruhi performa jaringan pada aplikasi tertentu. Beberapa aplikasi memerlukan konfigurasi khusus untuk bekerja dengan NAT. NAT sering digunakan pada jaringan rumahan atau kecil, sedangkan pada jaringan yang lebih besar biasanya digunakan teknologi lain seperti CIDR atau IPv6.

Lebih detail tentang [[Two NAT]].

### Static NAT (SNAT)

Static NAT (SNAT) adalah teknik konfigurasi pada router atau firewall yang mengalokasikan alamat IP statis dari jaringan lokal ke alamat IP publik pada jaringan eksternal. SNAT memungkinkan host atau jaringan lokal diakses dari luar jaringan dan meningkatkan keamanan jaringan dengan menyembunyikan alamat IP asli. SNAT bekerja dengan mengubah alamat IP asli host atau jaringan lokal dengan alamat IP publik yang ditentukan sebelumnya dan meneruskan permintaan ke jaringan eksternal. Respon dari jaringan eksternal diteruskan kembali ke host atau jaringan lokal dengan menggunakan alamat IP publik yang telah diganti.

Lebih detail tentang [[SNAT]].

### Dynamic NAT (DNAT)

Dynamic NAT (DNAT) adalah teknologi jaringan yang mengubah alamat IP sumber dalam paket data, digunakan untuk menjaga privasi dan keamanan, serta mengatasi keterbatasan jumlah alamat IP publik yang tersedia. DNAT menggunakan tabel pengalihan alamat untuk mengganti alamat IP sumber dengan alamat IP publik yang tersedia pada tabel. DNAT dapat dilakukan secara statis atau dinamis dan dapat digunakan bersama dengan teknologi lain seperti Port Forwarding atau VPN. Kekurangan DNAT adalah adanya keterlambatan pada waktu pengalihan alamat IP.

Lebih detail tentang [[DNAT]].

![[Pasted image 20230424114026.png]]

## Port Address translation (PAT)

Port Address Translation (PAT) adalah metode untuk menghubungkan perangkat LAN ke internet dengan menggunakan satu alamat IP publik. Dalam PAT, port perangkat LAN dipetakan ke port yang unik pada alamat IP publik. PAT menghemat alamat IP publik dan dapat memberikan tingkat keamanan tambahan dengan menyembunyikan alamat IP privat perangkat LAN.

Lebih detail tentang [[PAT]].

![[Pasted image 20230504141450.png]]
![[Pasted image 20230504141933.png]]

## The NAT terminology

NAT (Network Address Translation) adalah metode untuk mengubah alamat IP private menjadi alamat IP publik. Ini memungkinkan jaringan lokal terhubung ke internet menggunakan alamat IP publik. Ada tipe NAT statis dan dinamis, serta NAT Overload yang menggunakan port. NAT meningkatkan keamanan jaringan, tetapi juga dapat menyebabkan beberapa masalah.

Lebih detail tentang [[NAT Terminology]].

![[Pasted image 20230504142054.png]]

# Summary 

![[Pasted image 20230504142718.png]]
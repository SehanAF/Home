Static NAT (SNAT) adalah salah satu teknik konfigurasi pada router atau firewall yang digunakan untuk mengalokasikan alamat IP statis pada sebuah host atau jaringan lokal (LAN) ke sebuah alamat IP publik yang terdapat pada jaringan eksternal (WAN). Dalam SNAT, alamat IP asli host atau jaringan lokal akan diganti dengan alamat IP publik yang terdapat pada jaringan eksternal sehingga host atau jaringan lokal tersebut dapat diakses dari luar jaringan.

Beberapa keuntungan dari penggunaan SNAT adalah:

1.  Memungkinkan host atau jaringan lokal untuk dapat diakses dari luar jaringan, seperti internet.
2.  Memperbaiki masalah keterbatasan alamat IP publik yang terbatas dengan mengalokasikan beberapa host atau jaringan lokal pada sebuah alamat IP publik tunggal.
3.  Meningkatkan keamanan jaringan dengan menyembunyikan alamat IP asli host atau jaringan lokal dari luar jaringan.

Cara kerja SNAT adalah sebagai berikut:

1.  Sebuah host atau jaringan lokal akan mengirim permintaan ke jaringan eksternal.
2.  Router atau firewall yang dikonfigurasi dengan SNAT akan mengubah alamat IP asli host atau jaringan lokal dengan alamat IP publik yang telah ditentukan sebelumnya.
3.  Permintaan dari host atau jaringan lokal akan diteruskan ke jaringan eksternal dengan alamat IP publik yang baru.
4.  Respon dari jaringan eksternal akan diterima oleh router atau firewall dan akan diteruskan kembali ke host atau jaringan lokal dengan menggunakan alamat IP publik yang telah diganti sebelumnya.

Berikut adalah cheatsheet untuk Static NAT (SNAT):

Definisi:

-   Static NAT (SNAT) adalah teknik konfigurasi pada router atau firewall untuk mengalokasikan alamat IP statis pada sebuah host atau jaringan lokal ke sebuah alamat IP publik pada jaringan eksternal.

Keuntungan:

-   Memungkinkan host atau jaringan lokal dapat diakses dari luar jaringan.
-   Memperbaiki masalah keterbatasan alamat IP publik.
-   Meningkatkan keamanan jaringan dengan menyembunyikan alamat IP asli host atau jaringan lokal.

Cara kerja:

1.  Host atau jaringan lokal mengirim permintaan ke jaringan eksternal.
2.  Router atau firewall mengubah alamat IP asli dengan alamat IP publik yang telah ditentukan sebelumnya.
3.  Permintaan diteruskan ke jaringan eksternal dengan alamat IP publik yang baru.
4.  Respon dari jaringan eksternal diteruskan kembali ke host atau jaringan lokal dengan menggunakan alamat IP publik yang telah diganti.
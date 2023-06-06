Network Address Translation (NAT) adalah sebuah teknologi yang digunakan untuk mengubah alamat IP pada sebuah jaringan. Tujuan utama dari NAT adalah untuk menyembunyikan alamat IP internal dari jaringan, sehingga hanya alamat IP publik yang dapat dilihat oleh komputer luar jaringan. NAT biasanya digunakan pada jaringan yang terdiri dari beberapa komputer, karena pada jaringan tersebut terdapat banyak alamat IP internal yang harus dilindungi.

Ada beberapa jenis NAT, yaitu:

1.  Static NAT: NAT jenis ini mengalokasikan alamat IP publik yang tetap untuk setiap komputer pada jaringan internal. Dengan NAT statis, komputer luar jaringan dapat mengakses komputer internal dengan menggunakan alamat IP publik yang telah ditentukan.
    
2.  Dynamic NAT: NAT jenis ini mengalokasikan alamat IP publik secara dinamis untuk setiap komputer pada jaringan internal. Dengan NAT dinamis, komputer internal akan diberi alamat IP publik saat mereka terhubung ke internet, dan alamat IP tersebut akan dikembalikan ke kolam alamat IP ketika mereka terputus dari internet.
    
3.  Port Address Translation (PAT): NAT jenis ini digunakan untuk mengalokasikan beberapa komputer pada jaringan internal ke satu alamat IP publik. NAT PAT juga dikenal sebagai NAT overloading, karena banyak komputer pada jaringan internal dapat menggunakan satu alamat IP publik yang sama. Dalam NAT PAT, port yang berbeda digunakan untuk membedakan setiap koneksi jaringan internal.
    

Berikut ini adalah cheatsheet tentang tujuan dari Network Address Translation (NAT):

Tujuan: Menyembunyikan alamat IP internal dari jaringan, sehingga hanya alamat IP publik yang dapat dilihat oleh komputer luar jaringan.

Jenis NAT:

1.  Static NAT: mengalokasikan alamat IP publik yang tetap untuk setiap komputer pada jaringan internal.
2.  Dynamic NAT: mengalokasikan alamat IP publik secara dinamis untuk setiap komputer pada jaringan internal.
3.  Port Address Translation (PAT): digunakan untuk mengalokasikan beberapa komputer pada jaringan internal ke satu alamat IP publik.
4.  Twice NAT: NAT jenis ini mengubah alamat IP internal dan eksternal sebelum dan sesudah lalu lintas melewati router NAT. Dalam Twice NAT, alamat IP internal dan eksternal dapat diubah secara bersamaan.
5.  Policy NAT: NAT jenis ini digunakan untuk memberikan kontrol akses berdasarkan kebijakan keamanan jaringan. Dalam Policy NAT, alamat IP internal dan eksternal dapat diubah berdasarkan aturan kebijakan yang telah ditentukan.

Manfaat NAT:

1.  Meningkatkan keamanan jaringan dengan menyembunyikan alamat IP internal dari komputer luar jaringan.
2.  Mengurangi jumlah alamat IP publik yang dibutuhkan, karena banyak komputer dapat menggunakan satu alamat IP publik.
3.  Memungkinkan jaringan internal menggunakan alamat IP yang tidak valid secara publik, seperti alamat IP yang dimulai dengan 10.x.x.x atau 192.168.x.x.

Demikianlah penjelasan dan cheatsheet tentang tujuan dari Network Address Translation (NAT). Semoga bermanfaat!
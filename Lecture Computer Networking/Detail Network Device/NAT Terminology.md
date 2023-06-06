NAT (Network Address Translation) adalah sebuah metode yang digunakan untuk mengubah alamat IP (Internet Protocol) dari satu jaringan ke jaringan lain. NAT sering digunakan dalam lingkungan jaringan yang menggunakan alamat IP private (misalnya, alamat IP yang dimulai dengan 192.168.x.x atau 10.x.x.x) untuk menghubungkan ke internet yang menggunakan alamat IP publik.

Berikut ini adalah beberapa istilah yang terkait dengan NAT:

1.  Alamat IP Private: Alamat IP yang digunakan di dalam jaringan lokal, seperti 192.168.x.x atau 10.x.x.x. Alamat IP private ini tidak unik secara global dan tidak dapat diakses langsung dari internet.
    
2.  Alamat IP Publik: Alamat IP yang diberikan oleh ISP (Internet Service Provider) dan dapat diakses secara global melalui internet. Alamat IP publik digunakan untuk mengidentifikasi jaringan di internet.
    
3.  NAT Inside (NAT dalam): NAT Inside merujuk pada alamat IP private yang ada di dalam jaringan lokal. Ketika paket data dikirim dari jaringan lokal ke internet, NAT Inside akan mengganti alamat IP private dengan alamat IP publik sebelum paket data mencapai tujuan.
    
4.  NAT Outside (NAT luar): NAT Outside merujuk pada alamat IP publik yang digunakan untuk menggantikan alamat IP private ketika paket data keluar dari jaringan lokal menuju internet. NAT Outside berfungsi sebagai pengganti alamat IP private agar paket data dapat dikirim ke tujuan yang dituju di internet.
    
5.  Static NAT: Static NAT adalah tipe NAT yang menggunakan pengaturan statis untuk mengaitkan alamat IP publik secara tetap dengan alamat IP private tertentu di jaringan lokal. Hal ini memungkinkan koneksi dari luar jaringan untuk mengakses sumber daya di jaringan lokal dengan menggunakan alamat IP publik yang ditentukan.
    
6.  Dynamic NAT: Dynamic NAT adalah tipe NAT yang secara dinamis menerjemahkan alamat IP private menjadi alamat IP publik dari pool yang tersedia. Setiap kali paket data keluar dari jaringan lokal, NAT akan memilih alamat IP publik yang masih tersedia untuk digunakan.
    
7.  NAT Overload (Port Address Translation atau PAT): NAT Overload, juga dikenal sebagai Port Address Translation (PAT), adalah metode NAT yang menggunakan port untuk menerjemahkan alamat IP private ke alamat IP publik. Dalam NAT Overload, beberapa alamat IP private dapat dibagikan dengan menggunakan port yang berbeda untuk mengidentifikasi sumber dan tujuan paket data.
    

Cheatsheet NAT:

1.  NAT (Network Address Translation) adalah metode untuk mengubah alamat IP private menjadi alamat IP publik.
2.  Alamat IP private digunakan di jaringan lokal, sedangkan alamat IP publik digunakan di internet.
3.  NAT Inside mengacu pada alamat IP private dalam jaringan lokal.
4.  NAT Outside mengacu pada alamat IP publik yang digunakan untuk menggantikan alamat IP private.
5.  Static NAT adalah pengaturan statis yang mengaitkan alamat IP publik tetap dengan alamat IP private tertentu.
6.  Dynamic NAT secara dinamis menerjemahkan alamat IP private menjadi alamat IP publik dari pool yang tersedia.
7.  NAT Overload atau PAT menggunakan port untuk menerjemahkan alamat IP private menjadi alamat IP publik. Dalam NAT Overload, beberapa alamat IP private dapat dibagikan dengan menggunakan port yang berbeda untuk mengidentifikasi sumber dan tujuan paket data.

Poin-poin penting tentang NAT:

1.  NAT memungkinkan jaringan dengan alamat IP private untuk terhubung ke internet menggunakan alamat IP publik.
2.  NAT melindungi alamat IP private dari langsung terpapar di internet, sehingga meningkatkan keamanan jaringan.
3.  NAT memungkinkan penggunaan alamat IP private yang tidak unik secara global, karena alamat tersebut akan diterjemahkan menjadi alamat IP publik yang unik.
4.  Static NAT digunakan ketika ada kebutuhan untuk mengaitkan alamat IP publik secara tetap dengan alamat IP private tertentu di jaringan lokal.
5.  Dynamic NAT digunakan ketika alamat IP publik yang tersedia dibagikan secara dinamis kepada alamat IP private dari pool yang tersedia.
6.  NAT Overload atau PAT memungkinkan penggunaan beberapa alamat IP private dengan menggunakan port yang berbeda, sehingga lebih efisien dalam penggunaan alamat IP publik yang terbatas.
7.  NAT dapat menyebabkan beberapa masalah dalam pengaturan jaringan, seperti masalah kompatibilitas dengan protokol yang menggunakan alamat IP secara langsung, serta mempengaruhi koneksi peer-to-peer atau VoIP (Voice over IP) yang memerlukan alamat IP asli.
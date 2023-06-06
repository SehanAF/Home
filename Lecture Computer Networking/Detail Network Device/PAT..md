Port Address Translation (PAT) adalah metode yang digunakan dalam jaringan komputer untuk menghubungkan beberapa perangkat di dalam jaringan lokal (LAN) dengan internet menggunakan satu alamat IP publik. Dalam skenario ini, perangkat LAN akan menggunakan alamat IP privat yang tidak dapat diakses secara langsung dari internet. Sebagai gantinya, router yang menggunakan NAT (Network Address Translation) akan melakukan translasi alamat IP dan port untuk memungkinkan komunikasi antara perangkat LAN dan perangkat di internet.

PAT bekerja dengan cara memetakan port yang digunakan oleh setiap koneksi dari perangkat LAN ke port yang unik pada alamat IP publik. Dengan menggunakan mekanisme ini, satu alamat IP publik dapat mewakili banyak perangkat dalam jaringan lokal. Ketika paket data diterima dari internet, router NAT akan memeriksa port tujuan dan mengarahkannya ke perangkat yang tepat di jaringan lokal berdasarkan pemetaan port yang telah ditentukan sebelumnya.

Berikut adalah beberapa poin penting tentang Port Address Translation:

1.  Menghemat alamat IP publik: Dengan menggunakan PAT, hanya satu alamat IP publik yang diperlukan untuk menghubungkan banyak perangkat dalam jaringan lokal. Hal ini membantu mengatasi keterbatasan alamat IP publik yang terbatas.
    
2.  Pemetaan port: Setiap koneksi dari perangkat LAN akan diberi nomor port unik pada alamat IP publik. Pemetaan port ini memungkinkan router NAT untuk mengarahkan paket data ke perangkat yang sesuai di dalam jaringan lokal.
    
3.  Keterbatasan koneksi simultan: Karena PAT hanya menggunakan satu alamat IP publik, jumlah koneksi simultan yang dapat ditangani oleh router NAT terbatas oleh jumlah port yang tersedia. Jika jumlah koneksi melebihi kapasitas router, dapat terjadi penurunan kinerja atau koneksi yang ditolak.
    
4.  Keamanan: PAT dapat memberikan tingkat keamanan tambahan karena mengaburkan alamat IP privat perangkat di dalam jaringan lokal. Hal ini dapat membantu melindungi perangkat dari serangan yang ditargetkan langsung ke alamat IP mereka.
    

Berikut adalah cheatsheet singkat tentang Port Address Translation (PAT):

-   PAT adalah metode yang digunakan untuk menghubungkan perangkat dalam jaringan lokal ke internet menggunakan satu alamat IP publik.
-   PAT memetakan port perangkat LAN ke port yang unik pada alamat IP publik.
-   PAT menghemat alamat IP publik dengan memungkinkan banyak perangkat menggunakan satu alamat IP.
-   Koneksi simultan pada PAT terbatas oleh jumlah port yang tersedia.
-   PAT dapat memberikan tingkat keamanan tambahan dengan menyembunyikan alamat IP privat perangkat LAN.
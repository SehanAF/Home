Dynamic NAT (DNAT) adalah sebuah teknologi jaringan yang digunakan untuk mengubah alamat IP sumber dalam paket data yang dikirim melalui jaringan, dengan tujuan untuk menjaga privasi dan keamanan. DNAT digunakan untuk mengatasi keterbatasan dari jumlah alamat IP publik yang tersedia, sehingga memungkinkan beberapa perangkat di jaringan lokal menggunakan alamat IP publik yang sama secara bergantian.

Cara kerja DNAT adalah dengan menggunakan tabel pengalihan alamat (address translation table) yang menyimpan informasi alamat IP sumber dan tujuan, serta informasi port. Ketika suatu paket data diterima oleh router, router akan mencari informasi pengalihan alamat di dalam tabel, kemudian mengganti alamat IP sumber dengan alamat IP publik yang tersedia pada tabel, dan mengirimkan paket tersebut ke jaringan tujuan.

Berikut adalah cheatsheet tentang Dynamic NAT (DNAT):

-   DNAT adalah teknologi jaringan untuk mengubah alamat IP sumber dalam paket data
-   Digunakan untuk menjaga privasi dan keamanan, serta mengatasi keterbatasan jumlah alamat IP publik yang tersedia
-   Menggunakan tabel pengalihan alamat yang menyimpan informasi alamat IP sumber dan tujuan, serta informasi port
-   Router akan mencari informasi pengalihan alamat di dalam tabel, kemudian mengganti alamat IP sumber dengan alamat IP publik yang tersedia pada tabel
-   DNAT memungkinkan beberapa perangkat di jaringan lokal menggunakan alamat IP publik yang sama secara bergantian.
-   DNAT dapat dilakukan secara statis atau dinamis
-   Pada DNAT statis, pengalihan alamat IP ditentukan secara manual pada tabel pengalihan alamat
-   Pada DNAT dinamis, pengalihan alamat IP dilakukan secara otomatis oleh router
-   DNAT dapat digunakan bersama dengan teknologi lain seperti Port Forwarding atau Virtual Private Network (VPN) untuk meningkatkan keamanan dan aksesibilitas jaringan
-   Kekurangan DNAT adalah adanya keterlambatan pada waktu pengalihan alamat IP yang dapat mempengaruhi kinerja jaringan
-   DNAT merupakan salah satu teknologi yang umum digunakan pada jaringan komputer dan internet modern.
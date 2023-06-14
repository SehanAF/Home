# [Keamanan cyber](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#cybersecurity)

-   [Keamanan cyber](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#cybersecurity-1)
-   [Kata sandi](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#passwords)
-   [Keamanan Telepon](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#phone-security)
-   [Autentikasi Dua Faktor](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#two-factor-authentication)
-   [Pengelola Kata Sandi](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#password-managers)
-   [Enkripsi](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#encryption)
-   [Mode penyamaran](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#incognito-mode)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#summing-up)

## [Keamanan cyber](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#cybersecurity-1)

-   Hari ini akan menjadi ikhtisar tingkat tinggi dari beberapa topik terkait keamanan siber yang dibahas dalam kursus kami, CS50.

## [Kata sandi](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#passwords)

-   Kata sandi adalah salah satu metode yang digunakan untuk mengamankan data secara online.
-   Ada kata sandi umum yang digunakan orang:
    
    ```
    1. 123456
    2. 123456789
    3. 12345
    4. qwerty
    5. password
    6. 12345678
    7. 11111
    8. 123123
    9. 1234567890
    10. 1234567
    ```
    
-   Jika Anda memiliki salah satu password di atas, kemungkinan besar jutaan orang memiliki password yang sama dengan Anda!
-   Musuh di dunia akan memulai daftar ini.
-   Orang jahat juga dapat menebak sebagian besar heuristik yang Anda gunakan untuk menambahkan simbol ke kata sandi Anda.
-   Kata sandi Anda kemungkinan besar tidak seaman yang Anda kira.

## [Keamanan Telepon](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#phone-security)

-   Banyak telepon diamankan dengan kode empat digit.
-   Bentuk serangan yang paling sederhana adalah dengan “brute-force” mengetikkan semua kemungkinan kata sandi.
-   Ada 10.000 kemungkinan kata sandi saat menggunakan kode empat digit.
-   Jika dibutuhkan satu tebakan per detik, dibutuhkan 10.000 detik untuk memecahkan kata sandi.
-   Namun, jika seorang programmer membuat program untuk menghasilkan semua kode yang mungkin, waktu yang dibutuhkan akan menjadi minimal. Pertimbangkan kode berikut dengan Python:
    
    ```
    from string import digits
    from itertools import product
    
    for passcode in product(digits, repeat=4):
        print(*passcode)
    ```
    
-   Agak membingungkan bahwa kode di atas hanya membutuhkan beberapa detik (paling banyak!) untuk menemukan kata sandi Anda.
-   Kami dapat meningkatkan keamanan kami dengan beralih ke kata sandi empat huruf. Ini akan menghasilkan 7.311.616 kemungkinan kata sandi.
-   Termasuk karakter huruf besar dan kecil akan menciptakan lebih dari 78 juta kemungkinan.
-   Pertimbangkan bagaimana kami dapat memodifikasi kode Anda untuk menemukan kata sandi ini:
    
    ```
    from string import ascii_letters
    from itertools import product
    
    for passcode in product(ascii_letters, repeat=4):
        print(*passcode)
    ```
    
-   Kami bahkan dapat menambahkan kemampuan untuk melihat semua kemungkinan kata sandi empat digit dengan huruf, angka, dan tanda baca:
    
    ```
    from string import ascii_letters, digits, punctuation
    from itertools import product
    
    for passcode in product(ascii_letters + digits + punctuation, repeat=4):
        print(*passcode)
    ```
    
-   Memperluas menjadi delapan karakter, termasuk huruf besar dan kecil, angka, dan simbol, akan menghasilkan 6.095.689.385.410.816 kemungkinan kombinasi.
-   Pertimbangkan bagaimana kode berikut dapat melihat semua kemungkinan sebagai berikut:
    
    ```
    from string import ascii_letters, digits, punctuation
    from itertools import product
    
    for passcode in product(ascii_letters + digits + punctuation, repeat=8):
        print(*passcode)
    ```
    
-   Di dunia digital, Anda hanya ingin kata sandi Anda lebih baik daripada kata sandi orang lain sehingga orang lain akan diserang jauh sebelum Anda — karena Anda adalah target yang paling tidak nyaman.
-   Kelemahan menggunakan kata sandi yang panjang adalah kelemahan karena harus mengingatnya.
-   Oleh karena itu, ada pertahanan lain yang dapat digunakan untuk memperlambat penyerang. Misalnya, beberapa produsen ponsel mengunci mereka yang salah menebak kata sandi.
-   Keamanan adalah tentang menemukan "titik yang tepat" antara pertukaran keamanan yang ditingkatkan dengan tetap menjaga kenyamanan.

## [Autentikasi Dua Faktor](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#two-factor-authentication)

-   Menambahkan cara lain yang harus Anda autentikasi menambah keamanan lebih lanjut. Namun, ada biaya manusia karena Anda mungkin tidak memiliki akses ke faktor kedua Anda.
-   Selalu, kebijakan keamanan berusaha untuk menyeimbangkan kebutuhan keamanan dan kenyamanan manusia.

## [Pengelola Kata Sandi](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#password-managers)

-   Pengelola kata sandi dapat digunakan untuk membuat kata sandi yang sangat menantang dan mengingatnya untuk Anda.
-   Kemungkinan kata sandi yang diamankan oleh pengelola kata sandi dibobol sangat, sangat rendah.
-   Anda berharap pengelola kata sandi tersebut aman. Namun, jika seseorang mendapatkan akses ke pengelola kata sandi Anda, mereka akan memiliki akses ke semua kata sandi Anda.
-   Pada akhirnya, Anda jauh lebih kecil kemungkinannya untuk menghadapi risiko dari orang-orang yang tinggal bersama Anda—dan lebih kecil kemungkinannya untuk menghadapi risiko dari miliaran orang lain di internet.
-   Seperti disebutkan sebelumnya, Anda dapat membuat keputusan berdasarkan keseimbangan antara keamanan dan kenyamanan.

## [Enkripsi](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#encryption)

-   Enkripsi adalah cara dimana data dikaburkan sedemikian rupa sehingga hanya pengirim dan penerima yang dituju yang dapat dibaca.
-   Di awal kursus ini, kami mempelajari algoritme yang sangat sederhana untuk "menggeser" teks dengan satu atau lebih karakter sebagai bentuk enkripsi yang belum sempurna.
-   Enkripsi end-to-end adalah cara mengenkripsi dan mendekripsi terjadi pada sistem yang sama tanpa perantara. Ini mencegah perantara atau aktor jahat untuk dapat mengintai data Anda.
-   Enkripsi disk penuh adalah cara konten perangkat Anda hanya dapat dibuka tanpa kata sandi. Anda harus benar-benar mengaktifkan fitur ini di komputer Anda (tetapi jangan lupa kata sandinya!).
-   Ransomware adalah serangan berbahaya di mana data Anda dienkripsi oleh musuh. Secara harfiah, seseorang menyimpan data Anda untuk tebusan.

## [Mode penyamaran](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#incognito-mode)

-   Di Chrome, mode penyamaran mencegah komputer Anda mengingat situs web apa yang telah Anda jelajahi dan membuang semua informasi yang disimpan secara lokal tentang situs web tersebut. Cookie, file kecil yang digunakan untuk melacak kunjungan situs web Anda, dibuang dalam mode penyamaran.

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/cybersecurity/#summing-up)

-   Gunakan pengelola kata sandi.
-   Gunakan autentikasi dua faktor.
-   Gunakan enkripsi (end-to-end).
# [Kuliah 3](https://cs50.harvard.edu/college/2022/fall/notes/3/#lecture-3)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/3/#welcome)
-   [Algoritma](https://cs50.harvard.edu/college/2022/fall/notes/3/#algorithms)
-   [Durasi](https://cs50.harvard.edu/college/2022/fall/notes/3/#running-time)
-   [Pencarian Linear dan Biner](https://cs50.harvard.edu/college/2022/fall/notes/3/#linear-and-binary-search)
-   [Struktur data](https://cs50.harvard.edu/college/2022/fall/notes/3/#data-structures)
-   [Penyortiran](https://cs50.harvard.edu/college/2022/fall/notes/3/#sorting)
-   [Pengulangan](https://cs50.harvard.edu/college/2022/fall/notes/3/#recursion)
-   [Gabungkan Sortir](https://cs50.harvard.edu/college/2022/fall/notes/3/#merge-sort)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/3/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/3/#welcome)

-   Di minggu ke-0, kami memperkenalkan gagasan tentang _algoritme_ .
-   Minggu ini, kami akan memperluas pemahaman kami tentang algoritme melalui kodesemu dan menjadi kode itu sendiri.
-   Selain itu, kami akan mempertimbangkan efisiensi algoritme ini. Memang, kita akan membangun pemahaman kita tentang bagaimana menggunakan beberapa konsep _tingkat rendah_ yang kita diskusikan minggu lalu dalam membangun algoritme.

## [Algoritma](https://cs50.harvard.edu/college/2022/fall/notes/3/#algorithms)

![Tujuh loker merah berdampingan](https://cs50.harvard.edu/college/2022/fall/notes/3/cs50Week3Slide018.png "loker")
    
-   Kita dapat membayangkan bahwa kita memiliki masalah esensial ingin tahu, "Apakah angka 50 di dalam array?"
-   Kami berpotensi menyerahkan susunan kami ke algoritme, di mana algoritme kami akan mencari melalui loker kami untuk melihat apakah nomor 50 ada di balik salah satu pintu: Mengembalikan nilai benar atau salah.
    
    ![tujuh loker merah menunjuk ke sebuah kotak kosong.  Keluar dari kotak kosong datang dan keluar dari bool](https://cs50.harvard.edu/college/2022/fall/notes/3/cs50Week3Slide022.png "loker sebagai algoritma")
    
-   Kami dapat membayangkan berbagai instruksi yang dapat kami berikan pada algoritme kami untuk melakukan tugas ini sebagai berikut:
    
    ```
    For each door from left to right
        If 50 is behind door
            Return true
    Return false
    ```
    
    Perhatikan bahwa instruksi di atas disebut _pseudocode_ : Versi instruksi yang dapat dibaca manusia yang dapat kami sediakan untuk komputer.
    
-   Seorang ilmuwan komputer dapat menerjemahkan kodesemu itu sebagai berikut:
    
    ```
    For i from 0 to n-1
        If 50 is behind doors[i]
            Return true
    Return false
    ```
    
    Perhatikan bahwa di atas masih bukan kode, tetapi ini adalah perkiraan yang cukup dekat dari tampilan kode akhir.
    
-   _Pencarian biner_ adalah _algoritma pencarian_ yang dapat digunakan dalam tugas kita untuk menemukan 50.
-   Asumsikan bahwa nilai-nilai di dalam loker telah diatur dari yang terkecil hingga yang terbesar, kodesemu untuk pencarian biner akan muncul sebagai berikut:
    
    ```
    If there are no doors
        Return false
    If 50 is behind middle door
        Return true
    Else if 50 < middle door
        Search left half
    Else if 50 > middle door
        Search right half
    ```
    
-   Dengan menggunakan nomenklatur kode, kita selanjutnya dapat memodifikasi algoritme kita sebagai berikut:
    
    ```
    If no doors
        Return false
    If 50 is behind doors[middle]
        Return true
    Else if 50 < doors[middle]
        Search doors[0] through doors[middle-1]
    Else if 50 > doors[middle]
        Search doors[middle+1] through doors[n-1]
    ```
    
    Perhatikan, melihat perkiraan kode ini, Anda hampir bisa membayangkan seperti apa ini dalam kode sebenarnya.
    

## [Durasi](https://cs50.harvard.edu/college/2022/fall/notes/3/#running-time)

-   _waktu berjalan_ melibatkan analisis menggunakan notasi _O besar_ . Perhatikan grafik berikut:
    
    ![bagan dengan: "ukuran masalah" sebagai sumbu x;  "waktu untuk menyelesaikan" sebagai sumbu y;  merah, garis lurus terjal dari asal ke atas grafik dekat dengan kuning, garis lurus kurang curam dari asal ke atas grafik keduanya berlabel "O(n)";  hijau, garis melengkung yang semakin tidak curam dari asal ke kanan grafik berlabel "O(log n)](https://cs50.harvard.edu/college/2022/fall/notes/3/cs50Week3Slide042.png "grafik o besar")
    
-   Pada grafik di atas, algoritma pertama masukHAI(�). Yang kedua masukHAI(�)demikian juga. Yang ketiga masukHAI(catatan⁡�).
-   Bentuk kurva itulah yang menunjukkan efisiensi suatu algoritma. Beberapa waktu berjalan umum yang mungkin kita lihat adalah:
    
    -   HAI(�2)
    -   HAI(�catatan⁡�)
    -   HAI(�)
    -   HAI(catatan⁡�)
    -   HAI(1)
-   Dari waktu berjalan di atas,HAI(�2)dianggap sebagai waktu berjalan terburuk,HAI(1)adalah yang tercepat.
-   Pencarian linier sudah teraturHAI(�)karena bisa mengambil _n_ langkah dalam kasus terburuk untuk dijalankan.
-   Pencarian biner sudah beresHAI(catatan⁡�)karena akan membutuhkan lebih sedikit langkah untuk dijalankan bahkan dalam kasus terburuk.
-   Pemrogram tertarik pada kasus terburuk, atau _batas atas_ , dan kasus terbaik, atau _batas bawah_ .
-   ItuΩsimbol digunakan untuk menunjukkan kasus terbaik dari suatu algoritma, sepertiΩ(catatan⁡�).
-   ItuΘsimbol digunakan untuk menunjukkan di mana batas atas dan batas bawah adalah sama, di mana waktu berjalan kasus terbaik dan kasus terburuk adalah sama.

## [Pencarian Linear dan Biner](https://cs50.harvard.edu/college/2022/fall/notes/3/#linear-and-binary-search)

-   Anda dapat mengimplementasikan pencarian linier sendiri dengan mengetik `code search.c`di jendela terminal Anda dan dengan menulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // An array of integers
        int numbers[] = {20, 500, 10, 5, 100, 1, 50};
    
        // Search for number
        int n = get_int("Number: ");
        for (int i = 0; i < 7; i++)
        {
            if (numbers[i] == n)
            {
                printf("Found\n");
                return 0;
            }
        }
        printf("Not found\n");
        return 1;
    }
    ```
    
    Perhatikan bahwa baris yang dimulai dengan `int numbers[]`memungkinkan kita untuk menentukan nilai setiap elemen array saat kita membuatnya. Kemudian, dalam `for`loop, kami menerapkan pencarian linier.
    
-   Kami sekarang telah menerapkan pencarian linier sendiri di C!
-   Bagaimana jika kita ingin mencari string di dalam array? Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        // An array of strings
        string strings[] = {"battleship", "boot", "cannon", "iron", "thimble", "top hat"};
    
        // Search for string
        string s = get_string("String: ");
        for (int i = 0; i < 6; i++)
        {
            if (strcmp(strings[i], s) == 0)
            {
                printf("Found\n");
                return 0;
            }
        }
        printf("Not found\n");
        return 1;
    }
    ```
    
    Perhatikan bahwa kita tidak dapat memanfaatkan `==`seperti pada iterasi sebelumnya dari program ini. Sebagai gantinya, kita harus menggunakan `strcmp`, yang berasal dari `string.h`perpustakaan.
    
-   Memang, menjalankan kode ini memungkinkan kita untuk mengulang array string ini untuk melihat apakah ada string tertentu di dalamnya. Namun, jika Anda melihat _kesalahan segmentasi_ , di mana bagian dari memori disentuh oleh program Anda yang seharusnya tidak dapat diakses, pastikan Anda telah `i < 6`mencatat di atas, bukan `i < 7`.
    
-   Kita dapat menggabungkan ide angka dan string ini ke dalam satu program. Ketik `code phonebook.c`ke jendela terminal Anda dan tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        // Arrays of strings
        string names[] = {"Carter", "David"};
        string numbers[] = {"+1-617-495-1000", "+1-949-468-2750"};
    
        // Search for name
        string name = get_string("Name: ");
        for (int i = 0; i < 2; i++)
        {
            if (strcmp(names[i], name) == 0)
            {
                printf("Found %s\n", numbers[i]);
                return 0;
            }
        }
        printf("Not found\n");
        return 1;
    }
    ```
    
    Perhatikan bahwa nomor Carter dimulai dengan `+1-617`dan nomor telepon David dimulai dengan '1-949'. Oleh karena itu, `names[0]`adalah Carter dan `numbers[0]`adalah nomor Carter.
    
-   Meskipun kode ini berfungsi, ada banyak inefisiensi. Memang, ada kemungkinan nama dan nomor orang tidak sesuai. Tidakkah menyenangkan jika kita dapat membuat tipe data kita sendiri di mana kita dapat mengaitkan seseorang dengan nomor teleponnya?

## [Struktur data](https://cs50.harvard.edu/college/2022/fall/notes/3/#data-structures)

-   Ternyata C memungkinkan kita membuat tipe data kita sendiri melalui `struct`. Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    #include <string.h>
    
    typedef struct
    {
        string name;
        string number;
    }
    person;
    
    int main(void)
    {
        person people[2];
    
        people[0].name = "Carter";
        people[0].number = "+1-617-495-1000";
    
        people[1].name = "David";
        people[1].number = "+1-949-468-2750";
    
        // Search for name
        string name = get_string("Name: ");
        for (int i = 0; i < 2; i++)
        {
            if (strcmp(people[i].name, name) == 0)
            {
                printf("Found %s\n", people[i].number);
                return 0;
            }
        }
        printf("Not found\n");
        return 1;
    }
    ```
    
    Perhatikan bahwa kode dimulai dengan `typedef struct`di mana tipe data baru yang disebut `person`didefinisikan. Di dalam a `person`adalah string yang dipanggil `name`dan `string`nomor yang dipanggil. Pada `main`fungsi tersebut, mulailah dengan membuat array yang disebut `people`dengan tipe `person`yang berukuran 2. Kemudian, kami memperbarui nama dan nomor telepon dari dua orang dalam `people`array kami. Yang paling penting, perhatikan bagaimana _notasi titik_ seperti `people[0].name`memungkinkan kita untuk mengakses `person`di lokasi ke-0 dan menetapkan nama individu tersebut.
    

## [Penyortiran](https://cs50.harvard.edu/college/2022/fall/notes/3/#sorting)

-   _menyortir_ adalah tindakan mengambil daftar nilai yang tidak disortir dan mengubah daftar ini menjadi yang disortir.
-   Saat daftar diurutkan, mencari daftar itu jauh lebih ringan di komputer. Ingatlah bahwa kita dapat menggunakan pencarian biner pada daftar yang diurutkan, tetapi tidak pada daftar yang tidak disortir.
-   Ternyata ada banyak jenis algoritma pengurutan.
-   _Sortasi pilihan_ adalah salah satu algoritma pencarian tersebut.
-   Algoritma untuk pengurutan seleksi dalam pseudocode adalah:
    
    ```
    For i from 0 to n–1
        Find smallest number between numbers[i] and numbers[n-1]
        Swap smallest number with numbers[i]
    ```
    
-   Pertimbangkan daftar yang tidak disortir sebagai berikut:
    
    ```
      5 2 7 4 1 6 3 0
      ^
    ```
    
-   Pengurutan seleksi akan dimulai dengan mencari angka terkecil dalam daftar dan menukar angka tersebut dengan posisi kita saat ini dalam daftar. Dalam hal ini, nol ditempatkan dan dipindahkan ke posisi kita saat ini.
    
    ```
      0 | 2 7 4 1 6 3 5
    ```
    
-   Sekarang, masalah kita menjadi lebih kecil karena kita tahu setidaknya awal daftar kita sudah diurutkan. Jadi kami dapat mengulangi apa yang kami lakukan, mulai dari nomor kedua dalam daftar:
    
    ```
      0 | 2 7 4 1 6 3 5
          ^    
    ```
    
-   1 adalah angka terkecil sekarang, jadi kita akan menukarnya dengan angka kedua. Kami akan mengulangi ini lagi …
    
    ```
      0 1 | 7 4 2 6 3 5
            ^     
    ```
    
-   … dan lagi…
    
    ```
      0 1 2 | 4 7 6 3 5
              ^
    ```
    
-   … dan lagi…
    
    ```
      0 1 2 3 | 7 6 4 5
                ^
    ```
    
-   … dan lagi …
    
    ```
      0 1 2 3 4 | 6 7 5
                  ^
    ```
    
-   dan seterusnya.
-   _Bubble sort_ adalah algoritme pengurutan lain yang bekerja dengan berulang kali menukar elemen ke "gelembung" elemen yang lebih besar sampai akhir.
-   Kodesemu untuk bubble sort adalah:
    
    ```
    Repeat n-1 times
    For i from 0 to n–2
        If numbers[i] and numbers[i+1] out of order
            Swap them
    ```
    
-   Kita akan mulai dengan daftar yang tidak disortir, tetapi kali ini kita akan melihat pasangan angka dan menukarnya jika tidak berurutan:
    
    ```
    5 2 7 4 1 6 3 0
    ^ ^
    2 5 7 4 1 6 3 0
      ^ ^
    2 5 7 4 1 6 3 0
        ^ ^
    2 5 4 7 1 6 3 0
          ^ ^
    2 5 4 1 7 6 3 0
            ^ ^
    2 5 4 1 6 7 3 0
              ^ ^
    2 5 4 1 6 3 7 0
                ^ ^
    2 5 4 1 6 3 0 7
    ```
    
-   Sekarang, angka tertinggi ada di kanan, jadi kita telah memperbaiki masalah kita. Kami akan mengulangi ini lagi:
    
    ```
    2 5 4 1 6 3 0 | 7
    ^ ^
    2 5 4 1 6 3 0 | 7
      ^ ^
    2 4 5 1 6 3 0 | 7
        ^ ^
    2 4 1 5 6 3 0 | 7
          ^ ^
    2 4 1 5 6 3 0 | 7
            ^ ^
    2 4 1 5 3 6 0 | 7
              ^ ^
    2 4 1 5 3 0 6 | 7
    ```
    
-   Sekarang dua nilai terbesar ada di sebelah kanan. Kami ulangi lagi:
    
    ```
      2 4 1 5 3 0 | 6 7
      ^ ^
      2 4 1 5 3 0 | 6 7
        ^ ^
      2 1 4 5 3 0 | 6 7
          ^ ^
      2 1 4 5 3 0 | 6 7
            ^ ^
      2 1 4 3 5 0 | 6 7
              ^ ^
      2 1 4 3 0 5 | 6 7
    ```
    
-   … dan lagi …
    
    ```
      2 1 4 3 0 | 5 6 7
      ^ ^
      1 2 4 3 0 | 5 6 7
        ^ ^
      1 2 3 4 0 | 5 6 7
          ^ ^
      1 2 3 4 0 | 5 6 7
            ^ ^
      1 2 3 0 4 | 5 6 7
    ```
    
-   … dan lagi …
    
    ```
      1 2 3 0 | 4 5 6 7
      ^ ^
      1 2 3 0 | 4 5 6 7
        ^ ^
      1 2 3 0 | 4 5 6 7
          ^ ^
      1 2 0 3 | 4 5 6 7
    ```
    
-   … dan lagi …
    
    ```
      1 2 0 | 3 4 5 6 7
      ^ ^
      1 2 0 | 3 4 5 6 7
        ^ ^
      1 0 2 | 3 4 5 6 7
    ```
    
-   … dan akhirnya …
    
    ```
      1 0 | 2 3 4 5 6 7
      ^ ^
      0 1 | 2 3 4 5 6 7
    ```
    
-   Perhatikan bahwa, saat kita membaca daftar kita, kita tahu semakin banyak yang diurutkan, jadi kita hanya perlu melihat pasangan angka yang belum diurutkan.
-   Menganalisis pengurutan pilihan, kami hanya membuat tujuh perbandingan. Mewakili ini secara matematis, di mana _n_ mewakili jumlah kasus, dapat dikatakan bahwa sortasi pemilihan dapat dianalisis sebagai:
    
    ```
      (n-1)+(n-2)+(n-3)+ ... + 1
    ```
    
    atau, lebih sederhana�2/2−�/2.
    
-   Mengingat analisis matematis, n 2 adalah faktor yang paling berpengaruh dalam menentukan efisiensi algoritma ini. Oleh karena itu, pemilihan sortir dianggap sebagai urutan dariHAI(�2)dalam kasus terburuk di mana semua nilai tidak diurutkan. Bahkan ketika semua nilai diurutkan, itu akan mengambil jumlah langkah yang sama. Oleh karena itu, kasus terbaik dapat dicatat sebagaiΩ(�2). Karena kasus batas atas dan batas bawah sama, efisiensi algoritma ini secara keseluruhan dapat dianggap sebagaiΘ(�2).
-   Menganalisis jenis gelembung, kasus terburuknya adalahHAI(�2). Kasus terbaik adalahΩ(�).
-   Anda dapat [memvisualisasikan](https://www.cs.usfca.edu/~galles/visualization/ComparisonSort.html) perbandingan algoritme ini.

## [Pengulangan](https://cs50.harvard.edu/college/2022/fall/notes/3/#recursion)

-   Bagaimana kami dapat meningkatkan efisiensi dalam penyortiran kami?
-   _Rekursi_ adalah konsep dalam pemrograman di mana suatu fungsi memanggil dirinya sendiri. Kami melihat ini sebelumnya ketika kami melihat ...
    
    ```
    If no doors
        Return false
    If number behind middle door
        Return true
    Else if number < middle door
        Search left half
    Else if number > middle door
        Search right half
    ```
    
    Perhatikan bahwa kami memanggil `search`iterasi yang lebih kecil dan lebih kecil dari masalah ini.
    
-   Demikian pula, dalam pseudocode kami untuk Minggu 0, Anda dapat melihat di mana rekursi diterapkan:
    
    ```
    1  Pick up phone book
    2  Open to middle of phone book
    3  Look at page
    4  If person is on page
    5      Call person
    6  Else if person is earlier in book
    7      Open to middle of left half of book
    8      Go back to line 3
    9  Else if person is later in book
    10     Open to middle of right half of book
    11     Go back to line 3
    12 Else
    13     Quit
    ```
    
-   Pertimbangkan bagaimana di Minggu 1 kami ingin membuat struktur piramida sebagai berikut:
    
    ```
      #
      ##
      ###
      ####
    ```
    
-   Untuk mengimplementasikan ini menggunakan rekursi, ketik `code recursion.c`ke jendela terminal Anda dan tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    void draw(int n);
    
    int main(void)
    {
        draw(1);
    }
    
    void draw(int n)
    {
        for (int i = 0; i < n; i++)
        {
            printf("#");
        }
        printf("\n");
    
        draw(n + 1);
    }
    ```
    
    Perhatikan bahwa fungsi draw memanggil dirinya sendiri. Selanjutnya, perhatikan bahwa kode Anda mungkin terjebak dalam loop tak terbatas. Untuk keluar dari loop ini, jika Anda macet, tekan `ctrl-c`keyboard Anda. Alasan mengapa ini menciptakan loop tak terbatas adalah karena tidak ada yang memerintahkan program untuk diakhiri. Tidak ada kasus di mana program selesai.
    
-   Kami dapat memperbaiki kode kami sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    void draw(int n);
    
    int main(void)
    {
        // Get height of pyramid
        int height = get_int("Height: ");
    
        // Draw pyramid
        draw(height);
    }
    
    void draw(int n)
    {
        // If nothing to draw
        if (n <= 0)
        {
            return;
        }
    
        // Draw pyramid of height n - 1
        draw(n - 1);
    
        // Draw one more row of width n
        for (int i = 0; i < n; i++)
        {
            printf("#");
        }
        printf("\n");
    }
    ```
    
    Perhatikan _kasus dasar_ akan memastikan kode tidak berjalan selamanya. Garis `if (n <= 0)`mengakhiri rekursi karena masalah telah dipecahkan. Setiap kali `draw`memanggil dirinya sendiri, ia memanggil dirinya sendiri dengan `n-1`. Pada titik tertentu, `n-1`akan sama dengan `0`, menghasilkan `draw`fungsi kembali dan program akan berakhir.
    

## [Gabungkan Sortir](https://cs50.harvard.edu/college/2022/fall/notes/3/#merge-sort)

-   Kami sekarang dapat memanfaatkan rekursi dalam pencarian kami untuk algoritme pengurutan yang lebih efisien dan mengimplementasikan apa yang disebut _merge sort_ , algoritme pengurutan yang sangat efisien.
-   Kodesemu untuk jenis gabungan cukup singkat:
    
    ```
    If only one number
        Quit
    Else
        Sort left half of number
        Sort right half of number
        Merge sorted halves
    ```
    
-   Perhatikan daftar nomor berikut:
    
    ```
      7254
    ```
    
-   Pertama, gabung semacam bertanya, "apakah ini satu nomor?" Jawabannya adalah "tidak", jadi algoritme berlanjut.
    
    ```
      7254
    ```
    
-   Kedua, gabungkan sortir sekarang akan membagi angka di tengah (atau sedekat mungkin) dan mengurutkan bagian kiri angka.
    
    ```
      72|54
    ```
    
-   Ketiga, pengurutan gabungan akan melihat angka-angka ini di sebelah kiri dan bertanya, "apakah ini satu angka?" Karena jawabannya tidak, maka akan membagi angka di kiri bawah tengah.
    
    ```
      7|2
    ```
    
-   Keempat, merge sort akan kembali bertanya, “apakah ini satu angka?” Jawabannya adalah ya kali ini! Oleh karena itu, ini akan keluar dari tugas ini dan kembali ke tugas terakhir yang sedang dijalankan saat ini:
    
    ```
      72|54
    ```
    
-   Kelima, merge sort akan mengurutkan angka di sebelah kiri.
    
    ```
      27|54
    ```
    
-   Sekarang, kita kembali ke tempat kita tinggalkan di pseudocode sekarang setelah sisi kiri telah diurutkan. Proses serupa dari langkah 3-5 akan terjadi dengan angka sebelah kanan. Ini akan menghasilkan:
    
    ```
      27|45
    ```
    
-   Kedua bagian sekarang diurutkan. Akhirnya, algoritme akan menggabungkan kedua sisi. Ini akan melihat nomor pertama di sebelah kiri dan nomor pertama di sebelah kanan. Ini akan menempatkan angka yang lebih kecil terlebih dahulu, lalu yang terkecil kedua. Algoritme akan mengulangi ini untuk semua angka, menghasilkan:
    
    ```
      2457
    ```
    
-   Pengurutan gabungan selesai, dan program berhenti.
-   Pengurutan gabungan adalah algoritme pengurutan yang sangat efisien dengan kasus terburukHAI(�catatan⁡�). Kasus terbaik masihΩ(�catatan⁡�)karena algoritma masih harus mengunjungi setiap tempat dalam daftar. Oleh karena itu, gabungkan semacam jugaΘ(�catatan⁡�)karena kasus terbaik dan kasus terburuk adalah sama.
-   [Visualisasi](https://www.youtube.com/watch?v=ZZuD6iUe3Pc) akhir dibagikan.

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/3/#summing-up)

Dalam pelajaran ini, Anda belajar tentang pemikiran algoritmik dan membangun tipe data Anda sendiri. Secara khusus, Anda belajar…

-   Algoritma.
-   _notasi O_ besar .
-   Pencarian biner dan pencarian linier.
-   Berbagai algoritma pengurutan, termasuk pengurutan gelembung, pengurutan pilihan, dan pengurutan gabungan.
-   Pengulangan.

Sampai jumpa lain waktu!
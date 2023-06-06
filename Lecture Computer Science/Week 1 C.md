# [Kuliah 1](https://cs50.harvard.edu/college/2022/fall/notes/1/#lecture-1)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/1/#welcome)
-   [Halo Dunia](https://cs50.harvard.edu/college/2022/fall/notes/1/#hello-world)
-   [Fungsi](https://cs50.harvard.edu/college/2022/fall/notes/1/#functions)
-   [Variabel](https://cs50.harvard.edu/college/2022/fall/notes/1/#variables)
-   [Persyaratan](https://cs50.harvard.edu/college/2022/fall/notes/1/#conditionals)
-   [Loop](https://cs50.harvard.edu/college/2022/fall/notes/1/#loops)
-   [Linux dan Baris Perintah](https://cs50.harvard.edu/college/2022/fall/notes/1/#linux-and-the-command-line)
-   [Mario](https://cs50.harvard.edu/college/2022/fall/notes/1/#mario)
-   [Komentar](https://cs50.harvard.edu/college/2022/fall/notes/1/#comments)
-   [Abstraksi](https://cs50.harvard.edu/college/2022/fall/notes/1/#abstraction)
-   [Operator dan Jenis](https://cs50.harvard.edu/college/2022/fall/notes/1/#operators-and-types)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/1/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/1/#welcome)

-   Pada sesi sebelumnya, kita belajar tentang Scratch, sebuah bahasa pemrograman visual.
-   Memang, semua konsep pemrograman penting yang disajikan di Scratch akan digunakan saat Anda mempelajari cara memprogram bahasa pemrograman apa pun.
-   Ingatlah bahwa mesin hanya memahami biner. Di mana manusia menulis _kode sumber_ , daftar instruksi untuk komputer yang dapat dibaca manusia, mesin hanya mengerti apa yang sekarang kita sebut _kode mesin_ . Kode mesin ini adalah pola satu dan nol yang menghasilkan efek yang diinginkan.
-   Ternyata kita dapat mengonversi _kode sumber_ menjadi `machine code`menggunakan perangkat lunak yang sangat khusus yang disebut _kompiler_ . Hari ini, kami akan memperkenalkan Anda ke kompiler yang memungkinkan Anda mengonversi kode sumber dalam bahasa pemrograman _C_ menjadi kode mesin.
-   Hari ini, selain belajar cara membuat kode, Anda juga akan belajar cara menulis kode yang baik.
-   Kode dapat dievaluasi pada tiga sumbu. Pertama, _kebenaran_ mengacu pada "apakah kode berjalan sebagaimana mestinya?" Kedua, _desain_ mengacu pada "seberapa baik kode dirancang?" Akhirnya, _gaya_ mengacu pada "seberapa estetis dan konsisten kodenya?"

## [Halo Dunia](https://cs50.harvard.edu/college/2022/fall/notes/1/#hello-world)

-   Kompiler yang digunakan untuk kursus ini adalah _Visual Studio Code_ , biasa disebut sebagai, yang dapat diakses melalui url yang sama, atau hanya sebagai *VS Code.*
-   Salah satu alasan terpenting kami menggunakan VS Code adalah karena VS Code memiliki semua perangkat lunak yang diperlukan untuk kursus yang sudah dimuat sebelumnya. Kursus ini dan instruksi di dalamnya dirancang dengan mempertimbangkan Kode VS. Sebaiknya selalu gunakan VS Code untuk tugas dalam kursus ini.
-   Anda dapat membuka Kode VS di [code.cs50.io](https://code.cs50.io/) .
-   Kompiler dapat dibagi menjadi beberapa wilayah:
    
    ![IDE](https://cs50.harvard.edu/college/2022/fall/notes/1/cs50Week1Slide017.png "IDE") Perhatikan bahwa ada _penjelajah file_ di sisi kiri tempat Anda dapat menemukan file Anda. Selanjutnya, perhatikan bahwa ada wilayah di tengah yang disebut _editor teks_ tempat Anda dapat mengedit program. Terakhir, ada `command line interface`, yang dikenal sebagai _CLI_ , _baris perintah_ , atau _jendela terminal_ tempat kita dapat mengirim perintah ke komputer di cloud.
    
-   Kami dapat membuat program pertama Anda di C dengan mengetik `code hello.c`di jendela terminal. Perhatikan bahwa kami sengaja menurunkan seluruh nama file dan menyertakan `.c`ekstensi. Kemudian, pada teks editor yang muncul, tuliskan kode sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        printf("hello, world\n");
    }
    ```
    
    Perhatikan bahwa setiap karakter di atas memiliki tujuan. Jika Anda salah mengetik, program tidak akan berjalan.
    
-   Mengklik kembali di jendela terminal, Anda dapat mengkompilasi kode Anda dengan menjalankan `make hello`. Perhatikan bahwa kita menghilangkan `.c`. `make`adalah kompiler yang akan mencari `hello.c`file kita dan mengubahnya menjadi sebuah program bernama `hello`. Jika menjalankan perintah ini tidak menghasilkan kesalahan, Anda dapat melanjutkan. Jika tidak, periksa kembali kode Anda untuk memastikannya cocok dengan yang di atas.
-   Sekarang, ketik `./hello`dan program Anda akan mengeksekusi mengatakan `hello, world`.
-   Sekarang, buka _file explorer_ di sebelah kiri. Anda akan melihat bahwa sekarang ada file bernama `hello.c`dan file lain bernama `hello`. `hello.c`dapat dibaca oleh kompiler: Di situlah kode Anda disimpan. `hello`adalah file yang dapat dieksekusi yang dapat Anda jalankan, tetapi tidak dapat dibaca oleh kompiler.
-   Mari kita lihat kode kita lebih hati-hati:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        printf("hello, world\n");
    }
    ```
    
    Perhatikan bahwa kode kita disorot menggunakan penyorotan sintaks.
    

## [Fungsi](https://cs50.harvard.edu/college/2022/fall/notes/1/#functions)

-   Di Scratch, kami menggunakan `say`blok untuk menampilkan teks apa pun di layar. Memang, di C, kami memiliki fungsi bernama `printf`yang melakukan hal ini.
-   Perhatikan kode kita sudah memanggil fungsi ini:
    
    ```
    printf("hello, world\n");
    ```
    
    Perhatikan bahwa fungsi printf dipanggil. Argumen yang diteruskan ke printf adalah 'hello, world\n'. Pernyataan kode ditutup dengan a `;`.
    
-   Kesalahan umum dalam pemrograman C adalah penghilangan titik koma. Ubah kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        printf("hello, world\n")
    }
    ```
    
    Perhatikan titik koma sekarang hilang.
    
-   Di jendela terminal Anda, jalankan `make hello`. Anda sekarang akan bertemu dengan banyak kesalahan! Menempatkan titik koma kembali pada posisi yang benar dan menjalankannya `make hello`kembali, kesalahan akan hilang.
-   Perhatikan juga simbol khusus `\n`dalam kode Anda. Coba hapus karakter tersebut dan _buat_ program Anda lagi dengan menjalankan `make hello`. Mengetik `./hello`di jendela terminal, bagaimana program Anda berubah?
-   Pulihkan program Anda ke yang berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        printf("hello, world\n");
    }
    ```
    
    Perhatikan titik koma dan `\n`telah dipulihkan.
    
-   Pernyataan di awal kode `#include <stdio.h>`adalah perintah yang sangat khusus yang memberi tahu kompilasi bahwa Anda ingin menggunakan kemampuan _pustaka_ bernama `stdio.h`. Ini memungkinkan Anda, di antara banyak hal lainnya, untuk memanfaatkan `printf`fungsi tersebut. Anda dapat membaca tentang semua kemampuan perpustakaan ini di [Halaman Manual](https://manual.cs50.io/) .
-   Ternyata CS50 punya library sendiri bernama `cs50.h`. Mari gunakan perpustakaan ini di program Anda.

## [Variabel](https://cs50.harvard.edu/college/2022/fall/notes/1/#variables)

-   Ingatlah bahwa di Scratch, kami memiliki kemampuan untuk bertanya kepada pengguna “Siapa nama Anda?” dan katakan "halo" dengan nama itu ditambahkan padanya.
-   Di C, kita bisa melakukan hal yang sama. Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        string answer = get_string("What's your name? ");
        printf("hello, %s\n", answer);
    }
    ```
    
    Perhatikan yang `#include <cs50.h>`telah ditambahkan ke bagian atas kode Anda. Fungsi ini `get_string`digunakan untuk mendapatkan string dari pengguna. Kemudian, variabel `answer`dilewatkan ke `printf`fungsi. `%s`memberitahu `printf`fungsi untuk mempersiapkan diri untuk menerima `string`.
    
-   `answer`adalah tempat penyimpanan khusus yang kita sebut _variabel_ . `answer`bertipe `string`dan dapat menampung string apa pun di dalamnya. Ada banyak _tipe data_ , seperti `int`, `bool`, `char`, dan masih banyak lagi.
-   Jalankan `make hello`lagi di jendela terminal, Anda dapat menjalankan program Anda dengan mengetik `./hello`. Program sekarang menanyakan nama Anda dan kemudian menyapa dengan nama Anda terlampir.

## [Persyaratan](https://cs50.harvard.edu/college/2022/fall/notes/1/#conditionals)

-   Blok bangunan lain yang Anda gunakan dalam Scratch adalah _persyaratan_ . Misalnya, Anda mungkin ingin melakukan satu hal jika x lebih besar dari y. Selanjutnya, Anda mungkin ingin melakukan sesuatu yang lain jika kondisi itu tidak terpenuhi.
-   Di jendela terminal, ketik `code compare.c`dan tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        int x = get_int("What's x? ")
        int y = get_int("What's y? ")
    
        if (x < y)
        {
            printf("x is less than y\n")
        }
    }
    ```
    
    Perhatikan bahwa kita membuat dua variabel, satu `int`or integer dipanggil `x`dan satu lagi disebut `y`. Nilai-nilai ini diisi menggunakan `get_int`fungsi.
    
-   Anda dapat menjalankan kode Anda dengan mengeksekusi `make compare`di jendela terminal, diikuti dengan `./compare`. Jika Anda mendapatkan pesan kesalahan, periksa kode Anda untuk kesalahan.
-   Kami dapat meningkatkan program Anda dengan pengkodean sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        int x = get_int("What's x? ")
        int y = get_int("What's y? ")
    
        if (x < y)
        {
            printf("x is less than y\n");
        }
        else if (x > y)
        {
            printf("x is greater than y\n");
        }
        else
        {
            printf("x is equal to y\n");
        }
    }
    ```
    
    Perhatikan bahwa semua hasil potensial sekarang diperhitungkan.
    
-   Anda dapat membuat ulang dan menjalankan kembali program Anda dan mengujinya.
-   Mempertimbangkan tipe data lain yang disebut a, `char`kita dapat memulai program baru dengan mengetik `code agree.c`di jendela terminal. Di editor teks, tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Prompt user to agree
        char c = get_char("Do you agree? ");
    
        // Check whether agreed
        if (c == 'Y' || c == 'y')
        {
            printf("Agreed.\n");
        }
        else if (c == 'N' || c == 'n')
        {
            printf("Not agreed.\n");
        }
    }
    ```
    
    Perhatikan bahwa tanda kutip tunggal digunakan untuk karakter tunggal. Selanjutnya, perhatikan bahwa `==`pastikan bahwa sesuatu _itu sama_ dengan sesuatu yang lain, di mana satu tanda sama dengan akan memiliki fungsi yang sangat berbeda di C. Terakhir, perhatikan bahwa `||`secara efektif berarti _atau_ .
    
-   Anda dapat menguji kode Anda dengan mengetik `make agree`di jendela terminal, diikuti dengan `./agree`.

## [Loop](https://cs50.harvard.edu/college/2022/fall/notes/1/#loops)

-   Kami juga dapat menggunakan blok penyusun loop dari Scratch dalam program C kami.
-   Di jendela terminal Anda, ketik `code meow.c`dan tulis kode sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        printf("meow\n");
        printf("meow\n");
        printf("meow\n");
    }
    ```
    
    Perhatikan ini sesuai keinginan tetapi memiliki peluang untuk desain yang lebih baik.
    
-   Kami dapat meningkatkan program kami dengan memodifikasi kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        int i = 0;
        while (i < 3)
        {
            printf("meow\n");
            i++;
        }
    }
    ```
    
    Perhatikan bahwa kita membuat sebuah `int`panggilan `i`dan memberinya nilai `0`. Kemudian, kami membuat `while`loop yang akan berjalan selama `i < 3`. Kemudian, loop berjalan. Setiap kali `1`ditambahkan `i`menggunakan `i++`pernyataan.
    
-   Demikian pula, kita dapat menerapkan hitungan mundur dengan memodifikasi kode kita sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        int i = 3;
        while (i > 0)
        {
            printf("meow\n");
            i--;
        }
    }
    ```
    
    Perhatikan bagaimana penghitung kita `i`dimulai pada `3`. Setiap kali loop berjalan, itu akan mengurangi penghitung sebesar `1`. Setelah penghitung kurang dari nol, itu akan menghentikan putaran.
    
-   Kami dapat lebih meningkatkan desain menggunakan `for`loop. Ubah kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        for (int i = 0; i < 3; i++)
        {
            printf("meow\n");
        }
    }
    ```
    
    Perhatikan bahwa `for`loop menyertakan tiga argumen. Argumen pertama `int i = 0`memulai penghitung kita dari nol. Argumen kedua `i < 3`adalah kondisi yang sedang diperiksa. Terakhir, argumen `i++`memberi tahu loop untuk bertambah satu setiap kali loop berjalan.
    
-   Kami bahkan dapat mengulang selamanya menggunakan kode berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        while (true)
        {
            printf("meow\n");
        }
    }
    ```
    
    Perhatikan bahwa `true`akan selalu demikian. Oleh karena itu, kode akan selalu berjalan. Anda akan kehilangan kendali atas jendela terminal Anda dengan menjalankan kode ini. Anda dapat melepaskan diri dari yang tak terbatas dengan menekan `control-C`keyboard Anda.
    

## [Linux dan Baris Perintah](https://cs50.harvard.edu/college/2022/fall/notes/1/#linux-and-the-command-line)

-   _Linux_ adalah sistem operasi yang dapat diakses melalui baris perintah di jendela terminal di VS Code.
-   Beberapa argumen baris perintah umum yang dapat kami gunakan meliputi:
    -   `cd`, untuk mengubah direktori (folder) kami saat ini
    -   `cp`, untuk menyalin file dan direktori
    -   `ls`, untuk membuat daftar file dalam direktori
    -   `mkdir`, untuk membuat direktori
    -   `mv`, untuk memindahkan (mengganti nama) file dan direktori
    -   `rm`, untuk menghapus (menghapus) file
    -   `rmdir`, untuk menghapus (menghapus) direktori
-   Yang paling umum digunakan adalah `ls`yang akan mencantumkan semua file di direktori atau direktori saat ini. Lanjutkan dan ketik `ls`di jendela terminal dan tekan `enter`. Anda akan melihat semua file di folder saat ini.
-   Perintah lain yang berguna adalah `mv`, di mana Anda dapat memindahkan file dari satu file ke file lainnya. Misalnya, Anda dapat menggunakan perintah ini untuk mengganti nama `Hello.c`(perhatikan huruf besar `H`) menjadi `hello.c`dengan mengetik `mv Hello.c hello.c`.
-   Anda juga dapat membuat folder. Anda dapat mengetik `mkdir pset1`untuk membuat direktori bernama `pset1`.
-   Anda kemudian dapat menggunakan `cd pset1`untuk mengubah direktori Anda saat ini menjadi `pset1`.

## [Mario](https://cs50.harvard.edu/college/2022/fall/notes/1/#mario)

-   Semua yang telah kita diskusikan hari ini berfokus pada berbagai blok bangunan pekerjaan Anda sebagai seorang programmer.
-   Berikut ini akan membantu Anda mengarahkan untuk mengerjakan kumpulan masalah untuk kelas ini secara umum: Bagaimana seseorang mendekati masalah terkait ilmu komputer?
-   Bayangkan kita ingin meniru visual game Super Mario Bros. Dengan mempertimbangkan empat blok pertanyaan dalam gambar, bagaimana kita dapat membuat kode yang kira-kira mewakili empat blok horizontal ini?
    
    ![Tanda Tanya Mario](https://cs50.harvard.edu/college/2022/fall/notes/1/cs50Week1Slide123.png "Tanda Tanya Mario")
    
-   Di jendela terminal, ketik `code mario.c`dan kode sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        for (int i = 0; i < 4; i++)
        {
            printf("?");
        }
        printf("\n");
    }
    ```
    
    Perhatikan bagaimana empat tanda tanya dicetak di sini menggunakan lingkaran.
    
-   Demikian pula, kita dapat menerapkan logika yang sama untuk dapat membuat tiga blok vertikal.
    
    ![Blok Mario](https://cs50.harvard.edu/college/2022/fall/notes/1/cs50Week1Slide125.png "Blok Mario")
    
-   Untuk melakukannya, ubah kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        for (int i = 0; i < 3; i++)
        {
            printf("#\n");
        }
    }
    ```
    
    Perhatikan bagaimana tiga bata vertikal dicetak menggunakan lingkaran.
    
-   Bagaimana jika kita ingin menggabungkan ide-ide ini untuk membuat kelompok balok berukuran tiga kali tiga?
    
    ![Kotak Mario](https://cs50.harvard.edu/college/2022/fall/notes/1/cs50Week1Slide127.png "Kotak Mario")
    
-   Kita bisa mengikuti logika di atas, menggabungkan ide yang sama. Ubah kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 3; j++)
            {
                printf("#");
            }
            printf("\n");
        }
    }
    ```
    
    Notice that one loop is inside another. The first loop defines what vertical row is being printed. For each row, three columns are printed. After each row, a new line is printed.
    
-   What if we wanted to ensure that the number of blocks to be _constant_, that is, unchangeable? Modify your code as follows:
    
    ```
    int main(void)
    {
        const int n = 3;
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                printf("#");
            }
            printf("\n");
        }
    ```
    
    Notice how `n` is now a constant. It can never be changed.
    
-   As illustrated earlier in this lecture, we can make our code prompt the user for the size of the grid. Modify your code as follows:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        int n = get_int("Size: ");
    
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                printf("#");
            }
            printf("\n");
        }
    }
    ```
    
    Notice that `get_int` is used to prompt the user.
    
-   Saran umum dalam pemrograman adalah Anda tidak boleh sepenuhnya mempercayai pengguna Anda. Mereka kemungkinan besar akan berperilaku buruk, mengetikkan nilai yang salah di tempat yang tidak seharusnya. Kami dapat melindungi program kami dari perilaku buruk dengan memeriksa untuk memastikan input pengguna memenuhi kebutuhan kami. Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        int n;
        do
        {
            n = get_int("Size: ");
        }
        while (n < 1);
    
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                printf("#");
            }
            printf("\n");
        }
    }
    ```
    
    Perhatikan bagaimana pengguna terus dimintai ukuran hingga input pengguna adalah 1 atau lebih besar.
    

## [Komentar](https://cs50.harvard.edu/college/2022/fall/notes/1/#comments)

-   Komentar adalah bagian mendasar dari program komputer, tempat Anda meninggalkan komentar penjelasan untuk diri sendiri dan orang lain yang mungkin berkolaborasi dengan Anda terkait kode Anda.
-   Semua kode yang Anda buat untuk kursus ini harus menyertakan komentar yang kuat.
-   Biasanya setiap komentar terdiri dari beberapa kata atau lebih, memberikan kesempatan kepada pembaca untuk memahami apa yang terjadi di blok kode tertentu. Selanjutnya, komentar tersebut berfungsi sebagai pengingat bagi Anda nanti ketika Anda perlu merevisi kode Anda.
-   Komentar melibatkan penempatan `//`ke dalam kode Anda, diikuti dengan komentar. Ubah kode Anda sebagai berikut untuk mengintegrasikan komentar:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Get size of grid
        int n;
        do
        {
            n = get_int("Size: ");
        }
        while (n < 1);
    
        // Print grid of bricks
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                printf("#");
            }
            printf("\n");
        }
    }
    ```
    
    Perhatikan bagaimana setiap komentar dimulai dengan a `//`.
    

## [Abstraksi](https://cs50.harvard.edu/college/2022/fall/notes/1/#abstraction)

-   _Abstraksi_ adalah seni menyederhanakan kode kita sedemikian rupa sehingga menangani masalah yang semakin kecil.
-   Melihat kode Anda, Anda dapat melihat bagaimana dua masalah penting dalam kode kami adalah _get size of grid_ dan _print grid of bricks_ .
-   Kita dapat memisahkan kedua masalah ini menjadi fungsi yang terpisah. Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int get_size(void);
    void print_grid(int n);
    
    int main(void)
    {
        int n = get_size();
        print_grid(n);
    }
    
    int get_size(void)
    {
        int n;
        do
        {
            n = get_int("Size: ");
        }
        while (n < 1);
        return n;
    }
    
    void print_grid(int n)
    {
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                printf("#");
            }
            printf("\n");
        }
    }
    ```
    
    Perhatikan bahwa kita memiliki tiga fungsi sekarang. Pertama, kita memiliki `main`fungsi yang memanggil dua fungsi lain yang disebut `get_size`dan `print_grid`. Kedua, kami memiliki fungsi kedua yang disebut `get_size`yang menyertakan kode persis yang harus kami selesaikan untuk tugas ini sebelumnya. Ketiga, kami memiliki fungsi lain yang disebut `print_grid`mencetak kisi. Karena kami mengabstraksi masalah-masalah penting dalam program kami, `main`fungsi kami sangat singkat.
    

## [Operator dan Jenis](https://cs50.harvard.edu/college/2022/fall/notes/1/#operators-and-types)

-   _Operator_ mengacu pada operasi matematika yang didukung oleh kompiler Anda. Dalam C, operator matematika ini meliputi:
    
    -   `+`untuk tambahan
    -   `-`untuk pengurangan
    -   `*`untuk perkalian
    -   `/`untuk pembagian
    -   `%`untuk sisa
-   Tipe mengacu pada kemungkinan data yang dapat disimpan dalam variabel. Misalnya, a `char`dirancang untuk mengakomodasi satu karakter seperti `a`atau `2`.
-   Jenis sangat penting karena setiap jenis memiliki batasan tertentu. Misalnya, karena batasan dalam memori, nilai tertinggi dari suatu `int`dapat menjadi `4294967296`.
-   Jenis yang mungkin berinteraksi dengan Anda selama kursus ini meliputi:
    
    -   `bool`, ekspresi Boolean benar atau salah
    -   `char`, satu karakter seperti a atau 2
    -   `double`, nilai titik-mengambang dengan lebih banyak digit daripada pelampung
    -   `float`, nilai floating-point, atau bilangan real dengan nilai desimal
    -   `int`, bilangan bulat hingga ukuran tertentu, atau jumlah bit
    -   `long`, bilangan bulat dengan lebih banyak bit, sehingga mereka dapat menghitung lebih tinggi dari int
    -   `string`, serangkaian karakter
-   Anda dapat mengimplementasikan kalkulator di C. Di terminal Anda, ketik `code calculator.c`dan tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Prompt user for x
        int x = get_int("x: ");
    
        // Prompt user for y
        int y = get_int("y: ");
    
        // Perform addition
        printf("%i\n", x + y);
    }
    ```
    
    Perhatikan bagaimana `get_int`fungsi digunakan untuk mendapatkan bilangan bulat dari pengguna dua kali. Satu bilangan bulat disimpan dalam `int`variabel yang disebut `x`. Lain disimpan dalam `int`variabel yang disebut `y`. Kemudian, `printf`fungsi mencetak nilai `x + y`, yang ditunjukkan oleh `%i`simbol.
    
-   Saat Anda membuat kode, beri perhatian khusus pada jenis variabel yang Anda gunakan untuk menghindari masalah dalam kode Anda.

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/1/#summing-up)

Dalam pelajaran ini, Anda belajar bagaimana menerapkan blok penyusun yang Anda pelajari di Scratch ke bahasa pemrograman C. Anda belajar…

-   Cara membuat program pertama Anda di C.
-   Fungsi yang telah ditentukan sebelumnya yang datang secara native dengan C dan cara mengimplementasikan fungsi Anda sendiri.
-   Cara menggunakan variabel, conditional, dan loop.
-   Cara menggunakan baris perintah Linux.
-   Bagaimana mendekati pemecahan masalah untuk masalah ilmu komputer.
-   Cara mengintegrasikan komentar ke dalam kode Anda.
-   Cara mendekati abstraksi untuk menyederhanakan dan meningkatkan kode Anda.
-   Bagaimana memanfaatkan jenis dan operator.

Sampai jumpa lain waktu!
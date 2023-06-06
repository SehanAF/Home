# [Kuliah 4](https://cs50.harvard.edu/college/2022/fall/notes/4/#lecture-4)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/4/#welcome)
-   [Penyimpanan](https://cs50.harvard.edu/college/2022/fall/notes/4/#memory)
-   [Heksadesimal](https://cs50.harvard.edu/college/2022/fall/notes/4/#hexadecimal)
-   [Alamat](https://cs50.harvard.edu/college/2022/fall/notes/4/#addresses)
-   [Pointer](https://cs50.harvard.edu/college/2022/fall/notes/4/#pointers)
-   [String](https://cs50.harvard.edu/college/2022/fall/notes/4/#strings)
-   [Pointer Aritmatika](https://cs50.harvard.edu/college/2022/fall/notes/4/#pointer-arithmetic)
-   [Membandingkan String](https://cs50.harvard.edu/college/2022/fall/notes/4/#comparing-strings)
-   [Penyalinan](https://cs50.harvard.edu/college/2022/fall/notes/4/#copying)
-   [Valgrind](https://cs50.harvard.edu/college/2022/fall/notes/4/#valgrind)
-   [Nilai Sampah](https://cs50.harvard.edu/college/2022/fall/notes/4/#garbage-values)
-   [Pointer Fun dengan Binky](https://cs50.harvard.edu/college/2022/fall/notes/4/#pointer-fun-with-binky)
-   [Menukar](https://cs50.harvard.edu/college/2022/fall/notes/4/#swap)
-   [Meluap](https://cs50.harvard.edu/college/2022/fall/notes/4/#overflow)
-   [`scanf`](https://cs50.harvard.edu/college/2022/fall/notes/4/#scanf)
-   [File](https://cs50.harvard.edu/college/2022/fall/notes/4/#files)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/4/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/4/#welcome)

-   Di minggu-minggu sebelumnya, kita berbicara tentang gambar yang dibuat dari blok penyusun yang lebih kecil yang disebut piksel.
-   Hari ini, kita akan membahas detail lebih lanjut tentang nol dan satu yang menyusun gambar-gambar ini.
-   Selanjutnya kita akan membahas cara mengakses data pokok yang tersimpan di memori komputer.

## [Penyimpanan](https://cs50.harvard.edu/college/2022/fall/notes/4/#memory)

-   Anda dapat membayangkan sebuah drama kriminal di mana gambar ditingkatkan, ditingkatkan, dan ditingkatkan, tidak sepenuhnya akurat dalam kehidupan nyata. Memang, jika Anda terus memperbesar gambar, Anda akan melihat piksel.
    
    ![Foto buram](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide012.png "buram")
    
-   Anda dapat membayangkan gambar sebagai peta bit, di mana nol mewakili hitam dan satu mewakili putih.
    
    ![Nol dan satu diubah menjadi smiley hitam putih](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide015.png "tersenyum")
    
-   _RGB_ , atau _red, green, blue_ , adalah angka yang mewakili jumlah masing-masing warna tersebut. Di Adobe Photoshop, Anda dapat melihat pengaturan ini sebagai berikut:
    
    ![Panel photoshop dengan nilai RGB dan input heksadesimal](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide016.png "hex di photoshop")
    
    Perhatikan bagaimana jumlah warna merah, biru, dan hijau mengubah warna yang dipilih.
    
-   Anda dapat melihat dari gambar di atas bahwa warna tidak hanya direpresentasikan dalam tiga nilai. Di bagian bawah jendela, terdapat nilai khusus yang terdiri dari angka dan karakter. `255`direpresentasikan sebagai `FF`. Mengapa ini bisa terjadi?
    

## [Heksadesimal](https://cs50.harvard.edu/college/2022/fall/notes/4/#hexadecimal)

-   _Heksadesimal_ adalah sistem penghitungan yang memiliki 16 nilai penghitungan. Mereka adalah sebagai berikut:
    
    ```
      0 1 2 3 4 5 6 7 8 9 a b c d e f
    ```
    
    Perhatikan yang `F`mewakili `15`.
    
-   Heksadesimal juga dikenal sebagai _basis-16_ .
-   Saat menghitung dalam heksadesimal, setiap kolom adalah pangkat 16.
-   Angka tersebut `0`direpresentasikan sebagai `00`.
-   Angka tersebut `1`direpresentasikan sebagai `01`.
-   Jumlah `9`diwakili oleh `09`.
-   Angka tersebut `10`direpresentasikan sebagai `0A`.
-   Angka tersebut `15`direpresentasikan sebagai `0F`.
-   Angka tersebut `16`direpresentasikan sebagai `10`.
-   Bilangan `255`dinyatakan sebagai `FF`, karena 16 x 15 (atau `F`) adalah 240. Tambahkan 15 lagi untuk menghasilkan 255. Ini adalah angka tertinggi yang dapat Anda hitung menggunakan sistem heksadesimal dua digit.
-   Heksadesimal berguna karena dapat direpresentasikan menggunakan lebih sedikit digit. Heksadesimal memungkinkan kita untuk merepresentasikan informasi dengan lebih ringkas.

## [Alamat](https://cs50.harvard.edu/college/2022/fall/notes/4/#addresses)

-   Dalam beberapa minggu yang lalu, Anda mungkin ingat artis kami membuat blok memori bersamaan. Menerapkan penomoran heksadesimal ke masing-masing blok memori ini, Anda dapat memvisualisasikannya sebagai berikut:
    
    ![Blok memori diberi nomor dalam hex](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide065.png "kutukan memori")
    
-   Anda dapat membayangkan bagaimana mungkin ada kebingungan mengenai apakah `10`blok di atas dapat mewakili lokasi di memori atau nilainya `10`. Oleh karena itu, berdasarkan konvensi, semua bilangan heksadesimal sering direpresentasikan dengan `0x`awalan sebagai berikut:
    
    ![blok memori bernomor hex dengan 0x](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide066.png "0x")
    
-   Di jendela terminal Anda, ketik `code addresses.c`dan tulis kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        int n = 50;
        printf("%i\n", n);
    }
    ```
    
    Perhatikan bagaimana `n`disimpan dalam memori dengan nilai `50`.
    
-   Anda dapat memvisualisasikan bagaimana program ini menyimpan nilai ini sebagai berikut:
    
    ![nilai 50 disimpan di lokasi memori dengan hex](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide070.png "hex")
    
-   Bahasa ini `C`memiliki dua operator kuat yang berhubungan dengan memori:
    
    ```
      & Provides the address of something stored in memory.
      * Instructs the compiler to go to a location in memory.
    ```
    
-   Kita dapat memanfaatkan pengetahuan ini dengan memodifikasi kode kita sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        int n = 50;
        printf("%p\n", &n);
    }
    ```
    
    Notice the `%p`, which allows us to view the address of a location in memory. `&n` can be literally translated as “the address of `n`.” Executing this code will return an address of memory beginning with `0x`.
    

## [Pointers](https://cs50.harvard.edu/college/2022/fall/notes/4/#pointers)

-   A _pointer_ is a variable that contains the address of some value. Most succinctly, a pointer is an address in your computer’s memory.
-   Consider the following code:
    
    ```
    int n = 50;
    
    int *p = &n;
    ```
    
    Notice that `p` is a pointer that contains a number that is the address of an integer `n`.
    
-   Modify your code as follows:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        int n = 50;
        int *p = &n;
        printf("%p\n", p);
    }
    ```
    
    Notice that this code has the same effect as our previous code. We have simply leveraged our new knowledge of the `&` and `*` operators.
    
-   You can visualize our code as follows:
    
    ![Nilai 50 yang sama di lokasi memori dengan nilai penunjuk disimpan di tempat lain](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide078.png "penunjuk")
    
    Perhatikan pointer tampak agak besar. Memang, pointer biasanya disimpan sebagai nilai 8-byte.
    
-   Anda dapat lebih akurat memvisualisasikan penunjuk sebagai satu alamat yang menunjuk ke yang lain:
    
    ![Penunjuk sebagai panah, menunjuk dari satu lokasi memori ke lokasi lainnya](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide079.png "penunjuk")
    
-   Untuk mengilustrasikan penggunaan operator `*`, pertimbangkan hal berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        int n = 50;
        int *p = &n;
        printf("%i\n", *p);
    }
    ```
    
    Perhatikan bahwa `printf`garis mencetak bilangan bulat di lokasi `p`.
    

## [String](https://cs50.harvard.edu/college/2022/fall/notes/4/#strings)

-   Sekarang kita memiliki model mental untuk petunjuk, kita dapat mengupas kembali tingkat penyederhanaan yang ditawarkan sebelumnya dalam kursus ini.
-   Ingat bahwa sebuah string hanyalah sebuah array dari karakter. Misalnya, `string s = "HI!"`dapat direpresentasikan sebagai berikut:
    
    ![String HI dengan tanda seru disimpan di memori](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide085.png "Hai")
    
-   Namun, apa `s`sebenarnya? Di mana `s`disimpan dalam memori? Seperti yang dapat Anda bayangkan, `s`perlu disimpan di suatu tempat. Anda dapat memvisualisasikan hubungan ke `s`string sebagai berikut:
    
    ![String HI yang sama dengan pointer yang menunjuk ke sana](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide086.png "hai penunjuk")
    
    Perhatikan bagaimana pointer yang dipanggil `s`memberi tahu kompiler di mana byte pertama dari string ada di memori.
    
-   Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        string s = "HI!";
        printf("%p\n", s);
        printf("%p\n", &s[0]);
        printf("%p\n", &s[1]);
        printf("%p\n", &s[2]);
        printf("%p\n", &s[3]);
    }
    ```
    
    Perhatikan di atas mencetak lokasi memori dari setiap karakter dalam string `s`.
    
-   Demikian juga, Anda dapat memodifikasi kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        char *s = "HI!";
        printf("%s\n", s);
    }
    ```
    
    Perhatikan bahwa kode ini akan menyajikan string yang dimulai pada lokasi `s`.
    

## [Pointer Aritmatika](https://cs50.harvard.edu/college/2022/fall/notes/4/#pointer-arithmetic)

-   Anda dapat memodifikasi kode Anda untuk mencapai hal yang sama dalam bentuk yang lebih panjang sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        char *s = "HI!";
        printf("%c\n", s[0]);
        printf("%c\n", s[1]);
        printf("%c\n", s[2]);
    }
    ```
    
    Perhatikan bahwa kami mencetak setiap karakter di lokasi `s`.
    
-   Selanjutnya, Anda dapat memodifikasi kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        char *s = "HI!";
        printf("%c\n", *s);
        printf("%c\n", *(s + 1));
        printf("%c\n", *(s + 2));
    }
    ```
    
    Perhatikan bahwa karakter pertama di lokasi `s`dicetak. Kemudian, karakter di lokasi tersebut `s + 1`dicetak, dan seterusnya.
    
-   Bisakah Anda bayangkan apa yang akan terjadi jika Anda mencoba mengakses sesuatu di lokasi `s + 50`? Peretas terkadang mencoba untuk mendapatkan akses ke item dalam memori yang seharusnya tidak dapat mereka akses. Jika Anda mencobanya, program kemungkinan akan berhenti sebagai tindakan pencegahan keamanan.
    

## [Membandingkan String](https://cs50.harvard.edu/college/2022/fall/notes/4/#comparing-strings)

-   Sebuah string karakter hanyalah sebuah array dari karakter yang diidentifikasi oleh byte pertama.
-   Ingatlah bahwa minggu lalu kami mengusulkan agar kami tidak dapat membandingkan dua string menggunakan `==`operator.
-   Memanfaatkan `==`operator dalam upaya membandingkan string akan mencoba membandingkan lokasi memori string, bukan karakter di dalamnya. Oleh karena itu, kami merekomendasikan penggunaan `strcmp`.
-   Untuk mengilustrasikannya, ketik `code compare.c`dan tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Get two strings
        char *s = get_string("s: ");
        char *t = get_string("t: ");
    
        // Compare strings' addresses
        if (s == t)
        {
            printf("Same\n");
        }
        else
        {
            printf("Different\n");
        }
    }
    ```
    
    Memperhatikan bahwa mengetik `HI!`untuk kedua string masih menghasilkan keluaran `Different`.
    
-   Mengapa string ini tampak berbeda? Anda dapat menggunakan yang berikut untuk memvisualisasikan alasannya:
    
    ![dua string disimpan secara terpisah dalam memori](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide115.png "dua string")
    
-   Untuk lebih jelasnya, Anda dapat melihat bagaimana gambar berikut mengilustrasikan pointer yang menunjuk ke dua lokasi terpisah di memori:
    
    ![dua string disimpan secara terpisah dalam memori dengan pointer terpisah yang menunjuk ke mereka](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide116.png "dua string")
    
-   Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Get two strings
        char *s = get_string("s: ");
        char *t = get_string("t: ");
    
        // Print strings
        printf("%s\n", s);
        printf("%s\n", t);
    }
    ```
    
    Perhatikan bagaimana kita sekarang memiliki dua string terpisah yang kemungkinan disimpan di dua lokasi terpisah.
    
-   Anda dapat melihat lokasi dari dua string yang tersimpan ini dengan sedikit modifikasi:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Get two strings
        char *s = get_string("s: ");
        char *t = get_string("t: ");
    
        // Print strings' addresses
        printf("%p\n", s);
        printf("%p\n", t);
    }
    ```
    
    Perhatikan bahwa `%s`telah diubah menjadi `%p`pernyataan cetak.
    

## [Penyalinan](https://cs50.harvard.edu/college/2022/fall/notes/4/#copying)

-   Kebutuhan umum dalam pemrograman adalah menyalin satu string ke string lainnya.
-   Di jendela terminal Anda, ketik `code copy.c`dan tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <ctype.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        // Get a string
        string s = get_string("s: ");
    
        // Copy string's address
        string t = s;
    
        // Capitalize first letter in string
        t[0] = toupper(t[0]);
    
        // Print string twice
        printf("s: %s\n", s);
        printf("t: %s\n", t);
    }
    ```
    
    Perhatikan bahwa `string t = s`menyalin alamat `s`ke `t`. Ini tidak mencapai apa yang kita inginkan. String tidak disalin – hanya alamatnya.
    
-   Sebelum kita mengatasi tantangan ini, penting untuk memastikan bahwa kita tidak mengalami _kesalahan segmentasi_ melalui kode kita, di mana kita berusaha menyalin `string s`ke `string t`, di mana `string t`tidak ada. Kami dapat menggunakan `strlen`fungsi sebagai berikut untuk membantu dengan itu:
    
    ```
    #include <cs50.h>
    #include <ctype.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        // Get a string
        string s = get_string("s: ");
    
        // Copy string's address
        string t = s;
    
        // Capitalize first letter in string
        if (strlen(t) > 0)
        {
            t[0] = toupper(t[0]);
        }
    
        // Print string twice
        printf("s: %s\n", s);
        printf("t: %s\n", t);
    }
    ```
    
    Perhatikan yang `strlen`digunakan untuk memastikan `string t`ada. Jika tidak, tidak ada yang akan disalin.
    
-   Anda dapat memvisualisasikan kode di atas sebagai berikut:
    
    ![dua pointer menunjuk ke lokasi memori yang sama dengan sebuah string](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide124.png "dua string")
    
    Perhatikan itu `s`dan `t`masih menunjuk pada blok memori yang sama. Ini bukan salinan asli dari sebuah string. Sebaliknya, ini adalah dua penunjuk yang menunjuk ke string yang sama.
    
-   Untuk dapat membuat salinan asli dari string, kita perlu memperkenalkan dua blok bangunan baru. Pertama, `malloc`memungkinkan Anda, programmer, untuk mengalokasikan blok dengan ukuran memori tertentu. Kedua, `free`memungkinkan Anda memberi tahu kompiler untuk _mengosongkan_ blok memori yang sebelumnya Anda alokasikan.
    
-   Kami dapat memodifikasi kode kami untuk membuat salinan asli dari string kami sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <ctype.h>
    #include <stdio.h>
    #include <stdlib.h>
    #include <string.h>
    
    int main(void)
    {
        // Get a string
        char *s = get_string("s: ");
    
        // Allocate memory for another string
        char *t = malloc(strlen(s) + 1);
    
        // Copy string into memory, including '\0'
        for (int i = 0; i <= strlen(s); i++)
        {
            t[i] = s[i];
        }
    
        // Capitalize copy
        t[0] = toupper(t[0]);
    
        // Print strings
        printf("s: %s\n", s);
        printf("t: %s\n", t);
    }
    ```
    
    Perhatikan bahwa `malloc(strlen(s) + 1)`membuat blok memori yang panjangnya string `s`ditambah satu. Hal ini memungkinkan penyertaan karakter _null_ `\0` dalam string terakhir yang disalin. Kemudian, `for`perulangan menelusuri string `s`dan menetapkan setiap nilai ke lokasi yang sama pada string `t`.
    
-   Ternyata ada inefisiensi dalam kode kita. Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <ctype.h>
    #include <stdio.h>
    #include <stdlib.h>
    #include <string.h>
    
    int main(void)
    {
        // Get a string
        char *s = get_string("s: ");
    
        // Allocate memory for another string
        char *t = malloc(strlen(s) + 1);
    
        // Copy string into memory, including '\0'
        for (int i = 0, n = strlen(s); i <= n; i++)
        {
            t[i] = s[i];
        }
    
        // Capitalize copy
        t[0] = toupper(t[0]);
    
        // Print strings
        printf("s: %s\n", s);
        printf("t: %s\n", t);
    }
    ```
    
    Perhatikan yang `n = strlen(s)`didefinisikan sekarang di sisi kiri `for loop`. Sebaiknya jangan memanggil fungsi yang tidak dibutuhkan di tengah kondisi loop `for`, karena akan berjalan berulang kali. Saat berpindah `n = strlen(s)`ke sisi kiri, fungsi `strlen`hanya berjalan sekali.
    
-   Bahasa `C`memiliki fungsi bawaan untuk menyalin string yang disebut `strcpy`. Itu dapat diimplementasikan sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <ctype.h>
    #include <stdio.h>
    #include <stdlib.h>
    #include <string.h>
    
    int main(void)
    {
        // Get a string
        char *s = get_string("s: ");
    
        // Allocate memory for another string
        char *t = malloc(strlen(s) + 1);
    
        // Copy string into memory
        strcpy(t, s);
    
        // Capitalize copy
        t[0] = toupper(t[0]);
    
        // Print strings
        printf("s: %s\n", s);
        printf("t: %s\n", t);
    }
    ```
    
    Perhatikan bahwa `strcpy`melakukan pekerjaan yang sama seperti yang `for`dilakukan loop kami sebelumnya.
    
-   Keduanya `get_string`dan `malloc`kembali `NULL`, nilai khusus dalam memori, jika terjadi kesalahan. Anda dapat menulis kode yang dapat memeriksa `NULL`kondisi ini sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <ctype.h>
    #include <stdio.h>
    #include <stdlib.h>
    #include <string.h>
    
    int main(void)
    {
        // Get a string
        char *s = get_string("s: ");
        if (s == NULL)
        {
            return 1;
        }
    
        // Allocate memory for another string
        char *t = malloc(strlen(s) + 1);
        if (t == NULL)
        {
            return 1;
        }
    
        // Copy string into memory
        strcpy(t, s);
    
        // Capitalize copy
        if (strlen(t) > 0)
        {
            t[0] = toupper(t[0]);
        }
    
        // Print strings
        printf("s: %s\n", s);
        printf("t: %s\n", t);
    
        // Free memory
        free(t);
        return 0;
    }
    ```
    
    Perhatikan bahwa jika string yang diperoleh panjangnya `0`atau malloc gagal, `NULL`dikembalikan. Lebih lanjut, perhatikan bahwa `free`beri tahu komputer bahwa Anda telah selesai dengan blok memori yang Anda buat melalui `malloc`.
    

## [Valgrind](https://cs50.harvard.edu/college/2022/fall/notes/4/#valgrind)

-   _Valgrind_ adalah alat yang dapat memeriksa apakah ada masalah terkait memori dengan program yang Anda gunakan `malloc`. Secara khusus, ini memeriksa untuk melihat apakah Anda memiliki `free`semua memori yang Anda alokasikan.
-   Pertimbangkan kode berikut:
    
    ```
    #include <stdio.h>
    #include <stdlib.h>
    
    int main(void)
    {
        int *x = malloc(3 * sizeof(int));
        x[1] = 72;
        x[2] = 73;
        x[3] = 33;
    }
    ```
    
    Perhatikan bahwa menjalankan program ini tidak menyebabkan kesalahan apa pun. While `malloc`digunakan untuk mengalokasikan memori yang cukup untuk sebuah array, kode gagal untuk `free`mengalokasikan memori tersebut.
    
-   Jika Anda mengetik `make memory`diikuti dengan `valgrind ./memory`, Anda akan mendapatkan laporan dari valgrind yang akan melaporkan di mana memori telah hilang akibat program Anda.
-   Anda dapat memodifikasi kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    #include <stdlib.h>
    
    int main(void)
    {
        int *x = malloc(3 * sizeof(int));
        x[1] = 72;
        x[2] = 73;
        x[3] = 33;
        free(x);
    }
    ```
    
    Perhatikan bahwa menjalankan valgrind lagi sekarang menghasilkan kebocoran memori.
    

## [Nilai Sampah](https://cs50.harvard.edu/college/2022/fall/notes/4/#garbage-values)

-   Saat Anda meminta kompiler untuk satu blok memori, tidak ada jaminan bahwa memori ini akan kosong.
-   Sangat mungkin memori yang Anda alokasikan ini sebelumnya digunakan oleh komputer. Oleh karena itu, Anda mungkin melihat _nilai_ _sampah_ atau sampah . Ini adalah hasil dari Anda mendapatkan blok memori tetapi tidak menginisialisasinya. Misalnya, pertimbangkan kode berikut:
    
    ```
    #include <stdio.h>
    #include <stdlib.h>
    
    int main(void)
    {
        int scores[1024];
        for (int i = 0; i < 1024; i++)
        {
            printf("%i\n", scores[i]);
        }
    }
    ```
    
    Perhatikan bahwa menjalankan kode ini akan mengalokasikan `1024`lokasi dalam memori untuk larik Anda, tetapi `for`pengulangan kemungkinan akan menunjukkan bahwa tidak semua nilai di dalamnya adalah `0`. Itu selalu praktik terbaik untuk menyadari potensi nilai sampah saat Anda tidak menginisialisasi blok memori ke beberapa nilai lain seperti nol atau sebaliknya.
    

## [Pointer Fun dengan Binky](https://cs50.harvard.edu/college/2022/fall/notes/4/#pointer-fun-with-binky)

-   Kami menonton [video dari Universitas Stanford](https://www.youtube.com/watch?v=5VnDaHBi8dM) yang membantu kami memvisualisasikan dan memahami petunjuk.

## [Menukar](https://cs50.harvard.edu/college/2022/fall/notes/4/#swap)

-   Di dunia nyata, kebutuhan umum dalam pemrograman adalah menukar dua nilai. Secara alami, sulit untuk menukar dua variabel tanpa ruang penyimpanan sementara. Dalam praktiknya, Anda dapat mengetik `code swap.c`dan menulis kode sebagai berikut untuk melihat tindakannya:
    
    ```
    #include <stdio.h>
    
    void swap(int a, int b);
    
    int main(void)
    {
        int x = 1;
        int y = 2;
    
        printf("x is %i, y is %i\n", x, y);
        swap(x, y);
        printf("x is %i, y is %i\n", x, y);
    }
    
    void swap(int a, int b)
    {
        int tmp = a;
        a = b;
        b = tmp;
    }
    ```
    
    Perhatikan bahwa saat kode ini berjalan, itu tidak berfungsi. Nilainya, bahkan setelah dikirim ke `swap`fungsi, jangan ditukar. Mengapa?
    
-   Saat Anda meneruskan nilai ke suatu fungsi, Anda hanya memberikan salinan. Pada minggu-minggu sebelumnya, kita sudah membahas konsep _scope_ . Nilai dari `x`dan `y`yang dibuat dalam `{}`kurung kurawal fungsi `main`hanya memiliki ruang lingkup fungsi `main`. Pertimbangkan gambar berikut:
    
    ![persegi panjang dengan kode mesin di atas diikuti oleh tumpukan dan tumpukan global](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide163.png "menumpuk dan menumpuk")
    
    Perhatikan bahwa variabel _global_ , yang belum kita gunakan dalam kursus ini, tinggal di satu tempat di memori. Berbagai fungsi disimpan di `stack`area lain di memori.
    
-   Sekarang, perhatikan gambar berikut:
    
    ![persegi panjang dengan fungsi utama di bawah dan tukar fungsi langsung di atasnya](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide167.png "bingkai")
    
    Perhatikan bahwa `main`dan `swap`memiliki dua _frame_ atau area memori yang terpisah. Oleh karena itu, kita tidak bisa begitu saja meneruskan nilai dari satu fungsi ke fungsi lainnya untuk mengubahnya.
    
-   Ubah kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    void swap(int *a, int *b);
    
    int main(void)
    {
        int x = 1;
        int y = 2;
    
        printf("x is %i, y is %i\n", x, y);
        swap(&x, &y);
        printf("x is %i, y is %i\n", x, y);
    }
    
    void swap(int *a, int *b)
    {
        int tmp = *a;
        *a = *b;
        *b = tmp;
    }
    ```
    
    Perhatikan bahwa variabel tidak diteruskan oleh _nilai_ tetapi oleh _referensi_ . Artinya, alamat `a`dan `b`disediakan untuk fungsi tersebut. Oleh karena itu, `swap`fungsi dapat mengetahui di mana harus melakukan perubahan aktual `a`dan `b`dari fungsi utama.
    
-   Anda dapat memvisualisasikannya sebagai berikut:
    
    ![a dan b disimpan dalam fungsi utama yang diteruskan dengan referensi ke fungsi swap](https://cs50.harvard.edu/college/2022/fall/notes/4/cs50Week4Slide173.png "tukar dengan referensi")
    

## [Meluap](https://cs50.harvard.edu/college/2022/fall/notes/4/#overflow)

-   Heap _overflow_ adalah saat Anda meluapkan heap, menyentuh area memori yang tidak seharusnya Anda sentuh.
-   Stack _overflow_ adalah ketika terlalu banyak fungsi dipanggil, melebihi jumlah memori yang tersedia.
-   Keduanya dianggap _buffer overflows_ .

## [`scanf`](https://cs50.harvard.edu/college/2022/fall/notes/4/#scanf)

-   Di CS50, kami telah membuat fungsi seperti `get_int`menyederhanakan tindakan mendapatkan masukan dari pengguna.
-   `scanf`adalah fungsi bawaan yang bisa mendapatkan input pengguna.
-   Kita dapat mengimplementasikan ulang `get_int`dengan mudah menggunakan `scanf`sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        int x;
        printf("x: ");
        scanf("%i", &x);
        printf("x: %i\n", x);
    }
    ```
    
    Perhatikan bahwa nilai `x`disimpan di lokasi `x`di baris `scanf("%i", &x)`.
    
-   Namun, upaya untuk mengimplementasikan kembali `get_string`tidaklah mudah. Pertimbangkan hal berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        char *s;
        printf("s: ");
        scanf("%s", s);
        printf("s: %s\n", s);
    }
    ```
    
    Perhatikan bahwa tidak `&`diperlukan karena string adalah spesial. Tetap saja, program ini tidak akan berfungsi. Tidak ada tempat dalam program ini kami mengalokasikan jumlah memori yang diperlukan untuk string kami.
    
-   Kita dapat memodifikasi kode kita sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        char s[4];
        printf("s: ");
        scanf("%s", s);
        printf("s: %s\n", s);
    }
    ```
    
    Perhatikan bahwa jika kita mengalokasikan sebelumnya array size `4`, kita dapat mengetik `cat`dan fungsi program. Namun, string yang lebih besar dari ini akan menimbulkan kesalahan.
    

## [File](https://cs50.harvard.edu/college/2022/fall/notes/4/#files)

-   Anda dapat membaca dari dan memanipulasi file. Sementara topik ini akan dibahas lebih lanjut di minggu mendatang, pertimbangkan kode berikut untuk `phonebook.c`:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        // Open CSV file
        FILE *file = fopen("phonebook.csv", "a");
    
        // Get name and number
        char *name = get_string("Name: ");
        char *number = get_string("Number: ");
    
        // Print to file
        fprintf(file, "%s,%s\n", name, number);
    
        // Close file
        fclose(file);
    }
    ```
    
    Perhatikan bahwa kode ini menggunakan pointer untuk mengakses file.
    
-   Anda dapat membuat file bernama `phonebook.csv`sebelum menjalankan kode di atas. Setelah menjalankan program di atas dan memasukkan nama dan nomor telepon, Anda akan melihat bahwa data ini tetap ada di file CSV Anda.
    

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/4/#summing-up)

Dalam pelajaran ini, Anda mempelajari tentang pointer yang memberi Anda kemampuan untuk mengakses dan memanipulasi data di lokasi memori tertentu. Secara khusus, kami mempelajari…

-   Penyimpanan
-   Heksadesimal
-   Alamat
-   Pointer
-   String
-   Pointer Aritmatika
-   Membandingkan string
-   Penyalinan
-   Valgrind
-   Nilai sampah
-   Menukar
-   Meluap
-   `scanf`

Sampai jumpa lain waktu!
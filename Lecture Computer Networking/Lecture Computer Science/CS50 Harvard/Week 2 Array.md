# [Kuliah 2](https://cs50.harvard.edu/college/2022/fall/notes/2/#lecture-2)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/2/#welcome)
-   [Kompilasi](https://cs50.harvard.edu/college/2022/fall/notes/2/#compiling)
-   [Men-debug](https://cs50.harvard.edu/college/2022/fall/notes/2/#debugging)
-   [Array](https://cs50.harvard.edu/college/2022/fall/notes/2/#arrays)
-   [String](https://cs50.harvard.edu/college/2022/fall/notes/2/#strings)
-   [Argumen Baris Perintah](https://cs50.harvard.edu/college/2022/fall/notes/2/#command-line-arguments)
-   [Keluar Status](https://cs50.harvard.edu/college/2022/fall/notes/2/#exit-status)
-   [Kriptografi](https://cs50.harvard.edu/college/2022/fall/notes/2/#cryptography)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/2/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/2/#welcome)

-   Pada sesi sebelumnya, kita telah mempelajari tentang C, sebuah bahasa pemrograman berbasis teks.
-   Minggu ini, kita akan melihat lebih dalam blok penyusun tambahan yang akan mendukung tujuan kita untuk mempelajari lebih lanjut tentang pemrograman dari bawah ke atas.
-   Pada dasarnya, selain esensi pemrograman, kursus ini adalah tentang pemecahan masalah. Oleh karena itu, kami juga akan lebih fokus pada bagaimana mendekati masalah ilmu komputer.

## [Kompilasi](https://cs50.harvard.edu/college/2022/fall/notes/2/#compiling)

-   _Enkripsi_ adalah tindakan menyembunyikan teks biasa dari mencongkel mata. _mendekripsi_ , kemudian, adalah tindakan mengambil sepotong teks terenkripsi dan mengembalikannya ke bentuk yang dapat dibaca manusia.
-   Sepotong teks terenkripsi mungkin terlihat seperti berikut:
    
    ![enkripsi](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide008.png "enkripsi")
    
-   Ingatlah bahwa minggu lalu Anda belajar tentang _kompiler_ , program komputer khusus yang mengubah _kode sumber_ menjadi _kode mesin_ yang dapat dipahami oleh komputer.
-   Misalnya, Anda mungkin memiliki program komputer yang terlihat seperti ini:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        printf("hello, world\n");
    }
    ```
    
-   Kompiler akan mengambil kode di atas dan mengubahnya menjadi kode mesin berikut:
    
    ![kode mesin](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide012.png "kode mesin")
    
-   _VS Code_ , lingkungan pemrograman yang disediakan untuk Anda sebagai siswa CS50, menggunakan kompiler bernama `clang`atau _c language_ .
-   Jika Anda mengetik `make hello`, itu menjalankan perintah yang mengeksekusi dentang untuk membuat file keluaran yang dapat Anda jalankan sebagai pengguna.
-   VS Code telah diprogram sebelumnya sehingga `make`akan menjalankan banyak argumen baris perintah bersama dentang untuk kenyamanan Anda sebagai pengguna.
-   Pertimbangkan kode berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        string name = get_string("What's your name? ");
        printf("hello, %s\n", name);
    }
    ```
    
-   Anda dapat mencoba masuk ke jendela terminal: `clang -o hello hello.c`. Anda akan menemui kesalahan yang menunjukkan bahwa dentang tidak tahu di mana menemukan perpustakaan `cs50.h`.
-   Mencoba lagi mengkompilasi kode ini, jalankan perintah berikut di jendela terminal: `clang -o hello hello.c -lcs50`. Ini akan memungkinkan kompiler untuk mengakses `cs50.h`perpustakaan.
-   Berjalan di jendela terminal `./hello`, program Anda akan berjalan sebagaimana mestinya.
-   Sementara hal di atas ditawarkan sebagai ilustrasi, sehingga Anda dapat memahami lebih dalam proses dan konsep kompilasi kode, menggunakan `make`CS50 sangat baik dan sesuai harapan!
-   Kompilasi melibatkan langkah-langkah utama, termasuk yang berikut:
    
    -   Pertama, _preprocessing_ adalah tempat file header dalam kode Anda, yang ditunjuk oleh `#`(seperti `#include \<cs50.h\>`) disalin dan ditempelkan secara efektif ke dalam file Anda. Selama langkah ini, kode dari `cs50.h`disalin ke dalam program Anda. Demikian pula, sama seperti kode Anda berisi `#include \<stdio.h\>`, kode yang terdapat di `stdio.h`suatu tempat di komputer Anda akan disalin ke program Anda. Langkah ini dapat divisualisasikan sebagai berikut:
    
    ```
    ...
    string get_string(string prompt);
    int printf(string format, ...);
    ...
    
    int main(void)
    {
        string name = get_string("What's your name? ");
        printf("hello, %s\n", name);
    }
    ```
    
    -   Kedua, _kompilasi_ adalah tempat program Anda diubah menjadi kode rakitan. Langkah ini dapat divisualisasikan sebagai berikut:
        
        ![kompilasi](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide033.png "kompilasi")
        
    -   Ketiga, _perakitan_ melibatkan kompiler yang mengubah kode rakitan Anda menjadi kode mesin. Langkah ini dapat divisualisasikan sebagai berikut:
        
        ![perakitan](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide038.png "perakitan")
        
    -   Terakhir, selama langkah _penautan_ , kode dari pustaka yang Anda sertakan juga diubah menjadi kode mesin dan digabungkan dengan kode Anda. File terakhir yang dapat dieksekusi kemudian dikeluarkan.
        
        ![menghubungkan](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide049.png "menghubungkan")
        

## [Men-debug](https://cs50.harvard.edu/college/2022/fall/notes/2/#debugging)

-   Setiap orang akan membuat kesalahan saat coding.
-   Pertimbangkan gambar berikut dari minggu lalu:
    
    ![mario](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide061.png "mario")
    
-   Selanjutnya, pertimbangkan kode berikut yang memiliki bug yang sengaja dimasukkan di dalamnya:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        for (int i = 0; i <= 3; i++)
        {
            printf("#\n");
        }
    }
    ```
    
-   Ketik `code buggy0.c`di jendela terminal dan tulis kode di atas.
-   Menjalankan kode ini, empat bata muncul, bukan tiga yang dimaksud.
-   `printf`adalah cara yang sangat berguna untuk men-debug kode Anda. Anda dapat memodifikasi kode Anda sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        for (int i = 0; i <= 3; i++)
        {
            printf("i is %i\n", i);
            printf("#\n");
        }
    }
    ```
    
-   Menjalankan kode ini, Anda akan melihat banyak pernyataan, termasuk `i is 0`, `i is 1`, `i is 2`, dan `i is 3`. Melihat ini, Anda mungkin menyadari bahwa kode lebih lanjut perlu diperbaiki sebagai berikut:
    
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
    
    Perhatikan `<=`telah diganti dengan `<`.
    
-   Alat kedua dalam debugging disebut _debugger_ , alat perangkat lunak yang dibuat oleh pemrogram untuk membantu melacak bug dalam kode.
-   Dalam VS Code, debugger yang telah dikonfigurasi sebelumnya telah disediakan untuk Anda.
-   Untuk memanfaatkan debugger ini, pertama-tama setel _breakpoint_ dengan mengeklik di sebelah kiri baris kode Anda, tepat di sebelah kiri nomor baris. Ketika Anda mengklik di sana, Anda akan melihat titik merah muncul. Bayangkan ini sebagai tanda berhenti, meminta kompiler untuk berhenti sejenak sehingga Anda dapat mempertimbangkan apa yang terjadi di bagian kode Anda ini.
    
    ![titik istirahat](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Debugging.png "titik istirahat")
    
-   Second, run `debug50 ./buggy0`. You will notice that after the debugger comes to life that a line of your code will illuminate in a gold-like color. Quite literally, the code has _paused_ at this line of code. Notice in the top left corner how all local variables are being displayed, including `i`, which has a current value of `0`. At the top of your window, you can click the `step over` button and it will keep moving through your code. Notice how the value of `i` increases.
-   While this tool will not show you where your bug is, it will help you slow down and see how your code is running step by step.
    
-   To illustrate a third means of debugging, please start a new file by running `code buggy1.c` in your terminal window. Write your code as follows:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int get_negative_int(void);
    
    int main(void)
    {
        int i = get_negative_int();
        printf("%i\n", i);
    }
    
    // Prompt user for positive integer
    int get_negative_int(void)
    {
        int n;
        do
        {
            n = get_int("Negative Integer: ");
        }
        while (n < 0);
        return n;
    }
    ```
    
    Notice `get_negative_int` is designed to get a negative integer from the user.
    
-   Running `make buggy1`, you’ll notice that it does not do as intended. It accepts positive integers and seems to ignore negative ones.
-   As before, set a breakpoint at a line of your code. Best to set a breakpoint at `int i = get_negative_int`. Now, run `debug50 buggy1`.
-   Unlike before, where you utilized the `step over` button at the top of the window, use the `step into` button. This will take the debugger into your `get_negative_int` function. Notice how doing this will show you that you are, indeed, stuck in the `do while` loop.
-   With this knowledge, you might consider why you are stuck in this loop, leading you to edit your code as follows:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int get_negative_int(void);
    
    int main(void)
    {
        int i = get_negative_int();
        printf("%i\n", i);
    }
    
    // Prompt user for positive integer
    int get_negative_int(void)
    {
        int n;
        do
        {
            n = get_int("Negative Integer: ");
        }
        while (n >= 0);
        return n;
    }
    ```
    
    Notice `n < 0` has been changed.
    
-   A final form of debugging is called _rubber duck debugging_. When you are having challenges with your code, consider how speaking out loud to, quite literally, a rubber duck about the code problem. If you’d rather not talk to a small plastic duck, you are welcome to speak to a human near you! They need not understand how to program: Speaking with them is an opportunity for you to speak about your code.
    
    ![bebek](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide070.png "bebek")
    

## [Arrays](https://cs50.harvard.edu/college/2022/fall/notes/2/#arrays)

-   In Week 0, we talked about _data types_ such as `bool`, `int`, `char`, `string`, etc.
-   Each data type requires a certain amount of system resources:
    -   `bool` 1 byte
    -   `int` 4 bytes
    -   `long` 8 bytes
    -   `float` 4 bytes
    -   `double` 8 bytes
    -   `char` 1 byte
    -   `string` ? bytes
-   Inside of your computer, you have a finite amount of memory available.
    
    ![Penyimpanan](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide084.png "Penyimpanan")
    
-   Secara fisik, pada memori komputer Anda, Anda dapat membayangkan bagaimana jenis data tertentu disimpan di komputer Anda. Anda mungkin membayangkan bahwa a `char`, yang hanya membutuhkan 1 byte memori, mungkin terlihat seperti berikut:
    
    ![1 byte](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide087.png "1 byte")
    
-   Demikian pula, sebuah `int`, yang membutuhkan 4 byte mungkin terlihat seperti berikut:
    
    ![4 byte](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide088.png "4 byte")
    
-   Kita dapat membuat program yang mengeksplorasi konsep-konsep ini. Di dalam terminal Anda, ketik `code scores.c`dan tulis kode sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        // Scores
        int score1 = 72;
        int score2 = 73;
        int score3 = 33;
    
        // Print average
        printf("Average: %f\n", (score1 + score2 + score3) / 3.0);
    }
    ```
    
    Perhatikan bahwa angka di sebelah kanan adalah nilai floating point dari `3.0`, sehingga perhitungannya diberikan sebagai nilai floating point pada akhirnya.
    
-   Running `make scores`, program berjalan.
-   Anda dapat membayangkan bagaimana variabel-variabel ini disimpan dalam memori:
    
    ![skor dalam memori](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide098.png "skor dalam memori")
    
-   _Array_ adalah cara menyimpan data secara berurutan dalam memori sehingga data ini mudah diakses.
-   `int scores[3]` is a way of telling the compiler to provide you three back-to-back places in memory of size `int` to store three `scores`. Considering our program, you can revise your code as follows:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Scores
        int scores[3];
        scores[0] = 72;
        scores[1] = 73;
        scores[2] = 33;
    
        // Print average
        printf("Average: %f\n", (scores[0] + scores[1] + scores[2]) / 3.0);
    }
    ```
    
    Notice that `score[0]` examines the value at this location of memory by `indexing into` the array called `scores` at location `0` to see what value is stored there.
    
-   You can see how while the above code works, there is still an opportunity for improving our code. Revise your code as follows:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Get scores
        int scores[3];
        for (int i = 0; i < 3; i++)
        {
            scores[i] = get_int("Score: ");
        }
    
        // Print average
        printf("Average: %f\n", (scores[0] + scores[1] + scores[2]) / 3.0);
    }
    ```
    
    Notice how we index into `scores` by using `scores[i]` where `i` is supplied by the `for` loop.
    
-   We can simplify or _abstract away_ the calculation of the average. Modify your code as follows:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    // Constant
    const int N = 3;
    
    // Prototype
    float average(int length, int array[]);
    
    int main(void)
    {
        // Get scores
        int scores[N];
        for (int i = 0; i < N; i++)
        {
            scores[i] = get_int("Score: ");
        }
    
        // Print average
        printf("Average: %f\n", average(N, scores));
    }
    
    float average(int length, int array[])
    {
        // Calculate average
        int sum = 0;
        for (int i = 0; i < length; i++)
        {
            sum += array[i];
        }
        return sum / (float) length;
    }
    ```
    
    Perhatikan bahwa fungsi baru yang dipanggil `average`telah dideklarasikan. Selanjutnya, perhatikan bahwa `const`nilai a atau konstanta dari `N`dinyatakan. Yang terpenting, perhatikan bagaimana `average`fungsi mengambil `int array[]`, yang berarti kompiler meneruskan array ke fungsi ini.
    
-   Array tidak hanya dapat menjadi wadah: Mereka dapat diteruskan di antara fungsi.

## [String](https://cs50.harvard.edu/college/2022/fall/notes/2/#strings)

-   A `string`hanyalah sebuah array dari variabel tipe `char`: array karakter.
-   Mempertimbangkan gambar berikut, Anda dapat melihat bagaimana string adalah larik karakter yang dimulai dengan karakter pertama dan diakhiri dengan karakter khusus yang disebut a `NUL character`:
    
    ![hai dengan terminator](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide116.png "hai dengan terminator")
    
-   Membayangkan ini dalam desimal, array Anda akan terlihat seperti berikut:
    
    ![hai dengan desimal](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide117.png "hai dengan desimal")
    
-   Menerapkan ini dalam kode Anda sendiri, ketik `code hi.c`jendela terminal dan tulis kode sebagai berikut:
    
    ```
    #include <stdio.h>
    
    int main(void)
    {
        char c1 = 'H';
        char c2 = 'I';
        char c3 = '!';
    
        printf("%i %i %i\n", c1, c2, c3);
    }
    ```
    
    Perhatikan bahwa ini akan menampilkan nilai desimal dari setiap karakter.
    
-   Untuk lebih memahami cara `string`kerja, revisi kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        string s = "HI!";
        printf("%i %i %i\n", s[0], s[1], s[2]);
    }
    ```
    
    Perhatikan bagaimana `printf`pernyataan menyajikan tiga nilai dari array kita yang disebut `s`.
    
-   Bayangkan kita ingin mengatakan keduanya `HI!`dan `BYE!`. Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        string s = "HI!";
        string t = "BYE!";
    
        printf("%s\n", s);
        printf("%s\n", t);
    }
    ```
    
    Perhatikan bahwa dua string dideklarasikan dan digunakan dalam contoh ini.
    
-   Anda dapat memvisualisasikannya sebagai berikut:
    
    ![hai dan selamat tinggal](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide126.png "hai dan selamat tinggal")
    
-   Kami dapat lebih meningkatkan kode ini. Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        string words[2];
    
        words[0] = "HI!";
        words[1] = "BYE!";
    
        printf("%s\n", words[0]);
        printf("%s\n", words[1]);
    }
    ```
    
    Perhatikan bahwa kedua string disimpan dalam satu larik bertipe `string`.
    
-   Masalah umum dalam pemrograman, dan mungkin C lebih khusus lagi, adalah menemukan panjang dari sebuah array. Bagaimana kita bisa mengimplementasikan ini dalam kode? Ketik `code length.c`jendela terminal dan kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Prompt for user's name
        string name = get_string("Name: ");
    
        // Count number of characters up until '\0' (aka NUL)
        int n = 0;
        while (name[n] != '\0')
        {
            n++;
        }
        printf("%i\n", n);
    }
    ```
    
    Perhatikan bahwa kode ini berulang hingga `NUL`karakter ditemukan.
    
-   Karena ini adalah masalah umum dalam pemrograman, pemrogram lain telah membuat kode di perpustakaan `string.h`untuk menemukan panjang string. Anda dapat menemukan panjang string dengan memodifikasi kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        // Prompt for user's name
        string name = get_string("Name: ");
        int length = strlen(name);
        printf("%i\n", length);
    }
    ```
    
    Perhatikan bahwa kode ini menggunakan `string.h`pustaka, yang dideklarasikan di bagian atas file. Selanjutnya, ia menggunakan fungsi dari pustaka yang disebut `strlen`, yang menghitung panjang string yang diteruskan ke sana.
    
-   `ctype.h`adalah perpustakaan lain yang cukup berguna. Bayangkan kami ingin membuat program yang mengubah semua karakter huruf kecil menjadi huruf besar. Di jendela terminal ketik `code uppercase.c`dan tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        string s = get_string("Before: ");
        printf("After:  ");
        for (int i = 0, n = strlen(s); i < n; i++)
        {
            if (s[i] >= 'a' && s[i] <= 'z')
            {
                printf("%c", s[i] - 32);
            }
            else
            {
                printf("%c", s[i]);
            }
        }
        printf("\n");
    }
    ```
    
    Notice that this code _iterates_ through each value in the string. The program looks at each character. If the character is lowercase, it subtracts the value 32 from it to convert it to lowercase.
    
-   Recalling our previous work from last week, you might remember this ASCII values chart:
    
    ![ascii](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide120.png "ascii")
    
-   When a lowercase character has `32` subtracted from it, it results in an uppercase version of that same character.
-   While the program does what we want, there is an easier way using the `ctype.h` library. Modify your program as follows:
    
    ```
    #include <cs50.h>
    #include <ctype.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        string s = get_string("Before: ");
        printf("After:  ");
        for (int i = 0, n = strlen(s); i < n; i++)
        {
            if (islower(s[i]))
            {
                printf("%c", toupper(s[i]));
            }
            else
            {
                printf("%c", s[i]);
            }
        }
        printf("\n");
    }
    ```
    
    Notice that the program uses `islower` to detect if each character is uppercase or lowercase. Then, the `toupper` function is passed `s[i]`. Each character (if lowercase) is converted to uppercase.
    
-   Sekali lagi, sementara program ini melakukan apa yang diinginkan, ada peluang untuk perbaikan. Sebagai dokumentasi untuk `ctype.h`status, `toupper`cukup pintar untuk mengetahui bahwa jika dilewatkan apa yang sudah menjadi huruf besar, itu akan diabaikan begitu saja. Oleh karena itu, kami tidak lagi membutuhkan `if`pernyataan kami. Anda dapat menyederhanakan kode ini sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <ctype.h>
    #include <stdio.h>
    #include <string.h>
    
    int main(void)
    {
        string s = get_string("Before: ");
        printf("After:  ");
        for (int i = 0, n = strlen(s); i < n; i++)
        {
            printf("%c", toupper(s[i]));
        }
        printf("\n");
    }
    ```
    
    Perhatikan bahwa kode ini cukup disederhanakan, menghilangkan `if`pernyataan yang tidak perlu.
    
-   Anda dapat membaca tentang semua kemampuan perpustakaan `ctype`di [Halaman Manual](https://manual.cs50.io/#ctype.h) .

## [Argumen Baris Perintah](https://cs50.harvard.edu/college/2022/fall/notes/2/#command-line-arguments)

-   `Command-line arguments`adalah argumen yang diteruskan ke program Anda di baris perintah. Misalnya, semua pernyataan yang Anda ketik setelahnya `clang`dianggap sebagai argumen baris perintah. Anda dapat menggunakan argumen ini di program Anda sendiri!
-   Di jendela terminal Anda, ketik `code greet.c`dan tulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        string name = get_string("What's your name? ");
        printf("hello, %s\n", name);
    }
    ```
    
    Perhatikan bahwa ini mengatakan `hello`kepada pengguna.
    
-   Tetap saja, bukankah menyenangkan bisa mengambil argumen bahkan sebelum program berjalan? Ubah kode Anda sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(int argc, string argv[])
    {
        if (argc == 2)
        {
            printf("hello, %s\n", argv[1]);
        }
        else
        {
            printf("hello, world\n");
        }
    }  
    ```
    
    Perhatikan bahwa program ini mengetahui keduanya `argc`, jumlah argumen baris perintah, dan `argv`array mana dari karakter yang diteruskan sebagai argumen pada baris perintah.
    
-   Oleh karena itu, dengan menggunakan sintaks program ini, eksekusi `./greet David`akan menghasilkan program yang mengatakan `hello, David`.

## [Keluar Status](https://cs50.harvard.edu/college/2022/fall/notes/2/#exit-status)

-   Saat program berakhir, kode keluar khusus diberikan ke komputer.
-   Ketika sebuah program keluar tanpa kesalahan, kode status `0`disediakan komputer. Seringkali, ketika terjadi kesalahan yang mengakibatkan program berakhir, status `1`diberikan oleh komputer.
-   Anda dapat menulis program sebagai berikut yang mengilustrasikannya dengan mengetik `code status.c`dan menulis kode sebagai berikut:
    
    ```
    #include <cs50.h>
    #include <stdio.h>
    
    int main(int argc, string argv[])
    {
        if (argc != 2)
        {
            printf("Missing command-line argument\n");
            return 1;
        }
        printf("hello, %s\n", argv[1]);
        return 0;
    }
    ```
    
    Perhatikan bahwa jika Anda gagal memberikan `./status David`, Anda akan mendapatkan status keluar dari `1`. Namun, jika Anda memberikan `./status David`, Anda akan mendapatkan status keluar dari `0`.
    
-   Anda dapat membayangkan bagaimana Anda dapat menggunakan bagian dari program di atas untuk memeriksa apakah pengguna memberikan jumlah argumen baris perintah yang benar.

## [Kriptografi](https://cs50.harvard.edu/college/2022/fall/notes/2/#cryptography)

-   Kriptografi adalah seni penyandian dan penguraian pesan.
-   `plaintext`dan a `key`disediakan untuk a `cipher`, menghasilkan teks tersandi.
    
    ![kriptografi](https://cs50.harvard.edu/college/2022/fall/notes/2/cs50Week2Slide153.png "kriptografi")
    
-   Kuncinya adalah argumen khusus yang diteruskan ke sandi bersama dengan teks biasa. Cipher menggunakan kunci untuk membuat keputusan tentang bagaimana mengimplementasikan algoritma sandinya.

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/2/#summing-up)

Dalam pelajaran ini, Anda mempelajari lebih detail tentang kompilasi dan bagaimana data disimpan di dalam komputer. Secara khusus, Anda belajar…

-   Secara umum, cara kerja kompiler.
-   Cara men-debug kode Anda menggunakan empat metode.
-   Cara memanfaatkan array dalam kode Anda.
-   Bagaimana array menyimpan data di bagian belakang ke belakang memori.
-   Bagaimana string hanyalah susunan karakter.
-   Cara berinteraksi dengan array dalam kode Anda.
-   Bagaimana argumen baris perintah dapat diteruskan ke program Anda.
-   Blok bangunan dasar kriptografi.

Sampai jumpa lain waktu!
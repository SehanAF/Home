# [Kuliah 6](https://cs50.harvard.edu/college/2022/fall/notes/6/#lecture-6)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/6/#welcome)
-   [Piton](https://cs50.harvard.edu/college/2022/fall/notes/6/#python)
-   [Halo](https://cs50.harvard.edu/college/2022/fall/notes/6/#hello)
-   [Jenis](https://cs50.harvard.edu/college/2022/fall/notes/6/#types)
-   [Pengeja](https://cs50.harvard.edu/college/2022/fall/notes/6/#speller)
-   [Pengenalan Gambar](https://cs50.harvard.edu/college/2022/fall/notes/6/#image-recognition)
-   [Perpustakaan CS50](https://cs50.harvard.edu/college/2022/fall/notes/6/#cs50-library)
-   [Persyaratan](https://cs50.harvard.edu/college/2022/fall/notes/6/#conditionals)
-   [Variabel](https://cs50.harvard.edu/college/2022/fall/notes/6/#variables)
-   [Loop](https://cs50.harvard.edu/college/2022/fall/notes/6/#loops)
-   [Kalkulator](https://cs50.harvard.edu/college/2022/fall/notes/6/#calculator)
-   [Membandingkan](https://cs50.harvard.edu/college/2022/fall/notes/6/#compare)
-   [Pemrograman berorientasi objek](https://cs50.harvard.edu/college/2022/fall/notes/6/#object-oriented-programming)
-   [meong](https://cs50.harvard.edu/college/2022/fall/notes/6/#meow)
-   [Mario](https://cs50.harvard.edu/college/2022/fall/notes/6/#mario)
-   [Skor](https://cs50.harvard.edu/college/2022/fall/notes/6/#scores)
-   [Huruf besar](https://cs50.harvard.edu/college/2022/fall/notes/6/#uppercase)
-   [Menyapa](https://cs50.harvard.edu/college/2022/fall/notes/6/#greet)
-   [Keluar Status](https://cs50.harvard.edu/college/2022/fall/notes/6/#exit-status)
-   [Mencari](https://cs50.harvard.edu/college/2022/fall/notes/6/#search)
-   [Buku telepon](https://cs50.harvard.edu/college/2022/fall/notes/6/#phonebook)
-   [Perbandingan](https://cs50.harvard.edu/college/2022/fall/notes/6/#comparison)
-   [Menukar](https://cs50.harvard.edu/college/2022/fall/notes/6/#swap)
-   [CSV](https://cs50.harvard.edu/college/2022/fall/notes/6/#csv)
-   [Pidato](https://cs50.harvard.edu/college/2022/fall/notes/6/#speech)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/6/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/6/#welcome)

-   Di minggu-minggu sebelumnya, Anda telah diperkenalkan dengan blok bangunan dasar pemrograman.
-   Anda belajar tentang pemrograman dalam bahasa pemrograman tingkat rendah yang disebut C.
-   Hari ini, kita akan bekerja dengan bahasa pemrograman tingkat tinggi yang disebut _Python_ .
-   Saat Anda mempelajari bahasa baru ini, Anda akan menemukan bahwa Anda akan lebih mampu untuk belajar sendiri bahasa pemrograman baru.

## [Piton](https://cs50.harvard.edu/college/2022/fall/notes/6/#python)

-   Manusia, selama beberapa dekade, telah melihat bagaimana keputusan desain sebelumnya dapat diperbaiki.
-   Python adalah bahasa pemrograman yang dibangun di atas apa yang telah Anda pelajari di C.

## [Halo](https://cs50.harvard.edu/college/2022/fall/notes/6/#hello)

-   Sampai saat ini, kodenya terlihat seperti ini:
    
    ```
    // A program that says hello to the world
    
    #include <stdio.h>
    
    int main(void)
    {
        printf("hello, world\n");
    }
    ```
    
-   Hari ini, Anda akan menemukan bahwa proses penulisan dan kompilasi kode telah disederhanakan.
-   Misalnya, kode di atas akan dirender dengan Python sebagai:
    
    ```
    # A program that says hello to the world
    
    print("hello, world")
    ```
    
    Perhatikan bahwa titik koma hilang.
    
-   Di C, Anda mungkin ingat kode ini:
    
    ```
    // get_string and printf with %s
    
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        string answer = get_string("What's your name? ");
        printf("hello, %s\n", answer);
    }
    ```
    
-   Kode ini diubah dengan Python menjadi:
    
    ```
    # get_string and print, with concatenation
    
    from cs50 import get_string
    
    answer = get_string("What's your name? ")
    print("hello, " + answer)
    ```
    
    Anda dapat menulis kode ini dengan mengeksekusi `code hello.py`di jendela terminal. Kemudian, Anda dapat menjalankan kode ini dengan menjalankan `python hello.py`. Perhatikan bagaimana `+`tanda menggabungkan `"hello, "`dan `answer`.
    
-   Demikian pula, Anda dapat mengimplementasikan kode di atas sebagai:
    
    ```
    # get_string and print, with format strings
    
    from cs50 import get_string
    
    answer = get_string("What's your name? ")
    print(f"hello, {answer}")
    ```
    
    Perhatikan bagaimana kurung kurawal memungkinkan fungsi `print`menginterpolasi `answer`yang `answer`muncul di dalamnya.
    

## [Jenis](https://cs50.harvard.edu/college/2022/fall/notes/6/#types)

-   Tipe data dalam Python tidak perlu dideklarasikan secara eksplisit. Misalnya, Anda melihat bagaimana `answer`di atas adalah sebuah string, tetapi kami tidak harus memberi tahu juru bahasa bahwa inilah masalahnya: Ia tahu dengan sendirinya.
-   Di Python, tipe yang umum digunakan meliputi:
    
    ```
      bool
      float
      int
      str
    ```
    
    Perhatikan bahwa `long`dan `double`hilang. Python akan menangani tipe data apa yang harus digunakan untuk angka yang lebih besar dan lebih kecil.
    
-   Beberapa tipe data lain di Python meliputi:
    
    ```
      range
      list
      tuple
      dict
      set
    ```
    
-   Masing-masing tipe data ini dapat diimplementasikan dalam C, tetapi dengan Python mereka dapat diimplementasikan dengan lebih sederhana.

## [Pengeja](https://cs50.harvard.edu/college/2022/fall/notes/6/#speller)

-   Untuk mengilustrasikan kesederhanaan ini, mari ketik 'code dictionary.py' di jendela terminal dan tulis kode sebagai berikut:
    
    ```
    # Words in dictionary
    words = set()
    
    
    def check(word):
        """Return true if word is in dictionary else false"""
        if word.lower() in words:
            return True
        else:
            return False
    
    
    def load(dictionary):
        """Load dictionary into memory, returning true if successful else false"""
        file = open(dictionary, "r")
        for line in file:
            word = line.rstrip()
            words.add(word)
        file.close()
        return True
    
    
    def size():
        """Returns number of words in dictionary if loaded else 0 if not yet loaded"""
        return len(words)
    
    
    def unload():
        """Unloads dictionary from memory, returning true if successful else false"""
        return True
    ```
    
    Perhatikan bahwa ada empat fungsi di atas. Dalam `check`fungsi, jika a `word`di `words`, ia mengembalikan `True`. Jauh lebih mudah daripada implementasi di C! Demikian pula, dalam `load`fungsi file kamus dibuka. Untuk setiap baris dalam file itu, kami menambahkan baris itu ke `words`. Menggunakan `rstrip`, baris baru yang tertinggal dihapus dari kata yang ditambahkan. `size`cukup mengembalikan `len`atau panjang dari `words`. `unload`hanya perlu kembali `True`karena Python menangani manajemen memori sendiri.
    
-   Kode di atas mengilustrasikan mengapa ada bahasa tingkat tinggi: Untuk menyederhanakan dan memungkinkan Anda menulis kode dengan lebih mudah.
-   Namun, kecepatan adalah tradeoff. Karena C memungkinkan Anda, programmer, untuk membuat keputusan tentang manajemen memori, C mungkin berjalan lebih cepat daripada Python – tergantung pada kode Anda. Sementara C hanya menjalankan baris kode Anda, Python menjalankan semua kode yang ada di baliknya saat Anda memanggil fungsi bawaan Python.
-   Anda dapat mempelajari lebih lanjut tentang fungsi dalam [dokumentasi Python](https://docs.python.org/3/library/functions.html)

## [Pengenalan Gambar](https://cs50.harvard.edu/college/2022/fall/notes/6/#image-recognition)

-   Banyak perpustakaan telah ditulis oleh kontributor Python.
-   Anda dapat menggunakan pustaka ini dalam kode Anda sendiri.
-   Misalnya, Anda cukup mengimpor pengenalan wajah menggunakan pustaka Python seperti `PIL`.
-   David menyediakan demo pengenalan wajah menggunakan Python dan perpustakaan pihak ketiga.

## [Perpustakaan CS50](https://cs50.harvard.edu/college/2022/fall/notes/6/#cs50-library)

-   Seperti C, perpustakaan CS50 dapat digunakan dalam Python.
-   Fungsi-fungsi berikut akan sangat berguna:
    
    ```
      get_float
      get_int
      get_string
    ```
    
-   Anda juga memiliki opsi untuk mengimpor hanya fungsi tertentu dari pustaka CS50 sebagai berikut:
    
    ```
    from CS50 import get_float, get_int, get_string
    ```
    

## [Persyaratan](https://cs50.harvard.edu/college/2022/fall/notes/6/#conditionals)

-   Di C, Anda mungkin ingat program seperti ini:
    
    ```
    // Conditionals, Boolean expressions, relational operators
    
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Prompt user for integers
        int x = get_int("What's x? ");
        int y = get_int("What's y? ");
    
        // Compare integers
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
    
-   Dengan Python, akan muncul sebagai berikut:
    
    ```
    # Conditionals, Boolean expressions, relational operators
    
    from cs50 import get_int
    
    # Prompt user for integers
    x = get_int("What's x? ")
    y = get_int("What's y? ")
    
    # Compare integers
    if x < y:
        print("x is less than y")
    elif x > y:
        print("x is greater than y")
    else:
        print("x is equal to y")
    ```
    
    Perhatikan bahwa tidak ada lagi kurung kurawal. Sebaliknya, lekukan digunakan. Kedua, tanda titik dua digunakan dalam `if`pernyataan. Selanjutnya, `elif`ganti `else if`. Tanda kurung juga tidak lagi diperlukan dalam pernyataan `if`dan `elif`.
    

## [Variabel](https://cs50.harvard.edu/college/2022/fall/notes/6/#variables)

-   Deklarasi variabel juga disederhanakan. Di C, Anda mungkin memiliki `int counter = 1;`. Dengan Python, baris yang sama ini akan berbunyi `counter = 1`. Anda tidak perlu mendeklarasikan tipe variabel.
-   Python lebih suka `counter += 1`bertambah satu, kehilangan kemampuan yang ditemukan di C untuk mengetik `counter++`.

## [Loop](https://cs50.harvard.edu/college/2022/fall/notes/6/#loops)

-   Loop di Python sangat mirip dengan C. Anda dapat mengingat kode berikut di C:
    
    ```
    // Demonstrates while loop
    
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
    
-   Di Python, kode ini muncul sebagai:
    
    ```
    # Demonstrates while loop
    
    i = 0
    while i < 3:
        print("meow")
        i += 1
    ```
    
-   `for`loop dapat diimplementasikan dengan Python sebagai berikut:
    
    ```
    # Better design
    
    for i in range(3):
        print("meow")
    ```
    
-   Demikian pula, seseorang dapat mengekspresikan kode di atas sebagai:
    
    ```
    # Abstraction with parameterization
    
    def main():
        meow(3)
    
    
    # Meow some number of times
    def meow(n):
        for i in range(n):
            print("meow")
    
    
    main()
    ```
    
    Perhatikan bahwa suatu fungsi digunakan untuk mengabstraksi mengeong.
    

## [Kalkulator](https://cs50.harvard.edu/college/2022/fall/notes/6/#calculator)

-   Kita dapat mengimplementasikan kalkulator sederhana seperti yang kita lakukan di dalam C. Ketik `code calculator.py`di jendela terminal dan tulis kode sebagai berikut:
    
    ```
    # Addition with int [using get_int]
    
    from cs50 import get_int
    
    # Prompt user for x
    x = get_int("x: ")
    
    # Prompt user for y
    y = get_int("y: ")
    
    # Perform addition
    print(x + y)
    ```
    
    Perhatikan bagaimana pustaka CS50 diimpor. Kemudian, `x`dan `y` dikumpulkan dari pengguna. Akhirnya, hasilnya dicetak. Perhatikan bahwa `main`fungsi yang akan terlihat di program C hilang sama sekali! Meskipun seseorang dapat menggunakan suatu `main`fungsi, itu tidak diperlukan.
    
-   Seseorang dapat melepas roda pelatihan perpustakaan CS50. Ubah kode Anda sebagai berikut:
    
    ```
    # Addition with int [using input]
    
    # Prompt user for x
    x = input("x: ")
    
    # Prompt user for y
    y = input("y: ")
    
    # Perform addition
    print(x + y)
    ```
    
    Perhatikan bagaimana mengeksekusi kode di atas menghasilkan perilaku program yang aneh. Mengapa demikian?
    
-   Anda mungkin telah menebak bahwa penerjemah mengerti `x`dan `y`menjadi string. Anda dapat memperbaiki kode Anda dengan menggunakan `int`fungsi sebagai berikut:
    
    ```
    # Addition with int [using input]
    
    # Prompt user for x
    x = int(input("x: "))
    
    # Prompt user for y
    y = int(input("y: "))
    
    # Perform addition
    print(x + y)
    ```
    
    Perhatikan bagaimana masukan untuk `x`dan `y`diteruskan ke `int`fungsi yang mengubahnya menjadi bilangan bulat.
    
-   Kami dapat memperluas kemampuan kalkulator kami. Ubah kode Anda sebagai berikut:
    
    ```
    # Division with integers, demonstration lack of truncation
    
    # Prompt user for x
    x = int(input("x: "))
    
    # Prompt user for y
    y = int(input("y: "))
    
    # Divide x by y
    z = x / y
    print(z)
    ```
    
    Perhatikan bahwa mengeksekusi kode ini menghasilkan nilai, tetapi jika Anda melihat lebih banyak digit setelah `.333333`Anda melihat bahwa kita dihadapkan pada _ketidaktepatan titik-mengambang_ .
    
-   Kami dapat mengungkapkan ketidaktepatan ini dengan sedikit memodifikasi kode kami:
    
    ```
    # Floating-point imprecision
    
    # Prompt user for x
    x = int(input("x: "))
    
    # Prompt user for y
    y = int(input("y: "))
    
    # Divide x by y
    z = x / y
    print(f"{z:.50f}")
    ```
    
    Perhatikan bahwa kode ini mengungkapkan ketidaktepatan. Python masih menghadapi masalah ini, sama seperti C.
    

## [Membandingkan](https://cs50.harvard.edu/college/2022/fall/notes/6/#compare)

-   Di C, kami menghadapi tantangan ketika kami ingin membandingkan dua nilai. Pertimbangkan kode berikut:
    
    ```
    // Conditionals, Boolean expressions, relational operators
    
    #include <cs50.h>
    #include <stdio.h>
    
    int main(void)
    {
        // Prompt user for integers
        int x = get_int("What's x? ");
        int y = get_int("What's y? ");
    
        // Compare integers
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
    
-   Dengan Python, kita dapat menjalankan hal di atas sebagai berikut:
    
    ```
    # Conditionals, Boolean expressions, relational operators
    
    from cs50 import get_int
    
    # Prompt user for integers
    x = get_int("What's x? ")
    y = get_int("What's y? ")
    
    # Compare integers
    if x < y:
        print("x is less than y")
    elif x > y:
        print("x is greater than y")
    else:
        print("x is equal to y")
    ```
    
    Perhatikan bahwa perpustakaan CS50 diimpor. Selanjutnya, perubahan kecil ada dalam `if`pernyataan itu.
    
-   Lebih lanjut melihat perbandingan, pertimbangkan kode berikut di C:
    
    ```
    // Logical operators
    
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
    
-   Hal di atas dapat diimplementasikan sebagai berikut:
    
    ```
    # Logical operators
    
    from cs50 import get_string
    
    # Prompt user to agree
    s = get_string("Do you agree? ")
    
    # Check whether agreed
    if s == "Y" or s == "y":
        print("Agreed.")
    elif s == "N" or s == "n":
        print("Not agreed.")
    ```
    
    Perhatikan bahwa dua batang vertikal yang digunakan dalam C diganti dengan `or`. Memang, orang sering menikmati Python karena lebih mudah dibaca oleh manusia. Perhatikan juga bahwa `char`tidak ada di Python. Sebaliknya, `str`s digunakan.
    
-   Pendekatan lain untuk kode yang sama ini bisa sebagai berikut:
    
    ```
    # Logical operators, using lists
    
    from cs50 import get_string
    
    # Prompt user to agree
    s = get_string("Do you agree? ")
    
    # Check whether agreed
    if s in ["y", "yes"]:
        print("Agreed.")
    elif s in ["n", "no"]:
        print("Not agreed.")
    ```
    
    Perhatikan bagaimana kami dapat mengekspresikan beberapa kata kunci seperti `y`dan `yes`.
    

## [Pemrograman berorientasi objek](https://cs50.harvard.edu/college/2022/fall/notes/6/#object-oriented-programming)

-   Sampai saat ini, program kami dalam kursus ini bersifat linier: berurutan.
-   It’s possible to have certain types of values not only have properties or attributes inside of them but have functions as well. In Python, these values are known as _objects_
-   In C, we could create a `struct` where you could associate multiple variables inside a single self-created data type. In Python, we can do this and also include functions in a self-created data type. When a function belongs to a specific _object_, it is known as a _method_.
-   For example, `strs` in Python have a built-in _methods_. Therefore, you could modify your code as follows:
    
    ```
    # Logical operators, using lists
    
    from cs50 import get_string
    
    # Prompt user to agree
    s = get_string("Do you agree? ")
    
    # Check whether agreed
    if s.lower() in ["y", "yes"]:
        print("Agreed.")
    elif s.lower() in ["n", "no"]:
        print("Not agreed.")
    ```
    
    Notice how we are able to express multiple keywords like `y` and `yes` and convert any user input to lowercase.
    
-   This could be further simplified as:
    
    ```
    # Logical operators, using lists
    
    from cs50 import get_string
    
    # Prompt user to agree
    s = get_string("Do you agree? ")
    
    s = s.lower()
    
    # Check whether agreed
    if s in ["y", "yes"]:
        print("Agreed.")
    elif s in ["n", "no"]:
        print("Not agreed.")
    ```
    
    Perhatikan bagaimana nilai lama `s`ditimpa dengan hasil `s.lower()`.
    
-   Di kelas ini, kita hanya akan menggores permukaan Python. Oleh karena itu, [dokumentasi Python](https://docs.python.org/) akan sangat penting saat Anda melanjutkan.
-   Anda dapat mempelajari lebih lanjut tentang metode string dalam [dokumentasi Python](https://docs.python.org/3/library/stdtypes.html#string-methods)

## [meong](https://cs50.harvard.edu/college/2022/fall/notes/6/#meow)

-   Kembali ke `meow.c`dari minggu sebelumnya, ingat kode berikut:
    
    ```
    // Demonstrates while loop
    
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
    
-   Di atas dapat diimplementasikan dalam Python sebagai:
    
    ```
    # Demonstrates while loop
    
    i = 0
    while i < 3:
        print("meow")
        i += 1
    ```
    
-   Demikian pula, dengan menggunakan `for`loop, kita dapat menulis kode sebagai berikut:
    
    ```
    # Better design
    
    for i in range(3):
        print("meow")
    ```
    
-   Seperti yang kami tunjukkan sebelumnya hari ini, Anda dapat lebih meningkatkan kode ini menggunakan fungsi. Ubah kode Anda sebagai berikut:
    
    ```
    # Abstraction
    
    def main():
        for i in range(3):
            meow()
    
    # Meow once
    def meow():
        print("meow")
    
    
    main()
    ```
    
    Notice that the `meow` function abstracts away the `print` statement. Further, notice that the `main` function appears at the top of the file. At the bottom of the file, the `main` function is called. By convention, it’s expected that you create a `main` function in Python.
    
-   Indeed, we can pass variables between our functions as follows:
    
    ```
    # Abstraction with parameterization
    
    def main():
        meow(3)
    
    
    # Meow some number of times
    def meow(n):
        for i in range(n):
            print("meow")
    
    
    main()
    ```
    
    Notice how `meow` now takes a variable `n`. In the `main` function, you can call `meow` and pass a value like `3` to it. Then, `meow` utilizes the value of `n` in the `for` loop.
    
-   Reading the above code, notice how you, as a C programmer, are able to quite easily make sense of the above code. While some conventions are different, the building blocks you previously learned are very apparent in this new programming language.
    

## [Mario](https://cs50.harvard.edu/college/2022/fall/notes/6/#mario)

-   Recall a few weeks ago our challenge of building three blocks on top of one another, like in Mario.
    
    ![tiga blok vertikal](https://cs50.harvard.edu/college/2022/fall/notes/6/cs50Week6Slide073.png "blok mario")
    
-   In Python, we can implement something akin to this as follows:
    
    ```
    # Prints a column of 3 bricks with a loop
    
    for i in range(3):
        print("#")
    ```
    
-   In C, we had the advantage of a `do-while` loop. However, in Python it is convention to utilize a `while` loop, as Python does not have a `do while` loop. You can write code as follows in a file called `mario.py`:
    
    ```
    # Prints a column of bricks, using a helper function to get input
    
    from cs50 import get_int
    
    
    def main():
        height = get_height()
        for i in range(height):
            print("#")
    
    
    def get_height():
        while True:
            n = get_int("Height: ")
            if n > 0:
                return n
    
    
    main()
    ```
    
    Notice how the scope of `n` is everywhere in the `get_height` function once it is assigned a value. Further notice that by convention, there are double spaces between functions.
    
-   We can take away the training wheels of the CS50 library as follows:
    
    ```
    # Prints a column of bricks, catching exceptions
    
    def main():
        height = get_height()
        for i in range(height):
            print("#")
    
    
    def get_height():
        while True:
            try:
                n = int(input("Height: "))
                if n > 0:
                    return n
            except ValueError:
                print("Not an integer")
    
    
    main()
    ```
    
    Notice that `try` is utilized to attempt to convert `n` to an integer. If it cannot do so, an error is outputted.
    
-   Consider the following image:
    
    ![empat blok pertanyaan horizontal](https://cs50.harvard.edu/college/2022/fall/notes/6/cs50Week6Slide075.png "blok mario")
    
-   Di Python, kami dapat mengimplementasikan dengan memodifikasi kode Anda sebagai berikut:
    
    ```
    # Prints a row of 4 question marks with a loop
    
    for i in range(4):
        print("?", end="")
    print()
    ```
    
    Perhatikan bahwa Anda dapat mengganti perilaku fungsi `print`agar tetap berada di baris yang sama dengan cetakan sebelumnya.
    
-   Mirip dengan iterasi sebelumnya, kita dapat lebih menyederhanakan program ini:
    
    ```
    # Prints a row of 4 question marks without a loop
    
    print("?" * 4)
    ```
    
    Perhatikan bahwa kita dapat memanfaatkan `*`untuk melipatgandakan pernyataan cetak untuk mengulang `4`waktu.
    
-   Bagaimana dengan balok batu bata yang besar?
    
    ![tiga kali tiga blok blok mario](https://cs50.harvard.edu/college/2022/fall/notes/6/cs50Week6Slide078.png "blok mario")
    
-   Untuk mengimplementasikan hal di atas, Anda dapat memodifikasi kode Anda sebagai berikut:
    
    ```
    # Prints a 3-by-3 grid of bricks with loops
    
    for i in range(3):
        for j in range(3):
            print("#", end="")
        print()
    ```
    
    Perhatikan bagaimana satu `for`loop ada di dalam yang lain. Pernyataan itu `print`menambahkan baris baru di akhir setiap baris batu bata.
    
-   Anda dapat mempelajari lebih lanjut tentang `print`fungsi tersebut di [dokumentasi Python](https://docs.python.org/3/library/functions.html#print)
    

## [Skor](https://cs50.harvard.edu/college/2022/fall/notes/6/#scores)

-   `list`s adalah struktur data dalam Python.
-   `list`s telah membangun metode atau fungsi di dalamnya.
-   Misalnya, pertimbangkan kode berikut:
    
    ```
    # Averages three numbers using a list and a loop
    
    from cs50 import get_int
    
    # Get scores
    scores = []
    for i in range(3):
        score = get_int("Score: ")
        scores.append(score)
    
    # Print average
    average = sum(scores) / len(scores)
    print(f"Average: {average}")
    ```
    
    Notice that you can use the built-in `append` method, whereby you can `append` the score to the list. Also notice that we use the `sum` function to add all elements in the list.
    
-   You can even ultilize the following syntax:
    
    ```
    # Averages three numbers using a list and a loop with + operator
    
    from cs50 import get_int
    
    # Get scores
    scores = []
    for i in range(3):
        score = get_int("Score: ")
        scores += [score]
    
    # Print average
    average = sum(scores) / len(scores)
    print(f"Average: {average}")
    ```
    
    Notice that `+=` is utilized to append the score to the list. In this case we place square brackets around `score` because only a `list` can be added to another `list` using `+` or `+=`.
    
-   You can learn more about lists in the [Python documentation](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range)
-   You can also learn more about `len` in the [Python documentation](https://docs.python.org/3/library/functions.html#len)

## [Uppercase](https://cs50.harvard.edu/college/2022/fall/notes/6/#uppercase)

-   Similarly, consider the following code:
    
    ```
    # Uppercases string one character at a time
    
    before = input("Before: ")
    print("After:  ", end="")
    for c in before:
        print(c.upper(), end="")
    print()
    ```
    
    Notice that each character is uppercased one at a time.
    
-   Python has a built-in method for `str`s. You could modify your code as follows:
    
    ```
    # Uppercases string all at once
    
    before = input("Before: ")
    after = before.upper()
    print(f"After:  {after}")
    ```
    
    Perhatikan bahwa `upper`metode ini digunakan untuk menghurufbesarkan seluruh string sekaligus.
    

## [Menyapa](https://cs50.harvard.edu/college/2022/fall/notes/6/#greet)

-   Seperti halnya C, Anda juga dapat menggunakan argumen baris perintah. Pertimbangkan kode berikut:
    
    ```
    # Prints a command-line argument
    
    from sys import argv
    
    if len(argv) == 2:
        print(f"hello, {argv[1]}")
    else:
        print("hello, world")
    ```
    
    Perhatikan yang `argv[1]`dicetak menggunakan _string yang diformat_ , dicatat oleh `f`present dalam `print`pernyataan.
    
-   Anda dapat mencetak semua argumen `argv`sebagai berikut:
    
    ```
    # Printing command-line arguments, indexing into argv
    
    from sys import argv
    
    for i in range(len(argv)):
        print(argv[i])
    ```
    
    Perhatikan bahwa di atas tidak akan menampilkan kata `python`jika dijalankan, dan argumen pertama akan menjadi nama file yang sedang Anda jalankan. Anda dapat menganggap kata tersebut `python`analog dengan `./`saat kami menjalankan program di C.
    
-   Anda dapat memotong potongan daftar. Pertimbangkan kode berikut:
    
    ```
    # Printing command-line arguments using a slice
    
    from sys import argv
    
    for arg in argv[1:]:
        print(arg)
    ```
    
    Perhatikan bahwa mengeksekusi kode ini akan mengakibatkan nama file yang Anda jalankan terpotong.
    
-   Anda dapat mempelajari lebih lanjut tentang `sys`perpustakaan di [dokumentasi Python](https://docs.python.org/3/library/sys.html)
    

## [Keluar Status](https://cs50.harvard.edu/college/2022/fall/notes/6/#exit-status)

-   Perpustakaan `sys`juga memiliki metode bawaan. Kita dapat menggunakan `sys.exit(i)`untuk keluar dari program dengan kode keluar tertentu:
    
    ```
    # Exits with explicit value, importing sys
    
    import sys
    
    if len(sys.argv) != 2:
        print("Missing command-line argument")
        sys.exit(1)
    
    print(f"hello, {sys.argv[1]}")
    sys.exit(0)
    ```
    
    Perhatikan bahwa notasi titik digunakan untuk menggunakan fungsi bawaan dari `sys`.
    

## [Mencari](https://cs50.harvard.edu/college/2022/fall/notes/6/#search)

-   Python juga bisa digunakan untuk mencari. Di jendela terminal Anda, ketik `code names.py`dan tulis kode sebagai berikut:
    
    ```
    # Implements linear search for names
    
    import sys
    
    # A list of names
    names = ["Bill", "Charlie", "Fred", "George", "Ginny", "Percy", "Ron"]
    
    # Ask for name
    name = input("Name: ")
    
    # Search for name
    if name in names:
        print("Found")
        sys.exit(0)
    
    print("Not found")
    sys.exit(1)
    ```
    
    Perhatikan bahwa kode ini berfungsi. Memang, itu mengimplementasikan pencarian linier.
    
-   Anda dapat memanfaatkan kemampuan bawaan Python sebagai berikut:
    
    ```
    # Implements linear search for names using `in`
    
    import sys
    
    # A list of names
    names = ["Bill", "Charlie", "Fred", "George", "Ginny", "Percy", "Ron"]
    
    # Ask for name
    name = input("Name: ")
    
    # Search for name
    if name in names:
        print("Found")
        sys.exit(0)
    
    print("Not found")
    sys.exit(1)
    ```
    
    Perhatikan bahwa `in`preposisi digunakan. Python memahami cara mengimplementasikan kode tingkat rendah untuk melakukan pencarian linear.
    

## [Buku telepon](https://cs50.harvard.edu/college/2022/fall/notes/6/#phonebook)

-   Recall that a _dictionary_ or `dict` is a collection of _key_ and _value_ pairs.
-   You can implement a dictionary in Python as follows:
    
    ```
    # Implements a phone book
    
    from cs50 import get_string
    
    people = {
        "Carter": "+1-617-495-1000",
        "David": "+1-949-468-2750"
    }
    
    # Search for name
    name = get_string("Name: ")
    if name in people:
        print(f"Number: {people[name]}")
    ```
    
    Notice that the dictionary is implemented using curly braces. Then, the statement `if name in people` searches to see if the `name` is in the `people` dictionary. Further, notice how, in the `print` statement, we can index into the people dictionary using the value of `name`. Very useful!
    
-   Python has done their best to get to _constant time_ using their built-in searches.

## [Comparison](https://cs50.harvard.edu/college/2022/fall/notes/6/#comparison)

-   We can implement comparisons as follows in Python:
    
    ```
    # Compares two strings
    
    # Get two strings
    s = input("s: ")
    t = input("t: ")
    
    # Compare strings
    if s == t:
        print("Same")
    else:
        print("Different")
    ```
    
    Perhatikan bagaimana Python menggunakan the `==`untuk dapat membandingkan dua variabel. Selanjutnya, perhatikan bahwa Python memungkinkan Anda untuk membandingkan dua string tanpa memeriksa string karakter demi karakter menggunakan pointer seperti pada C.
    

## [Menukar](https://cs50.harvard.edu/college/2022/fall/notes/6/#swap)

-   Selanjutnya, kita dapat mengimplementasikan program yang menukar nilai seperti yang kita lakukan di C. Pertimbangkan kode berikut dengan Python:
    
    ```
    # Swaps two integers
    
    x = 1
    y = 2
    
    print(f"x is {x}, y is {y}")
    x, y = y, x
    print(f"x is {x}, y is {y}")
    ```
    
    Perhatikan bahwa setiap nilai ditukar, menggunakan beberapa sintaks yang sangat _Pythonic_`x, y = y, x` .
    

## [CSV](https://cs50.harvard.edu/college/2022/fall/notes/6/#csv)

-   Anda juga dapat menggunakan Python untuk terlibat dengan file CSV. Pertimbangkan program berikut yang disebut `phonebook.py`:
    
    ```
    # Saves names and numbers to a CSV file
    
    import csv
    
    # Get name and number
    name = input("Name: ")
    number = input("Number: ")
    
    # Open CSV file
    with open("phonebook.csv", "a") as file:
    
        # Print to file
        writer = csv.writer(file)
        writer.writerow([name, number])
    ```
    
    Perhatikan bahwa menggunakan `with`blok kode, dengan `writer`dan pekerjaannya terjadi di bawahnya, mencegah kita membutuhkan `close`file kita setelah selesai.
    
-   Biasanya, file CSV memiliki kolom dengan nama tertentu. A `DictWriter`dapat digunakan untuk membuat file CSV dan menetapkan nama tertentu untuk setiap kolom. Pertimbangkan modifikasi berikut pada kode kita:
    
    ```
    # Saves names and numbers to a CSV file using a DictWriter
    
    import csv
    
    # Get name and number
    name = input("Name: ")
    number = input("Number: ")
    
    # Open CSV file
    with open("phonebook.csv", "a") as file:
    
        # Print to file
        writer = csv.DictWriter(file, fieldnames=["name", "number"])
        writer.writerow({"name": name, "number": number})
    ```
    
    Perhatikan kolom `name`dan `number`didefinisikan di baris kode kedua dari belakang, dan nilai ditambahkan di baris terakhir.
    
-   Anda dapat mempelajari lebih lanjut tentang file CSV di Python dalam [dokumentasi Python](https://docs.python.org/3/library/csv.html)
    

## [Pidato](https://cs50.harvard.edu/college/2022/fall/notes/6/#speech)

-   Menggunakan perpustakaan pihak ketiga, Python dapat melakukan text-to-speech.
    
    ```
    # Says hello to someone
    
    import pyttsx3
    
    engine = pyttsx3.init()
    name = input("What's your name? ")
    engine.say(f"hello, {name}")
    engine.runAndWait()
    ```
    
-   Selanjutnya, Anda dapat menjalankan kode berikut:
    
    ```
    # Says "This was CS50"
    
    import pyttsx3
    
    engine = pyttsx3.init()
    engine.say("This was CS50")
    engine.runAndWait()
    ```
    

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/6/#summing-up)

Dalam pelajaran ini, Anda mempelajari bagaimana blok penyusun pemrograman dari pelajaran sebelumnya dapat diimplementasikan dalam Python. Selanjutnya, Anda belajar tentang bagaimana Python mengizinkan kode yang lebih disederhanakan. Juga, Anda belajar bagaimana memanfaatkan berbagai pustaka Python. Pada akhirnya, Anda mengetahui bahwa keahlian Anda sebagai programmer tidak terbatas pada satu bahasa pemrograman saja. Anda sudah melihat bagaimana Anda menemukan cara belajar baru melalui kursus ini yang dapat membantu Anda dalam bahasa pemrograman apa pun – dan, mungkin, di hampir semua cara belajar! Secara khusus, kami membahas…

-   Piton
-   Variabel
-   Persyaratan
-   Loop
-   Jenis
-   Perpustakaan
-   Kamus
-   Argumen baris perintah
-   Ekspresi reguler

Sampai jumpa lain waktu!
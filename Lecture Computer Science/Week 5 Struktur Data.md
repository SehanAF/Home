# [Kuliah 5](https://cs50.harvard.edu/college/2022/fall/notes/5/#lecture-5)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/5/#welcome)
-   [Struktur data](https://cs50.harvard.edu/college/2022/fall/notes/5/#data-structures)
-   [Tumpukan dan Antrian](https://cs50.harvard.edu/college/2022/fall/notes/5/#stacks-and-queues)
-   [Jack Mempelajari Fakta](https://cs50.harvard.edu/college/2022/fall/notes/5/#jack-learns-the-facts)
-   [Mengubah Ukuran Array](https://cs50.harvard.edu/college/2022/fall/notes/5/#resizing-arrays)
-   [Daftar Tertaut](https://cs50.harvard.edu/college/2022/fall/notes/5/#linked-lists)
-   [Pohon](https://cs50.harvard.edu/college/2022/fall/notes/5/#trees)
-   [Kamus](https://cs50.harvard.edu/college/2022/fall/notes/5/#dictionaries)
-   [Tabel Hash dan Hash](https://cs50.harvard.edu/college/2022/fall/notes/5/#hashing-and-hash-tables)
-   [Mencoba](https://cs50.harvard.edu/college/2022/fall/notes/5/#tries)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/5/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/5/#welcome)

-   Semua minggu sebelumnya telah memberi Anda blok bangunan dasar pemrograman.
-   Semua yang telah Anda pelajari di C akan memungkinkan Anda menerapkan blok bangunan ini dalam bahasa pemrograman tingkat tinggi seperti Python.
-   Hari ini, kita akan berbicara tentang mengatur data dalam memori.

## [Struktur data](https://cs50.harvard.edu/college/2022/fall/notes/5/#data-structures)

-   _Struktur data_ pada dasarnya adalah bentuk organisasi dalam memori.
-   Ada banyak cara untuk mengatur data dalam memori.
-   _Struktur data abstrak_ adalah yang dapat kita bayangkan secara konseptual. Saat belajar tentang ilmu komputer, seringkali berguna untuk memulai dengan struktur data konseptual ini. Mempelajari hal ini nantinya akan memudahkan untuk memahami bagaimana mengimplementasikan struktur data yang lebih konkret.

## [Tumpukan dan Antrian](https://cs50.harvard.edu/college/2022/fall/notes/5/#stacks-and-queues)

-   _Antrian_ merupakan salah satu bentuk struktur data abstrak.
-   Antrian memiliki sifat tertentu. Yakni, _FIFO_ atau “first in first out.” Anda dapat membayangkan diri Anda mengantri untuk berkendara di taman hiburan. Orang pertama dalam antrean akan naik terlebih dahulu. Orang terakhir yang mendapat tumpangan terakhir.
-   Antrean memiliki tindakan spesifik yang terkait dengannya. Misalnya, sebuah item dapat _diantrekan_ ; Artinya, item tersebut dapat bergabung dengan garis atau antrian. Selanjutnya, item dapat di _-dequeued_ atau keluar dari antrian setelah mencapai garis depan.
-   Antrian kontras dengan _tumpukan_ . Pada dasarnya, properti tumpukan berbeda dari antrian. Secara khusus, ini adalah _LIFO_ atau "last in first out." Sama seperti menumpuk baki di kafetaria, baki yang diletakkan di tumpukan terakhir adalah yang pertama yang boleh diambil.
-   Tumpukan memiliki tindakan khusus yang terkait dengannya. Misalnya, _push_ menempatkan sesuatu di atas tumpukan. _Pop_ menghapus sesuatu dari atas tumpukan.
-   Dalam kode, Anda mungkin membayangkan tumpukan sebagai berikut:
    
    ```
    const int CAPACITY = 50;
    
    typedef struct
    {
        person people[CAPACITY];
        int size;
    }
    stack;
    ```
    
    Perhatikan bahwa array yang disebut people bertipe `person`. Seberapa `CAPACITY`tinggi tumpukan itu. Bilangan bulat `size`adalah seberapa penuh tumpukan itu sebenarnya, terlepas dari berapa banyak yang _bisa_ ditampungnya.
    
-   Anda mungkin membayangkan bahwa kode di atas memiliki batasan. Karena kapasitas array selalu ditentukan sebelumnya dalam kode ini. Oleh karena itu, tumpukan mungkin selalu terlalu besar. Anda mungkin membayangkan hanya menggunakan satu tempat di tumpukan dari 5.000.
-   Alangkah baiknya tumpukan kita menjadi dinamis – dapat tumbuh saat item ditambahkan ke dalamnya.

## [Jack Mempelajari Fakta](https://cs50.harvard.edu/college/2022/fall/notes/5/#jack-learns-the-facts)

-   Kami menonton video berjudul [Jack Mempelajari Fakta](https://www.youtube.com/watch?v=ItAG3s6KIEI) oleh Profesor Shannon Duvall dari Universitas Elon.

## [Mengubah Ukuran Array](https://cs50.harvard.edu/college/2022/fall/notes/5/#resizing-arrays)

-   Memutar ulang ke Minggu 2, kami memperkenalkan Anda pada struktur data pertama Anda.
-   Array adalah blok memori yang berdekatan.
-   Anda mungkin membayangkan sebuah array sebagai berikut:
    
    ![tiga kotak dengan 1 2 3](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide019.png "Himpunan")
    
-   Di memori, ada nilai lain yang disimpan oleh program, fungsi, dan variabel lain. Banyak dari ini mungkin merupakan nilai sampah yang tidak terpakai yang digunakan pada satu titik tetapi sekarang tersedia untuk digunakan.
    
    ![tiga kotak dengan 1 2 3 di antara banyak elemen memori lainnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide022.png "array di dalam memori")
    
-   Bayangkan Anda ingin menyimpan nilai keempat `4`dalam larik kami? Yang diperlukan adalah mengalokasikan area memori baru dan memindahkan array lama ke yang baru.
    
    ![Tiga kotak dengan 1 2 3 di atas empat kotak dengan 1 2 dan dua nilai sampah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide025.png "dua array dengan nilai sampah")
    
-   Nilai sampah lama akan ditimpa dengan data baru kami.
    
    ![Tiga kotak dengan 1 2 3 di atas empat kotak dengan 1 2 3 dan nilai sampah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide026.png "dua array dengan nilai sampah")
    
-   Salah satu kelemahan dari pendekatan ini adalah desainnya yang buruk: Setiap kali kita menambahkan angka, kita harus menyalin item array demi item.
    
-   Bukankah lebih baik jika kita bisa meletakkannya `4`di tempat lain di memori? Menurut definisi, ini tidak lagi menjadi array karena `4`tidak lagi berada dalam memori yang berdekatan.
    
-   Di terminal Anda, ketik `code list.c`dan tulis kode sebagai berikut:
    
    ```
    // Implements a list of numbers with an array of fixed size
    
    #include <stdio.h>
    
    int main(void)
    {
        // List of size 3
        int list[3];
    
        // Initialize list with numbers
        list[0] = 1;
        list[1] = 2;
        list[2] = 3;
    
        // Print list
        for (int i = 0; i < 3; i++)
        {
            printf("%i\n", list[i]);
        }
    }
    ```
    
    Perhatikan bahwa hal di atas sangat mirip dengan apa yang telah kita pelajari sebelumnya dalam kursus ini. Kami memiliki memori yang dialokasikan sebelumnya untuk tiga item.
    
-   Membangun berdasarkan pengetahuan kami yang diperoleh baru-baru ini, kami dapat memanfaatkan pemahaman kami tentang pointer untuk membuat desain yang lebih baik dalam kode ini. Ubah kode Anda sebagai berikut:
    
    ```
    // Implements a list of numbers with an array of dynamic size
    
    #include <stdio.h>
    #include <stdlib.h>
    
    int main(void)
    {
        // List of size 3
        int *list = malloc(3 * sizeof(int));
        if (list == NULL)
        {
            return 1;
        }
    
        // Initialize list of size 3 with numbers
        list[0] = 1;
        list[1] = 2;
        list[2] = 3;
    
        // List of size 4
        int *tmp = malloc(4 * sizeof(int));
        if (tmp == NULL)
        {
            free(list);
            return 1;
        }
    
        // Copy list of size 3 into list of size 4
        for (int i = 0; i < 3; i++)
        {
            tmp[i] = list[i];
        }
    
        // Add number to list of size 4
        tmp[3] = 4;
    
        // Free list of size 3
        free(list);
    
        // Remember list of size 4
        list = tmp;
    
        // Print list
        for (int i = 0; i < 4; i++)
        {
            printf("%i\n", list[i]);
        }
    
        // Free list
        free(list);
        return 0;
    ```
    
    Perhatikan bahwa daftar ukuran tiga bilangan bulat dibuat. Kemudian, tiga alamat memori dapat diberi nilai `1`, `2`, dan `3`. Kemudian, daftar ukuran empat dibuat. Selanjutnya, daftar disalin dari yang pertama ke yang kedua. Nilai untuk `4`ditambahkan ke `tmp`daftar. Karena blok memori yang `list`menunjuk ke tidak lagi digunakan, maka dibebaskan menggunakan perintah `free(list)`. Terakhir, kompiler diperintahkan untuk mengarahkan `list`penunjuk sekarang ke blok memori yang `tmp`menunjuk ke. Isi dari `list`dicetak dan kemudian dibebaskan.
    
-   It’s useful to think about `list` and `tmp` as both signs that point at a chunk of memory. As in the example above, `list` at one point _pointed_ to an array of size 3. By the end, `list` was told to point to a chunk of memory of size 4. Technically, by the end of the above code, `tmp` and `list` both pointed to the same block of memory.
    
-   C comes with a very useful function called `realloc` that will reallocate the memory for you. `realloc` takes two arguments. First, it asks you to specify the array you are attempting to copy. Second, it asks you to specify the size to which you would like the final array to be. Modify your code as follows:
    
    ```
    // Implements a list of numbers with an array of dynamic size using realloc
    
    #include <stdio.h>
    #include <stdlib.h>
    
    int main(void)
    {
        // List of size 3
        int *list = malloc(3 * sizeof(int));
        if (list == NULL)
        {
            return 1;
        }
    
        // Initialize list of size 3 with numbers
        list[0] = 1;
        list[1] = 2;
        list[2] = 3;
    
        // Resize list to be of size 4
        int *tmp = realloc(list, 4 * sizeof(int));
        if (tmp == NULL)
        {
            free(list);
            return 1;
        }
        list = tmp;
    
        // Add number to list
        list[3] = 4;
    
        // Print list
        for (int i = 0; i < 4; i++)
        {
            printf("%i\n", list[i]);
        }
    
        // Free list
        free(list);
        return 0;
    }
    ```
    
    Perhatikan bahwa `int *tmp = realloc(list, 4 * sizeof(int))`membuat daftar ukuran empat bilangan bulat. Kemudian, ini akan menyalin nilai dari `list`ke array baru ini. Terakhir, sebuah pointer yang dipanggil `tmp`menunjuk ke lokasi memori dari array baru ini. Penyalinan ditangani oleh `realloc`. Setelah salinan itu dibuat, memori di lokasi `list`dibebaskan. Kemudian, pointer yang dipanggil `list`diarahkan ke lokasi `tmp`, di mana array baru berada.
    
-   Anda dapat membayangkan bagaimana menggunakan `realloc`antrian atau tumpukan bisa bermanfaat. Saat jumlah data bertambah, `realloc`dapat digunakan untuk menambah atau mengecilkan tumpukan atau antrian.

## [Daftar Tertaut](https://cs50.harvard.edu/college/2022/fall/notes/5/#linked-lists)

-   Dalam beberapa minggu terakhir, Anda telah belajar tentang tiga primitif yang berguna. A `struct`adalah tipe data yang dapat Anda definisikan sendiri. Notasi `.`titik memungkinkan Anda untuk mengakses variabel di dalam struktur itu _._ Operator `*`digunakan untuk mendeklarasikan sebuah pointer atau dereference sebuah variabel.
-   Hari ini, Anda diperkenalkan dengan `->`operator. Itu adalah panah. Operator ini pergi ke alamat dan melihat ke dalam struktur.
-   Daftar _tertaut_ adalah salah satu struktur data paling kuat dalam C. Daftar tertaut memungkinkan Anda memasukkan nilai yang terletak di berbagai area memori. Selanjutnya, mereka memungkinkan Anda untuk secara dinamis mengembangkan dan mengecilkan daftar sesuai keinginan Anda.
-   Anda mungkin membayangkan tiga nilai disimpan di tiga area memori yang berbeda sebagai berikut:
    
    ![Tiga kotak dengan 1 2 3 di area memori yang terpisah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide036.png "tiga nilai dalam memori")
    
-   Bagaimana seseorang bisa menyatukan nilai-nilai ini dalam sebuah daftar?
-   Kita bisa membayangkan data ini digambarkan di atas sebagai berikut:
    
    ![Tiga kotak dengan 1 2 3 di area memori terpisah dengan kotak yang lebih kecil terpasang](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide037.png "tiga nilai dalam memori")
    
-   Kami dapat menggunakan lebih banyak memori untuk melacak di mana item berikutnya berada.
    
    ![Tiga kotak dengan 1 2 3 di area memori yang terpisah dengan kotak yang lebih kecil terpasang di mana alamat memori berada di dalam kotak yang terpasang itu](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide041.png "tiga nilai dalam memori")
    
    Perhatikan bahwa NULL digunakan untuk menunjukkan bahwa tidak ada lagi yang _berikutnya_ dalam daftar.
    
-   Dengan konvensi, kami akan menyimpan satu elemen lagi di memori, sebuah pointer, yang melacak item pertama dalam daftar.
    
    ![Tiga kotak dengan 1 2 3 di area memori yang terpisah dengan kotak yang lebih kecil terpasang di mana alamat memori berada di dalam kotak yang terpasang sekarang dengan kotak terakhir dengan alamat memori dari kotak pertama](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide042.png "tiga nilai dalam memori dengan pointer")
    
-   Mengabstraksi alamat memori, daftar akan muncul sebagai berikut:
    
    ![Tiga kotak dengan area memori yang terpisah dengan kotak yang lebih kecil dengan kotak terakhir di mana satu kotak menunjuk ke yang lain dan yang lain sampai akhir kotak](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide043.png "tiga nilai dalam memori dengan pointer")
    
-   Kotak-kotak ini disebut _node_ . Node berisi _item_ dan pointer yang _disebut_ _next_ . Dalam kode, Anda dapat membayangkan sebuah simpul sebagai berikut:
    
    ```
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    ```
    
    Perhatikan bahwa item yang terkandung dalam simpul ini adalah bilangan bulat yang disebut `number`. Kedua, penunjuk ke simpul yang dipanggil `next`disertakan, yang akan menunjuk ke simpul lain di suatu tempat di memori.
    
-   Daftar tertaut tidak disimpan dalam blok memori yang berdekatan. Mereka dapat tumbuh sebesar yang Anda inginkan, asalkan tersedia sumber daya sistem yang cukup. Kelemahannya, bagaimanapun, adalah lebih banyak memori diperlukan untuk melacak daftar daripada array. Ini karena untuk setiap elemen, Anda tidak hanya harus menyimpan nilai elemen, tetapi juga pointer ke node berikutnya. Selanjutnya, daftar tertaut tidak dapat diindeks menjadi seperti yang dimungkinkan dalam array karena kita harus melewati yang pertama�−1elemen untuk menemukan lokasi�elemen th. Karena itu, daftar yang digambarkan di atas harus dicari secara linier. Oleh karena itu, pencarian biner tidak dimungkinkan dalam daftar yang dibuat seperti di atas.
    
-   Secara konseptual, kita bisa membayangkan proses pembuatan linked list. Pertama, `node *list`dideklarasikan, tetapi nilainya sampah.
    
    ![Satu nilai sampah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide055.png "daftar tertaut")
    
-   Selanjutnya, node yang dipanggil `n`dialokasikan dalam memori.
    
    ![Satu nilai sampah disebut n dengan penunjuk lain disebut daftar](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide059.png "daftar tertaut")
    
-   Selanjutnya, `number`node diberi nilai `1`.
    
    ![n menunjuk ke node dengan 1 sebagai angka dan nilai sampah sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide064.png "daftar tertaut")
    
-   Selanjutnya, bidang simpul `next`ditugaskan `NULL`.
    
    ![n menunjuk ke sebuah node dengan 1 sebagai nomor dan null sebagai nilai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide066.png "daftar tertaut")
    
-   Selanjutnya, `list`arahkan ke lokasi memori ke `n`titik mana. `n`dan `list`sekarang menunjuk ke tempat yang sama.
    
    ![n dan daftarkan keduanya menunjuk ke simpul dengan 1 sebagai angka dan nol sebagai nilai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide068.png "daftar tertaut")
    
-   Node baru kemudian dibuat. Bidang `number`dan `next`keduanya diisi dengan nilai sampah.
    
    ![list menunjuk ke node dengan 1 sebagai angka dan null sebagai nilai next dan n menunjuk ke node baru dengan nilai sampah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide073.png "daftar tertaut")
    
-   Nilai `number`node `n`(simpul baru) diperbarui menjadi `2`.
    
    ![list menunjuk ke node dengan 1 sebagai nomor dan null sebagai nilai berikutnya dan n menunjuk ke node baru dengan 2 sebagai nomor dan sampah sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide075.png "daftar tertaut")
    
-   Selain itu, `next`bidang juga diperbarui.
    
    ![list menunjuk ke node dengan 1 sebagai nomor dan null sebagai nilai berikutnya dan n menunjuk ke node baru dengan 2 sebagai nomor dan null sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide077.png "daftar tertaut")
    
-   Yang terpenting, kami tidak ingin kehilangan koneksi kami ke salah satu node ini agar tidak hilang selamanya. Oleh karena itu, bidang `n`'s `next`diarahkan ke lokasi memori yang sama dengan `list`.
    
    ![list menunjuk ke node dengan 1 sebagai nomor dan null sebagai nilai berikutnya dan n menunjuk ke node baru dengan 2 sebagai nomor dan null sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide084.png "daftar tertaut")
    
-   Akhirnya, `list`diperbarui untuk menunjuk ke `n`. Kami sekarang memiliki daftar tertaut dari dua item.
    
    ![daftar menunjuk ke sebuah node dengan 1 sebagai nomor dan selanjutnya menunjuk ke sebuah node dengan n menunjuk tempat yang sama node dengan satu menunjuk ke sebuah node dengan 2 sebagai nomor dan null sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide086.png "daftar tertaut")
    
-   Untuk menerapkan ini dalam kode, ubah kode Anda sebagai berikut:
    
    ```
    // Prepends numbers to a linked list, using while loop to print
    
    #include <cs50.h>
    #include <stdio.h>
    #include <stdlib.h>
    
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    
    int main(int argc, char *argv[])
    {
        // Memory for numbers
        node *list = NULL;
    
        // For each command-line argument
        for (int i = 1; i < argc; i++)
        {
            // Convert argument to int
            int number = atoi(argv[i]);
    
            // Allocate node for number
            node *n = malloc(sizeof(node));
            if (n == NULL)
            {
                return 1;
            }
            n->number = number;
            n->next = NULL;
    
            // Prepend node to list
            n->next = list;
            list = n;
        }
    
        // Print numbers
        node *ptr = list;
        while (ptr != NULL)
        {
            printf("%i\n", ptr->number);
            ptr = ptr->next;
        }
    
        // Free memory
        ptr = list;
        while (ptr != NULL)
        {
            node *next = ptr->next;
            free(ptr);
            ptr = next;
        }
    }
    ```
    
    Perhatikan bahwa apa yang dimasukkan pengguna pada baris perintah dimasukkan ke dalam `number`bidang simpul yang disebut `n`, dan kemudian simpul itu ditambahkan ke `list`. Misalnya, `./list 1 2`akan memasukkan angka `1`ke dalam `number`bidang simpul yang disebut `n`, lalu meletakkan penunjuk ke `list`bidang `next`simpul, lalu memperbarui `list`ke menunjuk ke `n`. Proses yang sama diulangi untuk `2`. Selanjutnya, `node *ptr = list`buat variabel sementara yang menunjuk ke tempat yang sama dengan yang `list`ditunjuk. Mencetak `while`apa yang ditunjuk oleh node `ptr`, dan kemudian memperbarui `ptr`untuk menunjuk ke `next`node dalam daftar. Akhirnya, semua memori dibebaskan.
    
-   Mempertimbangkan jumlah waktu yang diperlukan untuk mencari daftar ini, urutannya adalahHAI(�), dalam kasus terburuk, seluruh daftar harus selalu dicari untuk menemukan item. Kompleksitas waktu untuk menambahkan elemen baru ke daftar akan bergantung pada tempat elemen tersebut ditambahkan. Ini diilustrasikan dalam contoh di bawah ini.
-   Anda, sebagai pemrogram, memiliki pilihan bagaimana mengimplementasikan daftar Anda. Kode berikut, misalnya, mengimplementasikan daftar tertaut yang menambahkan angka ke depan daftar:
    
    ```
    // Prepends numbers to a linked list, using for loop to print
    
    #include <cs50.h>
    #include <stdio.h>
    #include <stdlib.h>
    
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    
    int main(int argc, char *argv[])
    {
        // Memory for numbers
        node *list = NULL;
    
        // For each command-line argument
        for (int i = 1; i < argc; i++)
        {
            // Convert argument to int
            int number = atoi(argv[i]);
    
            // Allocate node for number
            node *n = malloc(sizeof(node));
            if (n == NULL)
            {
                return 1;
            }
            n->number = number;
            n->next = NULL;
    
            // Prepend node to list
            n->next = list;
            list = n;
        }
    
        // Print numbers
        for (node *ptr = list; ptr != NULL; ptr = ptr->next)
        {
            printf("%i\n", ptr->number);
        }
    
        // Free memory
        node *ptr = list;
        while (ptr != NULL)
        {
            node *next = ptr->next;
            free(ptr);
            ptr = next;
        }
    }
    ```
    
    Perhatikan bagaimana angka ditempatkan di awal daftar. Penyisipan ini akan berjalan dalam urutanHAI(1), karena jumlah langkah yang diperlukan untuk melakukannya tidak bergantung pada ukuran daftar.
    
-   Selanjutnya, Anda dapat menempatkan angka di akhir daftar seperti yang diilustrasikan dalam kode ini:
    
    ```
    // Implements a list of numbers using a linked list
    
    #include <cs50.h>
    #include <stdio.h>
    #include <stdlib.h>
    
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    
    int main(int argc, char *argv[])
    {
        // Memory for numbers
        node *list = NULL;
    
        // For each command-line argument
        for (int i = 1; i < argc; i++)
        {
            // Convert argument to int
            int number = atoi(argv[i]);
    
            // Allocate node for number
            node *n = malloc(sizeof(node));
            if (n == NULL)
            {
                return 1;
            }
            n->number = number;
            n->next = NULL;
    
            // If list is empty
            if (list == NULL)
            {
                // This node is the whole list
                list = n;
            }
    
            // If list has numbers already
            else
            {
                // Iterate over nodes in list
                for (node *ptr = list; ptr != NULL; ptr = ptr->next)
                {
                    // If at end of list
                    if (ptr->next == NULL)
                    {
                        // Append node
                        ptr->next = n;
                        break;
                    }
                }
            }
        }
    
        // Print numbers
        for (node *ptr = list; ptr != NULL; ptr = ptr->next)
        {
            printf("%i\n", ptr->number);
        }
    
        // Free memory
        node *ptr = list;
        while (ptr != NULL)
        {
            node *next = ptr->next;
            free(ptr);
            ptr = next;
        }
    }
    ```
    
    Perhatikan bagaimana kode ini _menyusuri_ daftar ini untuk menemukan akhirnya. Saat menambahkan elemen, (menambahkan ke akhir daftar) kode kita akan berjalanHAI(�), karena kita harus menelusuri seluruh daftar sebelum kita dapat menambahkan elemen terakhir.
    
-   Selanjutnya, Anda dapat mengurutkan daftar Anda saat item ditambahkan:
    
    ```
    // Implements a sorted list of numbers using a linked list
    
    #include <cs50.h>
    #include <stdio.h>
    #include <stdlib.h>
    
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    
    int main(int argc, char *argv[])
    {
        // Memory for numbers
        node *list = NULL;
    
        // For each command-line argument
        for (int i = 1; i < argc; i++)
        {
            // Convert argument to int
            int number = atoi(argv[i]);
    
            // Allocate node for number
            node *n = malloc(sizeof(node));
            if (n == NULL)
            {
                return 1;
            }
            n->number = number;
            n->next = NULL;
    
            // If list is empty
            if (list == NULL)
            {
                list = n;
            }
    
            // If number belongs at beginning of list
            else if (n->number < list->number)
            {
                n->next = list;
                list = n;
            }
    
            // If number belongs later in list
            else
            {
                // Iterate over nodes in list
                for (node *ptr = list; ptr != NULL; ptr = ptr->next)
                {
                    // If at end of list
                    if (ptr->next == NULL)
                    {
                        // Append node
                        ptr->next = n;
                        break;
                    }
    
                    // If in middle of list
                    if (n->number < ptr->next->number)
                    {
                        n->next = ptr->next;
                        ptr->next = n;
                    }
                }
            }
        }
    
        // Print numbers
        for (node *ptr = list; ptr != NULL; ptr = ptr->next)
        {
            printf("%i\n", ptr->number);
        }
    
        // Free memory
        node *ptr = list;
        while (ptr != NULL)
        {
            node *next = ptr->next;
            free(ptr);
            ptr = next;
        }
    }
    ```
    
    Perhatikan bagaimana daftar ini diurutkan saat dibuat. Untuk memasukkan elemen dalam urutan khusus ini, kode kita akan tetap berjalanHAI(�)untuk setiap penyisipan, karena dalam kasus terburuk kita harus memeriksa semua elemen saat ini.
    

## [Pohon](https://cs50.harvard.edu/college/2022/fall/notes/5/#trees)

-   _Pohon pencarian biner_ adalah struktur data lain yang dapat digunakan untuk menyimpan data secara lebih efisien sehingga dapat dicari dan diambil.
-   Anda bisa membayangkan urutan angka yang diurutkan.
    
    ![1 2 3 4 5 6 7 dalam kotak yang bersebelahan](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide086.png "pohon")
    
-   Bayangkan kemudian bahwa nilai tengah menjadi puncak pohon. Mereka yang kurang dari nilai ini ditempatkan di sebelah kiri. Nilai-nilai yang lebih dari nilai ini berada di sebelah kanan.
    
    ![1 2 3 4 5 6 7 dalam kotak-kotak yang disusun menurut urutan 4 di atas 3 dan 5 di bawah itu dan 1 2 6 7 di bawah itu](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide119.png "pohon")
    
-   Pointer kemudian dapat digunakan untuk menunjuk ke lokasi yang benar dari setiap area memori sehingga masing-masing node dapat dihubungkan.
    
    ![1 2 3 4 5 6 7 dalam kotak-kotak yang tersusun dalam hirarki 4 di atas 3 dan 5 di bawahnya dan 1 2 6 7 di bawah panah menghubungkan mereka dalam formasi pohon](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide120.png "pohon")
    
-   Dalam kode, ini dapat diimplementasikan sebagai berikut.
    
    ```
    // Implements a list of numbers as a binary search tree
    
    #include <stdio.h>
    #include <stdlib.h>
    
    // Represents a node
    typedef struct node
    {
        int number;
        struct node *left;
        struct node *right;
    }
    node;
    
    void free_tree(node *root);
    void print_tree(node *root);
    
    int main(void)
    {
        // Tree of size 0
        node *tree = NULL;
    
        // Add number to list
        node *n = malloc(sizeof(node));
        if (n == NULL)
        {
            return 1;
        }
        n->number = 2;
        n->left = NULL;
        n->right = NULL;
        tree = n;
    
        // Add number to list
        n = malloc(sizeof(node));
        if (n == NULL)
        {
            free_tree(tree);
            return 1;
        }
        n->number = 1;
        n->left = NULL;
        n->right = NULL;
        tree->left = n;
    
        // Add number to list
        n = malloc(sizeof(node));
        if (n == NULL)
        {
            free_tree(tree);
            return 1;
        }
        n->number = 3;
        n->left = NULL;
        n->right = NULL;
        tree->right = n;
    
        // Print tree
        print_tree(tree);
    
        // Free tree
        free_tree(tree);
        return 0;
    }
    
    void free_tree(node *root)
    {
        if (root == NULL)
        {
            return;
        }
        free_tree(root->left);
        free_tree(root->right);
        free(root);
    }
    
    void print_tree(node *root)
    {
        if (root == NULL)
        {
            return;
        }
        print_tree(root->left);
        printf("%i\n", root->number);
        print_tree(root->right);
    }
    ```
    
-   Pencarian pohon ini dapat diimplementasikan sebagai berikut:
    
    ```
    bool search(node *tree, int number)
    {
        if (tree == NULL)
        {
            return false;
        }
        else if (number < tree->number)
        {
            return search(tree->left, number);
        }
        else if (number > tree->number)
        {
            return search(tree->right, number);
        }
        else if (number == tree->number)
        {
            return true;
        }
    }
    ```
    
    Perhatikan fungsi pencarian ini dimulai dengan pergi ke lokasi `tree`. Kemudian, menggunakan rekursi untuk mencari `number`.
    
-   Pohon seperti di atas menawarkan dinamisme yang tidak ditawarkan oleh array. Itu bisa tumbuh dan menyusut seperti yang kita inginkan.

## [Kamus](https://cs50.harvard.edu/college/2022/fall/notes/5/#dictionaries)

-   _Kamus_ adalah struktur data lainnya.
-   Kamus, seperti kamus bentuk buku sebenarnya yang memiliki kata dan definisi, memiliki _kunci_ dan _nilai_ .
-   Cawan _suci_ kompleksitas waktu adalahHAI(1)atau _waktu konstan_ . Artinya, yang paling utama adalah agar akses menjadi instan.
    
    ![grafik berbagai kompleksitas waktu di mana O dari log n adalah yang terbaik kedua dan O dari 1 adalah yang terbaik](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide151.png "kompleksitas waktu")
    
-   Kamus dapat menawarkan kecepatan akses ini.

## [Tabel Hash dan Hash](https://cs50.harvard.edu/college/2022/fall/notes/5/#hashing-and-hash-tables)

-   _Hashing_ adalah gagasan untuk mengambil nilai dan mampu menghasilkan nilai yang menjadi jalan pintas nanti.
-   Misalnya, hashing _apel_ dapat di-hash sebagai nilai `1`, dan _berry_ dapat di-hash sebagai `2`. Oleh karena itu, menemukan _apel_ semudah menanyakan algoritme _hash_ tempat _apel_ disimpan. Meskipun tidak ideal dalam hal desain, pada akhirnya, menempatkan semua _a_ ’ dalam satu keranjang dan _b_ ’ di keranjang lain, konsep _pengelompokan_ nilai hash ini mengilustrasikan bagaimana Anda dapat menggunakan konsep ini: nilai hash dapat digunakan untuk mencari jalan pintas seperti itu nilai.
-   Fungsi _hash_ adalah algoritma yang mengurangi nilai yang lebih besar menjadi sesuatu yang kecil dan dapat diprediksi. Umumnya, fungsi ini mengambil item yang ingin Anda tambahkan ke tabel hash Anda, dan mengembalikan bilangan bulat yang mewakili indeks array tempat item tersebut harus ditempatkan.
-   Tabel _hash_ adalah kombinasi fantastis dari array dan daftar tertaut. _Saat_ diimplementasikan dalam kode, tabel hash adalah _larik_ pointer ke _node_ s.
-   Tabel hash dapat dibayangkan sebagai berikut:
    
    ![kolom vertikal 26 kotak satu untuk setiap huruf alfabet](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide157.png "alfabet")
    
    Perhatikan bahwa ini adalah larik yang diberikan setiap nilai alfabet.
    
-   Kemudian, di setiap lokasi larik, daftar tertaut digunakan untuk melacak setiap nilai yang disimpan di sana:
    
    ![kolom vertikal 26 kotak satu untuk setiap huruf alfabet dengan berbagai nama dari harry potter unverise emergint ke albus kanan dengan a dan harry dengan h](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide169.png "alfabet")
    
-   _Tabrakan_ adalah saat Anda menambahkan nilai ke tabel hash, dan sesuatu sudah ada di lokasi hash. Di atas, tabrakan hanya ditambahkan ke akhir daftar.
-   Tabrakan dapat dikurangi dengan memprogram tabel hash dan algoritme hash Anda dengan lebih baik. Anda dapat membayangkan peningkatan di atas sebagai berikut:
    
    ![kolom vertikal dari berbagai kotak yang disusun oleh HAG dan HAR dengan hagrid muncul dari HAG dan harry muncul dari HAR](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide184.png "alfabet")
    
-   Anda, sebagai pemrogram, harus membuat keputusan tentang keuntungan menggunakan lebih banyak memori untuk memiliki tabel hash yang besar dan berpotensi mengurangi waktu pencarian atau menggunakan lebih sedikit memori dan berpotensi meningkatkan waktu pencarian.

## [Mencoba](https://cs50.harvard.edu/college/2022/fall/notes/5/#tries)

-   _Mencoba_ adalah bentuk lain dari struktur data.
-   _Percobaan_ selalu dapat dicari dalam waktu yang konstan.
-   Satu kelemahan dari _Tries_ adalah mereka cenderung menghabiskan banyak memori. Perhatikan bahwa kita membutuhkan26×5=130 `node`ini hanya untuk menyimpan _Hagrid_ !
-   _Hagrid_ akan disimpan sebagai berikut:
    
    ![hagrid dieja dengan satu huruf pada satu waktu di mana satu huruf dikaitkan dengan satu daftar H dari satu daftar A dari yang lain dan seterusnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide207.png "mencoba")
    
-   _Harry_ kemudian akan disimpan sebagai berikut:
    
    ![hagrid dieja dengan satu huruf pada satu waktu di mana satu huruf dikaitkan dengan satu daftar H dari satu daftar A dari yang lain dan seterusnya dan harry dieja dengan cara yang sama di mana hagrid dan harry berbagi dua huruf umum H dan A](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide209.png "mencoba")
    

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/5/#summing-up)

Dalam pelajaran ini, Anda belajar tentang menggunakan pointer untuk membangun struktur data baru. Secara khusus, kami mempelajari…

-   Struktur data
-   Tumpukan dan antrian
-   Mengubah ukuran array
-   Daftar tertaut
-   Kamus
-   Mencoba

Sampai jumpa lain waktu!# [Kuliah 5](https://cs50.harvard.edu/college/2022/fall/notes/5/#lecture-5)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/5/#welcome)
-   [Struktur data](https://cs50.harvard.edu/college/2022/fall/notes/5/#data-structures)
-   [Tumpukan dan Antrian](https://cs50.harvard.edu/college/2022/fall/notes/5/#stacks-and-queues)
-   [Jack Mempelajari Fakta](https://cs50.harvard.edu/college/2022/fall/notes/5/#jack-learns-the-facts)
-   [Mengubah Ukuran Array](https://cs50.harvard.edu/college/2022/fall/notes/5/#resizing-arrays)
-   [Daftar Tertaut](https://cs50.harvard.edu/college/2022/fall/notes/5/#linked-lists)
-   [Pohon](https://cs50.harvard.edu/college/2022/fall/notes/5/#trees)
-   [Kamus](https://cs50.harvard.edu/college/2022/fall/notes/5/#dictionaries)
-   [Tabel Hash dan Hash](https://cs50.harvard.edu/college/2022/fall/notes/5/#hashing-and-hash-tables)
-   [Mencoba](https://cs50.harvard.edu/college/2022/fall/notes/5/#tries)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/5/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/5/#welcome)

-   Semua minggu sebelumnya telah memberi Anda blok bangunan dasar pemrograman.
-   Semua yang telah Anda pelajari di C akan memungkinkan Anda menerapkan blok bangunan ini dalam bahasa pemrograman tingkat tinggi seperti Python.
-   Hari ini, kita akan berbicara tentang mengatur data dalam memori.

## [Struktur data](https://cs50.harvard.edu/college/2022/fall/notes/5/#data-structures)

-   _Struktur data_ pada dasarnya adalah bentuk organisasi dalam memori.
-   Ada banyak cara untuk mengatur data dalam memori.
-   _Struktur data abstrak_ adalah yang dapat kita bayangkan secara konseptual. Saat belajar tentang ilmu komputer, seringkali berguna untuk memulai dengan struktur data konseptual ini. Mempelajari hal ini nantinya akan memudahkan untuk memahami bagaimana mengimplementasikan struktur data yang lebih konkret.

## [Tumpukan dan Antrian](https://cs50.harvard.edu/college/2022/fall/notes/5/#stacks-and-queues)

-   _Antrian_ merupakan salah satu bentuk struktur data abstrak.
-   Antrian memiliki sifat tertentu. Yakni, _FIFO_ atau “first in first out.” Anda dapat membayangkan diri Anda mengantri untuk berkendara di taman hiburan. Orang pertama dalam antrean akan naik terlebih dahulu. Orang terakhir yang mendapat tumpangan terakhir.
-   Antrean memiliki tindakan spesifik yang terkait dengannya. Misalnya, sebuah item dapat _diantrekan_ ; Artinya, item tersebut dapat bergabung dengan garis atau antrian. Selanjutnya, item dapat di _-dequeued_ atau keluar dari antrian setelah mencapai garis depan.
-   Antrian kontras dengan _tumpukan_ . Pada dasarnya, properti tumpukan berbeda dari antrian. Secara khusus, ini adalah _LIFO_ atau "last in first out." Sama seperti menumpuk baki di kafetaria, baki yang diletakkan di tumpukan terakhir adalah yang pertama yang boleh diambil.
-   Tumpukan memiliki tindakan khusus yang terkait dengannya. Misalnya, _push_ menempatkan sesuatu di atas tumpukan. _Pop_ menghapus sesuatu dari atas tumpukan.
-   Dalam kode, Anda mungkin membayangkan tumpukan sebagai berikut:
    
    ```
    const int CAPACITY = 50;
    
    typedef struct
    {
        person people[CAPACITY];
        int size;
    }
    stack;
    ```
    
    Perhatikan bahwa array yang disebut people bertipe `person`. Seberapa `CAPACITY`tinggi tumpukan itu. Bilangan bulat `size`adalah seberapa penuh tumpukan itu sebenarnya, terlepas dari berapa banyak yang _bisa_ ditampungnya.
    
-   Anda mungkin membayangkan bahwa kode di atas memiliki batasan. Karena kapasitas array selalu ditentukan sebelumnya dalam kode ini. Oleh karena itu, tumpukan mungkin selalu terlalu besar. Anda mungkin membayangkan hanya menggunakan satu tempat di tumpukan dari 5.000.
-   Alangkah baiknya tumpukan kita menjadi dinamis – dapat tumbuh saat item ditambahkan ke dalamnya.

## [Jack Mempelajari Fakta](https://cs50.harvard.edu/college/2022/fall/notes/5/#jack-learns-the-facts)

-   Kami menonton video berjudul [Jack Mempelajari Fakta](https://www.youtube.com/watch?v=ItAG3s6KIEI) oleh Profesor Shannon Duvall dari Universitas Elon.

## [Mengubah Ukuran Array](https://cs50.harvard.edu/college/2022/fall/notes/5/#resizing-arrays)

-   Memutar ulang ke Minggu 2, kami memperkenalkan Anda pada struktur data pertama Anda.
-   Array adalah blok memori yang berdekatan.
-   Anda mungkin membayangkan sebuah array sebagai berikut:
    
    ![tiga kotak dengan 1 2 3](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide019.png "Himpunan")
    
-   Di memori, ada nilai lain yang disimpan oleh program, fungsi, dan variabel lain. Banyak dari ini mungkin merupakan nilai sampah yang tidak terpakai yang digunakan pada satu titik tetapi sekarang tersedia untuk digunakan.
    
    ![tiga kotak dengan 1 2 3 di antara banyak elemen memori lainnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide022.png "array di dalam memori")
    
-   Bayangkan Anda ingin menyimpan nilai keempat `4`dalam larik kami? Yang diperlukan adalah mengalokasikan area memori baru dan memindahkan array lama ke yang baru.
    
    ![Tiga kotak dengan 1 2 3 di atas empat kotak dengan 1 2 dan dua nilai sampah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide025.png "dua array dengan nilai sampah")
    
-   Nilai sampah lama akan ditimpa dengan data baru kami.
    
    ![Tiga kotak dengan 1 2 3 di atas empat kotak dengan 1 2 3 dan nilai sampah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide026.png "dua array dengan nilai sampah")
    
-   Salah satu kelemahan dari pendekatan ini adalah desainnya yang buruk: Setiap kali kita menambahkan angka, kita harus menyalin item array demi item.
    
-   Bukankah lebih baik jika kita bisa meletakkannya `4`di tempat lain di memori? Menurut definisi, ini tidak lagi menjadi array karena `4`tidak lagi berada dalam memori yang berdekatan.
    
-   Di terminal Anda, ketik `code list.c`dan tulis kode sebagai berikut:
    
    ```
    // Implements a list of numbers with an array of fixed size
    
    #include <stdio.h>
    
    int main(void)
    {
        // List of size 3
        int list[3];
    
        // Initialize list with numbers
        list[0] = 1;
        list[1] = 2;
        list[2] = 3;
    
        // Print list
        for (int i = 0; i < 3; i++)
        {
            printf("%i\n", list[i]);
        }
    }
    ```
    
    Perhatikan bahwa hal di atas sangat mirip dengan apa yang telah kita pelajari sebelumnya dalam kursus ini. Kami memiliki memori yang dialokasikan sebelumnya untuk tiga item.
    
-   Membangun berdasarkan pengetahuan kami yang diperoleh baru-baru ini, kami dapat memanfaatkan pemahaman kami tentang pointer untuk membuat desain yang lebih baik dalam kode ini. Ubah kode Anda sebagai berikut:
    
    ```
    // Implements a list of numbers with an array of dynamic size
    
    #include <stdio.h>
    #include <stdlib.h>
    
    int main(void)
    {
        // List of size 3
        int *list = malloc(3 * sizeof(int));
        if (list == NULL)
        {
            return 1;
        }
    
        // Initialize list of size 3 with numbers
        list[0] = 1;
        list[1] = 2;
        list[2] = 3;
    
        // List of size 4
        int *tmp = malloc(4 * sizeof(int));
        if (tmp == NULL)
        {
            free(list);
            return 1;
        }
    
        // Copy list of size 3 into list of size 4
        for (int i = 0; i < 3; i++)
        {
            tmp[i] = list[i];
        }
    
        // Add number to list of size 4
        tmp[3] = 4;
    
        // Free list of size 3
        free(list);
    
        // Remember list of size 4
        list = tmp;
    
        // Print list
        for (int i = 0; i < 4; i++)
        {
            printf("%i\n", list[i]);
        }
    
        // Free list
        free(list);
        return 0;
    ```
    
    Perhatikan bahwa daftar ukuran tiga bilangan bulat dibuat. Kemudian, tiga alamat memori dapat diberi nilai `1`, `2`, dan `3`. Kemudian, daftar ukuran empat dibuat. Selanjutnya, daftar disalin dari yang pertama ke yang kedua. Nilai untuk `4`ditambahkan ke `tmp`daftar. Karena blok memori yang `list`menunjuk ke tidak lagi digunakan, maka dibebaskan menggunakan perintah `free(list)`. Terakhir, kompiler diperintahkan untuk mengarahkan `list`penunjuk sekarang ke blok memori yang `tmp`menunjuk ke. Isi dari `list`dicetak dan kemudian dibebaskan.
    
-   It’s useful to think about `list` and `tmp` as both signs that point at a chunk of memory. As in the example above, `list` at one point _pointed_ to an array of size 3. By the end, `list` was told to point to a chunk of memory of size 4. Technically, by the end of the above code, `tmp` and `list` both pointed to the same block of memory.
    
-   C comes with a very useful function called `realloc` that will reallocate the memory for you. `realloc` takes two arguments. First, it asks you to specify the array you are attempting to copy. Second, it asks you to specify the size to which you would like the final array to be. Modify your code as follows:
    
    ```
    // Implements a list of numbers with an array of dynamic size using realloc
    
    #include <stdio.h>
    #include <stdlib.h>
    
    int main(void)
    {
        // List of size 3
        int *list = malloc(3 * sizeof(int));
        if (list == NULL)
        {
            return 1;
        }
    
        // Initialize list of size 3 with numbers
        list[0] = 1;
        list[1] = 2;
        list[2] = 3;
    
        // Resize list to be of size 4
        int *tmp = realloc(list, 4 * sizeof(int));
        if (tmp == NULL)
        {
            free(list);
            return 1;
        }
        list = tmp;
    
        // Add number to list
        list[3] = 4;
    
        // Print list
        for (int i = 0; i < 4; i++)
        {
            printf("%i\n", list[i]);
        }
    
        // Free list
        free(list);
        return 0;
    }
    ```
    
    Perhatikan bahwa `int *tmp = realloc(list, 4 * sizeof(int))`membuat daftar ukuran empat bilangan bulat. Kemudian, ini akan menyalin nilai dari `list`ke array baru ini. Terakhir, sebuah pointer yang dipanggil `tmp`menunjuk ke lokasi memori dari array baru ini. Penyalinan ditangani oleh `realloc`. Setelah salinan itu dibuat, memori di lokasi `list`dibebaskan. Kemudian, pointer yang dipanggil `list`diarahkan ke lokasi `tmp`, di mana array baru berada.
    
-   Anda dapat membayangkan bagaimana menggunakan `realloc`antrian atau tumpukan bisa bermanfaat. Saat jumlah data bertambah, `realloc`dapat digunakan untuk menambah atau mengecilkan tumpukan atau antrian.

## [Daftar Tertaut](https://cs50.harvard.edu/college/2022/fall/notes/5/#linked-lists)

-   Dalam beberapa minggu terakhir, Anda telah belajar tentang tiga primitif yang berguna. A `struct`adalah tipe data yang dapat Anda definisikan sendiri. Notasi `.`titik memungkinkan Anda untuk mengakses variabel di dalam struktur itu _._ Operator `*`digunakan untuk mendeklarasikan sebuah pointer atau dereference sebuah variabel.
-   Hari ini, Anda diperkenalkan dengan `->`operator. Itu adalah panah. Operator ini pergi ke alamat dan melihat ke dalam struktur.
-   Daftar _tertaut_ adalah salah satu struktur data paling kuat dalam C. Daftar tertaut memungkinkan Anda memasukkan nilai yang terletak di berbagai area memori. Selanjutnya, mereka memungkinkan Anda untuk secara dinamis mengembangkan dan mengecilkan daftar sesuai keinginan Anda.
-   Anda mungkin membayangkan tiga nilai disimpan di tiga area memori yang berbeda sebagai berikut:
    
    ![Tiga kotak dengan 1 2 3 di area memori yang terpisah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide036.png "tiga nilai dalam memori")
    
-   Bagaimana seseorang bisa menyatukan nilai-nilai ini dalam sebuah daftar?
-   Kita bisa membayangkan data ini digambarkan di atas sebagai berikut:
    
    ![Tiga kotak dengan 1 2 3 di area memori terpisah dengan kotak yang lebih kecil terpasang](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide037.png "tiga nilai dalam memori")
    
-   Kami dapat menggunakan lebih banyak memori untuk melacak di mana item berikutnya berada.
    
    ![Tiga kotak dengan 1 2 3 di area memori yang terpisah dengan kotak yang lebih kecil terpasang di mana alamat memori berada di dalam kotak yang terpasang itu](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide041.png "tiga nilai dalam memori")
    
    Perhatikan bahwa NULL digunakan untuk menunjukkan bahwa tidak ada lagi yang _berikutnya_ dalam daftar.
    
-   Dengan konvensi, kami akan menyimpan satu elemen lagi di memori, sebuah pointer, yang melacak item pertama dalam daftar.
    
    ![Tiga kotak dengan 1 2 3 di area memori yang terpisah dengan kotak yang lebih kecil terpasang di mana alamat memori berada di dalam kotak yang terpasang sekarang dengan kotak terakhir dengan alamat memori dari kotak pertama](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide042.png "tiga nilai dalam memori dengan pointer")
    
-   Mengabstraksi alamat memori, daftar akan muncul sebagai berikut:
    
    ![Tiga kotak dengan area memori yang terpisah dengan kotak yang lebih kecil dengan kotak terakhir di mana satu kotak menunjuk ke yang lain dan yang lain sampai akhir kotak](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide043.png "tiga nilai dalam memori dengan pointer")
    
-   Kotak-kotak ini disebut _node_ . Node berisi _item_ dan pointer yang _disebut_ _next_ . Dalam kode, Anda dapat membayangkan sebuah simpul sebagai berikut:
    
    ```
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    ```
    
    Perhatikan bahwa item yang terkandung dalam simpul ini adalah bilangan bulat yang disebut `number`. Kedua, penunjuk ke simpul yang dipanggil `next`disertakan, yang akan menunjuk ke simpul lain di suatu tempat di memori.
    
-   Daftar tertaut tidak disimpan dalam blok memori yang berdekatan. Mereka dapat tumbuh sebesar yang Anda inginkan, asalkan tersedia sumber daya sistem yang cukup. Kelemahannya, bagaimanapun, adalah lebih banyak memori diperlukan untuk melacak daftar daripada array. Ini karena untuk setiap elemen, Anda tidak hanya harus menyimpan nilai elemen, tetapi juga pointer ke node berikutnya. Selanjutnya, daftar tertaut tidak dapat diindeks menjadi seperti yang dimungkinkan dalam array karena kita harus melewati yang pertama�−1elemen untuk menemukan lokasi�elemen th. Karena itu, daftar yang digambarkan di atas harus dicari secara linier. Oleh karena itu, pencarian biner tidak dimungkinkan dalam daftar yang dibuat seperti di atas.
    
-   Secara konseptual, kita bisa membayangkan proses pembuatan linked list. Pertama, `node *list`dideklarasikan, tetapi nilainya sampah.
    
    ![Satu nilai sampah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide055.png "daftar tertaut")
    
-   Selanjutnya, node yang dipanggil `n`dialokasikan dalam memori.
    
    ![Satu nilai sampah disebut n dengan penunjuk lain disebut daftar](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide059.png "daftar tertaut")
    
-   Selanjutnya, `number`node diberi nilai `1`.
    
    ![n menunjuk ke node dengan 1 sebagai angka dan nilai sampah sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide064.png "daftar tertaut")
    
-   Selanjutnya, bidang simpul `next`ditugaskan `NULL`.
    
    ![n menunjuk ke sebuah node dengan 1 sebagai nomor dan null sebagai nilai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide066.png "daftar tertaut")
    
-   Selanjutnya, `list`arahkan ke lokasi memori ke `n`titik mana. `n`dan `list`sekarang menunjuk ke tempat yang sama.
    
    ![n dan daftarkan keduanya menunjuk ke simpul dengan 1 sebagai angka dan nol sebagai nilai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide068.png "daftar tertaut")
    
-   Node baru kemudian dibuat. Bidang `number`dan `next`keduanya diisi dengan nilai sampah.
    
    ![list menunjuk ke node dengan 1 sebagai angka dan null sebagai nilai next dan n menunjuk ke node baru dengan nilai sampah](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide073.png "daftar tertaut")
    
-   Nilai `number`node `n`(simpul baru) diperbarui menjadi `2`.
    
    ![list menunjuk ke node dengan 1 sebagai nomor dan null sebagai nilai berikutnya dan n menunjuk ke node baru dengan 2 sebagai nomor dan sampah sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide075.png "daftar tertaut")
    
-   Selain itu, `next`bidang juga diperbarui.
    
    ![list menunjuk ke node dengan 1 sebagai nomor dan null sebagai nilai berikutnya dan n menunjuk ke node baru dengan 2 sebagai nomor dan null sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide077.png "daftar tertaut")
    
-   Yang terpenting, kami tidak ingin kehilangan koneksi kami ke salah satu node ini agar tidak hilang selamanya. Oleh karena itu, bidang `n`'s `next`diarahkan ke lokasi memori yang sama dengan `list`.
    
    ![list menunjuk ke node dengan 1 sebagai nomor dan null sebagai nilai berikutnya dan n menunjuk ke node baru dengan 2 sebagai nomor dan null sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide084.png "daftar tertaut")
    
-   Akhirnya, `list`diperbarui untuk menunjuk ke `n`. Kami sekarang memiliki daftar tertaut dari dua item.
    
    ![daftar menunjuk ke sebuah node dengan 1 sebagai nomor dan selanjutnya menunjuk ke sebuah node dengan n menunjuk tempat yang sama node dengan satu menunjuk ke sebuah node dengan 2 sebagai nomor dan null sebagai berikutnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide086.png "daftar tertaut")
    
-   Untuk menerapkan ini dalam kode, ubah kode Anda sebagai berikut:
    
    ```
    // Prepends numbers to a linked list, using while loop to print
    
    #include <cs50.h>
    #include <stdio.h>
    #include <stdlib.h>
    
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    
    int main(int argc, char *argv[])
    {
        // Memory for numbers
        node *list = NULL;
    
        // For each command-line argument
        for (int i = 1; i < argc; i++)
        {
            // Convert argument to int
            int number = atoi(argv[i]);
    
            // Allocate node for number
            node *n = malloc(sizeof(node));
            if (n == NULL)
            {
                return 1;
            }
            n->number = number;
            n->next = NULL;
    
            // Prepend node to list
            n->next = list;
            list = n;
        }
    
        // Print numbers
        node *ptr = list;
        while (ptr != NULL)
        {
            printf("%i\n", ptr->number);
            ptr = ptr->next;
        }
    
        // Free memory
        ptr = list;
        while (ptr != NULL)
        {
            node *next = ptr->next;
            free(ptr);
            ptr = next;
        }
    }
    ```
    
    Perhatikan bahwa apa yang dimasukkan pengguna pada baris perintah dimasukkan ke dalam `number`bidang simpul yang disebut `n`, dan kemudian simpul itu ditambahkan ke `list`. Misalnya, `./list 1 2`akan memasukkan angka `1`ke dalam `number`bidang simpul yang disebut `n`, lalu meletakkan penunjuk ke `list`bidang `next`simpul, lalu memperbarui `list`ke menunjuk ke `n`. Proses yang sama diulangi untuk `2`. Selanjutnya, `node *ptr = list`buat variabel sementara yang menunjuk ke tempat yang sama dengan yang `list`ditunjuk. Mencetak `while`apa yang ditunjuk oleh node `ptr`, dan kemudian memperbarui `ptr`untuk menunjuk ke `next`node dalam daftar. Akhirnya, semua memori dibebaskan.
    
-   Mempertimbangkan jumlah waktu yang diperlukan untuk mencari daftar ini, urutannya adalahHAI(�), dalam kasus terburuk, seluruh daftar harus selalu dicari untuk menemukan item. Kompleksitas waktu untuk menambahkan elemen baru ke daftar akan bergantung pada tempat elemen tersebut ditambahkan. Ini diilustrasikan dalam contoh di bawah ini.
-   Anda, sebagai pemrogram, memiliki pilihan bagaimana mengimplementasikan daftar Anda. Kode berikut, misalnya, mengimplementasikan daftar tertaut yang menambahkan angka ke depan daftar:
    
    ```
    // Prepends numbers to a linked list, using for loop to print
    
    #include <cs50.h>
    #include <stdio.h>
    #include <stdlib.h>
    
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    
    int main(int argc, char *argv[])
    {
        // Memory for numbers
        node *list = NULL;
    
        // For each command-line argument
        for (int i = 1; i < argc; i++)
        {
            // Convert argument to int
            int number = atoi(argv[i]);
    
            // Allocate node for number
            node *n = malloc(sizeof(node));
            if (n == NULL)
            {
                return 1;
            }
            n->number = number;
            n->next = NULL;
    
            // Prepend node to list
            n->next = list;
            list = n;
        }
    
        // Print numbers
        for (node *ptr = list; ptr != NULL; ptr = ptr->next)
        {
            printf("%i\n", ptr->number);
        }
    
        // Free memory
        node *ptr = list;
        while (ptr != NULL)
        {
            node *next = ptr->next;
            free(ptr);
            ptr = next;
        }
    }
    ```
    
    Perhatikan bagaimana angka ditempatkan di awal daftar. Penyisipan ini akan berjalan dalam urutanHAI(1), karena jumlah langkah yang diperlukan untuk melakukannya tidak bergantung pada ukuran daftar.
    
-   Selanjutnya, Anda dapat menempatkan angka di akhir daftar seperti yang diilustrasikan dalam kode ini:
    
    ```
    // Implements a list of numbers using a linked list
    
    #include <cs50.h>
    #include <stdio.h>
    #include <stdlib.h>
    
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    
    int main(int argc, char *argv[])
    {
        // Memory for numbers
        node *list = NULL;
    
        // For each command-line argument
        for (int i = 1; i < argc; i++)
        {
            // Convert argument to int
            int number = atoi(argv[i]);
    
            // Allocate node for number
            node *n = malloc(sizeof(node));
            if (n == NULL)
            {
                return 1;
            }
            n->number = number;
            n->next = NULL;
    
            // If list is empty
            if (list == NULL)
            {
                // This node is the whole list
                list = n;
            }
    
            // If list has numbers already
            else
            {
                // Iterate over nodes in list
                for (node *ptr = list; ptr != NULL; ptr = ptr->next)
                {
                    // If at end of list
                    if (ptr->next == NULL)
                    {
                        // Append node
                        ptr->next = n;
                        break;
                    }
                }
            }
        }
    
        // Print numbers
        for (node *ptr = list; ptr != NULL; ptr = ptr->next)
        {
            printf("%i\n", ptr->number);
        }
    
        // Free memory
        node *ptr = list;
        while (ptr != NULL)
        {
            node *next = ptr->next;
            free(ptr);
            ptr = next;
        }
    }
    ```
    
    Perhatikan bagaimana kode ini _menyusuri_ daftar ini untuk menemukan akhirnya. Saat menambahkan elemen, (menambahkan ke akhir daftar) kode kita akan berjalanHAI(�), karena kita harus menelusuri seluruh daftar sebelum kita dapat menambahkan elemen terakhir.
    
-   Selanjutnya, Anda dapat mengurutkan daftar Anda saat item ditambahkan:
    
    ```
    // Implements a sorted list of numbers using a linked list
    
    #include <cs50.h>
    #include <stdio.h>
    #include <stdlib.h>
    
    typedef struct node
    {
        int number;
        struct node *next;
    }
    node;
    
    int main(int argc, char *argv[])
    {
        // Memory for numbers
        node *list = NULL;
    
        // For each command-line argument
        for (int i = 1; i < argc; i++)
        {
            // Convert argument to int
            int number = atoi(argv[i]);
    
            // Allocate node for number
            node *n = malloc(sizeof(node));
            if (n == NULL)
            {
                return 1;
            }
            n->number = number;
            n->next = NULL;
    
            // If list is empty
            if (list == NULL)
            {
                list = n;
            }
    
            // If number belongs at beginning of list
            else if (n->number < list->number)
            {
                n->next = list;
                list = n;
            }
    
            // If number belongs later in list
            else
            {
                // Iterate over nodes in list
                for (node *ptr = list; ptr != NULL; ptr = ptr->next)
                {
                    // If at end of list
                    if (ptr->next == NULL)
                    {
                        // Append node
                        ptr->next = n;
                        break;
                    }
    
                    // If in middle of list
                    if (n->number < ptr->next->number)
                    {
                        n->next = ptr->next;
                        ptr->next = n;
                    }
                }
            }
        }
    
        // Print numbers
        for (node *ptr = list; ptr != NULL; ptr = ptr->next)
        {
            printf("%i\n", ptr->number);
        }
    
        // Free memory
        node *ptr = list;
        while (ptr != NULL)
        {
            node *next = ptr->next;
            free(ptr);
            ptr = next;
        }
    }
    ```
    
    Perhatikan bagaimana daftar ini diurutkan saat dibuat. Untuk memasukkan elemen dalam urutan khusus ini, kode kita akan tetap berjalanHAI(�)untuk setiap penyisipan, karena dalam kasus terburuk kita harus memeriksa semua elemen saat ini.
    

## [Pohon](https://cs50.harvard.edu/college/2022/fall/notes/5/#trees)

-   _Pohon pencarian biner_ adalah struktur data lain yang dapat digunakan untuk menyimpan data secara lebih efisien sehingga dapat dicari dan diambil.
-   Anda bisa membayangkan urutan angka yang diurutkan.
    
    ![1 2 3 4 5 6 7 dalam kotak yang bersebelahan](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide086.png "pohon")
    
-   Bayangkan kemudian bahwa nilai tengah menjadi puncak pohon. Mereka yang kurang dari nilai ini ditempatkan di sebelah kiri. Nilai-nilai yang lebih dari nilai ini berada di sebelah kanan.
    
    ![1 2 3 4 5 6 7 dalam kotak-kotak yang disusun menurut urutan 4 di atas 3 dan 5 di bawah itu dan 1 2 6 7 di bawah itu](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide119.png "pohon")
    
-   Pointer kemudian dapat digunakan untuk menunjuk ke lokasi yang benar dari setiap area memori sehingga masing-masing node dapat dihubungkan.
    
    ![1 2 3 4 5 6 7 dalam kotak-kotak yang tersusun dalam hirarki 4 di atas 3 dan 5 di bawahnya dan 1 2 6 7 di bawah panah menghubungkan mereka dalam formasi pohon](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide120.png "pohon")
    
-   Dalam kode, ini dapat diimplementasikan sebagai berikut.
    
    ```
    // Implements a list of numbers as a binary search tree
    
    #include <stdio.h>
    #include <stdlib.h>
    
    // Represents a node
    typedef struct node
    {
        int number;
        struct node *left;
        struct node *right;
    }
    node;
    
    void free_tree(node *root);
    void print_tree(node *root);
    
    int main(void)
    {
        // Tree of size 0
        node *tree = NULL;
    
        // Add number to list
        node *n = malloc(sizeof(node));
        if (n == NULL)
        {
            return 1;
        }
        n->number = 2;
        n->left = NULL;
        n->right = NULL;
        tree = n;
    
        // Add number to list
        n = malloc(sizeof(node));
        if (n == NULL)
        {
            free_tree(tree);
            return 1;
        }
        n->number = 1;
        n->left = NULL;
        n->right = NULL;
        tree->left = n;
    
        // Add number to list
        n = malloc(sizeof(node));
        if (n == NULL)
        {
            free_tree(tree);
            return 1;
        }
        n->number = 3;
        n->left = NULL;
        n->right = NULL;
        tree->right = n;
    
        // Print tree
        print_tree(tree);
    
        // Free tree
        free_tree(tree);
        return 0;
    }
    
    void free_tree(node *root)
    {
        if (root == NULL)
        {
            return;
        }
        free_tree(root->left);
        free_tree(root->right);
        free(root);
    }
    
    void print_tree(node *root)
    {
        if (root == NULL)
        {
            return;
        }
        print_tree(root->left);
        printf("%i\n", root->number);
        print_tree(root->right);
    }
    ```
    
-   Pencarian pohon ini dapat diimplementasikan sebagai berikut:
    
    ```
    bool search(node *tree, int number)
    {
        if (tree == NULL)
        {
            return false;
        }
        else if (number < tree->number)
        {
            return search(tree->left, number);
        }
        else if (number > tree->number)
        {
            return search(tree->right, number);
        }
        else if (number == tree->number)
        {
            return true;
        }
    }
    ```
    
    Perhatikan fungsi pencarian ini dimulai dengan pergi ke lokasi `tree`. Kemudian, menggunakan rekursi untuk mencari `number`.
    
-   Pohon seperti di atas menawarkan dinamisme yang tidak ditawarkan oleh array. Itu bisa tumbuh dan menyusut seperti yang kita inginkan.

## [Kamus](https://cs50.harvard.edu/college/2022/fall/notes/5/#dictionaries)

-   _Kamus_ adalah struktur data lainnya.
-   Kamus, seperti kamus bentuk buku sebenarnya yang memiliki kata dan definisi, memiliki _kunci_ dan _nilai_ .
-   Cawan _suci_ kompleksitas waktu adalahHAI(1)atau _waktu konstan_ . Artinya, yang paling utama adalah agar akses menjadi instan.
    
    ![grafik berbagai kompleksitas waktu di mana O dari log n adalah yang terbaik kedua dan O dari 1 adalah yang terbaik](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide151.png "kompleksitas waktu")
    
-   Kamus dapat menawarkan kecepatan akses ini.

## [Tabel Hash dan Hash](https://cs50.harvard.edu/college/2022/fall/notes/5/#hashing-and-hash-tables)

-   _Hashing_ adalah gagasan untuk mengambil nilai dan mampu menghasilkan nilai yang menjadi jalan pintas nanti.
-   Misalnya, hashing _apel_ dapat di-hash sebagai nilai `1`, dan _berry_ dapat di-hash sebagai `2`. Oleh karena itu, menemukan _apel_ semudah menanyakan algoritme _hash_ tempat _apel_ disimpan. Meskipun tidak ideal dalam hal desain, pada akhirnya, menempatkan semua _a_ ’ dalam satu keranjang dan _b_ ’ di keranjang lain, konsep _pengelompokan_ nilai hash ini mengilustrasikan bagaimana Anda dapat menggunakan konsep ini: nilai hash dapat digunakan untuk mencari jalan pintas seperti itu nilai.
-   Fungsi _hash_ adalah algoritma yang mengurangi nilai yang lebih besar menjadi sesuatu yang kecil dan dapat diprediksi. Umumnya, fungsi ini mengambil item yang ingin Anda tambahkan ke tabel hash Anda, dan mengembalikan bilangan bulat yang mewakili indeks array tempat item tersebut harus ditempatkan.
-   Tabel _hash_ adalah kombinasi fantastis dari array dan daftar tertaut. _Saat_ diimplementasikan dalam kode, tabel hash adalah _larik_ pointer ke _node_ s.
-   Tabel hash dapat dibayangkan sebagai berikut:
    
    ![kolom vertikal 26 kotak satu untuk setiap huruf alfabet](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide157.png "alfabet")
    
    Perhatikan bahwa ini adalah larik yang diberikan setiap nilai alfabet.
    
-   Kemudian, di setiap lokasi larik, daftar tertaut digunakan untuk melacak setiap nilai yang disimpan di sana:
    
    ![kolom vertikal 26 kotak satu untuk setiap huruf alfabet dengan berbagai nama dari harry potter unverise emergint ke albus kanan dengan a dan harry dengan h](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide169.png "alfabet")
    
-   _Tabrakan_ adalah saat Anda menambahkan nilai ke tabel hash, dan sesuatu sudah ada di lokasi hash. Di atas, tabrakan hanya ditambahkan ke akhir daftar.
-   Tabrakan dapat dikurangi dengan memprogram tabel hash dan algoritme hash Anda dengan lebih baik. Anda dapat membayangkan peningkatan di atas sebagai berikut:
    
    ![kolom vertikal dari berbagai kotak yang disusun oleh HAG dan HAR dengan hagrid muncul dari HAG dan harry muncul dari HAR](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide184.png "alfabet")
    
-   Anda, sebagai pemrogram, harus membuat keputusan tentang keuntungan menggunakan lebih banyak memori untuk memiliki tabel hash yang besar dan berpotensi mengurangi waktu pencarian atau menggunakan lebih sedikit memori dan berpotensi meningkatkan waktu pencarian.

## [Mencoba](https://cs50.harvard.edu/college/2022/fall/notes/5/#tries)

-   _Mencoba_ adalah bentuk lain dari struktur data.
-   _Percobaan_ selalu dapat dicari dalam waktu yang konstan.
-   Satu kelemahan dari _Tries_ adalah mereka cenderung menghabiskan banyak memori. Perhatikan bahwa kita membutuhkan26×5=130 `node`ini hanya untuk menyimpan _Hagrid_ !
-   _Hagrid_ akan disimpan sebagai berikut:
    
    ![hagrid dieja dengan satu huruf pada satu waktu di mana satu huruf dikaitkan dengan satu daftar H dari satu daftar A dari yang lain dan seterusnya](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide207.png "mencoba")
    
-   _Harry_ kemudian akan disimpan sebagai berikut:
    
    ![hagrid dieja dengan satu huruf pada satu waktu di mana satu huruf dikaitkan dengan satu daftar H dari satu daftar A dari yang lain dan seterusnya dan harry dieja dengan cara yang sama di mana hagrid dan harry berbagi dua huruf umum H dan A](https://cs50.harvard.edu/college/2022/fall/notes/5/cs50Week5Slide209.png "mencoba")
    

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/5/#summing-up)

Dalam pelajaran ini, Anda belajar tentang menggunakan pointer untuk membangun struktur data baru. Secara khusus, kami mempelajari…

-   Struktur data
-   Tumpukan dan antrian
-   Mengubah ukuran array
-   Daftar tertaut
-   Kamus
-   Mencoba

Sampai jumpa lain waktu!
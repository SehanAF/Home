# [Kuliah 7](https://cs50.harvard.edu/college/2022/fall/notes/7/#lecture-7)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/7/#welcome)
-   [Database File Datar](https://cs50.harvard.edu/college/2022/fall/notes/7/#flat-file-database)
-   [Database Relasional](https://cs50.harvard.edu/college/2022/fall/notes/7/#relational-databases)
-   [IMDb](https://cs50.harvard.edu/college/2022/fall/notes/7/#imdb)
-   [`JOIN`S](https://cs50.harvard.edu/college/2022/fall/notes/7/#joins)
-   [Indeks](https://cs50.harvard.edu/college/2022/fall/notes/7/#indexes)
-   [Menggunakan SQL dengan Python](https://cs50.harvard.edu/college/2022/fall/notes/7/#using-sql-in-python)
-   [Kondisi Ras](https://cs50.harvard.edu/college/2022/fall/notes/7/#race-conditions)
-   [Serangan Injeksi SQL](https://cs50.harvard.edu/college/2022/fall/notes/7/#sql-injection-attacks)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/7/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/7/#welcome)

-   Di minggu-minggu sebelumnya, kami memperkenalkan Anda ke Python, bahasa pemrograman tingkat tinggi yang menggunakan blok penyusun yang sama dengan yang kami pelajari di C.
-   Minggu ini, kami akan melanjutkan lebih banyak sintaks yang terkait dengan Python.
-   Selanjutnya, kami akan mengintegrasikan pengetahuan ini dengan data.
-   Terakhir, kita akan membahas _SQL_ atau _Structured Query Language_ .
-   Secara keseluruhan, salah satu tujuan dari kursus ini adalah untuk belajar memprogram secara umum – bukan hanya bagaimana memprogram dalam bahasa yang dijelaskan dalam kursus ini.

## [Database File Datar](https://cs50.harvard.edu/college/2022/fall/notes/7/#flat-file-database)

-   Seperti yang mungkin telah Anda lihat sebelumnya, data seringkali dapat dijelaskan dalam pola kolom dan tabel.
-   Spreadsheet seperti yang dibuat di Microsoft Excel dan Google Sheets dapat dikeluarkan ke file _nilai yang dipisahkan_`csv` koma .
-   Jika Anda melihat `csv`file, Anda akan melihat bahwa file tersebut rata karena semua data kami disimpan dalam satu tabel yang diwakili oleh file teks. Kami menyebut bentuk data ini sebagai _basis data file datar_ .
-   Python hadir dengan dukungan asli untuk `csv`file.
-   Di jendela terminal Anda, ketik `code favorites.py`dan tulis kode sebagai berikut:
    
    ```
    # Prints all favorites in CSV using csv.reader
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create reader
        reader = csv.reader(file)
    
        # Skip header row
        next(reader)
    
        # Iterate over CSV file, printing each favorite
        for row in reader:
            print(row[1])
    ```
    
    Perhatikan bahwa `csv`perpustakaan diimpor. Selanjutnya, kami membuat `reader`yang akan menampung hasil `csv.reader(file)`. Fungsi `csv.reader`membaca setiap baris dari file, dan dalam kode kami, kami menyimpan hasilnya di `reader`. `print(row[1])`, oleh karena itu, akan mencetak bahasa dari `favorites.csv`file.
    
-   Anda dapat meningkatkan kode Anda sebagai berikut:
    
    ```
    # Stores favorite in a variable
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create reader
        reader = csv.reader(file)
    
        # Skip header row
        next(reader)
    
        # Iterate over CSV file, printing each favorite
        for row in reader:
            favorite = row[1]
            print(favorite)
    ```
    
    Perhatikan yang `favorite`disimpan dan kemudian dicetak. Perhatikan juga bahwa kita menggunakan `next`fungsi untuk melompat ke baris berikutnya dari pembaca kita.
    
-   Python juga memungkinkan Anda untuk mengindeks dengan kunci daftar. Ubah kode Anda sebagai berikut:
    
    ```
    # Prints all favorites in CSV using csv.DictReader
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Iterate over CSV file, printing each favorite
        for row in reader:
            print(row["language"])
    ```
    
    Perhatikan bahwa contoh ini secara langsung menggunakan `language`kunci dalam pernyataan cetak.
    
-   Untuk menghitung jumlah bahasa favorit yang diekspresikan dalam `csv`file, kita dapat melakukan hal berikut:
    
    ```
    # Counts favorites using variables
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Counts
        scratch, c, python = 0, 0, 0
    
        # Iterate over CSV file, counting favorites
        for row in reader:
            favorite = row["language"]
            if favorite == "Scratch":
                scratch += 1
            elif favorite == "C":
                c += 1
            elif favorite == "Python":
                python += 1
    
    # Print counts
    print(f"Scratch: {scratch}")
    print(f"C: {c}")
    print(f"Python: {python}")
    ```
    
    Perhatikan bahwa setiap bahasa dihitung menggunakan `if`pernyataan.
    
-   Python memungkinkan kita menggunakan kamus untuk menghitung `counts`setiap bahasa. Pertimbangkan peningkatan berikut pada kode kami:
    
    ```
    # Counts favorites using dictionary
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Counts
        counts = {}
    
        # Iterate over CSV file, counting favorites
        for row in reader:
            favorite = row["language"]
            if favorite in counts:
                counts[favorite] += 1
            else:
                counts[favorite] = 1
    
    # Print counts
    for favorite in counts:
        print(f"{favorite}: {counts[favorite]}")
    ```
    
    Perhatikan bahwa nilai `counts`dengan kunci `favorite`bertambah ketika sudah ada. Jika tidak ada, kita definisikan `counts[favorite]`dan atur ke 1. Selanjutnya, string yang diformat telah diperbaiki untuk menyajikan `counts[favorite]`.
    
-   Python juga memungkinkan penyortiran `counts`. Perbaiki kode Anda sebagai berikut:
    
    ```
    # Sorts favorites by key
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Counts
        counts = {}
    
        # Iterate over CSV file, counting favorites
        for row in reader:
            favorite = row["language"]
            if favorite in counts:
                counts[favorite] += 1
            else:
                counts[favorite] = 1
    
    # Print counts
    for favorite in sorted(counts):
        print(f"{favorite}: {counts[favorite]}")
    ```
    
    Perhatikan `sorted(counts)`di bagian bawah kode.
    
-   Jika Anda melihat parameter untuk `sorted`fungsi dalam dokumentasi Python, Anda akan menemukannya memiliki banyak parameter bawaan. Anda dapat memanfaatkan beberapa parameter bawaan ini sebagai berikut:
    
    ```
    # Sorts favorites by value
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Counts
        counts = {}
    
        # Iterate over CSV file, counting favorites
        for row in reader:
            favorite = row["language"]
            if favorite in counts:
                counts[favorite] += 1
            else:
                counts[favorite] = 1
    
    def get_value(language):
        return counts[language]
    
    # Print counts
    for favorite in sorted(counts, key=get_value, reverse=True):
        print(f"{favorite}: {counts[favorite]}")
    ```
    
    Perhatikan bahwa fungsi yang dipanggil `get_value`telah dibuat, dan fungsi itu sendiri diteruskan sebagai argumen ke `sorted`fungsi tersebut. Argumen `key`memungkinkan Anda memberi tahu Python metode yang ingin Anda gunakan untuk mengurutkan item.
    
-   Python memiliki kemampuan unik yang belum kita lihat sampai saat ini: Memungkinkan penggunaan _anonim_ atau `lambda`fungsi. Fungsi-fungsi ini dapat digunakan saat Anda tidak ingin repot membuat fungsi yang sama sekali berbeda. Perhatikan modifikasi berikut:
    
    ```
    # Sorts favorites by value using lambda function
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Counts
        counts = {}
    
        # Iterate over CSV file, counting favorites
        for row in reader:
            favorite = row["language"]
            if favorite in counts:
                counts[favorite] += 1
            else:
                counts[favorite] = 1
    
    # Print counts
    for favorite in sorted(counts, key=lambda language: counts[language], reverse=True):
        print(f"{favorite}: {counts[favorite]}")
    ```
    
    Perhatikan bahwa `get_value`fungsi telah dihapus. Alih-alih, `lambda language: counts[language]`lakukan dalam satu baris apa yang dilakukan fungsi dua baris kami sebelumnya.
    
-   Kita dapat mengubah kolom yang sedang kita periksa, sebagai gantinya berfokus pada masalah favorit kita:
    
    ```
    # Favorite problem instead of favorite language
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Counts
        counts = {}
    
        # Iterate over CSV file, counting favorites
        for row in reader:
            favorite = row["problem"]
            if favorite in counts:
                counts[favorite] += 1
            else:
                counts[favorite] = 1
    
    # Print counts
    for favorite in sorted(counts, key=lambda problem: counts[problem], reverse=True):
        print(f"{favorite}: {counts[favorite]}")
    ```
    
    Perhatikan bahwa `problem`diganti `language`.
    
-   Bagaimana jika kami ingin mengizinkan pengguna untuk memberikan masukan langsung di terminal? Kami dapat memodifikasi kode kami, memanfaatkan pengetahuan kami sebelumnya tentang input pengguna:
    
    ```
    # Favorite problem instead of favorite language
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Counts
        counts = {}
    
        # Iterate over CSV file, counting favorites
        for row in reader:
            favorite = row["problem"]
            if favorite in counts:
                counts[favorite] += 1
            else:
                counts[favorite] = 1
    
    # Print count
    favorite = input("Favorite: ")
    if favorite in counts:
        print(f"{favorite}: {counts[favorite]}")
    ```
    
    Perhatikan betapa padatnya kode kita dibandingkan dengan pengalaman kita di C.
    

## [Database Relasional](https://cs50.harvard.edu/college/2022/fall/notes/7/#relational-databases)

-   Google, Twitter, dan Meta semuanya menggunakan database relasional untuk menyimpan informasi mereka dalam skala besar.
-   Database relasional menyimpan data dalam baris dan kolom dalam struktur yang disebut _tabel_ .
-   SQL memungkinkan untuk empat jenis perintah:
    
    ```
      Create
      Read
      Update
      Delete
    ```
    
-   Keempat operasi ini disebut _CRUD_ .
-   Kita dapat membuat database SQL di terminal dengan mengetikkan `sqlite3 favorites.db`. Saat diminta, kami akan setuju bahwa kami ingin membuat `favorites.db`dengan menekan `y`.
-   Anda akan melihat prompt yang berbeda karena kita sekarang berada di dalam program bernama `sqlite3`.
-   Kita bisa masuk `sqlite3`ke `csv`mode dengan mengetik `.mode csv`. Kemudian, kita dapat mengimpor data dari `csv`file kita dengan mengetik `.import favorites.csv favorites`. Sepertinya tidak ada yang terjadi!
-   Kita bisa mengetik `.schema`untuk melihat struktur database.
-   Anda dapat membaca item dari tabel menggunakan sintaks `SELECT columns FROM table`.
-   Misalnya, Anda dapat mengetik `SELECT * FROM favorites;`which akan mengulang setiap baris dalam `favorites`.
-   Anda bisa mendapatkan subset data menggunakan perintah `SELECT language FROM favorites;`.
-   SQL mendukung banyak perintah untuk mengakses data, termasuk:
    
    ```SQL
      AVG
      COUNT
      DISTINCT
      LOWER
      MAX
      MIN
      UPPER
    ```
    
-   Misalnya, Anda dapat mengetik `SELECT COUNT(language) FROM favorites;`. Selanjutnya, Anda dapat mengetik `SELECT DISTINCT(language) FROM favorites;`untuk mendapatkan daftar masing-masing bahasa di dalam database. Anda bahkan dapat mengetik `SELECT COUNT(DISTINCT(language)) FROM favorites;`untuk menghitungnya.
    
    ```
    # Searches database popularity of a problem
    
    import csv
    
    from cs50 import SQL
    
    # Open database
    db = SQL("sqlite:///favorites.db")
    
    # Prompt user for favorite
    favorite = input("Favorite: ")
    
    # Search for title
    rows = db.execute("SELECT COUNT(*) FROM favorites WHERE problem LIKE ?", "%" + favorite + "%")
    
    # Get first (and only) row
    row = rows[0]
    
    # Print popularity
    print(row["COUNT(*)"])
    ```
    
-   SQL menawarkan perintah tambahan yang dapat kami gunakan dalam kueri kami:
    
    ```
      WHERE       -- adding a Boolean expression to filter our data
      LIKE        -- filtering responses more loosely
      ORDER BY    -- ordering responses
      LIMIT       -- limiting the number of responses
      GROUP BY    -- grouping responses together
    ```
    
    Perhatikan bahwa kami menggunakan `--`untuk menulis komentar di SQL.
    
-   Sebagai contoh, kita dapat mengeksekusi `SELECT COUNT(*) FROM favorites WHERE language = 'C';`. Hitungan disajikan.
-   Selanjutnya, kita bisa mengetik `SELECT COUNT(*) FROM favorites WHERE language = 'C' AND problem = 'Mario';`. Perhatikan bagaimana `AND`digunakan untuk mempersempit hasil kami.
-   Demikian pula, kita bisa mengeksekusi `SELECT language, COUNT(*) FROM favorites GROUP BY language;`. Ini akan menawarkan tabel sementara yang akan menunjukkan bahasa dan hitungan.
-   Kami dapat memperbaikinya dengan mengetik `SELECT language, COUNT(*) FROM favorites GROUP BY language ORDER BY COUNT(*);`. Ini akan mengurutkan tabel yang dihasilkan oleh `count`.
-   Kita juga bisa `INSERT`memasukkan database SQL menggunakan form `INSERT INTO table (column...) VALUES(value, ...);`.
-   Kita bisa mengeksekusi `INSERT INTO favorites (language, problem) VALUES ('SQL', 'Fiftyville');`.
-   Kami juga dapat menggunakan `UPDATE`perintah untuk memperbarui data Anda.
-   Misalnya, Anda dapat mengeksekusi `UPDATE favorites SET language = 'C++' WHERE language = 'C';`. Ini akan mengakibatkan penimpaan semua pernyataan sebelumnya di mana C adalah bahasa pemrograman favorit.
-   Perhatikan bahwa kueri ini memiliki kekuatan yang sangat besar. Oleh karena itu, dalam pengaturan dunia nyata, Anda harus mempertimbangkan siapa yang memiliki izin untuk menjalankan perintah tertentu.
-   `DELETE`memungkinkan Anda untuk menghapus bagian dari data Anda. Misalnya, Anda bisa `DELETE FROM favorites WHERE problem = 'Tideman';`.

## [IMDb](https://cs50.harvard.edu/college/2022/fall/notes/7/#imdb)

-   IMDb menawarkan database orang, acara, penulis, mulai, genre, dan peringkat. Masing-masing tabel ini terkait satu sama lain sebagai berikut:
    
    ![enam kotak yang mewakili berbagai panah tabel sql ditarik ke masing-masing menunjukkan banyak hubungannya satu sama lain](https://cs50.harvard.edu/college/2022/fall/notes/7/cs50Week7Slide025.png "hubungan imdb")
    
-   Setelah mengunduh [`shows.db`](https://github.com/cs50/lectures/blob/2022/fall/7/src7/imdb/shows.db), Anda dapat mengeksekusi `sqlite3 shows.db`di jendela terminal Anda.
-   Setelah mengeksekusi, `.schema`Anda tidak hanya akan menemukan masing-masing tabel tetapi juga masing-masing bidang di dalam masing-masing bidang ini.
-   Seperti yang Anda lihat pada gambar di atas, `shows`memiliki `id`bidang. Tabel `genres`memiliki `show_id`bidang yang memiliki data yang sama antara itu dan tabel `shows`.
-   Seperti yang Anda lihat juga pada gambar di atas, `show_id`ada di semua tabel. Dalam `shows`tabel, itu hanya disebut `id`. Bidang umum di antara semua bidang ini disebut _kunci_ . Kunci utama digunakan untuk mengidentifikasi catatan unik dalam sebuah tabel. _Kunci asing_ digunakan untuk membangun hubungan antar tabel dengan menunjuk ke kunci utama di tabel lain.
-   Dengan menyimpan data dalam database relasional, seperti di atas, data dapat disimpan dengan lebih efisien.
-   Di _sqlite_ , kami memiliki lima tipe data, termasuk:
    
    ```
      BLOB       -- binary large objects that are groups of ones and zeros
      INTEGER    -- an integer
      NUMERIC    -- for numbers that are formatted specially like dates
      REAL       -- like a float
      TEXT       -- for strings and the like
    ```
    
-   Selain itu, kolom dapat diatur untuk menambahkan batasan khusus:
    
    ```
      NOT NULL
      UNIQUE
    ```
    
-   Untuk mengilustrasikan lebih lanjut hubungan antara tabel-tabel ini, kita dapat menjalankan perintah berikut: `SELECT * FROM people LIMIT 10;`. Memeriksa output, kita bisa mengeksekusi `SELECT * FROM shows LIMIT 10;`. Selanjutnya, kita bisa mengeksekusi `SELECT * FROM stars LIMIT 10;`. `show_id`adalah kunci asing dalam kueri terakhir ini karena `show_id`sesuai dengan bidang unik `id`di `shows`. `person_id`sesuai dengan bidang unik `id`di `people`kolom.
-   Kami selanjutnya dapat bermain dengan data ini untuk memahami hubungan ini. Jalankan `SELECT * FROM genres;`. Ada banyak genre!
-   Kami selanjutnya dapat membatasi data ini dengan mengeksekusi `SELECT * FROM genres WHERE genre = 'Comedy' LIMIT 10;`. Dari kueri ini, Anda dapat melihat bahwa ada 10 pertunjukan yang disajikan.
-   Anda dapat menemukan acara apa ini dengan mengeksekusi`SELECT * FROM shows WHERE id = 626124;`
-   Kami dapat melanjutkan kueri kami agar lebih efisien dengan mengeksekusi
    
    ```
    SELECT title
    FROM shows
    WHERE id IN (
        SELECT *
        FROM genres
        WHERE genre = 'Comedy'
    )
    LIMIT 10;
    ```
    
    Perhatikan bahwa kueri ini menyatukan dua kueri. Kueri dalam digunakan oleh kueri luar.
    
-   Kami dapat menyempurnakan lebih lanjut dengan mengeksekusi
    
    ```
    SELECT title
    FROM shows
    WHERE id IN (
        SELECT *
        FROM genres
        WHERE genre = 'Comedy'
    )
    ORDER BY title LIMIT 10;
    ```
    
-   Bagaimana jika Anda ingin menemukan semua pertunjukan yang dibintangi oleh Steve Carell? Anda bisa mengeksekusi `SELECT * FROM people WHERE name = 'Steve Carell';`Anda akan menemukan orangnya `id`. Anda dapat menggunakan ini `id`untuk menemukan banyak `shows`di mana dia muncul. Namun, ini akan membosankan untuk mencoba ini satu per satu. Bagaimana kami dapat melanjutkan pertanyaan kami untuk membuatnya lebih ramping? Pertimbangkan hal berikut:
    
    ```SQL
    SELECT title FROM shows WHERE id IN
      (SELECT show_id FROM stars WHERE person_id =
        (SELECT * FROM people WHERE name = 'Steve Carell'));
    ```
    
    Perhatikan bahwa kueri yang panjang ini akan menghasilkan hasil akhir yang berguna untuk menemukan jawaban atas pertanyaan kita.
    

## [`JOIN`](https://cs50.harvard.edu/college/2022/fall/notes/7/#joins)[S](https://cs50.harvard.edu/college/2022/fall/notes/7/#joins)

-   Pertimbangkan dua tabel berikut:
    
    ![dua kotak yang mewakili tabel acara dan genre dengan panah yang menghubungkan id dan id acara](https://cs50.harvard.edu/college/2022/fall/notes/7/cs50Week7Slide030.png "kunci primer dan kunci asing")
    
-   Bagaimana kita bisa menggabungkan tabel untuk sementara? Tabel dapat digabungkan menggunakan `JOIN`perintah.
-   Jalankan perintah berikut:
    
    ```
    SELECT * FROM shows
      JOIN ratings on shows.id = ratings.show_id
      WHERE title = 'The Office';
    ```
    
-   Sekarang Anda dapat melihat semua pertunjukan yang disebut _The Office_ .
-   Anda juga dapat menerapkan `JOIN`permintaan Steve Carell kami di atas dengan menjalankan yang berikut:
    
    ```
    SELECT title FROM people
      JOIN stars ON people.id = stars.person_id
      JOIN shows ON stars.show_id = shows.id
      WHERE name = `Steve Carell`;
    ```
    
    Perhatikan bagaimana setiap `JOIN`perintah memberi tahu kita kolom mana yang disejajarkan dengan kolom lainnya.
    
-   Ini dapat diimplementasikan dengan cara yang sama sebagai berikut:
    
    ```
    SELECT title FROM people, stars, shows
    WHERE people.id = stars.person_id
    AND stars.show_id = shows.id
    AND name = 'Steve Carell';
    ```
    
    Perhatikan bahwa ini mencapai hasil yang sama.
    
-   Operator wildcard `%`dapat digunakan untuk menemukan semua orang yang namanya dimulai dengan `Steve C`satu dapat menggunakan sintaks `SELECT * FROM people WHERE name LIKE 'Steve C%';`.

## [Indeks](https://cs50.harvard.edu/college/2022/fall/notes/7/#indexes)

-   Sementara database relasional memiliki kemampuan untuk menjadi lebih cepat dan lebih kuat daripada menggunakan `CSV`file, data dapat dioptimalkan dalam tabel menggunakan _indeks_ .
-   Indeks dapat digunakan untuk mempercepat permintaan kami.
-   Kami dapat melacak kecepatan kueri kami dengan mengeksekusi `.timer on`di `sqlite3`.
-   Untuk memahami bagaimana indeks dapat mempercepat kueri kami, jalankan perintah berikut: `SELECT * FROM shows WHERE title = 'The Office';`Perhatikan waktu yang ditampilkan setelah kueri dijalankan.
-   Kemudian, kita dapat membuat indeks dengan sintaks `CREATE INDEX title_index on shows (title);`. Ini memberi tahu `sqlite3`untuk membuat indeks dan melakukan beberapa pengoptimalan tersembunyi khusus yang berkaitan dengan kolom ini `title`.
-   Ini akan membuat struktur data yang disebut _B Tree_ , struktur data yang terlihat mirip dengan pohon biner. Namun, tidak seperti pohon biner, bisa ada lebih dari dua catatan anak.
    
    ![satu node di bagian atas yang berasal dari empat anak dan di bawahnya ada tiga anak yang berasal dari salah satu node dan dua dari yang lain dua dari yang lain dan tiga dari yang lain](https://cs50.harvard.edu/college/2022/fall/notes/7/cs50Week7Slide039.png "b pohon")
    
-   Menjalankan kueri `SELECT * FROM shows WHERE title = 'The Office';`, Anda akan melihat bahwa kueri berjalan lebih cepat!
-   Sayangnya, mengindeks semua kolom akan menghasilkan lebih banyak ruang penyimpanan. Oleh karena itu, ada tradeoff untuk peningkatan kecepatan.

## [Menggunakan SQL dengan Python](https://cs50.harvard.edu/college/2022/fall/notes/7/#using-sql-in-python)

-   Untuk membantu bekerja dengan SQL dalam kursus ini, Pustaka CS50 dapat digunakan sebagai berikut dalam kode Anda:
    
    ```
    from cs50 import SQL
    ```
    
-   Mirip dengan penggunaan Pustaka CS50 sebelumnya, pustaka ini akan membantu dengan langkah-langkah rumit dalam menggunakan SQL dalam kode Python Anda.
-   Anda dapat membaca selengkapnya tentang fungsionalitas SQL Perpustakaan CS50 di [dokumentasi](https://cs50.readthedocs.io/libraries/cs50/python/#cs50.SQL) .
-   Ingat di mana kita terakhir tinggalkan di `favorites.py`. Kode Anda akan muncul sebagai berikut:
    
    ```
    # Favorite problem instead of favorite language
    
    import csv
    
    # Open CSV file
    with open("favorites.csv", "r") as file:
    
        # Create DictReader
        reader = csv.DictReader(file)
    
        # Counts
        counts = {}
    
        # Iterate over CSV file, counting favorites
        for row in reader:
            favorite = row["problem"]
            if favorite in counts:
                counts[favorite] += 1
            else:
                counts[favorite] = 1
    
    # Print count
    favorite = input("Favorite: ")
    if favorite in counts:
        print(f"{favorite}: {counts[favorite]}")
    ```
    
-   Ubah kode Anda sebagai berikut:
    
    ```
    # Searches database popularity of a problem
    
    import csv
    
    from cs50 import SQL
    
    # Open database
    db = SQL("sqlite:///favorites.db")
    
    # Prompt user for favorite
    favorite = input("Favorite: ")
    
    # Search for title
    rows = db.execute("SELECT COUNT(*) FROM favorites WHERE problem LIKE ?", "%" + favorite + "%")
    
    # Get first (and only) row
    row = rows[0]
    
    # Print popularity
    print(row["COUNT(*)"])
    ```
    
    Perhatikan bahwa `db = SQL("sqlite:///favorites.db")`berikan Python lokasi file database. Kemudian, baris yang dimulai dengan `rows`menjalankan perintah SQL menggunakan `db.execute`. Memang, perintah ini meneruskan sintaks di dalam tanda kutip ke `db.execute`fungsi. Kami dapat mengeluarkan perintah SQL apa pun menggunakan sintaks ini. Selanjutnya, pemberitahuan yang `rows`dikembalikan sebagai daftar kamus. Dalam hal ini, hanya ada satu hasil, satu baris, dikembalikan ke daftar baris sebagai kamus.
    

## [Kondisi Ras](https://cs50.harvard.edu/college/2022/fall/notes/7/#race-conditions)

-   Pemanfaatan SQL terkadang dapat mengakibatkan beberapa masalah.
-   Anda dapat membayangkan kasus di mana banyak pengguna dapat mengakses database yang sama dan menjalankan perintah secara bersamaan.
-   Ini dapat mengakibatkan gangguan di mana kode terganggu oleh tindakan orang lain. Hal ini dapat mengakibatkan hilangnya data.
-   Fitur SQL bawaan seperti `BEGIN TRANSACTION`, `COMMIT`, dan `ROLLBACK`membantu menghindari beberapa masalah kondisi balapan ini.

## [Serangan Injeksi SQL](https://cs50.harvard.edu/college/2022/fall/notes/7/#sql-injection-attacks)

-   Sekarang, masih mempertimbangkan kode di atas, Anda mungkin bertanya-tanya apa `?`fungsi tanda tanya di atas. Salah satu masalah yang dapat muncul dalam aplikasi SQL dunia nyata adalah apa yang disebut _serangan injeksi_ . Serangan injeksi adalah saat aktor jahat dapat memasukkan kode SQL berbahaya.
-   Misalnya, pertimbangkan layar login sebagai berikut:
    
    ![layar masuk kunci harvard dengan bidang nama pengguna dan kata sandi](https://cs50.harvard.edu/college/2022/fall/notes/7/cs50Week7Slide051.png "layar masuk kunci harvard")
    
-   Tanpa perlindungan yang tepat dalam kode kita sendiri, aktor jahat dapat menjalankan kode berbahaya. Pertimbangkan hal berikut:
    
    ```
    rows = db.execute("SELECT COUNT(*) FROM favorites WHERE problem LIKE ?", "%" + favorite + "%")
    ```
    
    Perhatikan bahwa karena `?`sudah ada, validasi dapat dijalankan `favorite`sebelum diterima secara membabi buta oleh kueri.
    
-   Anda tidak pernah ingin menggunakan string yang diformat dalam kueri seperti di atas atau memercayai input pengguna secara membabi buta.
-   Memanfaatkan Perpustakaan CS50, perpustakaan akan _membersihkan_ dan menghapus karakter yang berpotensi berbahaya.

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/7/#summing-up)

Dalam pelajaran ini, Anda mempelajari lebih banyak sintaks yang terkait dengan Python. Selanjutnya, Anda belajar bagaimana mengintegrasikan pengetahuan ini dengan data dalam bentuk flat-file dan database relasional. Akhirnya, Anda belajar tentang _SQL_ . Secara khusus, kami membahas…

-   Database file datar
-   Database relasional
-   SQL
-   `JOIN`S
-   Indeks
-   Menggunakan SQL dengan Python
-   Kondisi balapan
-   serangan injeksi SQL

Sampai jumpa lain waktu!
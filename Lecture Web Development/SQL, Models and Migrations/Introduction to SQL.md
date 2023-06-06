# [Kuliah 4](https://cs50.harvard.edu/web/2020/notes/4/#lecture-4)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/4/#introduction)
-   [SQL](https://cs50.harvard.edu/web/2020/notes/4/#sql)
    -   [Database](https://cs50.harvard.edu/web/2020/notes/4/#databases)
    -   [Jenis Kolom](https://cs50.harvard.edu/web/2020/notes/4/#column-types)
-   [Tabel](https://cs50.harvard.edu/web/2020/notes/4/#tables)
-   [PILIH](https://cs50.harvard.edu/web/2020/notes/4/#select)
    -   [Bekerja dengan SQL di Terminal](https://cs50.harvard.edu/web/2020/notes/4/#working-with-sql-in-the-terminal)
    -   [Fungsi](https://cs50.harvard.edu/web/2020/notes/4/#functions)
    -   [MEMPERBARUI](https://cs50.harvard.edu/web/2020/notes/4/#update)
    -   [MENGHAPUS](https://cs50.harvard.edu/web/2020/notes/4/#delete)
    -   [Klausul lainnya](https://cs50.harvard.edu/web/2020/notes/4/#other-clauses)
-   [Menggabungkan Tabel](https://cs50.harvard.edu/web/2020/notes/4/#joining-tables)
    -   [GABUNG Kueri](https://cs50.harvard.edu/web/2020/notes/4/#join-query)
    -   [Pengindeksan](https://cs50.harvard.edu/web/2020/notes/4/#indexing)
    -   [Kerentanan SQL](https://cs50.harvard.edu/web/2020/notes/4/#sql-vulnerabilities)
-   [Model Django](https://cs50.harvard.edu/web/2020/notes/4/#django-models)
-   [Migrasi](https://cs50.harvard.edu/web/2020/notes/4/#migrations)
-   [Kerang](https://cs50.harvard.edu/web/2020/notes/4/#shell)
    -   [Memulai aplikasi kita](https://cs50.harvard.edu/web/2020/notes/4/#starting-our-application)
-   [Admin Django](https://cs50.harvard.edu/web/2020/notes/4/#django-admin)
-   [Relasi Banyak ke Banyak](https://cs50.harvard.edu/web/2020/notes/4/#many-to-many-relationships)
-   [Pengguna](https://cs50.harvard.edu/web/2020/notes/4/#users)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/4/#introduction)

-   Sejauh ini, kita telah membahas cara membuat halaman web sederhana menggunakan HTML dan CSS, serta cara menggunakan Git dan GitHub untuk melacak perubahan pada kode kita dan berkolaborasi dengan orang lain. Kami juga membiasakan diri dengan bahasa pemrograman Python, dan mulai menggunakan Django untuk membuat aplikasi web.
-   Hari ini, kita akan belajar tentang penggunaan model SQL dan Django untuk menyimpan dan mengakses data secara efisien.

## [SQL](https://cs50.harvard.edu/web/2020/notes/4/#sql)

[SQL](https://www.w3schools.com/sql/) , atau Structured Query Language, adalah bahasa pemrograman yang memungkinkan kita memperbarui dan membuat kueri basis data.

![Logo SQL](https://cs50.harvard.edu/web/2020/notes/4/images/sql.png)

### [Database](https://cs50.harvard.edu/web/2020/notes/4/#databases)

Sebelum kita masuk ke cara menggunakan bahasa SQL, kita harus membahas bagaimana data kita disimpan. Saat menggunakan SQL, kami akan bekerja dengan [basis data relasional](https://www.oracle.com/database/what-is-a-relational-database/#:~:text=A%20relational%20database%20is%20a,of%20representing%20data%20in%20tables.) tempat kami dapat menemukan semua data kami disimpan dalam sejumlah [tabel](https://www.essentialsql.com/what-is-a-database-table/) . Masing-masing tabel ini terdiri dari sejumlah kolom dan sejumlah baris yang fleksibel.

Untuk mengilustrasikan cara bekerja dengan SQL, kami akan menggunakan contoh situs web untuk maskapai penerbangan yang digunakan untuk memantau penerbangan dan penumpang. Pada tabel berikut, kita melihat bahwa kita melacak sejumlah penerbangan, yang masing-masing memiliki `origin`, a `destination`, dan a `duration`.

![Penerbangan 0](https://cs50.harvard.edu/web/2020/notes/4/images/flights0.png)

Ada beberapa sistem manajemen basis data relasional berbeda yang biasanya digunakan untuk menyimpan informasi, dan dapat dengan mudah berinteraksi dengan perintah SQL:

-   [MySQL](https://www.mysql.com/)
-   [PostgreSQL](https://www.postgresql.org/)
-   [SQLite](https://www.sqlite.org/index.html)
-   …

Dua yang pertama, MySQL dan PostgreSQL, adalah sistem manajemen basis data tugas berat yang biasanya dijalankan di server terpisah dari server yang menjalankan situs web. SQLite, di sisi lain, adalah sistem yang lebih ringan yang dapat menyimpan semua datanya dalam satu file. Kami akan menggunakan SQLite selama kursus ini, karena ini adalah sistem default yang digunakan oleh Django.

### [Jenis Kolom](https://cs50.harvard.edu/web/2020/notes/4/#column-types)

Sama seperti kami bekerja dengan beberapa tipe variabel berbeda di Python, SQLite memiliki [tipe](https://www.sqlite.org/datatype3.html) yang mewakili berbagai bentuk informasi. Sistem manajemen lain mungkin memiliki tipe data yang berbeda, tetapi semuanya cukup mirip dengan SQLite:

-   `TEXT`: Untuk rangkaian teks (mis. nama seseorang)
-   `NUMERIC`: Bentuk data numerik yang lebih umum (Mis. Tanggal atau nilai boolean)
-   `INTEGER`: Angka non-desimal apa pun (Mis. usia seseorang)
-   `REAL`: Bilangan riil apa pun (Misalnya, berat seseorang)
-   `BLOB`(Binary Large Object): Data biner lain yang mungkin ingin kita simpan di database kita (Mis. gambar)

## [Tabel](https://cs50.harvard.edu/web/2020/notes/4/#tables)

Sekarang, untuk benar-benar mulai menggunakan SQL untuk berinteraksi dengan database, mari kita mulai dengan membuat tabel baru. Perintah [untuk membuat tabel baru](https://www.w3schools.com/sql/sql_create_table.asp) terlihat seperti ini:

```
CREATE TABLE flights(
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    origin TEXT NOT NULL,
    destination TEXT NOT NULL,
    duration INTEGER NOT NULL
);
```

Dalam perintah di atas, kami membuat tabel baru yang telah kami putuskan untuk dipanggil `flights`, dan kami telah menambahkan empat kolom ke tabel ini:

1.  `id`: Seringkali berguna untuk memiliki nomor yang memungkinkan kita mengidentifikasi secara unik setiap baris dalam tabel. Di sini kami telah menentukan bahwa `id`adalah bilangan bulat, dan juga itu adalah [kunci utama](https://www.w3schools.com/sql/sql_primarykey.ASP) kami , yang berarti itu adalah pengidentifikasi unik kami. Kami juga telah menentukan bahwa itu akan `AUTOINCREMENT`, yang berarti kami tidak perlu memberikan id setiap kali kami menambahkan ke tabel karena akan dilakukan secara otomatis.
2.  `origin`: Di sini kami telah menetapkan bahwa ini akan menjadi bidang teks, dan dengan menulis `NOT NULL`kami telah meminta agar memiliki nilai.
3.  `destination`: Sekali lagi kami telah menetapkan bahwa ini akan menjadi bidang teks dan mencegahnya menjadi nol.
4.  `duration`: Sekali lagi nilai ini tidak boleh nol, tetapi kali ini diwakili oleh bilangan bulat, bukan sebagai teks.

Kita baru saja melihat batasan `NOT NULL`and `PRIMARY KEY`saat membuat kolom, tetapi ada beberapa [batasan](https://www.tutorialspoint.com/sqlite/sqlite_constraints.htm) lain yang tersedia bagi kita:

-   `CHECK`: Memastikan batasan tertentu terpenuhi sebelum mengizinkan baris ditambahkan/dimodifikasi
-   `DEFAULT`: Memberikan nilai default jika tidak ada nilai yang diberikan
-   `NOT NULL`: Memastikan nilai diberikan
-   `PRIMARY KEY`: Menunjukkan ini adalah cara utama mencari baris dalam database
-   `UNIQUE`: Memastikan tidak ada dua baris yang memiliki nilai yang sama di kolom tersebut.
-   …

Sekarang setelah kita melihat cara membuat tabel, mari kita lihat cara menambahkan baris ke dalamnya. Dalam SQL, kami melakukan ini menggunakan `INSERT`perintah:

```
INSERT INTO flights
    (origin, destination, duration)
    VALUES ("New York", "London", 415);
```

Pada perintah di atas, kami telah menentukan nama tabel yang ingin kami masukkan, kemudian memberikan daftar nama kolom yang akan kami berikan informasinya, dan kemudian menentukan baris yang ingin kami `VALUES`isi dalam tabel, memastikan datang `VALUES`dalam urutan yang sama dengan daftar kolom kami yang sesuai. Perhatikan bahwa kita tidak perlu memberikan nilai untuk `id`karena secara otomatis bertambah.

## [PILIH](https://cs50.harvard.edu/web/2020/notes/4/#select)

Setelah tabel diisi dengan beberapa baris, kita mungkin menginginkan cara untuk mengakses data di dalam tabel itu. Kami melakukan ini menggunakan kueri [SELECT](https://www.w3schools.com/sql/sql_select.asp) SQL . Kueri paling sederhana `SELECT`ke dalam tabel penerbangan kami mungkin terlihat seperti ini:

```
SELECT * FROM flights;
```

Perintah di atas (*) mengambil semua data dari tabel penerbangan kami

![semua](https://cs50.harvard.edu/web/2020/notes/4/images/all.png)

Mungkin saja kita tidak benar-benar membutuhkan semua kolom dari database, hanya asal dan tujuan. Untuk mengakses kolom ini saja, kita dapat mengganti * dengan nama kolom yang ingin kita akses. Kueri berikut mengembalikan semua asal dan tujuan.

```
SELECT origin, destination FROM flights;
```

![Hanya dua col](https://cs50.harvard.edu/web/2020/notes/4/images/flights1.png)

Saat tabel kita semakin besar dan semakin besar, kita juga ingin mempersempit baris mana yang dikembalikan kueri kita. Kami melakukan ini dengan menambahkan [WHERE](https://www.w3schools.com/sql/sql_where.asp) diikuti dengan beberapa kondisi. Misalnya, perintah berikut hanya memilih baris dengan `id`dari `3`:

```
SELECT * FROM flights WHERE id = 3;
```

![hanya satu baris](https://cs50.harvard.edu/web/2020/notes/4/images/where0.png)

e dapat memfilter berdasarkan kolom mana pun, bukan hanya `id`!

```
SELECT * FROM flights WHERE origin = "New York";
```

![Asalnya adalah New York](https://cs50.harvard.edu/web/2020/notes/4/images/where1.png)

### [Bekerja dengan SQL di Terminal](https://cs50.harvard.edu/web/2020/notes/4/#working-with-sql-in-the-terminal)

Now that we know some basic SQL commands, let’s test them out in the terminal! In order to work with SQLite on your computer, you must first [download SQLite](https://www.sqlite.org/download.html). (We won’t use it in lecture, but you can also [download DB Browser](https://sqlitebrowser.org/dl/) for a more user-friendly way to run SQL queries.)

We can start by creating a file for our database either by manually creating a new file, or running `touch flights.sql` in the terminal. Now, if we run `sqlite3 flights.sql` in the terminal, we’ll be brought to a SQLite prompt where we can run SQL commands:

```

# Entering into the SQLite Prompt
(base) % sqlite3 flights.sql
SQLite version 3.26.0 2018-12-01 12:34:55
Enter ".help" for usage hints.

# Creating a new Table
sqlite> CREATE TABLE flights(
   ...>     id INTEGER PRIMARY KEY AUTOINCREMENT,
   ...>     origin TEXT NOT NULL,
   ...>     destination TEXT NOT NULL,
   ...>     duration INTEGER NOT NULL
   ...> );

# Listing all current tables (Just flights for now)
sqlite> .tables
flights

# Querying for everything within flights (Which is now empty)
sqlite> SELECT * FROM flights;

# Adding one flight
sqlite> INSERT INTO flights
   ...>     (origin, destination, duration)
   ...>     VALUES ("New York", "London", 415);

# Checking for new information, which we can now see
sqlite> SELECT * FROM flights;
1|New York|London|415

# Adding some more flights
sqlite> INSERT INTO flights (origin, destination, duration) VALUES ("Shanghai", "Paris", 760);
sqlite> INSERT INTO flights (origin, destination, duration) VALUES ("Istanbul", "Tokyo", 700);
sqlite> INSERT INTO flights (origin, destination, duration) VALUES ("New York", "Paris", 435);
sqlite> INSERT INTO flights (origin, destination, duration) VALUES ("Moscow", "Paris", 245);
sqlite> INSERT INTO flights (origin, destination, duration) VALUES ("Lima", "New York", 455);

# Querying this new information
sqlite> SELECT * FROM flights;
1|New York|London|415
2|Shanghai|Paris|760
3|Istanbul|Tokyo|700
4|New York|Paris|435
5|Moscow|Paris|245
6|Lima|New York|455

# Changing the settings to make output more readable
sqlite> .mode columns
sqlite> .headers yes

# Querying all information again
sqlite> SELECT * FROM flights;
id          origin      destination  duration
----------  ----------  -----------  ----------
1           New York    London       415
2           Shanghai    Paris        760
3           Istanbul    Tokyo        700
4           New York    Paris        435
5           Moscow      Paris        245
6           Lima        New York     455

# Searching for just those flights originating in New York
sqlite> SELECT * FROM flights WHERE origin = "New York";
id          origin      destination  duration
----------  ----------  -----------  ----------
1           New York    London       415
4           New York    Paris        435
```

We can also use more than just equality to filter out our flights. For integer and real values, we can use greater than or less than:

```
SELECT * FROM flights WHERE duration > 500;
```

![> 500](https://cs50.harvard.edu/web/2020/notes/4/images/500.png)

And we can also use other logic ([AND, OR](https://www.w3schools.com/sql/sql_and_or.asp)) like in Python:

```
SELECT * FROM flights WHERE duration > 500 AND destination = "Paris";
```

![> 500 dan paris](https://cs50.harvard.edu/web/2020/notes/4/images/500andparis.png)

```
SELECT * FROM flights WHERE duration > 500 OR destination = "Paris";
```

![> 500 atau paris](https://cs50.harvard.edu/web/2020/notes/4/images/500orparis.png)

Kami juga dapat menggunakan kata kunci [IN](https://www.w3schools.com/sql/sql_in.asp) untuk melihat apakah sedikit data adalah salah satu dari beberapa opsi:

```
SELECT * FROM flights WHERE origin IN ("New York", "Lima");
```

![di dalam](https://cs50.harvard.edu/web/2020/notes/4/images/in.png)

Kami bahkan dapat menggunakan ekspresi reguler untuk mencari kata secara lebih luas menggunakan kata kunci [LIKE](https://www.w3schools.com/sql/sql_like.asp) . Kueri di bawah menemukan semua hasil dengan `a`asal, dengan menggunakan `%`sebagai karakter wildcard.

```
SELECT * FROM flights WHERE origin LIKE "%a%";
```

![Asal memiliki 'a'](https://cs50.harvard.edu/web/2020/notes/4/images/like.png)

### [Fungsi](https://cs50.harvard.edu/web/2020/notes/4/#functions)

Ada juga sejumlah fungsi SQL yang bisa kita terapkan pada hasil kueri. Ini bisa berguna jika kita tidak memerlukan semua data yang dikembalikan oleh kueri, tetapi hanya beberapa ringkasan statistik data.

-   [RATA-RATA](https://www.w3schools.com/sql/sql_count_avg_sum.asp)
-   [MENGHITUNG](https://www.w3schools.com/sql/sql_count_avg_sum.asp)
-   [MAKS](https://www.w3schools.com/sql/sql_min_max.asp)
-   [MIN](https://www.w3schools.com/sql/sql_min_max.asp)
-   [JUMLAH](https://www.w3schools.com/sql/sql_count_avg_sum.asp)
-   …

### [MEMPERBARUI](https://cs50.harvard.edu/web/2020/notes/4/#update)

Kami sekarang telah melihat bagaimana menambahkan dan mencari tabel, tetapi kami mungkin juga ingin memperbarui baris tabel yang sudah ada. Kami melakukan ini menggunakan perintah [UPDATE](https://www.w3schools.com/sql/sql_update.asp) seperti yang ditunjukkan di bawah ini. Seperti yang mungkin sudah Anda duga dengan membaca ini dengan lantang, perintah menemukan penerbangan apa pun yang berangkat dari New York ke London, dan kemudian menetapkan durasinya menjadi 430.

```
UPDATE flights
    SET duration = 430
    WHERE origin = "New York"
    AND destination = "London";
```

### [MENGHAPUS](https://cs50.harvard.edu/web/2020/notes/4/#delete)

Kami juga mungkin menginginkan kemampuan untuk menghapus baris dari database kami, dan kami dapat melakukannya dengan menggunakan perintah [DELETE](https://www.w3schools.com/sql/sql_delete.asp) . Kode berikut akan menghapus semua penerbangan yang mendarat di Tokyo:

```
DELETE FROM flights WHERE destination = "Tokyo";
```

### [Klausul lainnya](https://cs50.harvard.edu/web/2020/notes/4/#other-clauses)

Ada sejumlah klausa tambahan yang dapat kita gunakan untuk mengontrol kueri yang kembali kepada kita

-   [LIMIT](https://www.w3schools.com/sql/sql_top.asp) : Membatasi jumlah hasil yang dikembalikan oleh kueri
-   [ORDER BY](https://www.w3schools.com/sql/sql_orderby.asp) : Mengurutkan hasil berdasarkan kolom yang ditentukan
-   [GROUP BY](https://www.w3schools.com/sql/sql_groupby.asp): Groups results by a specified column
-   [HAVING](https://www.w3schools.com/sql/sql_having.asp): Allows for additional constraints based on the number of results

## [Joining Tables](https://cs50.harvard.edu/web/2020/notes/4/#joining-tables)

So far, we’ve only been working with one table at a time, but many databases in practice are populated by a number of tables that all relate to each other in some way. In our flights example, let’s imagine we also want to add an airport code to go with the city. The way our table is currently set up, we would have to add two more columns to go with each row. We would also be repeating information, as we would have to write in multiple places that city X is associated with code Y.

One way we can solve this problem is by deciding to have one table that keeps track of flights, and then another table keeping track of airports. The second table might look something like this

![Meja Bandara](https://cs50.harvard.edu/web/2020/notes/4/images/airports.png)

Now we have a table relating codes and cities, rather than storing an entire city name in our flights table, it will save storage space if we’re able to just save the `id` of that airport. Therefore, we should rewrite the flights table accordingly. Since we’re using the `id` column of the airports table to populate `origin_id` and `destination_id`, we call those values [Foreign Keys](https://www.w3schools.com/sql/sql_foreignkey.asp)

![Penerbangan Baru](https://cs50.harvard.edu/web/2020/notes/4/images/flights2.png)

In addition to flights and airports, an airline might also want to store data about its passengers, like which flight each passenger will be on. Using the power of relational databases, we can add another table that stores first and last names, and a foreign key representing the flight they are on

![Meja Penumpang Sederhana](https://cs50.harvard.edu/web/2020/notes/4/images/simple_pass.png)

We can do even better than this though, as the same person may be on more than one flight. To account for this, we can create a `people` table that stores first and last names, and a `passengers` table that pairs people with flights

![Rakyat](https://cs50.harvard.edu/web/2020/notes/4/images/people.png)

![Penumpang](https://cs50.harvard.edu/web/2020/notes/4/images/passengers.png)

ecause in this case a single person can be on many flights and a single flight can have many people, we call the relationship between `flights` and `people` a **Many to Many** relationship. The `passengers` table that connects the two is known as an **association table**.

### [JOIN Query](https://cs50.harvard.edu/web/2020/notes/4/#join-query)

Although our data is now more efficiently stored, it seems like it may be harder to query our data. Thankfully, SQL has a [JOIN](https://www.w3schools.com/sql/sql_join.asp) query where we can combine two tables for the purposes of another query.

For example, let’s say we want to find the origin, destination, and first name of every trip a passenger is taking. Also for simplicity in this table, we’re going to be using the unoptimized `passengers` table that includes the flight id, first name, and last name. The first part of this query looks fairly familiar:

```
SELECT first, origin, destination
FROM ...
```

But we run into a problem here because `first` is stored in the `passengers` table, while `origin` and `destination` are stored in the `flights` table. We solve this by joining the two tables using the fact that `flight_id` in the `passengers` table corresponds to `id` in the `flights` table:

```
SELECT first, origin, destination
FROM flights JOIN passengers
ON passengers.flight_id = flights.id;
```

![Bergabung dengan buram](https://cs50.harvard.edu/web/2020/notes/4/images/join.png)

We’ve just used something called an [INNER JOIN](https://www.w3schools.com/sql/sql_join_inner.asp), which means we are ignoring rows that have no matches between the tables, but there are other types of joins, including [**LEFT JOIN**s](https://www.w3schools.com/sql/sql_join_left.asp), [**RIGHT JOIN**s](https://www.w3schools.com/sql/sql_join_right.asp), and [**FULL OUTER JOIN**s](https://www.w3schools.com/sql/sql_join_full.asp), which we won’t discuss here in detail.

### [Indexing](https://cs50.harvard.edu/web/2020/notes/4/#indexing)

One way we can make our queries more efficient when dealing with large tables is to create an index similar to the index you might see in the back of a textbook. For example, if we know that we’ll often look up passengers by their last name, we could create an index from last name to id using the command:

```
CREATE INDEX name_index ON passengers (last);
```

### [SQL Vulnerabilities](https://cs50.harvard.edu/web/2020/notes/4/#sql-vulnerabilities)

Now that we know the basics of using SQL to work with data, it’s important to point out the main vulnerabilities associated with using SQL. We’ll start with [SQL Injection](https://www.w3schools.com/sql/sql_injection.asp).

A SQL injection attack is when a malicious user enters SQL code as input on a site in order to bypass the sites security measures. For example, let’s say we have a table storing usernames and passwords, and then a login form on the home site of a page. We may search for the user using a query such as:

```
SELECT * FROM users
WHERE username = username AND password = password;
```

A user named Harry might go to this site and type `harry` as a username and `12345` as a password, in which case the query would look like this:

```
SELECT * FROM users
WHERE username = "harry" AND password = "12345";
```

Seorang hacker, di sisi lain, mungkin mengetik `harry" --`sebagai nama pengguna dan bukan kata sandi. Ternyata itu `--`singkatan dari komentar di SQL, artinya kueri akan terlihat seperti:

```
SELECT * FROM users
WHERE username = "harry"--" AND password = "12345";
```

Karena dalam kueri ini pemeriksaan kata sandi telah dikomentari, peretas dapat masuk ke akun Harry tanpa mengetahui kata sandinya. Untuk mengatasi masalah ini, kita dapat menggunakan:

-   Keluarkan karakter untuk memastikan SQL memperlakukan input sebagai teks biasa dan bukan sebagai kode SQL.
-   Lapisan abstraksi di atas SQL yang menyertakan urutan pelariannya sendiri, jadi kita tidak perlu menulis kueri SQL sendiri.

Kerentanan utama lainnya dalam hal SQL dikenal sebagai [Race Condition](https://searchstorage.techtarget.com/definition/race-condition#:~:text=A%20race%20condition%20is%20an,sequence%20to%20be%20done%20correctly.) .

Kondisi balapan adalah situasi yang terjadi ketika beberapa kueri ke database terjadi secara bersamaan. Ketika ini tidak ditangani secara memadai, masalah dapat muncul pada waktu yang tepat ketika database diperbarui. Misalnya, katakanlah saya memiliki $150 di rekening bank saya. Kondisi balapan dapat terjadi jika saya masuk ke rekening bank saya di ponsel dan laptop saya, dan mencoba menarik $100 di setiap perangkat. Jika pengembang perangkat lunak bank tidak menangani kondisi balapan dengan benar, maka saya mungkin dapat menarik $200 dari akun yang hanya berisi $150. Salah satu solusi potensial untuk masalah ini adalah mengunci database. Kami tidak dapat mengizinkan interaksi lain dengan database hingga satu transaksi selesai. Dalam contoh bank, setelah mengklik navigasi ke halaman "Lakukan Penarikan" di komputer saya,

## [Model Django](https://cs50.harvard.edu/web/2020/notes/4/#django-models)

[Model Django](https://docs.djangoproject.com/en/4.0/topics/db/models/) adalah tingkat [abstraksi](https://techterms.com/definition/abstraction) di atas SQL yang memungkinkan kita bekerja dengan basis data menggunakan kelas dan objek Python daripada kueri SQL langsung.

Mari mulai menggunakan model dengan membuat proyek django untuk maskapai kita, dan membuat aplikasi di dalam proyek itu.

```
django-admin startproject airline
cd airline
python manage.py startapp flights
```

Sekarang kita harus melalui proses penambahan aplikasi seperti biasa:

1.  Tambahkan `flights`ke `INSTALLED_APPS`daftar di`settings.py`
2.  Tambahkan rute untuk `flights`di `urls.py`:
    
    ```
     path("flights/", include("flights.urls")),
    ```
    
3.  Buat `urls.py`file di dalam `flights`aplikasi. Dan isi dengan `urls.py`impor dan daftar standar.

Sekarang, daripada membuat jalur aktual dan memulai `views.py`, kami akan membuat beberapa model di `models.py`file. Dalam file ini, kami akan menguraikan data apa yang ingin kami simpan di aplikasi kami. Kemudian, Django akan menentukan sintaks SQL yang diperlukan untuk menyimpan informasi pada setiap model kita. Mari kita lihat seperti apa model untuk satu penerbangan:

```
class Flight(models.Model):
    origin = models.CharField(max_length=64)
    destination = models.CharField(max_length=64)
    duration = models.IntegerField()
```

Mari kita lihat apa yang terjadi dalam definisi model ini:

-   Di baris pertama, kami membuat model baru yang **memperluas** kelas model Django.
-   Di bawah ini, kami menambahkan bidang asal, tujuan, dan durasi. Dua yang pertama adalah [Char Fields](https://docs.djangoproject.com/en/4.0/ref/forms/fields/#charfield) , artinya mereka menyimpan string, dan yang ketiga adalah [Integer Field](https://docs.djangoproject.com/en/4.0/ref/forms/fields/#integerfield) . Ini hanya dua dari banyak [kelas bawaan Django Field](https://docs.djangoproject.com/en/4.0/ref/forms/fields/#built-in-field-classes)
-   Kami menentukan panjang maksimal 64 untuk dua Bidang Karakter. Anda dapat memeriksa spesifikasi yang tersedia untuk bidang tertentu dengan memeriksa [dokumentasi](https://docs.djangoproject.com/en/4.0/ref/forms/fields/#built-in-field-classes) .

## [Migrasi](https://cs50.harvard.edu/web/2020/notes/4/#migrations)

Sekarang, meskipun kami telah membuat model, kami belum memiliki database untuk menyimpan informasi ini. untuk membuat database dari model kami, kami menavigasi ke direktori utama proyek kami dan menjalankan perintah.

```
python manage.py makemigrations
```

Perintah ini membuat beberapa file Python yang akan membuat atau mengedit database kita agar dapat menyimpan apa yang kita miliki di model kita. Anda harus mendapatkan output yang terlihat seperti di bawah ini, dan jika Anda menavigasi ke `migrations`direktori Anda, Anda akan melihat file baru telah dibuat untuk kami

![keluaran migrasi 0](https://cs50.harvard.edu/web/2020/notes/4/images/migration0.png)

Selanjutnya, untuk menerapkan migrasi ini ke database kami, kami menjalankan perintah

```
python manage.py migrate
```

Sekarang, Anda akan melihat beberapa migrasi default telah diterapkan bersama milik kami, dan Anda juga akan melihat bahwa kami sekarang memiliki file yang dipanggil `db.sqlite3`di direktori proyek kami

![migrasi keluaran](https://cs50.harvard.edu/web/2020/notes/4/images/migration1.png)

## [Kerang](https://cs50.harvard.edu/web/2020/notes/4/#shell)

Sekarang, untuk mulai bekerja menambahkan informasi ke dan memanipulasi database ini, kita bisa masuk ke shell Django dimana kita bisa menjalankan perintah Python di dalam proyek kita.

```
python manage.py shell
Python 3.7.2 (default, Dec 29 2018, 00:00:04)
Type 'copyright', 'credits' or 'license' for more information
IPython 6.5.0 -- An enhanced Interactive Python. Type '?' for help.
```

```
# Import our flight model
In [1]: from flights.models import Flight

# Create a new flight
In [2]: f = Flight(origin="New York", destination="London", duration=415)

# Instert that flight into our database
In [3]: f.save()

# Query for all flights stored in the database
In [4]: Flight.objects.all()
Out[4]: <QuerySet [<Flight: Flight object (1)>]>
```

Saat kami menanyakan basis data kami, kami melihat bahwa kami hanya mendapatkan satu penerbangan yang dipanggil `Flight object (1)`. Ini bukan nama yang sangat informatif, tetapi kami dapat memperbaikinya. Di dalam `models.py`, kita akan mendefinisikan sebuah `__str__`fungsi yang menyediakan instruksi bagaimana mengubah objek Flight menjadi sebuah string:

```
class Flight(models.Model):
    origin = models.CharField(max_length=64)
    destination = models.CharField(max_length=64)
    duration = models.IntegerField()

    def __str__(self):
        return f"{self.id}: {self.origin} to {self.destination}"
```

Sekarang, ketika kita kembali ke shell, keluaran kita sedikit lebih mudah dibaca:

```
# Create a variable called flights to store the results of a query
In [7]: flights = Flight.objects.all()

# Displaying all flights
In [8]: flights
Out[8]: <QuerySet [<Flight: 1: New York to London>]>

# Isolating just the first flight
In [9]: flight = flights.first()

# Printing flight information
In [10]: flight
Out[10]: <Flight: 1: New York to London>

# Display flight id
In [11]: flight.id
Out[11]: 1

# Display flight origin
In [12]: flight.origin
Out[12]: 'New York'

# Display flight destination
In [13]: flight.destination
Out[13]: 'London'

# Display flight duration
In [14]: flight.duration
Out[14]: 415
```

This is a good start, but thinking back to earlier, we don’t want to have to store the city name as an origin and destination for every flight, so we probably want another model for an airport that is somehow related to the flight model:

```
class Airport(models.Model):
    code = models.CharField(max_length=3)
    city = models.CharField(max_length=64)

    def __str__(self):
        return f"{self.city} ({self.code})"

class Flight(models.Model):
    origin = models.ForeignKey(Airport, on_delete=models.CASCADE, related_name="departures")
    destination = models.ForeignKey(Airport, on_delete=models.CASCADE, related_name="arrivals")
    duration = models.IntegerField()

    def __str__(self):
        return f"{self.id}: {self.origin} to {self.destination}"
```

We’ve seen everything in our new `Airport` class before, but the changes to the `origin` and `destination` fields within the `Flight` class are new to us:

-   We specify that the `origin` and `destination` fields are each [Foreign Keys](https://docs.djangoproject.com/en/4.0/topics/db/examples/many_to_one/), which means they refer to another object.
-   By entering `Airport` as our first argument, we are specifying the type of object this field refers to.
-   The next argument, `on_delete=models.CASCADE` gives instructions for what should happen if an airport is deleted. In this case, we specify that when an airport is deleted, all flights associated with it should also be deleted. There are [several other options](https://docs.djangoproject.com/en/4.0/ref/models/fields/#django.db.models.ForeignKey.on_delete) in addition to `CASCADE`.
-   We provide a [related name](https://docs.djangoproject.com/en/4.0/ref/models/fields/#django.db.models.ForeignKey.related_name), which gives us a way to search for all flights with a given airport as their origin or destination.

Every time we make changes in `models.py`, we have to make migrations and then migrate. Note that you may have to delete your existing flight from New York to London, as it doesn’t fit in with the new database structure.

```
# Create New Migrations
python manage.py makemigration

# Migrate
python manage.py migrate
```

Now, let’s try these new models out in the Django shell:

```
# Import all models
In [1]: from flights.models import *

# Create some new airports
In [2]: jfk = Airport(code="JFK", city="New York")
In [4]: lhr = Airport(code="LHR", city="London")
In [6]: cdg = Airport(code="CDG", city="Paris")
In [9]: nrt = Airport(code="NRT", city="Tokyo")

# Save the airports to the database
In [3]: jfk.save()
In [5]: lhr.save()
In [8]: cdg.save()
In [10]: nrt.save()

# Add a flight and save it to the database
f = Flight(origin=jfk, destination=lhr, duration=414)
f.save()

# Display some info about the flight
In [14]: f
Out[14]: <Flight: 1: New York (JFK) to London (LHR)>
In [15]: f.origin
Out[15]: <Airport: New York (JFK)>

# Using the related name to query by airport of arrival:
In [17]: lhr.arrivals.all()
Out[17]: <QuerySet [<Flight: 1: New York (JFK) to London (LHR)>]>
```

### [Starting our application](https://cs50.harvard.edu/web/2020/notes/4/#starting-our-application)

We can now begin to build an application around this process of using models to interact with a database. Let’s begin by creating an index route for our airline. Inside `urls.py`:

```
urlpatterns = [
    path('', views.index, name="index"),
]
```

Inside `views.py`:

```
from django.shortcuts import render
from .models import Flight, Airport

# Create your views here.

def index(request):
    return render(request, "flights/index.html", {
        "flights": Flight.objects.all()
    })
```

Inside our new `layout.html` file:

```

<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Flights</title>
    </head>
    <body>
        {% block body %}
        {% endblock %}
    </body>
</html>

```

Inside a new `index.html` file:

```

{% extends "flights/layout.html" %}

{% block body %}
    <h1>Flights:</h1>
    <ul>
        {% for flight in flights %}
            <li>Flight {{ flight.id }}: {{ flight.origin }} to {{ flight.destination }}</li>
        {% endfor %}
    </ul>
{% endblock %}

```

What we’ve done here is created a default page where we have a list of all flights we’ve created so far. When we open up the page now, it looks like this

![Hanya satu dalam daftar](https://cs50.harvard.edu/web/2020/notes/4/images/flightspage0.png)

Now, let’s add some more flights to our application by returning to the Django shell:

```
# Using the filter command to find all airports based in New York
In [3]: Airport.objects.filter(city="New York")
Out[3]: <QuerySet [<Airport: New York (JFK)>]>

# Using the get command to get only one airport in New York
In [5]: Airport.objects.get(city="New York")
Out[5]: <Airport: New York (JFK)>

# Assigning some airports to variable names:
In [6]: jfk = Airport.objects.get(city="New York")
In [7]: cdg = Airport.objects.get(city="Paris")

# Creating and saving a new flight:
In [8]: f = Flight(origin=jfk, destination=cdg, duration=435)
In [9]: f.save()
```

Now, when we visit our site again

![Dua penerbangan](https://cs50.harvard.edu/web/2020/notes/4/images/flightpage1.png)

## [Django Admin](https://cs50.harvard.edu/web/2020/notes/4/#django-admin)

Karena sangat umum bagi pengembang harus membuat objek baru seperti yang telah kita lakukan di shell, Django hadir dengan [antarmuka admin default](https://docs.djangoproject.com/en/4.0/ref/contrib/admin/) yang memungkinkan kita melakukan ini dengan lebih mudah. Untuk mulai menggunakan alat ini, pertama-tama kita harus membuat pengguna administratif:

```
(base) cleggett@Connors-MacBook-Pro airline % python manage.py createsuperuser
Username: user_a
Email address: a@a.com
Password:
Password (again):
Superuser created successfully.
```

Sekarang, kita harus menambahkan model kita ke aplikasi admin dengan memasukkan `admin.py`file di dalam aplikasi kita, dan mengimpor serta mendaftarkan model kita. Ini memberi tahu Django model mana yang ingin kami akses di aplikasi admin.

```
from django.contrib import admin
from .models import Flight, Airport

# Register your models here.
admin.site.register(Flight)
admin.site.register(Airport)
```

Sekarang, saat kita mengunjungi situs kita dan menambahkan `/admin`url, kita bisa login ke halaman yang terlihat seperti ini

![Gabung](https://cs50.harvard.edu/web/2020/notes/4/images/login.png)

Setelah login, Anda akan dibawa ke halaman seperti di bawah ini di mana Anda dapat membuat, mengedit, dan menghapus objek yang tersimpan di database

![halaman admin](https://cs50.harvard.edu/web/2020/notes/4/images/admin.png)

Sekarang, mari tambahkan beberapa halaman lagi ke situs kita. Kami akan mulai dengan menambahkan kemampuan mengklik penerbangan untuk mendapatkan lebih banyak informasi tentangnya. Untuk melakukannya, mari buat jalur URL yang menyertakan `id`penerbangan:

```
path("<int:flight_id>", views.flight, name="flight")
```

Kemudian, `views.py`kita akan membuat `flight`fungsi yang mengambil id penerbangan dan menampilkan halaman html baru:

```
def flight(request, flight_id):
    flight = Flight.objects.get(id=flight_id)
    return render(request, "flights/flight.html", {
        "flight": flight
    })
```

Sekarang kita akan membuat template untuk menampilkan informasi penerbangan ini dengan tautan kembali ke halaman beranda

```

{% extends "flights/layout.html" %}

{% block body %}
    <h1>Flight {{ flight.id }}</h1>
    <ul>
        <li>Origin: {{ flight.origin }}</li>
        <li>Destination: {{ flight.destination }}</li>
        <li>Duration: {{ flight.duration }} minutes</li>
    </ul>
    <a href="{% url 'index' %}">All Flights</a>
{% endblock %}

```

Terakhir, kita perlu menambahkan kemampuan untuk menautkan dari satu halaman ke halaman lainnya, jadi kita akan memodifikasi halaman indeks untuk menyertakan link:

```

{% extends "flights/layout.html" %}

{% block body %}
    <h1>Flights:</h1>
    <ul>
        {% for flight in flights %}
            <li><a href="{% url 'flight' flight.id %}">Flight {{ flight.id }}</a>: {{ flight.origin }} to {{ flight.destination }}</li>
        {% endfor %}
    </ul>
{% endblock %}

```

Sekarang beranda kami terlihat seperti ini

![rumah baru](https://cs50.harvard.edu/web/2020/notes/4/images/flights_links.png)

Dan ketika kita mengklik penerbangan 5, misalnya, kita dibawa ke halaman ini

![Satu penerbangan](https://cs50.harvard.edu/web/2020/notes/4/images/flight5.png)

## [Relasi Banyak ke Banyak](https://cs50.harvard.edu/web/2020/notes/4/#many-to-many-relationships)

Sekarang, mari bekerja untuk mengintegrasikan penumpang ke dalam model kita. Kami akan membuat model penumpang untuk memulai:

```
class Passenger(models.Model):
    first = models.CharField(max_length=64)
    last = models.CharField(max_length=64)
    flights = models.ManyToManyField(Flight, blank=True, related_name="passengers")

    def __str__(self):
        return f"{self.first} {self.last}"
```

-   Seperti yang telah kita diskusikan, penumpang memiliki hubungan **Banyak ke Banyak** dengan penerbangan, yang kami uraikan di Django menggunakan ManyToManyField.
-   Argumen pertama dalam bidang ini adalah kelas objek yang terkait dengannya.
-   Kami telah memberikan argumen `blank=True`yang berarti penumpang tidak boleh memiliki penerbangan
-   Kami telah menambahkan a `related_name`yang melayani tujuan yang sama seperti sebelumnya: ini memungkinkan kami menemukan semua penumpang pada penerbangan tertentu.

Untuk benar-benar melakukan perubahan ini, kita harus melakukan migrasi dan migrasi. Kami kemudian dapat mendaftarkan model Penumpang `admin.py`dan mengunjungi halaman admin untuk membuat beberapa penumpang!

Sekarang kami telah menambahkan beberapa penumpang, mari perbarui halaman penerbangan kami sehingga menampilkan semua penumpang dalam satu penerbangan. Kami pertama-tama akan mengunjungi `views.py`dan memperbarui tampilan penerbangan kami untuk memberikan daftar penumpang sebagai konteks. Kami mengakses daftar menggunakan nama terkait yang kami tentukan sebelumnya.

```
def flight(request, flight_id):
    flight = Flight.objects.get(id=flight_id)
    passengers = flight.passengers.all()
    return render(request, "flights/flight.html", {
        "flight": flight,
        "passengers": passengers
    })
```

Sekarang, tambahkan daftar penumpang ke `flight.html`:

```

<h2>Passengers:</h2>
<ul>
    {% for passenger in passengers %}
        <li>{{ passenger }}</li>
    {% empty %}
        <li>No Passengers.</li>
    {% endfor %}
</ul>

```

Pada titik ini, saat kami mengklik penerbangan 5, kami melihat

![penerbangan baru5](https://cs50.harvard.edu/web/2020/notes/4/images/flight5update.png)

Sekarang, mari berupaya memberi pengunjung situs kita kemampuan untuk memesan penerbangan. Kami akan melakukannya dengan menambahkan rute pemesanan di `urls.py`:

```
path("<int:flight_id>/book", views.book, name="book")
```

Sekarang, kami akan menambahkan fungsi buku yang `views.py`menambahkan penumpang ke penerbangan:

```
def book(request, flight_id):

    # For a post request, add a new flight
    if request.method == "POST":

        # Accessing the flight
        flight = Flight.objects.get(pk=flight_id)

        # Finding the passenger id from the submitted form data
        passenger_id = int(request.POST["passenger"])

        # Finding the passenger based on the id
        passenger = Passenger.objects.get(pk=passenger_id)

        # Add passenger to the flight
        passenger.flights.add(flight)

        # Redirect user to flight page
        return HttpResponseRedirect(reverse("flight", args=(flight.id,)))
```

Berikutnya, kita akan menambahkan beberapa konteks ke templat penerbangan kita sehingga laman memiliki akses ke setiap orang yang saat ini bukan penumpang dalam penerbangan menggunakan kemampuan Django untuk [mengecualikan](https://docs.djangoproject.com/en/4.0/topics/db/queries/#retrieving-specific-objects-with-filters) objek tertentu dari kueri:

```
def flight(request, flight_id):
    flight = Flight.objects.get(id=flight_id)
    passengers = flight.passengers.all()
    non_passengers = Passenger.objects.exclude(flights=flight).all()
    return render(request, "flights/flight.html", {
        "flight": flight,
        "passengers": passengers,
        "non_passengers": non_passengers
    })
```

Sekarang, kami akan menambahkan formulir ke HTML halaman penerbangan kami menggunakan kolom input pilihan:

```

<form action="{% url 'book' flight.id %}" method="post">
    {% csrf_token %}
    <select name="passenger" id="">
        {% for passenger in non_passengers %}
            <option value="{{ passenger.id }}">{{ passenger }}</option>
        {% endfor %}
    </select>
    <input type="submit">
</form>

```

Sekarang, mari kita lihat seperti apa situsnya ketika saya membuka halaman penerbangan dan kemudian menambahkan penumpang

![membentuk](https://cs50.harvard.edu/web/2020/notes/4/images/form.png)

![disampaikan](https://cs50.harvard.edu/web/2020/notes/4/images/submitted.png)

Keuntungan lain menggunakan aplikasi admin Django adalah dapat disesuaikan. Misalnya, jika kita ingin melihat semua aspek penerbangan di antarmuka admin, kita dapat membuat kelas baru di dalamnya `admin.py`dan menambahkannya sebagai argumen saat mendaftarkan `Flight`model:

```
class FlightAdmin(admin.ModelAdmin):
    list_display = ("id", "origin", "destination", "duration")

# Register your models here.
admin.site.register(Flight, FlightAdmin)
```

`id`Nah, saat kita mengunjungi halaman admin untuk penerbangan, kita juga bisa melihatnya

![meja admin](https://cs50.harvard.edu/web/2020/notes/4/images/admin1.png)

Lihat [dokumentasi admin Django](https://docs.djangoproject.com/en/4.0/ref/contrib/admin/) untuk menemukan lebih banyak cara menyesuaikan aplikasi admin.

## [Pengguna](https://cs50.harvard.edu/web/2020/notes/4/#users)

Hal terakhir yang akan kita bahas dalam kuliah hari ini adalah ide autentikasi, atau mengizinkan pengguna untuk masuk dan keluar dari sebuah situs web. Untungnya, Django membuat ini sangat mudah bagi kita, jadi mari kita lihat contoh bagaimana kita akan melakukan ini. Kita akan mulai dengan membuat aplikasi baru bernama `users`. Di sini kita akan melakukan semua langkah normal untuk membuat aplikasi baru, tetapi di `urls.py`file baru kita, kita akan menambahkan beberapa rute lagi:

```
urlpatterns = [
    path('', views.index, name="index"),
    path("login", views.login_view, name="login"),
    path("logout", views.logout_view, name="logout")
]
```

Mari kita mulai dengan membuat formulir di mana pengguna bisa masuk. Kita akan membuat file `layout.html`seperti biasa, lalu membuat `login.html`file yang berisi formulir, dan menampilkan pesan jika ada.

```

{% extends "users/layout.html" %}

{% block body %}
    {% if message %}
        <div>{{ message }}</div>
    {% endif %}

    <form action="{% url 'login' %}" method="post">
        {% csrf_token %}
        <input type="text", name="username", placeholder="Username">
        <input type="password", name="password", placeholder="Password">
        <input type="submit", value="Login">
    </form>
{% endblock %}

```

Sekarang, di `views.py`, kita akan menambahkan tiga fungsi:

```
def index(request):
    # If no user is signed in, return to login page:
    if not request.user.is_authenticated:
        return HttpResponseRedirect(reverse("login"))
    return render(request, "users/user.html")

def login_view(request):
    return render(request, "users/login.html")

def logout_view(request):
    # Pass is a simple way to tell python to do nothing.
    pass
```

Selanjutnya, kita bisa menuju ke situs admin dan menambahkan beberapa pengguna. Setelah melakukan itu, kami akan kembali `views.py`dan memperbarui fungsi kami `login_view`untuk menangani `POST`permintaan dengan nama pengguna dan kata sandi:

```
# Additional imports we'll need:
from django.contrib.auth import authenticate, login, logout

def login_view(request):
    if request.method == "POST":
        # Accessing username and password from form data
        username = request.POST["username"]
        password = request.POST["password"]

        # Check if username and password are correct, returning User object if so
        user = authenticate(request, username=username, password=password)

        # If user object is returned, log in and route to index page:
        if user:
            login(request, user)
            return HttpResponseRedirect(reverse("index"))
        # Otherwise, return login page again with new context
        else:
            return render(request, "users/login.html", {
                "message": "Invalid Credentials"
            })
    return render(request, "users/login.html")
```

Sekarang, kita akan membuat `user.html`file yang `index`dirender oleh fungsi saat pengguna diautentikasi:

```

{% extends "users/layout.html" %}

{% block body %}
    <h1>Welcome, {{ request.user.first_name }}</h1>
    <ul>
        <li>Username: {{ request.user.username }}</li>
        <li>Email: {{ request.user.email }}</li>
    </ul>

    <a href="{% url 'logout' %}">Log Out</a>
{% endblock %}

```

Akhirnya, untuk mengizinkan pengguna untuk keluar, kami akan memutakhirkan fungsi `logout_view`sehingga menggunakan fungsi bawaan Django `logout`:

```
def logout_view(request):
    logout(request)
    return render(request, "users/login.html", {
                "message": "Logged Out"
            })
```

Sekarang setelah kita selesai, inilah demonstrasi situsnya

![Demo](https://cs50.harvard.edu/web/2020/notes/4/images/demo.gif)

Itu saja untuk kuliah ini! Lain kali, kita akan mempelajari bahasa pemrograman kedua dari kursus ini: JavaScript.
# ⭐️ Course Contents ⭐️

<iframe width="560" height="315" src="https://www.youtube.com/embed/Fo1tW09KIwo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

⌨️ ([3:27:33](https://www.youtube.com/watch?v=8DvywoWv6fI&t=12453s)) Reading Files 

<iframe width="560" height="315" src="https://www.youtube.com/embed/cIA0EokbaHE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

⌨️ ([3:35:12](https://www.youtube.com/watch?v=8DvywoWv6fI&t=12912s)) Reading Files - Reading Files in Python 

# Slides

![[Pythonlearn-07-Files.pdf]]


# Summary

- Bab tujuh memperkenalkan konsep bekerja dengan file dalam Python.
- Program Python berinteraksi dengan keyboard, layar, CPU, dan memori, tetapi sekarang program ini akan mulai bekerja dengan sumber daya eksternal seperti database, file, dan jaringan.
- Fokus pada bab ini adalah pada file teks, yang merupakan urutan baris yang dapat dengan mudah dibaca oleh Python.
- Untuk membaca sebuah file, fungsi `open()` digunakan untuk mendapatkan pegangan file, yang memungkinkan akses ke konten file.
- Pegangan berkas adalah pembungkus yang menyediakan akses ke berkas tetapi bukan berkas itu sendiri.
- Fungsi `open()` mengambil nama file sebagai parameter yang diperlukan dan memiliki parameter opsional untuk menentukan mode baca atau tulis.
- Membaca file tidak mengubah isinya, sementara menulis ke file akan menimpa data yang ada.
- Tuas berkas memungkinkan operasi membaca atau menulis dan harus ditutup ketika selesai.
- Karakter baris baru (`\n`) sangat penting untuk pembacaan file dan melambangkan akhir dari sebuah baris.
- Python menginterpretasikan `\n` sebagai karakter baris baru, yang menyebabkan teks berpindah ke awal baris baru.
- Karakter baris baru adalah karakter yang tidak dapat dicetak dan direpresentasikan sebagai urutan escape (`\n`).
- File dapat dibaca baris per baris atau karakter per karakter.
- Umumnya file dibaca baris demi baris, dengan memperlakukannya sebagai urutan baris.
- Setiap baris dalam file diakhiri dengan karakter baris baru, yang menunjukkan jeda baris.
- Memahami keberadaan baris baru dalam file adalah penting untuk operasi tertentu.
- Topik selanjutnya akan membahas membaca file dalam Python.

# [Bab 7: File](https://www.youtube.com/watch?v=8DvywoWv6fI&t=12453s)

- Bab tujuh memperkenalkan konsep bekerja dengan file dalam Python.
- Program-program Python berinteraksi dengan keyboard, layar, CPU, dan memori, namun sekarang akan mulai bekerja dengan sumber daya eksternal seperti basis data, file, dan jaringan.

## Fokus pada File Teks

- Pada bab ini, fokusnya adalah pada file teks, yang merupakan urutan baris-baris yang dapat dengan mudah dibaca oleh Python.
- File-file teks yang akan dibahas adalah file-file yang berisi baris-baris teks dan mudah dibaca oleh Python.
- Sebagai contoh, file-file teks yang telah dibuat sebelumnya, seperti file "HELLO.PY", adalah contoh file teks. File-file tersebut dibuat menggunakan editor teks, berisi perintah-perintah Python, dan dapat dieksekusi.

## Membaca File dengan File Handle

- Untuk membaca file, digunakan fungsi `open()` untuk mendapatkan file handle, yang memungkinkan akses ke konten file.
- File handle adalah lapisan yang menyediakan akses ke file tetapi bukan merupakan file itu sendiri.
- Fungsi `open()` menerima parameter wajib berupa nama file dan memiliki parameter opsional untuk menentukan mode baca atau tulis.
- Saat membaca file, konten file tidak dimodifikasi, sedangkan saat menulis ke file, data yang ada akan ditimpa.
- File handle memungkinkan operasi baca atau tulis dan harus ditutup setelah selesai.

## Karakter Baris Baru

- Karakter baris baru (`\n`) merupakan elemen penting dalam membaca file dan mewakili akhir baris.
- Python menginterpretasikan `\n` sebagai karakter baris baru, sehingga teks berpindah ke awal baris baru.
- Karakter `\n` merupakan karakter yang tidak tercetak dan direpresentasikan sebagai urutan escape (`\n`).
- File dapat dibaca per baris atau per karakter.
- Umumnya, file dibaca per baris, di mana file dianggap sebagai urutan baris.
- Setiap baris dalam file diakhiri oleh karakter baris baru, yang menandakan pemisah antarbaris.
- Memahami keberadaan karakter baris baru dalam file penting untuk operasi tertentu.

## Contoh Kode Python
```python
# Membuka file untuk dibaca
file_handle = open("namafile.txt", "r")

# Membaca file baris per baris
for line in file_handle:
    print(line)

# Menutup file handle setelah selesai
file_handle.close()
```

- Dalam contoh di atas, file dengan nama "namafile.txt" dibuka untuk dibaca dengan mode "r" (read).
- Penggunaan `for line in file_handle` memungkinkan kita membaca file baris per baris.
- Setelah selesai membaca file, file handle ditutup menggunakan metode `.close()`.

## Membaca File dengan Metode `read()`
- Selain membaca file baris per baris, kita juga dapat membaca seluruh konten file sekaligus menggunakan metode `read()`.
- Metode `read()` mengembalikan seluruh isi file sebagai satu string.
- Contoh penggunaan metode `read()` dalam kode Python:

```python
# Membuka file untuk dibaca
file_handle = open("namafile.txt", "r")

# Membaca seluruh isi file
file_content = file_handle.read()

# Menampilkan isi file
print(file_content)

# Menutup file handle setelah selesai
file_handle.close()
```

- Dalam contoh di atas, kita membuka file dengan mode "r" (read) dan menggunakan metode `read()` untuk membaca seluruh isi file.
- Isi file kemudian disimpan dalam variabel `file_content`.
- Selanjutnya, kita dapat menampilkan isi file dengan menggunakan perintah `print(file_content)`.
- Setelah selesai membaca file, file handle ditutup menggunakan metode `.close()`.

Dengan memahami cara membaca file per baris atau seluruh isi file menggunakan metode `read()`, kita dapat dengan mudah mengakses dan memanipulasi konten file dalam program Python.


# [Reading Files in Python](https://www.youtube.com/watch?v=8DvywoWv6fI&t=12912s)

Ringkasan:

- Cara umum untuk membaca file adalah dengan memperlakukannya sebagai urutan baris dan menggunakan loop for untuk membacanya.
- Loop for digunakan untuk mengambil setiap baris dalam file secara berurutan.
- Dalam Python, loop for sangat elegan dan sederhana untuk membaca semua baris dalam file.
- Ada juga cara untuk membaca file sebagai serangkaian karakter sekaligus, tetapi ini hanya cocok untuk file kecil.
- Ada beberapa cara untuk melakukan loop dengan memilih baris yang sesuai dengan kriteria tertentu.
- Beberapa metode melibatkan penggunaan fungsi strip() untuk menghilangkan karakter baru (\n) dari setiap baris.
- Jika pengguna memasukkan nama file yang tidak ada, program akan menangani kesalahan dengan menggunakan blok try-except.

Fakta-fakta yang relevan:

- File yang diberikan adalah Python for Everybody Course di YouTube.
- Cara umum untuk membaca file adalah dengan memperlakukannya sebagai urutan baris dan menggunakan loop for.
- Loop for membaca setiap baris dalam file secara berurutan.
- Ada cara lain untuk membaca file sebagai serangkaian karakter sekaligus, tetapi lebih cocok untuk file kecil.
- Ada beberapa cara untuk melakukan loop dengan memilih baris yang sesuai dengan kriteria tertentu.
- Metode strip() dapat digunakan untuk menghilangkan karakter baru (\n) dari setiap baris.
- Program juga mampu menangani kesalahan jika pengguna memasukkan nama file yang tidak ada.

Berikut adalah penjelasan secara detail tentang cara membaca file menggunakan Python dan contoh kode Python yang menggambarkan penggunaan loop dan manipulasi string:

1. Cara umum untuk membaca file:
   - File dapat dibaca dengan memperlakukannya sebagai urutan baris.
   - Biasanya, loop `for` digunakan untuk membaca setiap baris dalam file secara berurutan.

   Contoh kode Python:

   ```python
   # Membuka file
   file = open("nama_file.txt", "r")

   # Membaca file menggunakan loop for
   for line in file:
       # Lakukan sesuatu dengan setiap baris
       print(line)

   # Menutup file setelah selesai membacanya
   file.close()
   ```

2. Membaca file sebagai serangkaian karakter:
   - Ada cara lain untuk membaca file sebagai serangkaian karakter sekaligus, menggunakan metode `read()`.
   - Namun, ini lebih cocok untuk file kecil karena mengharuskan file berada dalam memori secara keseluruhan.

   Contoh kode Python:

   ```python
   # Membuka file
   file = open("nama_file.txt", "r")

   # Membaca file sebagai serangkaian karakter
   content = file.read()

   # Melakukan manipulasi pada isi file
   print(content)

   # Menutup file setelah selesai membacanya
   file.close()
   ```

3. Loop dengan memilih baris berdasarkan kriteria:
   - Ada beberapa cara untuk melakukan loop dengan memilih baris yang sesuai dengan kriteria tertentu.
   - Salah satu metode yang umum adalah menggunakan fungsi `strip()` untuk menghilangkan karakter baru (`\n`) dari setiap baris sebelum memprosesnya.

   Contoh kode Python:

   ```python
   # Membuka file
   file = open("nama_file.txt", "r")

   # Membaca file menggunakan loop for dengan pemilihan baris berdasarkan kriteria
   for line in file:
       # Menghilangkan karakter newline (\n) dari setiap baris
       stripped_line = line.strip()

       # Memproses baris yang memenuhi kriteria
       if stripped_line.startswith("Teks Awal"):
           # Lakukan sesuatu dengan baris tersebut
           print(stripped_line)

   # Menutup file setelah selesai membacanya
   file.close()
   ```

4. Penanganan kesalahan jika file tidak ada:
   - Untuk menghindari kesalahan jika pengguna memasukkan nama file yang tidak ada, dapat menggunakan blok `try-except` untuk menangani exception yang mungkin terjadi.

   Contoh kode Python:

   ```python
   try:
       # Membuka file
       file = open("nama_file.txt", "r")

       # Membaca file menggunakan loop for
       for line in file:
           # Lakukan sesuatu dengan setiap baris
           print(line)

       # Menutup file setelah selesai membacanya
       file.close()

   except FileNotFoundError:
       print("File tidak ditemukan!")
   ```

Dengan menggunakan penjelasan dan contoh kode di atas, Anda dapat membaca file dan melakukan manipulasi data dengan Python. Pastikan untuk mengganti "nama_file.txt" dengan nama file yang ingin Anda baca.

5. Manipulasi string pada setiap baris:
   - Ketika membaca file baris per baris, seringkali diperlukan manipulasi pada string yang ada di setiap baris.
   - Misalnya, menggunakan metode `split()` untuk membagi baris menjadi bagian-bagian terpisah berdasarkan pemisah tertentu.

   Contoh kode Python:

   ```python
   # Membuka file
   file = open("nama_file.txt", "r")

   # Membaca file menggunakan loop for
   for line in file:
       # Memecah baris menjadi bagian-bagian terpisah
       parts = line.split(",")

       # Mengakses setiap bagian dan melakukan manipulasi
       for part in parts:
           # Lakukan sesuatu dengan setiap bagian
           print(part)

   # Menutup file setelah selesai membacanya
   file.close()
   ```

6. Penggunaan with statement:
   - Selain membuka dan menutup file secara manual, dapat menggunakan blok `with` statement untuk mengelola pembukaan dan penutupan file secara otomatis.
   - Ini akan memastikan bahwa file ditutup dengan benar setelah selesai digunakan.

   Contoh kode Python:

   ```python
   # Membaca file menggunakan with statement
   with open("nama_file.txt", "r") as file:
       # Membaca file menggunakan loop for
       for line in file:
           # Lakukan sesuatu dengan setiap baris
           print(line)
   ```

   Dalam contoh di atas, setelah keluar dari blok `with`, file akan secara otomatis ditutup.

Dengan menggunakan penjelasan dan contoh kode di atas, Anda dapat membaca file dengan Python, melakukan manipulasi string pada setiap baris, serta menggunakan blok `with` statement untuk memastikan penutupan file yang tepat.

Tentu, berikut adalah kelanjutan penjelasan tentang membaca file dengan Python:

9. Menutup file secara otomatis menggunakan statement `with`:
   - Saat membaca file, Anda perlu memastikan bahwa file ditutup setelah selesai digunakan.
   - Untuk memudahkan hal ini, Python menyediakan statement `with` yang secara otomatis menutup file setelah blok kode selesai dieksekusi.

   Contoh kode Python:

   ```python
   with open("nama_file.txt", "r") as file:
       for line in file:
           print(line)

   # Setelah blok kode di atas selesai dieksekusi,
   # file akan ditutup secara otomatis oleh statement with

   ```

   Dalam contoh di atas, file "nama_file.txt" dibuka menggunakan statement `with` dan dibaca menggunakan loop for. Setelah blok kode selesai dieksekusi, file akan ditutup secara otomatis.

10. Membaca file dalam format CSV:
    - CSV (Comma-Separated Values) adalah format file yang sering digunakan untuk menyimpan data dalam bentuk tabel, dengan nilai-nilai yang dipisahkan oleh koma.
    - Python menyediakan modul `csv` yang memudahkan pembacaan dan penulisan file CSV.

   Contoh kode Python:

   ```python
   import csv

   with open("data.csv", "r") as file:
       reader = csv.reader(file)

       for row in reader:
           print(row)

   ```

   Dalam contoh di atas, file "data.csv" dibuka menggunakan statement `with`. Modul `csv` digunakan untuk membuat pembaca CSV yang memungkinkan kita membaca setiap baris sebagai list nilai yang dipisahkan oleh koma.

Dengan penjelasan dan contoh kode di atas, Anda sekarang memiliki pemahaman yang lebih mendalam tentang membaca file dengan Python, termasuk penggunaan statement `with` untuk menutup file secara otomatis dan membaca file dalam format CSV menggunakan modul `csv`.
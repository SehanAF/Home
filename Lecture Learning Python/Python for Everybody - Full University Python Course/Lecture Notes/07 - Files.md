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
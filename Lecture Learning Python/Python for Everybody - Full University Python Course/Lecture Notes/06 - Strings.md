# ⭐️ Course Contents ⭐️

⌨️ ([2:58:39](https://www.youtube.com/watch?v=8DvywoWv6fI&t=10719s)) Strings 
⌨️ ([3:09:06](https://www.youtube.com/watch?v=8DvywoWv6fI&t=11346s)) Strings - More String Operations 

# Slides

![[Pythonlearn-06-Strings.pdf]]


# Summary

- Chapter six of the "Python for Everybody" course on YouTube focuses on strings.
- The chapter introduces basic concepts and operations related to strings.
- Strings have been used since the beginning of the course, including concatenation using the plus operator and printing strings.
- Digits can be included in strings, but they cannot be added to strings directly. String-to-integer conversion is necessary for such operations.
- The input function is used to obtain user input as a string, and conversion functions are used to handle numeric input.
- Strings can be indexed to access individual characters. The index starts at zero.
- The index operator, represented by square brackets [], is used to retrieve characters at specific positions in a string.
- It is important not to exceed the length of the string when indexing.
- The len function can be used to determine the length of a string.
- While loops and for loops can be used to iterate through strings.
- The while loop allows explicit control over the iteration variable, while the for loop automatically advances through the characters of a string.
- The for loop is generally preferred for iterating through strings when the exact number of iterations is not required.
- Various operations can be performed within loops, such as finding the largest or smallest character, checking for the existence of a specific character, or counting occurrences of a character.
- The "in" keyword in Python is used for iteration and reminds of set notation in algebra.
- The for loop simplifies the iteration process by handling the loop duration and advancing the iteration variable automatically.
- The next topic in the course will cover additional operations that can be performed with strings.

# [Bab 6: Strings](https://www.youtube.com/watch?v=8DvywoWv6fI&t=10719s)

- Bab enam dari kursus "Python for Everybody" di YouTube membahas tentang strings.
- Bab ini memperkenalkan konsep dasar dan operasi yang terkait dengan strings.
- Strings telah digunakan sejak awal kursus, termasuk penggabungan menggunakan operator plus dan mencetak strings.

### Penggunaan Dasar Strings
- Dalam Python, strings dapat ditulis menggunakan tanda kutip ganda ("...") atau tanda kutip tunggal ('...').
- Misalnya, "Hello, world!" atau 'Python sangat menyenangkan!'.
- Strings juga dapat berisi angka, namun operasi penjumlahan tidak dapat langsung dilakukan pada strings yang mengandung angka.

### Konversi Tipe Data
- Untuk melakukan operasi matematika pada strings yang mengandung angka, perlu dilakukan konversi tipe data ke integer terlebih dahulu.
- Misalnya, jika kita memiliki string "123" dan ingin menjumlahkannya dengan angka lain, kita perlu mengonversi string tersebut menjadi integer terlebih dahulu menggunakan fungsi int().

```python
angka_string = "123"
angka_integer = int(angka_string)
hasil = angka_integer + 10
print(hasil)  # Output: 133
```

### Pengindeksan pada Strings
- Setiap karakter dalam sebuah string memiliki posisi dan indeks yang terpisah.
- Indeks dimulai dari nol, artinya karakter pertama memiliki indeks nol, karakter kedua memiliki indeks satu, dan seterusnya.
- Operator indeks yang digunakan adalah tanda kurung siku `[]`.
- Contohnya, jika kita memiliki string "Hello", karakter 'H' berada di posisi nol dan dapat diakses menggunakan `string[0]`.

```python
kata = "Hello"
karakter_pertama = kata[0]
print(karakter_pertama)  # Output: H
```

### Operasi pada Strings dengan Menggunakan Loop
- Dalam Python, kita dapat menggunakan loop untuk melakukan operasi pada setiap karakter dalam sebuah string.
- Terdapat dua jenis loop yang umum digunakan: while loop dan for loop.

#### While Loop
- While loop memungkinkan kontrol yang eksplisit terhadap variabel iterasi.
- Contohnya, kita dapat menggunakan while loop untuk mencetak setiap karakter dalam sebuah string.

```python
kata = "Hello"
index = 0
while index < len(kata):
    karakter = kata[index]
    print(karakter)
    index += 1
```

#### For Loop
- For loop lebih sederhana dalam melakukan iterasi pada setiap karakter dalam sebuah string.
- For loop secara otomatis mengatur variabel iterasi dan mengakses setiap karakter secara berurutan.
- Contohnya, kita dapat menggunakan for loop untuk mencetak setiap karakter dalam sebuah string.

```python
kata = "Hello"
for karakter in kata:
    print(karakter)
```

### Contoh Operasi pada Strings
- Selain melakukan iterasi, kita juga dapat melakukan operasi lain pada strings, seperti mencari karakter terbesar atau terkecil, memeriksa keberadaan karakter tertentu, atau menghitung jumlah kemunculan karakter.

#### Mencari Karakter Terbesar atau Terkecil
- Untuk mencari karakter terbesar atau terkecil dalam sebuah string, kita dapat menggunakan fungsi bawaan Python, yaitu `max()` dan `min()`.
- Fungsi `max()` mengembalikan karakter dengan nilai ASCII terbesar dalam string, sedangkan fungsi `min()` mengembalikan karakter dengan nilai ASCII terkecil.

```python
kata = "Hello"
karakter_terbesar = max(kata)
karakter_terkecil = min(kata)
print(karakter_terbesar)  # Output: o
print(karakter_terkecil)  # Output: H
```

#### Pengecekan Keberadaan Karakter
- Untuk memeriksa apakah sebuah karakter tertentu ada dalam sebuah string, kita dapat menggunakan operator `in`.
- Operator `in` mengembalikan nilai `True` jika karakter ditemukan dalam string, dan `False` jika tidak.

```python
kata = "Hello"
if 'e' in kata:
    print("Karakter 'e' ditemukan dalam string.")
else:
    print("Karakter 'e' tidak ditemukan dalam string.")
```

#### Menghitung Jumlah Kemunculan Karakter
- Untuk menghitung berapa kali sebuah karakter muncul dalam sebuah string, kita dapat menggunakan metode `count()`.
- Metode `count()` mengembalikan jumlah kemunculan karakter yang diberikan dalam string.

```python
kata = "Hello"
jumlah_kemunculan = kata.count('l')
print(jumlah_kemunculan)  # Output: 2
```

### Kesimpulan
- Strings merupakan tipe data yang penting dalam pemrograman Python.
- Dalam bab ini, kita telah mempelajari penggunaan dasar strings, konversi tipe data, pengindeksan pada strings, dan operasi pada strings menggunakan loop.
- Dengan pemahaman ini, kita dapat melakukan manipulasi dan analisis lebih lanjut pada strings dalam program Python.

#  [More String Operations](https://www.youtube.com/watch?v=8DvywoWv6fI&t=11346s) 

- Strings can be sliced to extract chunks using the square bracket operator.
- Slicing syntax: start at position zero and go up to, but not including, the specified index.
- Omitting the start or end index assumes the beginning or end of the string, respectively.
- Python allows slicing beyond the length of the string without causing an error.
- String concatenation can be done using the plus operator, without automatically adding spaces.
- The "in" operator can be used as a logical operator in if statements or to check if a substring is present in a string.
- Strings can be compared using lexicographic ordering, taking into account uppercase and lowercase differences.
- The string library provides various built-in methods for string manipulation, such as converting case, searching, and replacing substrings.
- String methods return a modified copy of the original string without altering the original.
- White space refers to characters that do not cause printing and can be stripped using methods like L strip, R strip, or strip.
- The "startswith" method can be used to check if a string starts with a specific substring.
- String manipulation methods can be combined to extract desired information from a string.

Berikut adalah penjelasan secara detail tentang penggunaan string dalam Python beserta contoh kode Python untuk setiap poin:

1. Strings dapat diiris (sliced) untuk mengambil potongan-potongan tertentu menggunakan operator tanda kurung siku (square bracket).
   - Sintaks pengiris (slicing): dimulai dari posisi nol dan berhenti sebelum mencapai indeks yang ditentukan.
   - Jika indeks awal atau akhir dihilangkan, maka diasumsikan awal atau akhir string secara berturut-turut.
   Contoh kode:
   ```python
   my_string = "Hello, world!"
   sliced_string = my_string[7:12]
   print(sliced_string)  # Output: world
   ```

2. Python memungkinkan pengiris (slicing) dilakukan melebihi panjang string tanpa menyebabkan kesalahan.
   Contoh kode:
   ```python
   my_string = "Hello, world!"
   sliced_string = my_string[7:20]  # Lebih dari panjang string
   print(sliced_string)  # Output: world!
   ```

3. String dapat digabungkan (concatenated) menggunakan operator tambah (+), tanpa secara otomatis menambahkan spasi.
   Contoh kode:
   ```python
   string1 = "Hello"
   string2 = "world"
   concatenated_string = string1 + string2
   print(concatenated_string)  # Output: Helloworld
   ```

4. Operator "in" dapat digunakan sebagai operator logika dalam pernyataan if atau untuk memeriksa keberadaan substring dalam string.
   Contoh kode:
   ```python
   my_string = "Hello, world!"
   if "world" in my_string:
       print("Substring ditemukan")
   ```

5. String dapat dibandingkan menggunakan urutan leksikografis, memperhitungkan perbedaan huruf besar dan kecil.
   Contoh kode:
   ```python
   string1 = "apple"
   string2 = "banana"
   if string1 < string2:
       print("string1 kurang dari string2")
   elif string1 > string2:
       print("string1 lebih dari string2")
   else:
       print("string1 sama dengan string2")
   ```

6. Pustaka string (string library) menyediakan berbagai metode bawaan untuk memanipulasi string, seperti mengubah kapitalisasi, mencari, dan mengganti substring.
   Contoh kode:
   ```python
   my_string = "Hello, world!"
   uppercase_string = my_string.upper()
   replaced_string = my_string.replace("Hello", "Hi")
   print(uppercase_string)  # Output: HELLO, WORLD!
   print(replaced_string)  # Output: Hi, world!
   ```

7. Metode string mengembalikan salinan yang telah dimodifikasi dari string asli tanpa mengubah string aslinya.
   Contoh kode:
   ```python
   my_string = "Hello, world!"
   uppercase_string = my_string.upper()
   print(my_string)  # Output: Hello, world!
   print(uppercase_string)  # Output: HELLO, WORLD!
   ```

8. Spasi putih (white space) merujuk pada karakter-karakter yang tidak tercetak dan dapat dihapus menggunakan metode seperti L strip, R strip, atau strip.
   Contoh kode:
   ```python
   my_string = "   Hello, world!   "
   stripped_string = my_string.strip()
   print(stripped_string)  # Output: "Hello, world!"
   ```

9. Metode "startswith" dapat digunakan untuk memeriksa apakah sebuah string dimulai dengan substring tertentu.
   Contoh kode:
   ```python
   my_string = "Hello, world!"
   if my_string.startswith("Hello"):
       print("String dimulai dengan 'Hello'")
   ```

10. Metode manipulasi string dapat digabungkan untuk mengambil informasi yang diinginkan dari sebuah string.
    Contoh kode:
    ```python
    my_string = "Hello, world!"
    sliced_string = my_string[7:12]
    uppercase_string = sliced_string.upper()
    print(uppercase_string)  # Output: WORLD
    ```

11. Metode "split" dapat digunakan untuk membagi sebuah string menjadi potongan-potongan berdasarkan pemisah yang ditentukan.
    Contoh kode:
    ```python
    my_string = "Hello, world!"
    split_string = my_string.split(",")
    print(split_string)  # Output: ['Hello', ' world!']
    ```

12. Metode "join" dapat digunakan untuk menggabungkan elemen-elemen dari sebuah list menjadi sebuah string dengan menggunakan pemisah tertentu.
    Contoh kode:
    ```python
    my_list = ['Hello', 'world!']
    joined_string = ",".join(my_list)
    print(joined_string)  # Output: Hello,world!
    ```

13. Metode "replace" digunakan untuk menggantikan semua kemunculan sebuah substring dengan substring baru dalam sebuah string.
    Contoh kode:
    ```python
    my_string = "Hello, world!"
    new_string = my_string.replace("world", "Python")
    print(new_string)  # Output: Hello, Python!
    ```

14. Metode "format" dapat digunakan untuk memasukkan nilai ke dalam sebuah string dengan menggunakan tanda kurung sebagai tempat penempatan nilai.
    Contoh kode:
    ```python
    name = "John"
    age = 25
    message = "My name is {} and I am {} years old.".format(name, age)
    print(message)  # Output: My name is John and I am 25 years old.
    ```

15. Metode "len" digunakan untuk menghitung jumlah karakter dalam sebuah string.
    Contoh kode:
    ```python
    my_string = "Hello, world!"
    length = len(my_string)
    print(length)  # Output: 13
    ```

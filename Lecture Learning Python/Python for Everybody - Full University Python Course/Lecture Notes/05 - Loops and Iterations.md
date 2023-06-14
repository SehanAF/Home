# ⭐️ Course Contents ⭐️

⌨️ ([2:15:21](https://www.youtube.com/watch?v=8DvywoWv6fI&t=8121s)) Loops and Iteration 
⌨️ ([2:25:04](https://www.youtube.com/watch?v=8DvywoWv6fI&t=8704s)) Loops and Iteration - Definite Loops
⌨️ ([2:31:40](https://www.youtube.com/watch?v=8DvywoWv6fI&t=9100s)) Loops and Iteration - Loop Idioms 
⌨️ ([2:40:07](https://www.youtube.com/watch?v=8DvywoWv6fI&t=9607s)) Loops and Iteration - More Loop Patterns 

# Slides

![[Pythonlearn-05-Iterations.pdf]]

# [Loops and Iteration](https://www.youtube.com/watch?v=8DvywoWv6fI&t=8121s)

- Introduction to Chapter 5: Loops and Iteration
- Explanation of while loop and its structure
- Illustration of a simple loop with a variable "n"
- Example of a well-constructed loop with an iteration variable
- Example of an infinite loop with no changes to the iteration variable
- Demonstration of a loop that doesn't run at all
- Introduction to using "break" to exit a loop
- Explanation of how "break" works and exits the loop
- Introduction to using "continue" to stop the current iteration and go back to the top of the loop
- Illustration of how "continue" works within a loop
- Construction of an infinite loop with "break" to escape it
- Explanation of indefinite loops and their termination conditions
- Introduction to definite loops as the focus of the upcoming discussion

Saya akan menjelaskan dengan lebih detail menggunakan bahasa Indonesia. Berikut adalah penjelasan rinci tentang materi tersebut:

1. Pengantar Bab 5: Perulangan dan Iterasi
   - Bab ini membahas tentang konsep perulangan dan iterasi dalam pemrograman.

2. Penjelasan tentang perulangan "while" dan strukturnya
   - Perulangan "while" digunakan untuk menjalankan blok kode selama kondisi tertentu terpenuhi.
   - Strukturnya terdiri dari kata kunci "while", kondisi yang dievaluasi, tanda titik dua (:), dan blok kode yang dijalankan jika kondisi terpenuhi.

Contoh kode Python:

```python
angka = 1
while angka <= 5:
    print(angka)
    angka += 1
```

Pada contoh di atas, perulangan "while" akan menjalankan blok kode selama nilai `angka` kurang dari atau sama dengan 5. Setiap kali perulangan dilakukan, nilai `angka` akan ditampilkan dan kemudian diincrement menggunakan operator `+=`.

Output:
```
1
2
3
4
5
```

3. Ilustrasi tentang perulangan sederhana dengan menggunakan variabel "n"
   - Contoh ini menggambarkan perulangan sederhana dengan menggunakan variabel "n" sebagai variabel perulangan.

Contoh kode Python:

```python
n = 5
while n > 0:
    print(n)
    n -= 1
```

Pada contoh di atas, perulangan "while" akan terus berjalan selama nilai `n` lebih dari 0. Setiap kali perulangan dilakukan, nilai `n` akan ditampilkan dan kemudian dikurangi 1 menggunakan operator `-=`.

Output:
```
5
4
3
2
1
```

4. Contoh perulangan yang dibangun dengan baik dengan menggunakan variabel iterasi
   - Pada contoh ini, kita menggunakan variabel iterasi "n" untuk mengendalikan berapa kali perulangan akan dijalankan.

Contoh kode Python:

```python
n = 5
while n > 0:
    print(n)
    n -= 1
print("Selesai")
```

Pada contoh di atas, perulangan "while" akan terus berjalan selama nilai `n` lebih dari 0. Setiap kali perulangan dilakukan, nilai `n` akan ditampilkan dan kemudian dikurangi 1 menggunakan operator `-=`. Setelah perulangan selesai, akan ditampilkan pesan "Selesai".

Output:
```
5
4
3
2
1
Selesai
```

Dengan menggunakan variabel iterasi seperti "n", kita dapat mengendalikan berapa kali perulangan akan dijalankan.

5. Contoh perulangan yang tidak berjalan sama sekali
   - Terkadang kita juga dapat memiliki perulangan yang tidak berjalan sama sekali, tergantung pada kondisi yang diberikan.

Contoh kode Python:

```python
n = 0
while n > 0:
    print(n)
    n -= 1
```

Pada contoh di atas, perulangan "while" tidak akan pernah berjalan karena kondisi awal `n` adalah 0. Karena kondisi awalnya tidak terpenuhi, maka blok kode dalam perulangan akan dilewati dan tidak dijalankan sama sekali.

6. Penggunaan "break" untuk keluar dari perulangan
   - Kita dapat menggunakan pernyataan "break" untuk menghentikan perulangan secara paksa, meskipun kondisi perulangan masih terpenuhi.

Contoh kode Python:

```python
while True:
    angka = int(input("Masukkan angka: "))
    if angka == 0:
        break
    print("Angka yang Anda masukkan:", angka)
```

Pada contoh di atas, kita menggunakan perulangan "while True" yang berarti perulangan akan berjalan selamanya, kecuali jika terdapat pernyataan "break". Program akan meminta pengguna untuk memasukkan angka, dan jika angka yang dimasukkan adalah 0, maka perulangan akan dihentikan dengan pernyataan "break". Jika angka yang dimasukkan bukan 0, maka program akan mencetak angka tersebut.

7. Penggunaan "continue" untuk menghentikan iterasi saat ini dan melanjutkan ke iterasi berikutnya
   - Kita juga dapat menggunakan pernyataan "continue" untuk menghentikan iterasi saat ini dalam perulangan dan melanjutkan ke iterasi berikutnya.

Contoh kode Python:

```python
n = 5
while n > 0:
    n -= 1
    if n == 3:
        continue
    print(n)
```

Pada contoh di atas, setiap kali nilai `n` adalah 3, pernyataan "continue" akan dijalankan. Hal ini akan menghentikan iterasi saat itu dan langsung melanjutkan ke iterasi berikutnya tanpa menjalankan kode di bawahnya. Dalam contoh ini, saat nilai `n` adalah 3, pernyataan "print(n)" akan dilewati.

# [Loops and Iteration - Definite Loops](https://www.youtube.com/watch?v=8DvywoWv6fI&t=8704s)

- Definite loops use the keyword "for"
- Definite loops iterate through a set of things a finite number of times
- The iteration variable is declared using the "in" keyword
- The iteration variable takes on successive values from the set
- Code within the loop block is executed for each value of the iteration variable
- Examples of sets to iterate through include lines in a file, characters in a string, and strings in a list
- Variable names should be chosen carefully to avoid confusion
- A for loop simplifies the syntax for looping and setting an iteration variable
- The for loop handles the initialization, iteration, and termination of the loop
- The "in" keyword in the for loop is reminiscent of set theory in mathematics
- The for loop can be imagined as running the code for each value in the set
- The code within the loop is executed based on the contract between Python and the programmer
- Loop idioms are discussed as a way to accomplish tasks with multiple items
- The video ends with a preview of loop idioms

Berikut adalah penjelasan lebih detail tentang materi yang disampaikan dalam video tersebut, beserta contoh kode Python:

1. Definite loops menggunakan kata kunci "for" dan digunakan untuk melakukan pengulangan sejumlah item dalam suatu set.
Contoh kode:
```python
for i in range(5):
    print(i)
```
Output:
```
0
1
2
3
4
```

2. Kata kunci "in" digunakan untuk mendeklarasikan variabel iterasi yang akan mengambil nilai-nilai berurutan dari set yang sedang diulang.
Contoh kode:
```python
friends = ["Joseph", "Glenn", "Sally"]
for friend in friends:
    print("Happy Birthday", friend)
```
Output:
```
Happy Birthday Joseph
Happy Birthday Glenn
Happy Birthday Sally
```

3. Pemilihan nama variabel yang tepat sangat penting agar tidak membingungkan. Python tidak secara otomatis mengetahui bahwa sebuah variabel berupa list hanya berdasarkan nama variabel yang dipilih.
Contoh kode yang sebaiknya dihindari:
```python
friends = ["Joseph", "Glenn", "Sally"]
for friends in friends:
    print("Happy Birthday", friends)
```
Output:
```
Happy Birthday Joseph
Happy Birthday Glenn
Happy Birthday Sally
```
Namun, sebaiknya menghindari penggunaan nama variabel yang sama dengan nama set yang sedang diulang agar tidak menimbulkan kebingungan.

4. Struktur for loop mencakup inisialisasi variabel iterasi, pengulangan, dan penentuan kapan pengulangan berakhir. Dalam satu baris kode for loop mengatur semua hal tersebut.
Contoh kode:
```python
for i in range(1, 6):
    print(i)
```
Output:
```
1
2
3
4
5
```

5. Kata kunci "in" dalam for loop menggambarkan konsep dalam teori himpunan matematika, yaitu bahwa variabel iterasi adalah anggota dari set yang sedang diulang.
Contoh kode:
```python
for i in [5, 4, 3, 2, 1]:
    print(i)
```
Output:
```
5
4
3
2
1
```

Tentu, saya dapat melanjutkan dengan penjelasan lebih lanjut. Berikutnya adalah beberapa poin tambahan yang dapat membantu Anda memahami konsep loop yang diberikan dalam video:

6. For loop tidak hanya digunakan untuk mengulang angka secara berurutan. Anda juga dapat menggunakan for loop untuk mengulang item dalam list atau string.
Contoh kode:
```python
fruits = ["apel", "mangga", "pisang"]
for buah in fruits:
    print("Saya suka", buah)
```
Output:
```
Saya suka apel
Saya suka mangga
Saya suka pisang
```

7. Anda dapat menggunakan fungsi `enumerate()` untuk mengulang melalui sebuah list sambil mendapatkan indeks dan nilai dari setiap item.
Contoh kode:
```python
fruits = ["apel", "mangga", "pisang"]
for indeks, buah in enumerate(fruits):
    print("Buah ke-", indeks, "adalah", buah)
```
Output:
```
Buah ke- 0 adalah apel
Buah ke- 1 adalah mangga
Buah ke- 2 adalah pisang
```

8. Anda juga dapat menggabungkan for loop dengan kondisi if untuk melakukan tindakan tertentu berdasarkan kondisi yang diberikan.
Contoh kode:
```python
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    if num % 2 == 0:
        print(num, "adalah angka genap")
    else:
        print(num, "adalah angka ganjil")
```
Output:
```
1 adalah angka ganjil
2 adalah angka genap
3 adalah angka ganjil
4 adalah angka genap
5 adalah angka ganjil
```

9. For loop juga dapat digunakan untuk mengulang melalui string karakter per karakter.
Contoh kode:
```python
word = "Python"
for char in word:
    print(char)
```
Output:
```
P
y
t
h
o
n
```

10. Anda dapat menggunakan pernyataan `break` dalam loop untuk menghentikan iterasi jika suatu kondisi terpenuhi.
Contoh kode:
```python
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    if num == 3:
        break
    print(num)
```
Output:
```
1
2
```
Pada contoh di atas, ketika nilai `num` sama dengan 3, pernyataan `break` akan dijalankan dan menghentikan iterasi loop.

11. Selain `break`, Anda juga dapat menggunakan pernyataan `continue` dalam loop untuk melanjutkan ke iterasi berikutnya tanpa menjalankan kode di bawahnya.
Contoh kode:
```python
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    if num == 3:
        continue
    print(num)
```
Output:
```
1
2
4
5
```
Pada contoh di atas, ketika nilai `num` sama dengan 3, pernyataan `continue` akan dijalankan dan mengabaikan kode di bawahnya, kemudian melanjutkan ke iterasi berikutnya.

12. Anda juga dapat menggunakan pernyataan `else` setelah loop. Blok kode dalam pernyataan `else` akan dijalankan setelah iterasi loop selesai, kecuali jika loop dihentikan oleh pernyataan `break`.
Contoh kode:
```python
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    print(num)
else:
    print("Selesai mengulang")
```
Output:
```
1
2
3
4
5
Selesai mengulang
```
Pada contoh di atas, setelah loop selesai mengulang, blok kode dalam pernyataan `else` dijalankan dan mencetak "Selesai mengulang".

# [Loops and Iteration - Loop Idioms](https://www.youtube.com/watch?v=8DvywoWv6fI&t=9100s)

- Idiom Loop adalah pola untuk membuat perulangan dalam Python
- Perulangan digunakan untuk memecahkan masalah dengan mengulang sekumpulan data
- Perulangan mengikuti pola menyiapkan sesuatu sebelum perulangan, melakukan tindakan selama perulangan, dan mendapatkan hasil setelah perulangan
- Contoh perulangan mengulang satu set enam angka dan mencetaknya
- Untuk menemukan angka terbesar dalam satu set angka, sebuah perulangan dapat dibuat
- Perulangan melacak angka terbesar yang terlihat sejauh ini menggunakan variabel yang disebut "terbesar_sejauh_ini"
- Variabel ini pada awalnya disetel ke -1
- Untuk setiap angka dalam kumpulan, jika lebih besar dari angka terbesar saat ini, maka angka tersebut menjadi angka terbesar yang baru
- Perulangan berlanjut sampai semua angka diproses
- Pada akhirnya, variabel "terbesar_sejauh_ini" menyimpan angka terbesar
- Angka terbesar adalah jawaban yang diperoleh setelah perulangan selesai
- Perulangan hanya mempertimbangkan angka yang sedang diproses dan membandingkannya dengan angka terbesar yang terlihat sejauh ini
- Angka-angka lain tidak ditinjau kembali atau dibandingkan
- Contoh kode menunjukkan bagaimana perulangan bekerja
- Contoh perulangan menemukan angka terbesar di antara angka-angka yang diberikan
- Setelah perulangan, variabel "terbesar_sejauh_ini" menyimpan angka terbesar
- Selanjutnya, video ini akan membahas lebih banyak pola perulangan, termasuk menghitung, menjumlahkan, merata-rata, dan menemukan angka terkecil

Di bawah ini adalah penjelasan yang lebih detail mengenai konsep Loop Idioms dan contoh kode Python yang terkait:

1. Loop Idioms (Pola Perulangan):
   - Loop Idioms adalah pola-pola yang digunakan dalam konstruksi perulangan di Python.
   - Pola-pola ini membantu kita menyelesaikan masalah dengan menggunakan perulangan, seperti mencari nilai terbesar, terkecil, menjumlahkan data, dll.

2. Konsep dasar:
   - Untuk mencapai tujuan tertentu dengan perulangan, kita perlu melakukan langkah-langkah berikut:
     a. Persiapan awal sebelum perulangan dimulai.
     b. Melakukan sesuatu pada setiap elemen dalam set data.
     c. Mendapatkan hasil atau pemrosesan terakhir setelah perulangan selesai.

3. Contoh Kode Python:
   - Misalkan kita memiliki set data berupa angka-angka: 9, 41, 12, 3, 74, dan 15.
   - Tujuan kita adalah mencari angka terbesar dari set tersebut.
   - Kita dapat menggunakan perulangan untuk mencapai hal tersebut dengan mengikuti pola Loop Idioms.
   - Berikut adalah contoh kode Python:

```python
largest_so_far = -1   # Persiapan awal sebelum perulangan dimulai

numbers = [9, 41, 12, 3, 74, 15]   # Set data yang akan kita periksa

for num in numbers:   # Melakukan iterasi untuk setiap elemen dalam set data
    if num > largest_so_far:   # Membandingkan apakah elemen saat ini lebih besar dari angka terbesar yang telah ditemukan sebelumnya
        largest_so_far = num   # Jika iya, maka update nilai angka terbesar

print("Angka terbesar:", largest_so_far)   # Menampilkan angka terbesar setelah perulangan selesai
```

Pada contoh di atas, kita menggunakan variabel `largest_so_far` untuk menyimpan angka terbesar yang ditemukan selama perulangan. Kita membandingkan setiap angka dalam set dengan `largest_so_far` dan mengubah nilainya jika ditemukan angka yang lebih besar.

Setelah perulangan selesai, kita mencetak angka terbesar yang ditemukan. Dalam contoh ini, hasilnya akan menjadi 74, karena itu adalah angka terbesar dalam set data yang diberikan.

# [Loops and Iteration - More Loop Patterns](https://www.youtube.com/watch?v=8DvywoWv6fI&t=9607s)

1. Pola penghitungan:
  - Tetapkan variabel (mis., zork) ke nol di awal
  - Jalankan perulangan beberapa kali, dengan menambah variabel sebanyak satu kali setiap kali
  - Mencetak nilai akhir dari variabel

2. Pola total:
  - Tetapkan variabel (mis., zork) ke nol di awal
  - Jalankan perulangan beberapa kali, tambahkan nilai dari setiap iterasi ke variabel
  - Mencetak nilai akhir dari variabel

3. Pola pencarian:
  - Gunakan pernyataan if di dalam perulangan untuk mencari kondisi tertentu
  - Cetak nilai yang memenuhi kondisi tersebut

4. Variabel Boolean:
  - Membuat variabel Boolean (misalnya, ditemukan) dengan nilai awal false
  - Gunakan untuk melacak apakah kondisi tertentu terpenuhi selama iterasi perulangan
  - Mencetak nilai akhir dari variabel Boolean

5. Menemukan nilai terbesar:
  - Gunakan variabel (misalnya, largest_so_far) untuk melacak nilai terbesar yang ditemukan sejauh ini
  - Bandingkan setiap nilai iterasi dengan nilai largest_so_far saat ini dan perbarui jika perlu
  - Mencetak nilai terbesar_sejauh_terakhir

6. Menemukan nilai terkecil:
  - Gunakan sebuah variabel (mis., smallest_so_far) untuk melacak nilai terkecil yang ditemukan sejauh ini
  - Inisialisasi variabel terkecil_sejauh_jauh dengan nilai yang besar (misalnya, 100)
  - Bandingkan setiap nilai iterasi dengan nilai terkecil_so_far saat ini dan perbarui jika perlu
  - Cetak nilai terkecil_so_far terakhir

Berikut penjelasan lebih detail untuk setiap pola dan contoh kode Python-nya:

1. Pola Penghitungan (Counting Pattern):
   - Set sebuah variabel (misalnya, zork) dengan nilai nol pada awalnya.
   - Jalankan perulangan beberapa kali, dengan menambahkan satu ke variabel setiap kali perulangan dilakukan.
   - Cetak nilai akhir dari variabel tersebut.

Contoh kode Python:
```python
zork = 0
for i in range(5):
    zork += 1
print(zork)
```
Output:
```
5
```

2. Pola Penjumlahan (Total Pattern):
   - Set sebuah variabel (misalnya, zork) dengan nilai nol pada awalnya.
   - Jalankan perulangan beberapa kali, dengan menambahkan nilai setiap iterasi ke variabel tersebut.
   - Cetak nilai akhir dari variabel tersebut.

Contoh kode Python:
```python
zork = 0
for i in range(5):
    zork += i
print(zork)
```
Output:
```
10
```

3. Pola Pencarian (Searching Pattern):
   - Gunakan pernyataan if di dalam perulangan untuk mencari kondisi tertentu.
   - Cetak nilai yang memenuhi kondisi tersebut.

Contoh kode Python:
```python
for i in range(1, 6):
    if i % 2 == 0:
        print(i)
```
Output:
```
2
4
```

4. Variabel Boolean:
   - Buat sebuah variabel Boolean (misalnya, found) dengan nilai awal false.
   - Gunakan variabel tersebut untuk melacak apakah kondisi tertentu terpenuhi selama iterasi perulangan.
   - Cetak nilai akhir dari variabel Boolean tersebut.

Contoh kode Python:
```python
found = False
for i in range(1, 6):
    if i == 3:
        found = True
if found:
    print("Ditemukan!")
else:
    print("Tidak ditemukan.")
```
Output:
```
Ditemukan!
```

5. Mencari Nilai Terbesar:
   - Gunakan sebuah variabel (misalnya, largest_so_far) untuk melacak nilai terbesar yang ditemukan.
   - Bandingkan setiap nilai iterasi dengan nilai largest_so_far saat ini dan perbarui jika diperlukan.
   - Cetak nilai largest_so_far terakhir.

Contoh kode Python:
```python
largest_so_far = float("-inf")
for num in [5, 12, 3, 8, 1]:
    if num > largest_so_far:
        largest_so_far = num
print(largest_so_far)
```
Output:
```
12
```

6. Pola Mencari Nilai Terkecil:
   - Tetapkan sebuah variabel (misalnya, smallest_so_far) untuk melacak nilai terkecil yang ditemukan sejauh ini.
   - Inisialisasikan variabel smallest_so_far dengan nilai yang besar, misalnya 100, sehingga semua nilai yang dibandingkan akan lebih kecil darinya.
   - Jalankan perulangan dan pada setiap iterasi, bandingkan nilai iterasi saat ini dengan nilai smallest_so_far.
   - Jika nilai iterasi saat ini lebih kecil daripada smallest_so_far, perbarui nilai smallest_so_far dengan nilai iterasi saat ini.
   - Setelah perulangan selesai, cetak nilai smallest_so_far yang merupakan nilai terkecil.

Contoh kode Python:
```python
smallest_so_far = 100
numbers = [9, 4, 6, 1, 3, 7, 2, 8]
for num in numbers:
    if num < smallest_so_far:
        smallest_so_far = num
print(smallest_so_far)
```
Output:
```
1
```

Dengan menggunakan pola ini, Anda dapat mencari dan melacak nilai terkecil dalam suatu rangkaian nilai. 

7. Pola Penjumlahan dengan Kondisi (Conditional Total Pattern):
   - Set sebuah variabel (misalnya, zork) dengan nilai nol pada awalnya.
   - Jalankan perulangan beberapa kali, dengan menambahkan nilai setiap iterasi ke variabel tersebut hanya jika memenuhi kondisi tertentu.
   - Cetak nilai akhir dari variabel tersebut.

Contoh kode Python:
```python
zork = 0
for i in range(1, 11):
    if i % 2 == 0:  # Hanya menjumlahkan bilangan genap
        zork += i
print(zork)
```
Output:
```
30
```

8. Pola Pencarian dengan Aksi (Search and Action Pattern):
   - Gunakan pernyataan if di dalam perulangan untuk mencari kondisi tertentu.
   - Ketika kondisi terpenuhi, lakukan suatu aksi (misalnya, mencetak nilai).
   - Cetak pesan jika tidak ada nilai yang memenuhi kondisi.

Contoh kode Python:
```python
found = False
for i in range(1, 6):
    if i > 3:
        found = True
        print(f"Nilai {i} memenuhi kondisi.")
if not found:
    print("Tidak ada nilai yang memenuhi kondisi.")
```
Output:
```
Nilai 4 memenuhi kondisi.
Nilai 5 memenuhi kondisi.
```

9. Pola Perulangan dengan Indeks Terbalik (Looping Backwards with Range):
   - Gunakan fungsi `range()` dengan parameter yang memungkinkan perulangan mundur.
   - Jalankan perulangan mundur dengan menggunakan nilai indeks yang sesuai.
   - Cetak nilai yang diinginkan.

Contoh kode Python:
```python
for i in range(5, 0, -1):
    print(i)
```
Output:
```
5
4
3
2
1
```

10. Pola Perulangan dengan Langkah Lain (Looping with Step):
    - Gunakan fungsi `range()` dengan parameter langkah yang diinginkan.
    - Jalankan perulangan dengan menggunakan nilai indeks yang disesuaikan dengan langkah.
    - Cetak nilai yang diinginkan.

Contoh kode Python:
```python
for i in range(1, 10, 2):  # Perulangan dengan langkah 2 (hanya bilangan ganjil)
    print(i)
```
Output:
```
1
3
5
7
9
```


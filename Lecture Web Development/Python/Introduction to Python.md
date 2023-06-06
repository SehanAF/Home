# [Kuliah 2](https://cs50.harvard.edu/web/2020/notes/2/#lecture-2)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/2/#introduction)
-   [Piton](https://cs50.harvard.edu/web/2020/notes/2/#python)
-   [Variabel](https://cs50.harvard.edu/web/2020/notes/2/#variables)
-   [Memformat String](https://cs50.harvard.edu/web/2020/notes/2/#formatting-strings)
-   [Kondisi](https://cs50.harvard.edu/web/2020/notes/2/#conditions)
-   [Urutan](https://cs50.harvard.edu/web/2020/notes/2/#sequences)
    -   [String](https://cs50.harvard.edu/web/2020/notes/2/#strings)
    -   [Daftar](https://cs50.harvard.edu/web/2020/notes/2/#lists)
    -   [Tupel](https://cs50.harvard.edu/web/2020/notes/2/#tuples)
    -   [Set](https://cs50.harvard.edu/web/2020/notes/2/#sets)
    -   [Kamus](https://cs50.harvard.edu/web/2020/notes/2/#dictionaries)
    -   [Loop](https://cs50.harvard.edu/web/2020/notes/2/#loops)
-   [Fungsi](https://cs50.harvard.edu/web/2020/notes/2/#functions)
-   [Modul](https://cs50.harvard.edu/web/2020/notes/2/#modules)
-   [Pemrograman berorientasi objek](https://cs50.harvard.edu/web/2020/notes/2/#object-oriented-programming)
-   [Pemrograman Fungsional](https://cs50.harvard.edu/web/2020/notes/2/#functional-programming)
    -   [Dekorator](https://cs50.harvard.edu/web/2020/notes/2/#decorators)
    -   [Fungsi Lambda](https://cs50.harvard.edu/web/2020/notes/2/#lambda-functions)
-   [Pengecualian](https://cs50.harvard.edu/web/2020/notes/2/#exceptions)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/2/#introduction)

-   Sejauh ini, kita telah membahas cara membuat halaman web sederhana menggunakan HTML dan CSS, serta cara menggunakan Git dan GitHub untuk melacak perubahan pada kode kita dan berkolaborasi dengan orang lain.
-   Hari ini, kita akan mendalami Python, salah satu dari dua bahasa pemrograman utama yang akan kita gunakan selama kursus ini.

## [Piton](https://cs50.harvard.edu/web/2020/notes/2/#python)

![Logo Piton](https://cs50.harvard.edu/web/2020/notes/2/images/python.png)

-   Python adalah bahasa yang sangat kuat dan banyak digunakan yang memungkinkan kita membangun aplikasi web yang cukup rumit dengan cepat. Dalam kursus ini, kita akan menggunakan Python 3, meskipun Python 2 masih digunakan di beberapa tempat. Saat melihat sumber daya luar, berhati-hatilah untuk memastikan mereka menggunakan versi yang sama.
    
-   Mari kita mulai dari mana kita mulai dengan banyak bahasa pemrograman: Halo, dunia. Program ini, ditulis dengan Python, akan terlihat seperti ini:
    

```
print("Hello, world!")
```

-   Untuk memecah apa yang terjadi di baris itu, ada `print` **fungsi** yang dibangun ke dalam bahasa python, yang mengambil **argumen** dalam tanda kurung, dan menampilkan argumen itu di baris perintah.
-   Untuk benar-benar menulis dan menjalankan program ini di komputer Anda, pertama-tama Anda akan mengetikkan baris ini ke dalam editor teks pilihan Anda, dan kemudian menyimpan file sebagai `something.py`. Selanjutnya, Anda akan menuju ke terminal Anda, arahkan ke direktori yang berisi file Anda, dan ketik `python something.py`. Dalam kasus program di atas, kata-kata "Halo, dunia!" kemudian akan ditampilkan di terminal.
-   Bergantung pada bagaimana komputer Anda diatur, Anda mungkin harus mengetik `python3`sebelum `python`nama file, dan Anda bahkan mungkin harus [mengunduh Python](https://www.python.org/downloads/) jika Anda belum melakukannya. Setelah menginstal Python, kami sarankan Anda juga [mengunduh Pip](https://pip.pypa.io/en/stable/installing/) , karena Anda akan membutuhkannya nanti dalam kursus.
-   Saat Anda mengetik `python file.py`di terminal, sebuah program bernama **interpreter** , yang Anda unduh bersama dengan Python, membaca file Anda baris demi baris, dan mengeksekusi setiap baris kode. Ini berbeda dari bahasa seperti **C** atau **Java** , yang perlu dikompilasi **menjadi** kode mesin sebelum dapat dijalankan.

## [Variabel](https://cs50.harvard.edu/web/2020/notes/2/#variables)

Bagian penting dari setiap bahasa pemrograman adalah kemampuan untuk membuat dan memanipulasi variabel. Untuk menetapkan nilai ke variabel dengan Python, sintaksnya terlihat seperti ini:

```
a = 28
b = 1.5
c = "Hello!"
d = True
e = None
```

Setiap baris ini mengambil nilai di sebelah kanan `=`, dan menyimpannya di nama variabel di sebelah kiri.

Tidak seperti di beberapa bahasa pemrograman lain, tipe variabel Python disimpulkan, artinya meskipun setiap variabel memiliki tipe, kita tidak harus secara eksplisit menyatakan tipe yang mana saat kita membuat variabel. Beberapa jenis variabel yang paling umum adalah:

-   **int** : bilangan bulat
-   **float** : Angka desimal
-   **chr** : Satu karakter
-   **str** : Sebuah string, atau urutan karakter
-   **bool** : Nilai yang salah satu `True`atau`False`
-   **NoneType** : Nilai khusus ( `None`) yang menunjukkan tidak adanya nilai.

Sekarang, kita akan bekerja untuk menulis program yang lebih menarik yang dapat menerima masukan dari pengguna dan menyapa pengguna tersebut. Untuk melakukan ini, kami akan menggunakan fungsi bawaan lain yang disebut `input`yang menampilkan prompt kepada pengguna, dan mengembalikan apa pun yang diberikan pengguna sebagai input. Misalnya, kita dapat menulis yang berikut ini dalam sebuah file bernama `name.py`:

```
name = input("Name: ")
print("Hello, " + name)
```

Saat dijalankan di terminal, seperti inilah tampilan programnya:

![Halo](https://cs50.harvard.edu/web/2020/notes/2/images/hello.png)

Beberapa hal yang perlu diperhatikan di sini:

-   Di baris pertama, alih-alih menugaskan nama variabel ke nilai eksplisit, kami menugaskannya ke apa pun yang `input`dikembalikan fungsi.
-   Di baris kedua, kami menggunakan `+`operator untuk menggabungkan, atau **menggabungkan** , dua string. Dalam python, `+`operator dapat digunakan untuk menambahkan angka atau menggabungkan string dan daftar.

## [Memformat String](https://cs50.harvard.edu/web/2020/notes/2/#formatting-strings)

-   Meskipun kita dapat menggunakan `+`operator untuk menggabungkan string seperti yang kita lakukan di atas, di versi terbaru python, bahkan ada cara yang lebih mudah untuk bekerja dengan string, yang dikenal sebagai [formatted strings](https://realpython.com/python-f-strings/) , atau disingkat **f-strings .**
-   Untuk menunjukkan bahwa kami menggunakan string yang diformat, kami cukup menambahkan `f`sebelum tanda kutip. Misalnya, alih-alih menggunakan `"Hello, " + name`seperti yang kami lakukan di atas, kami dapat menulis `f"Hello, {name}"`untuk hasil yang sama. Kita bahkan dapat menyambungkan fungsi ke dalam string ini jika kita mau, dan mengubah program kita di atas menjadi satu baris:

```
print(f"Hello, {input("Name: ")}")
```

## [Kondisi](https://cs50.harvard.edu/web/2020/notes/2/#conditions)

-   Sama seperti bahasa pemrograman lainnya, Python memberi kita kemampuan untuk menjalankan segmen kode yang berbeda berdasarkan [kondisi](https://realpython.com/python-conditional-statements/) yang berbeda . Misalnya, dalam program di bawah ini, kami akan mengubah keluaran kami tergantung pada angka yang diketik pengguna:

```
num = input("Number: ")
if num > 0:
    print("Number is positive")
elif num < 0:
    print("Number is negative")
else:
    print("Number is 0")
```

-   Masuk ke cara kerja program di atas, kondisional dalam python berisi kata kunci ( `if`, `elif`, atau `else`) dan kemudian (kecuali dalam `else`kasus ini) ekspresi boolean, atau ekspresi yang mengevaluasi salah satu `True`atau `False`. Kemudian, semua kode yang ingin kita jalankan jika ekspresi tertentu bernilai benar, **diindentasi** tepat di bawah pernyataan tersebut. Lekukan diperlukan sebagai bagian dari sintaks Python.
-   Namun, saat kami menjalankan program ini, kami menemukan [pengecualian](https://docs.python.org/3/tutorial/errors.html) yang terlihat seperti ini:

![kondisi](https://cs50.harvard.edu/web/2020/notes/2/images/cond.png)

-   Pengecualian adalah apa yang terjadi ketika kesalahan terjadi saat kami menjalankan kode python kami, dan seiring waktu Anda akan menjadi lebih baik dan lebih baik dalam menafsirkan kesalahan ini, yang merupakan keterampilan yang sangat berharga untuk dimiliki.
-   Mari kita lihat lebih dekat pada pengecualian khusus ini: Jika kita melihat di bagian bawah, kita akan melihat bahwa kita menemukan a `TypeError`, yang umumnya berarti Python mengharapkan variabel tertentu dari satu jenis, tetapi ternyata dari jenis lain . Dalam hal ini, pengecualian memberi tahu kita bahwa kita tidak dapat menggunakan `>`simbol untuk membandingkan a `str`dan `int`, lalu di atas kita dapat melihat bahwa perbandingan ini terjadi pada baris 2.
-   Dalam hal ini, jelas bahwa itu `0`adalah bilangan bulat, jadi `num`variabel kita harus berupa string. Hal ini terjadi karena ternyata `input`fungsi tersebut selalu mengembalikan sebuah string, dan kita harus menentukan bahwa itu harus diubah menjadi (atau **dilemparkan** ke dalam) bilangan bulat menggunakan `int`fungsi tersebut. Ini berarti baris pertama kita sekarang akan terlihat seperti:

```
num = int(input("Number: "))
```

-   Sekarang, program akan bekerja seperti yang kita inginkan!

## [Urutan](https://cs50.harvard.edu/web/2020/notes/2/#sequences)

Salah satu bagian paling kuat dari bahasa Python adalah kemampuannya untuk bekerja dengan **urutan** data selain variabel individual.

Ada beberapa jenis urutan yang serupa dalam beberapa hal, tetapi berbeda dalam hal lain. Saat menjelaskan perbedaan tersebut, kami akan menggunakan istilah **mutable/immutable** dan **orders/unordered** . **Dapat berubah** berarti bahwa setelah urutan ditentukan, kita dapat mengubah elemen individual dari urutan itu, dan **memerintahkan** berarti bahwa urutan objek itu penting.

### [String](https://cs50.harvard.edu/web/2020/notes/2/#strings)

**Dipesan** : Ya

**Bisa berubah** : Tidak

Kita telah melihat string sedikit, tetapi bukan hanya variabel, kita dapat menganggap string sebagai rangkaian karakter. Ini berarti kita dapat mengakses elemen individual di dalam string! Misalnya:

```
name = "Harry"
print(name[0])
print(name[1])
```

mencetak karakter pertama (atau indeks-0) dalam string, yang dalam hal ini adalah `H`, dan kemudian mencetak karakter kedua (atau indeks-1), yaitu `a`.

### [Daftar](https://cs50.harvard.edu/web/2020/notes/2/#lists)

**Dipesan** : Ya

**Dapat berubah** : Ya

Daftar [Python](https://www.w3schools.com/python/python_lists.asp) memungkinkan Anda untuk menyimpan jenis variabel apa pun. Kami membuat daftar menggunakan tanda kurung siku dan koma, seperti yang ditunjukkan di bawah ini. Mirip dengan string, kita dapat mencetak seluruh daftar, atau beberapa elemen individual. Kami juga dapat menambahkan elemen ke daftar menggunakan `append`, dan mengurutkan daftar menggunakan`sort`

```
# This is a Python comment
names = ["Harry", "Ron", "Hermione"]
# Print the entire list:
print(names)
# Print the second element of the list:
print(names[1])
# Add a new name to the list:
names.append("Draco")
# Sort the list:
names.sort()
# Print the new list:
print(names)
```

![Nama](https://cs50.harvard.edu/web/2020/notes/2/images/list.png)

### [Tupel](https://cs50.harvard.edu/web/2020/notes/2/#tuples)

**Dipesan** : Ya

**Bisa berubah** : Tidak

[Tuple](https://www.w3schools.com/python/python_tuples.asp) umumnya digunakan ketika Anda hanya perlu menyimpan dua atau tiga nilai secara bersamaan, seperti nilai x dan y untuk suatu titik. Dalam kode Python, kami menggunakan tanda kurung:

```
point = (12.5, 10.6)
```

### [Set](https://cs50.harvard.edu/web/2020/notes/2/#sets)

**Dipesan** : Tidak

**Dapat berubah** : T/A

[Set](https://www.w3schools.com/python/python_sets.asp) berbeda dari list dan tuple karena tidak **diurutkan** . Mereka juga berbeda karena meskipun Anda dapat memiliki dua atau lebih elemen yang sama di dalam daftar/tupel, satu set hanya akan menyimpan setiap nilai satu kali. Kita dapat mendefinisikan himpunan kosong menggunakan `set`fungsi. Kita kemudian dapat menggunakan `add`dan `remove`untuk menambah dan menghapus elemen dari himpunan itu, dan fungsi `len`untuk menemukan ukuran himpunan. Perhatikan bahwa `len`fungsinya bekerja pada semua urutan dengan python. Perhatikan juga bahwa meskipun menambahkan `4`dan `3`ke set dua kali, setiap item hanya dapat muncul sekali dalam satu set.

```
# Create an empty set:
s = set()

# Add some elements:
s.add(1)
s.add(2)
s.add(3)
s.add(4)
s.add(3)
s.add(1)

# Remove 2 from the set
s.remove(2)

# Print the set:
print(s)

# Find the size of the set:
print(f"The set has {len(s)} elements.")

""" This is a python multi-line comment:
Output:
{1, 3, 4}
The set has 3 elements.
"""
```

### [Kamus](https://cs50.harvard.edu/web/2020/notes/2/#dictionaries)

**Dipesan** : Tidak

**Dapat berubah** : Ya

[Kamus Python](https://www.w3schools.com/python/python_dictionaries.asp) atau `dict`s, akan sangat berguna dalam kursus ini. Kamus adalah sekumpulan **pasangan kunci-nilai** , di mana setiap kunci memiliki nilai yang sesuai, seperti halnya dalam kamus, setiap kata (kunci) memiliki definisi (nilai) yang sesuai. Di Python, kami menggunakan kurung kurawal untuk memuat kamus, dan titik dua untuk menunjukkan kunci dan nilai. Misalnya:

```
# Define a dictionary
houses = {"Harry": "Gryffindor", "Draco": "Slytherin"}
# Print out Harry's house
print(houses["Harry"])
# Adding values to a dictionary:
houses["Hermione"] = "Gryffindor"
# Print out Hermione's House:
print(houses["Hermione"])

""" Output:
Gryffindor
Gryffindor
"""
```

### [Loop](https://cs50.harvard.edu/web/2020/notes/2/#loops)

Loop adalah bagian yang sangat penting dari bahasa pemrograman apa pun, dan dalam Python, loop hadir dalam dua bentuk utama: [for loop](https://www.w3schools.com/python/python_for_loops.asp) dan [while loop](https://www.w3schools.com/python/python_while_loops.asp) . Untuk saat ini, kami akan fokus pada For Loops.

-   For loop digunakan untuk mengulangi urutan elemen, melakukan beberapa blok kode (diberi indentasi di bawah) untuk setiap elemen dalam urutan. Misalnya, kode berikut akan mencetak angka dari 0 hingga 5:

```
for i in [0, 1, 2, 3, 4, 5]:
    print(i)

""" Output:
0
1
2
3
4
5
"""
```

-   Kita dapat memadatkan kode ini menggunakan fungsi python `range`, yang memungkinkan kita mendapatkan urutan angka dengan mudah. Kode berikut memberikan hasil yang sama persis dengan kode kita dari atas:

```
for i in range(6):
    print(i)

""" Output:
0
1
2
3
4
5
"""
```

-   Jenis loop ini dapat bekerja untuk urutan apa pun! Misalnya, jika kita ingin mencetak setiap nama dalam daftar, kita dapat menulis kode di bawah ini:

```
# Create a list:
names = ["Harry", "Ron", "Hermione"]

# Print each name:
for name in names:
    print(name)

""" Output:
Harry
Ron
Hermione
"""
```

-   Kita bisa menjadi lebih spesifik jika kita mau, dan mengulang setiap karakter dalam satu nama!

```
name = "Harry"
for char in name:
    print(char)

""" Output:
H
a
r
r
y
"""
```

## [Fungsi](https://cs50.harvard.edu/web/2020/notes/2/#functions)

Kita telah melihat beberapa fungsi python seperti `print`and `input`, tapi sekarang kita akan menyelami penulisan fungsi kita sendiri. Untuk memulai, kita akan menulis fungsi yang mengambil angka dan mengkuadratkannya:

```
def square(x):
    return x * x
```

Perhatikan bagaimana kita menggunakan `def`kata kunci untuk menunjukkan bahwa kita mendefinisikan sebuah fungsi, bahwa kita menerima satu masukan yang dipanggil `x`dan bahwa kita menggunakan `return`kata kunci untuk menunjukkan seperti apa keluaran fungsi itu.

Kita kemudian dapat "memanggil" fungsi ini sama seperti kita memanggil yang lain: menggunakan tanda kurung:

```
for i in range(10):
    print(f"The square of {i} is {square(i)}")

""" Output:
The square of 0 is 0
The square of 1 is 1
The square of 2 is 4
The square of 3 is 9
The square of 4 is 16
The square of 5 is 25
The square of 6 is 36
The square of 7 is 49
The square of 8 is 64
The square of 9 is 81
"""
```

## [Modul](https://cs50.harvard.edu/web/2020/notes/2/#modules)

Saat proyek kita semakin besar dan besar, akan berguna untuk dapat menulis fungsi dalam satu file dan menjalankannya di file lain. Dalam kasus di atas, kita dapat membuat satu file bernama `functions.py`dengan kode:

```
def square(x):
    return x * x
```

Dan file lain dipanggil `square.py`dengan kode:

```
for i in range(10):
    print(f"The square of {i} is {square(i)}")
```

Namun, ketika kami mencoba menjalankan `square.py`, kami mengalami kesalahan berikut:

![Kesalahan Nama](https://cs50.harvard.edu/web/2020/notes/2/images/NameError.png)

Kami mengalami masalah ini karena secara default, file Python tidak tahu satu sama lain, jadi kami harus secara eksplisit `import`fungsi kuadrat dari `functions` **modul** yang baru saja kami tulis. Sekarang, ketika `square.py`terlihat seperti ini:

```
from functions import square

for i in range(10):
    print(f"The square of {i} is {square(i)}")
```

Alternatifnya, kita dapat memilih untuk mengimpor seluruh `functions`modul dan kemudian menggunakan notasi titik untuk mengakses `square`fungsi:

```
import functions

for i in range(10):
    print(f"The square of {i} is {functions.square(i)}")
```

Ada banyak modul Python bawaan yang dapat kita impor seperti `math`atau `csv`yang memberi kita akses ke lebih banyak fungsi. Selain itu, kami dapat mengunduh lebih banyak Modul untuk mengakses lebih banyak fungsi! Kita akan menghabiskan banyak waktu menggunakan `Django`Modul, yang akan kita bahas pada kuliah berikutnya.

## [Pemrograman berorientasi objek](https://cs50.harvard.edu/web/2020/notes/2/#object-oriented-programming)

[Pemrograman Berorientasi Objek](https://en.wikipedia.org/wiki/Object-oriented_programming) adalah paradigma pemrograman, atau cara berpikir tentang pemrograman, yang berpusat di sekitar objek yang dapat menyimpan informasi dan melakukan tindakan.

-   **Classes** : Kita telah melihat beberapa jenis variabel di python, tapi bagaimana jika kita ingin membuat tipe kita sendiri? Kelas [Python](https://www.w3schools.com/python/python_classes.asp) pada dasarnya adalah templat untuk jenis objek baru yang dapat menyimpan informasi dan melakukan tindakan. Inilah kelas yang mendefinisikan titik dua dimensi:

```
class Point():
    # A method defining how to create a point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
```

-   Perhatikan bahwa dalam kode di atas, kami menggunakan kata kunci `self`untuk mewakili objek yang sedang kami kerjakan. `self`harus menjadi argumen pertama untuk metode apa pun dalam kelas Python.

Sekarang, mari kita lihat bagaimana kita bisa menggunakan kelas dari atas untuk membuat objek:

```
p = Point(2, 8)
print(p.x)
print(p.y)

""" Output:
2
8
"""
```

Sekarang, mari kita lihat contoh yang lebih menarik di mana alih-alih hanya menyimpan koordinat Titik, kita membuat kelas yang merepresentasikan penerbangan maskapai:

```
class Flight():
    # Method to create new flight with given capacity
    def __init__(self, capacity):
        self.capacity = capacity
        self.passengers = []

    # Method to add a passenger to the flight:
    def add_passenger(self, name):
        self.passengers.append(name)
```

Namun, kelas ini memiliki kekurangan karena meskipun kami menetapkan kapasitas, kami masih dapat menambah terlalu banyak penumpang. Mari tingkatkan sehingga sebelum menambahkan penumpang, kami memeriksa apakah ada ruang di penerbangan:

```
class Flight():
    # Method to create new flight with given capacity
    def __init__(self, capacity):
        self.capacity = capacity
        self.passengers = []

    # Method to add a passenger to the flight:
    def add_passenger(self, name):
        if not self.open_seats():
            return False
        self.passengers.append(name)
        return True

    # Method to return number of open seats
    def open_seats(self):
        return self.capacity - len(self.passengers)
```

Perhatikan bahwa di atas, kami menggunakan garis `if not self.open_seats()`untuk menentukan ada atau tidaknya kursi yang terbuka. Ini berfungsi karena dalam Python, angka 0 dapat diartikan sebagai meaning `False`, dan kita juga dapat menggunakan kata kunci `not`untuk menandakan kebalikan dari pernyataan berikut so `not True`is `False`dan `not False`is `True`. Oleh karena itu, jika `open_seats`mengembalikan 0, seluruh ekspresi akan dievaluasi menjadi`True`

Sekarang, mari kita coba kelas yang telah kita buat dengan menginisiasi beberapa objek:

```
# Create a new flight with o=up to 3 passengers
flight = Flight(3)

# Create a list of people
people = ["Harry", "Ron", "Hermione", "Ginny"]

# Attempt to add each person in the list to a flight
for person in people:
    if flight.add_passenger(person):
        print(f"Added {person} to flight successfully")
    else:
        print(f"No available seats for {person}")

""" Output:
Added Harry to flight successfully
Added Ron to flight successfully
Added Hermione to flight successfully
No available seats for Ginny
"""
```

## [Pemrograman Fungsional](https://cs50.harvard.edu/web/2020/notes/2/#functional-programming)

Selain mendukung Pemrograman Berorientasi Objek, Python juga mendukung [Paradigma Pemrograman Fungsional](https://en.wikipedia.org/wiki/Functional_programming) , di mana fungsi diperlakukan sebagai nilai seperti variabel lainnya.

### [Dekorator](https://cs50.harvard.edu/web/2020/notes/2/#decorators)

Satu hal yang dimungkinkan oleh pemrograman fungsional adalah gagasan dekorator, yang merupakan fungsi tingkat tinggi yang dapat mengubah fungsi lain. Sebagai contoh, mari kita menulis dekorator yang mengumumkan kapan suatu fungsi akan dimulai, dan kapan akan berakhir. Kami kemudian dapat menerapkan dekorator ini menggunakan `@`simbol.

```
def announce(f):
    def wrapper():
        print("About to run the function")
        f()
        print("Done with the function")
    return wrapper

@announce
def hello():
    print("Hello, world!")

hello()

""" Output:
About to run the function
Hello, world!
Done with the function
"""
```

### [Fungsi Lambda](https://cs50.harvard.edu/web/2020/notes/2/#lambda-functions)

Fungsi Lambda menyediakan cara lain untuk membuat fungsi dengan python. Misalnya, jika kita ingin mendefinisikan `square`fungsi yang sama dengan yang kita lakukan sebelumnya, kita dapat menulis:

```
square = lambda x: x * x
```

Dimana input berada di sebelah kiri `:`dan output berada di sebelah kanan.

Ini bisa berguna saat kita tidak ingin menulis seluruh fungsi terpisah untuk satu kali penggunaan kecil. Misalnya, jika kita ingin mengurutkan beberapa objek yang awalnya tidak jelas cara mengurutkannya. Bayangkan kita memiliki daftar orang, tetapi dengan nama dan rumah, bukan hanya nama yang ingin kita urutkan:

```
people = [
    {"name": "Harry", "house": "Gryffindor"},
    {"name": "Cho", "house": "Ravenclaw"},
    {"name": "Draco", "house": "Slytherin"}
]

people.sort()

print(people)
```

Ini, bagaimanapun, meninggalkan kita dengan kesalahan:

![Ketik Kesalahan](https://cs50.harvard.edu/web/2020/notes/2/images/TypeError.png)

Yang terjadi karena Python tidak tahu cara membandingkan dua Kamus untuk memeriksa apakah yang satu kurang dari yang lain.

Kita dapat mengatasi masalah ini dengan memasukkan `key`argumen ke fungsi pengurutan, yang menentukan bagian mana dari kamus yang ingin kita gunakan untuk mengurutkan:

```
people = [
    {"name": "Harry", "house": "Gryffindor"},
    {"name": "Cho", "house": "Ravenclaw"},
    {"name": "Draco", "house": "Slytherin"}
]

def f(person):
    return person["name"]

people.sort(key=f)

print(people)

""" Output:
[{'name': 'Cho', 'house': 'Ravenclaw'}, {'name': 'Draco', 'house': 'Slytherin'}, {'name': 'Harry', 'house': 'Gryffindor'}]
"""
```

Meskipun ini berhasil, kami harus menulis seluruh fungsi yang hanya kami gunakan satu kali, kami dapat membuat kode kami lebih mudah dibaca dengan menggunakan fungsi lambda:

```
people = [
    {"name": "Harry", "house": "Gryffindor"},
    {"name": "Cho", "house": "Ravenclaw"},
    {"name": "Draco", "house": "Slytherin"}
]

people.sort(key=lambda person: person["name"])

print(people)

""" Output:
[{'name': 'Cho', 'house': 'Ravenclaw'}, {'name': 'Draco', 'house': 'Slytherin'}, {'name': 'Harry', 'house': 'Gryffindor'}]
"""
```

## [Pengecualian](https://cs50.harvard.edu/web/2020/notes/2/#exceptions)

Selama kuliah ini, kita menemukan beberapa pengecualian yang berbeda, jadi sekarang kita akan melihat beberapa cara baru untuk menghadapinya.

Dalam potongan kode berikut, kami akan mengambil dua bilangan bulat dari pengguna, dan mencoba membaginya:

```
x = int(input("x: "))
y = int(input("y: "))

result = x / y

print(f"{x} / {y} = {result}")
```

Dalam banyak kasus, program ini bekerja dengan baik:

![Contoh yang baik](https://cs50.harvard.edu/web/2020/notes/2/images/dividegood.png)

Namun, kami akan mengalami masalah saat mencoba membaginya dengan 0:

![Contoh buruk](https://cs50.harvard.edu/web/2020/notes/2/images/dividebad.png)

Kita dapat mengatasi kesalahan yang berantakan ini menggunakan [Penanganan Pengecualian](https://www.w3schools.com/python/python_try_except.asp) . Pada blok kode berikut ini, kita akan `try`membagi kedua bilangan tersebut, `except`ketika kita mendapatkan `ZeroDivisionError`:

```
import sys

x = int(input("x: "))
y = int(input("y: "))

try:
    result = x / y
except ZeroDivisionError:
    print("Error: Cannot divide by 0.")
    # Exit the program
    sys.exit(1)

print(f"{x} / {y} = {result}")
```

Dalam hal ini, ketika kami mencobanya lagi:

![Bagilah dengan 0 pengecualian](https://cs50.harvard.edu/web/2020/notes/2/images/divide0.png)

Namun, kami masih mengalami kesalahan saat pengguna memasukkan bukan angka untuk x dan y:

![Kesalahan nilai](https://cs50.harvard.edu/web/2020/notes/2/images/valueError.png)

Kita bisa memecahkan masalah ini dengan cara yang sama!

```
import sys

try:
    x = int(input("x: "))
    y = int(input("y: "))
except ValueError:
    print("Error: Invalid input")
    sys.exit(1)

try:
    result = x / y
except ZeroDivisionError:
    print("Error: Cannot divide by 0.")
    # Exit the program
    sys.exit(1)

print(f"{x} / {y} = {result}")
```

Itu saja untuk kuliah ini! Lain kali, kita akan menggunakan Modul Python `Django`untuk membuat beberapa aplikasi!
# [Kuliah 7](https://cs50.harvard.edu/web/2020/notes/7/#lecture-7)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/7/#introduction)
-   [Pengujian](https://cs50.harvard.edu/web/2020/notes/7/#testing)
-   [Menegaskan](https://cs50.harvard.edu/web/2020/notes/7/#assert)
    -   [Pengembangan Berbasis Tes](https://cs50.harvard.edu/web/2020/notes/7/#test-driven-development)
-   [Pengujian Unit](https://cs50.harvard.edu/web/2020/notes/7/#unit-testing)
-   [Pengujian Django](https://cs50.harvard.edu/web/2020/notes/7/#django-testing)
    -   [Pengujian Klien](https://cs50.harvard.edu/web/2020/notes/7/#client-testing)
-   [Selenium](https://cs50.harvard.edu/web/2020/notes/7/#selenium)
-   [CI/CD](https://cs50.harvard.edu/web/2020/notes/7/#cicd)
-   [Tindakan GitHub](https://cs50.harvard.edu/web/2020/notes/7/#github-actions)
-   [Buruh pelabuhan](https://cs50.harvard.edu/web/2020/notes/7/#docker)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/7/#introduction)

-   Sejauh ini, kita telah membahas cara membuat halaman web sederhana menggunakan HTML dan CSS, serta cara menggunakan Git dan GitHub untuk melacak perubahan pada kode kita dan berkolaborasi dengan orang lain. Kami juga membiasakan diri dengan bahasa pemrograman Python, mulai menggunakan Django untuk membuat aplikasi web, dan mempelajari cara menggunakan model Django untuk menyimpan informasi di situs kami. Kami kemudian memperkenalkan JavaScript dan belajar bagaimana menggunakannya untuk membuat halaman web lebih interaktif, dan berbicara tentang penggunaan animasi dan React untuk lebih meningkatkan Antarmuka Pengguna kami.
-   Hari ini, kita akan belajar tentang praktik terbaik saat mengerjakan dan meluncurkan proyek yang lebih besar.

## [Pengujian](https://cs50.harvard.edu/web/2020/notes/7/#testing)

Salah satu bagian penting dari proses pengembangan perangkat lunak adalah tindakan **Menguji** kode yang telah kami tulis untuk memastikan semuanya berjalan seperti yang kami harapkan. Dalam kuliah ini, kita akan membahas beberapa cara untuk meningkatkan cara kita menguji kode kita.

## [Menegaskan](https://cs50.harvard.edu/web/2020/notes/7/#assert)

Salah satu cara paling sederhana untuk menjalankan pengujian dengan Python adalah dengan menggunakan `assert`perintah. Perintah ini diikuti oleh beberapa ekspresi yang seharusnya `True`. Jika ekspresi adalah `True`, tidak akan terjadi apa-apa, dan jika ya `False`, pengecualian akan dilemparkan. Mari kita lihat bagaimana kita dapat memasukkan perintah untuk menguji `square`fungsi yang kita tulis saat pertama kali mempelajari Python. Ketika fungsi ditulis dengan benar, tidak ada yang terjadi sebagaimana `assert`adanya`True`

```
def square(x):
    return x * x

assert square(10) == 100

""" Output:

"""
```

Dan kemudian ketika ditulis salah, pengecualian dilemparkan.

```
def square(x):
    return x + x

assert square(10) == 100

""" Output:
Traceback (most recent call last):
  File "assert.py", line 4, in <module>
    assert square(10) == 100
AssertionError
"""
```

### [Pengembangan Berbasis Tes](https://cs50.harvard.edu/web/2020/notes/7/#test-driven-development)

Saat Anda mulai membangun proyek yang lebih besar, Anda mungkin ingin mempertimbangkan untuk menggunakan **pengembangan berbasis pengujian** , gaya pengembangan di mana setiap kali Anda memperbaiki bug, Anda menambahkan pengujian yang memeriksa bug tersebut ke rangkaian pengujian yang terus bertambah yang dijalankan setiap kali Anda membuat perubahan. Ini akan membantu Anda memastikan bahwa fitur tambahan yang Anda tambahkan ke proyek tidak mengganggu fitur yang sudah ada.

Sekarang, mari kita lihat fungsi yang sedikit lebih rumit, dan pikirkan tentang bagaimana menulis tes dapat membantu kita menemukan kesalahan. Sekarang kita akan menulis sebuah fungsi bernama `is_prime`yang mengembalikan `True`jika dan hanya jika masukannya prima:

```
import math

def is_prime(n):

    # We know numbers less than 2 are not prime
    if n < 2:
        return False

    # Checking factors up to sqrt(n)
    for i in range(2, int(math.sqrt(n))):

        # If i is a factor, return false
        if n % i == 0:
            return False

    # If no factors were found, return true
    return True
```

Sekarang, mari kita lihat fungsi yang telah kita tulis untuk menguji `prime`fungsi kita:

```
from prime import is_prime

def test_prime(n, expected):
    if is_prime(n) != expected:
        print(f"ERROR on is_prime({n}), expected {expected}")
```

Pada titik ini, kita bisa masuk ke juru bahasa python kita dan menguji beberapa nilai:

```
>>> test_prime(5, True)
>>> test_prime(10, False)
>>> test_prime(25, False)
ERROR on is_prime(25), expected False
```

Kita dapat melihat dari output di atas bahwa 5 dan 10 diidentifikasi dengan benar sebagai prima dan bukan prima, tetapi 25 salah diidentifikasi sebagai prima, jadi pasti ada yang salah dengan fungsi kita. Sebelum kita melihat apa yang salah dengan fungsi kita, mari kita lihat cara mengotomatiskan pengujian kita. Salah satu cara kita dapat melakukannya adalah dengan membuat **skrip shell** , atau beberapa skrip yang dapat dijalankan di dalam terminal kita. File-file ini memerlukan `.sh`ekstensi, jadi file kami akan dipanggil `tests0.sh`. Setiap baris di bawah ini terdiri dari

1.  A `python3`untuk menentukan versi Python yang sedang kita jalankan
2.  A `-c`untuk menunjukkan bahwa kami ingin menjalankan perintah
3.  Perintah untuk dijalankan dalam format string

```
python3 -c "from tests0 import test_prime; test_prime(1, False)"
python3 -c "from tests0 import test_prime; test_prime(2, True)"
python3 -c "from tests0 import test_prime; test_prime(8, False)"
python3 -c "from tests0 import test_prime; test_prime(11, True)"
python3 -c "from tests0 import test_prime; test_prime(25, False)"
python3 -c "from tests0 import test_prime; test_prime(28, False)"
```

Sekarang kita dapat menjalankan perintah ini dengan menjalankan `./tests0.sh`di terminal kita, memberi kita hasil ini:

```
ERROR on is_prime(8), expected False
ERROR on is_prime(25), expected False
```

## [Pengujian Unit](https://cs50.harvard.edu/web/2020/notes/7/#unit-testing)

Meskipun kami dapat menjalankan pengujian secara otomatis menggunakan metode di atas, kami mungkin masih ingin menghindari keharusan menulis setiap pengujian tersebut. Untungnya, kita bisa menggunakan pustaka Python `unittest`untuk membuat proses ini sedikit lebih mudah. Mari kita lihat seperti apa program pengujian untuk `is_prime`fungsi kita.

```
# Import the unittest library and our function
import unittest
from prime import is_prime

# A class containing all of our tests
class Tests(unittest.TestCase):

    def test_1(self):
        """Check that 1 is not prime."""
        self.assertFalse(is_prime(1))

    def test_2(self):
        """Check that 2 is prime."""
        self.assertTrue(is_prime(2))

    def test_8(self):
        """Check that 8 is not prime."""
        self.assertFalse(is_prime(8))

    def test_11(self):
        """Check that 11 is prime."""
        self.assertTrue(is_prime(11))

    def test_25(self):
        """Check that 25 is not prime."""
        self.assertFalse(is_prime(25))

    def test_28(self):
        """Check that 28 is not prime."""
        self.assertFalse(is_prime(28))


# Run each of the testing functions
if __name__ == "__main__":
    unittest.main()
```

Perhatikan bahwa setiap fungsi di dalam `Tests`kelas kita mengikuti sebuah pola:

-   Nama fungsi diawali dengan `test_`. Ini diperlukan agar fungsi dapat dijalankan secara otomatis dengan panggilan ke `unittest.main()`.
-   Setiap tes mengambil argumen `self`. Ini standar saat menulis metode dalam kelas Python.
-   Baris pertama dari setiap fungsi berisi sebuah **docstring** yang diapit oleh tiga tanda kutip. Ini bukan hanya untuk keterbacaan kode. Saat tes dijalankan, komentar akan ditampilkan sebagai deskripsi tes jika gagal.
-   Baris berikutnya dari setiap fungsi berisi pernyataan dalam bentuk `self.assertSOMETHING`. Ada banyak pernyataan berbeda yang dapat Anda buat termasuk `assertTrue`, `assertFalse`, `assertEqual`, dan `assertGreater`. Anda dapat menemukan yang ini dan lainnya dengan melihat [dokumentasinya](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertEqual) .

Sekarang, mari kita periksa hasil tes ini:

```
...F.F
======================================================================
FAIL: test_25 (__main__.Tests)
Check that 25 is not prime.
----------------------------------------------------------------------
Traceback (most recent call last):
  File "tests1.py", line 26, in test_25
    self.assertFalse(is_prime(25))
AssertionError: True is not false

======================================================================
FAIL: test_8 (__main__.Tests)
Check that 8 is not prime.
----------------------------------------------------------------------
Traceback (most recent call last):
  File "tests1.py", line 18, in test_8
    self.assertFalse(is_prime(8))
AssertionError: True is not false

----------------------------------------------------------------------
Ran 6 tests in 0.001s

FAILED (failures=2)
```

Setelah menjalankan tes, `unittest`beri kami beberapa informasi berguna tentang apa yang ditemukannya. Di baris pertama, ini memberi kita serangkaian `.`s untuk sukses dan `F`s untuk kegagalan sesuai urutan pengujian kami ditulis.

```
...F.F
```

Selanjutnya, untuk setiap pengujian yang gagal, kita diberi nama fungsi yang gagal:

```
FAIL: test_25 (__main__.Tests)
```

komentar deskriptif yang kami berikan sebelumnya:

```
Check that 25 is not prime.
```

Dan traceback untuk pengecualian:

```
Traceback (most recent call last):
  File "tests1.py", line 26, in test_25
    self.assertFalse(is_prime(25))
AssertionError: True is not false
```

Dan akhirnya, kita diberi tahu berapa banyak tes yang dijalankan, berapa banyak waktu yang dibutuhkan, dan berapa banyak yang gagal:

```
Ran 6 tests in 0.001s

FAILED (failures=2)
```

Sekarang mari kita lihat memperbaiki bug di fungsi kita. Ternyata kita perlu menguji satu nomor tambahan di `for`loop kita. Misalnya, ketika `n`adalah `25`, akar kuadratnya adalah `5`, tetapi ketika itu adalah salah satu argumen dalam `range`fungsi, `for`perulangan berakhir pada angka `4`. Oleh karena itu, kita cukup mengubah tajuk `for`loop kita menjadi:

```
for i in range(2, int(math.sqrt(n)) + 1):
```

Sekarang, ketika kami menjalankan pengujian lagi menggunakan unit test kami, kami mendapatkan output berikut, yang menunjukkan bahwa perubahan kami telah memperbaiki bug.

```
......
----------------------------------------------------------------------
Ran 6 tests in 0.000s

OK
```

Tes otomatis ini akan menjadi lebih berguna saat Anda bekerja untuk mengoptimalkan fungsi ini. Misalnya, Anda mungkin ingin menggunakan fakta bahwa Anda tidak perlu mencentang semua bilangan bulat sebagai faktor, hanya bilangan prima yang lebih kecil (jika suatu bilangan tidak habis dibagi 3, bilangan itu juga tidak habis dibagi 6, 9, 12, …) , atau Anda mungkin ingin menggunakan uji primalitas probabilistik yang lebih canggih seperti uji primalitas [Fermat](https://en.wikipedia.org/wiki/Fermat_primality_test) dan [Miller-Rabin](https://en.wikipedia.org/wiki/Miller%E2%80%93Rabin_primality_test) . Setiap kali Anda membuat perubahan untuk meningkatkan fungsi ini, Anda akan menginginkan kemampuan untuk menjalankan pengujian unit dengan mudah lagi untuk memastikan fungsi Anda masih benar.

## [Pengujian Django](https://cs50.harvard.edu/web/2020/notes/7/#django-testing)

Sekarang, mari kita lihat bagaimana kita dapat menerapkan ide pengujian otomatis saat membuat aplikasi Django. Saat bekerja dengan ini, kami akan menggunakan `flights`proyek yang kami buat saat pertama kali mempelajari tentang model Django. Pertama-tama kita akan menambahkan metode ke `Flight`model kita yang memverifikasi bahwa sebuah penerbangan valid dengan memeriksa dua kondisi:

1.  Asal tidak sama dengan tujuan
2.  Durasinya lebih dari 0 menit

Sekarang, model kita bisa terlihat seperti ini:

```
class Flight(models.Model):
    origin = models.ForeignKey(Airport, on_delete=models.CASCADE, related_name="departures")
    destination = models.ForeignKey(Airport, on_delete=models.CASCADE, related_name="arrivals")
    duration = models.IntegerField()

    def __str__(self):
        return f"{self.id}: {self.origin} to {self.destination}"

    def is_valid_flight(self):
        return self.origin != self.destination or self.duration > 0
```

Untuk memastikan aplikasi kita berfungsi seperti yang diharapkan, setiap kali kita membuat aplikasi baru, kita secara otomatis diberi file `tests.py`. [Ketika kami pertama kali membuka file ini, kami melihat bahwa pustaka TestCase](https://docs.djangoproject.com/en/4.0/topics/testing/overview/) Django secara otomatis diimpor:

```
from django.test import TestCase
```

Satu keuntungan menggunakan `TestCase`pustaka ini adalah saat kami menjalankan pengujian, database yang benar-benar baru akan dibuat hanya untuk tujuan pengujian. Hal ini berguna karena kami menghindari risiko tidak sengaja memodifikasi atau menghapus entri yang ada di basis data kami dan kami tidak perlu khawatir menghapus entri dummy yang kami buat hanya untuk pengujian.

Untuk mulai menggunakan pustaka ini, pertama-tama kita ingin mengimpor semua model kita:

```
from .models import Flight, Airport, Passenger
```

Dan kemudian kita akan membuat kelas baru yang memperluas `TestCase`kelas yang baru saja kita impor. Di dalam class ini, kita akan mendefinisikan sebuah `setUp`fungsi yang akan dijalankan pada awal proses pengujian. Dalam fungsi ini, kita mungkin ingin membuat. Inilah tampilan kelas kita untuk memulai:

```
class FlightTestCase(TestCase):

    def setUp(self):

        # Create airports.
        a1 = Airport.objects.create(code="AAA", city="City A")
        a2 = Airport.objects.create(code="BBB", city="City B")

        # Create flights.
        Flight.objects.create(origin=a1, destination=a2, duration=100)
        Flight.objects.create(origin=a1, destination=a1, duration=200)
        Flight.objects.create(origin=a1, destination=a2, duration=-100)
```

Sekarang kita memiliki beberapa entri dalam database pengujian kita, mari tambahkan beberapa fungsi ke kelas ini untuk melakukan beberapa pengujian. Pertama, mari kita pastikan kolom `departures`and `arrivals`berfungsi dengan benar dengan mencoba menghitung jumlah keberangkatan (yang kita tahu seharusnya 3) dan kedatangan (yang seharusnya 1) dari bandara `AAA`:

```
def test_departures_count(self):
    a = Airport.objects.get(code="AAA")
    self.assertEqual(a.departures.count(), 3)

def test_arrivals_count(self):
    a = Airport.objects.get(code="AAA")
    self.assertEqual(a.arrivals.count(), 1)
```

Kami juga dapat menguji `is_valid_flight`fungsi yang kami tambahkan ke `Flight`model kami. Kami akan mulai dengan menyatakan bahwa fungsi mengembalikan true saat penerbangan valid:

```
def test_valid_flight(self):
    a1 = Airport.objects.get(code="AAA")
    a2 = Airport.objects.get(code="BBB")
    f = Flight.objects.get(origin=a1, destination=a2, duration=100)
    self.assertTrue(f.is_valid_flight())
```

Selanjutnya, mari pastikan bahwa penerbangan dengan tujuan dan durasi yang tidak valid menampilkan false:

```
def test_invalid_flight_destination(self):
    a1 = Airport.objects.get(code="AAA")
    f = Flight.objects.get(origin=a1, destination=a1)
    self.assertFalse(f.is_valid_flight())

def test_invalid_flight_duration(self):
    a1 = Airport.objects.get(code="AAA")
    a2 = Airport.objects.get(code="BBB")
    f = Flight.objects.get(origin=a1, destination=a2, duration=-100)
    self.assertFalse(f.is_valid_flight())
```

Sekarang, untuk menjalankan pengujian kami, kami akan menjalankan `python manage.py test`. Keluaran untuk ini hampir identik dengan keluaran yang kita lihat saat menggunakan `unittest`pustaka Python, meskipun ia juga mencatat bahwa ia membuat dan menghancurkan basis data pengujian:

```
Creating test database for alias 'default'...
System check identified no issues (0 silenced).
..FF.
======================================================================
FAIL: test_invalid_flight_destination (flights.tests.FlightTestCase)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/Users/cleggett/Documents/cs50/web_notes_files/7/django/airline/flights/tests.py", line 37, in test_invalid_flight_destination
    self.assertFalse(f.is_valid_flight())
AssertionError: True is not false

======================================================================
FAIL: test_invalid_flight_duration (flights.tests.FlightTestCase)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/Users/cleggett/Documents/cs50/web_notes_files/7/django/airline/flights/tests.py", line 43, in test_invalid_flight_duration
    self.assertFalse(f.is_valid_flight())
AssertionError: True is not false

----------------------------------------------------------------------
Ran 5 tests in 0.018s

FAILED (failures=2)
Destroying test database for alias 'default'...
```

Kita dapat melihat dari output di atas bahwa ada kalanya `is_valid_flight`dikembalikan `True`ketika seharusnya kembali `False`. Kita dapat melihat, setelah memeriksa fungsi kita lebih lanjut, bahwa kita membuat kesalahan dengan menggunakan `or`bukan `and`, artinya hanya satu persyaratan penerbangan yang harus dipenuhi agar penerbangan tersebut valid. Jika kita mengubah fungsinya menjadi ini:

```
 def is_valid_flight(self):
    return self.origin != self.destination and self.duration > 0
```

Kami kemudian dapat menjalankan tes lagi dengan hasil yang lebih baik:

```
Creating test database for alias 'default'...
System check identified no issues (0 silenced).
.....
----------------------------------------------------------------------
Ran 5 tests in 0.014s

OK
Destroying test database for alias 'default'...
```

### [Pengujian Klien](https://cs50.harvard.edu/web/2020/notes/7/#client-testing)

Saat membuat aplikasi web, kami mungkin ingin memeriksa tidak hanya apakah fungsi tertentu berfungsi atau tidak, tetapi juga apakah halaman web individual dimuat sebagaimana dimaksud atau tidak. Kita bisa melakukan ini dengan membuat `Client`objek di kelas pengujian Django kita, dan kemudian membuat permintaan menggunakan objek itu. Untuk melakukan ini, pertama-tama kita harus menambahkan `Client`impor kita:

```
from django.test import Client, TestCase

```

Misalnya, sekarang mari kita tambahkan pengujian yang memastikan bahwa kita mendapatkan kode respons HTTP 200 dan ketiga penerbangan kita ditambahkan ke konteks respons:

```
def test_index(self):

    # Set up client to make requests
    c = Client()

    # Send get request to index page and store response
    response = c.get("/flights/")

    # Make sure status code is 200
    self.assertEqual(response.status_code, 200)

    # Make sure three flights are returned in the context
    self.assertEqual(response.context["flights"].count(), 3)
```

Kami juga dapat memeriksa untuk memastikan kami mendapatkan kode respons yang valid untuk halaman penerbangan yang valid, dan kode respons yang tidak valid untuk halaman penerbangan yang tidak ada. (Perhatikan bahwa kami menggunakan `Max`fungsi untuk menemukan maximum `id`, yang dapat kami akses dengan menyertakannya `from django.db.models import Max`di bagian atas file kami)

```
def test_valid_flight_page(self):
    a1 = Airport.objects.get(code="AAA")
    f = Flight.objects.get(origin=a1, destination=a1)

    c = Client()
    response = c.get(f"/flights/{f.id}")
    self.assertEqual(response.status_code, 200)

def test_invalid_flight_page(self):
    max_id = Flight.objects.all().aggregate(Max("id"))["id__max"]

    c = Client()
    response = c.get(f"/flights/{max_id + 1}")
    self.assertEqual(response.status_code, 404)
```

Terakhir, mari tambahkan beberapa pengujian untuk memastikan daftar penumpang dan non-penumpang dihasilkan seperti yang diharapkan:

```
def test_flight_page_passengers(self):
    f = Flight.objects.get(pk=1)
    p = Passenger.objects.create(first="Alice", last="Adams")
    f.passengers.add(p)

    c = Client()
    response = c.get(f"/flights/{f.id}")
    self.assertEqual(response.status_code, 200)
    self.assertEqual(response.context["passengers"].count(), 1)

def test_flight_page_non_passengers(self):
    f = Flight.objects.get(pk=1)
    p = Passenger.objects.create(first="Alice", last="Adams")

    c = Client()
    response = c.get(f"/flights/{f.id}")
    self.assertEqual(response.status_code, 200)
    self.assertEqual(response.context["non_passengers"].count(), 1)
```

Sekarang, kita dapat menjalankan semua pengujian kita bersama-sama, dan melihat bahwa saat ini kita tidak memiliki kesalahan!

```
Creating test database for alias 'default'...
System check identified no issues (0 silenced).
..........
----------------------------------------------------------------------
Ran 10 tests in 0.048s

OK
Destroying test database for alias 'default'...
```

## [Selenium](https://cs50.harvard.edu/web/2020/notes/7/#selenium)

Sejauh ini, kami dapat menguji kode sisi server yang telah kami tulis menggunakan Python dan Django, tetapi saat kami membangun aplikasi, kami ingin kemampuan membuat pengujian untuk kode sisi klien kami sebagai Sehat. Sebagai contoh, mari berpikir kembali ke `counter.html`halaman kita dan bekerja menulis beberapa tes untuk itu.

Kami akan mulai dengan menulis halaman penghitung yang sedikit berbeda di mana kami menyertakan tombol untuk mengurangi hitungan:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Counter</title>
        <script>
            
            // Wait for page to load
            document.addEventListener('DOMContentLoaded', () => {

                // Initialize variable to 0
                let counter = 0;

                // If increase button clicked, increase counter and change inner html
                document.querySelector('#increase').onclick = () => {
                    counter ++;
                    document.querySelector('h1').innerHTML = counter;
                }

                // If decrease button clicked, decrease counter and change inner html
                document.querySelector('#decrease').onclick = () => {
                    counter --;
                    document.querySelector('h1').innerHTML = counter;
                }
            })
        </script>
    </head>
    <body>
        <h1>0</h1>
        <button id="increase">+</button>
        <button id="decrease">-</button>
    </body>
</html>
```

Sekarang jika kita ingin menguji kode ini, kita tinggal membuka web browser kita, klik dua tombol, dan amati apa yang terjadi. Namun, ini akan menjadi sangat membosankan saat Anda menulis aplikasi satu halaman yang lebih besar dan lebih besar, itulah sebabnya beberapa kerangka kerja telah dibuat yang membantu pengujian dalam browser, salah satunya disebut [Selenium](https://www.selenium.dev/) .

Dengan menggunakan Selenium, kita akan dapat menentukan file pengujian dengan Python tempat kita dapat mensimulasikan pengguna membuka browser web, menavigasi ke halaman kita, dan berinteraksi dengannya. Alat utama kami saat melakukan ini dikenal sebagai **Driver Web** , yang akan membuka browser web di komputer Anda. Mari kita lihat bagaimana kita bisa mulai menggunakan perpustakaan ini untuk mulai berinteraksi dengan halaman. Perhatikan bahwa di bawah ini kami menggunakan keduanya `selenium`dan `ChromeDriver`. Selenium dapat diinstal untuk python dengan menjalankan `pip install selenium`, dan `ChromeDriver`dapat diinstal dengan menjalankan`pip install chromedriver-py`

```
import os
import pathlib
import unittest

from selenium import webdriver

# Finds the Uniform Resourse Identifier of a file
def file_uri(filename):
    return pathlib.Path(os.path.abspath(filename)).as_uri()

# Sets up web driver using Google chrome
driver = webdriver.Chrome()
```

Kode di atas adalah semua penyiapan dasar yang kita butuhkan, jadi sekarang kita bisa menggunakan beberapa kegunaan yang lebih menarik dengan menggunakan interpreter Python. Satu catatan tentang beberapa baris pertama adalah bahwa untuk menargetkan halaman tertentu, kita memerlukan **Uniform Resource Identifier (URI)** halaman tersebut yang merupakan string unik yang mewakili sumber daya tersebut.

```
# Find the URI of our newly created file
>>> uri = file_uri("counter.html")

# Use the URI to open the web page
>>> driver.get(uri)

# Access the title of the current page
>>> driver.title
'Counter'

# Access the source code of the page
>>> driver.page_source
'<html lang="en"><head>\n        <title>Counter</title>\n        <script>\n            \n            // Wait for page to load\n            document.addEventListener(\'DOMContentLoaded\', () => {\n\n                // Initialize variable to 0\n                let counter = 0;\n\n                // If increase button clicked, increase counter and change inner html\n                document.querySelector(\'#increase\').onclick = () => {\n                    counter ++;\n                    document.querySelector(\'h1\').innerHTML = counter;\n                }\n\n                // If decrease button clicked, decrease counter and change inner html\n                document.querySelector(\'#decrease\').onclick = () => {\n                    counter --;\n                    document.querySelector(\'h1\').innerHTML = counter;\n                }\n            })\n        </script>\n    </head>\n    <body>\n        <h1>0</h1>\n        <button id="increase">+</button>\n        <button id="decrease">-</button>\n    \n</body></html>'

# Find and store the increase and decrease buttons:
>>> increase = driver.find_element_by_id("increase")
>>> decrease = driver.find_element_by_id("decrease")

# Simulate the user clicking on the two buttons
>>> increase.click()
>>> increase.click()
>>> decrease.click()

# We can even include clicks within other Python constructs:
>>> for i in range(25):
...     increase.click()
```

Sekarang mari kita lihat bagaimana kita dapat menggunakan simulasi ini untuk membuat pengujian otomatis pada halaman kita:

```
# Standard outline of testing class
class WebpageTests(unittest.TestCase):

    def test_title(self):
        """Make sure title is correct"""
        driver.get(file_uri("counter.html"))
        self.assertEqual(driver.title, "Counter")

    def test_increase(self):
        """Make sure header updated to 1 after 1 click of increase button"""
        driver.get(file_uri("counter.html"))
        increase = driver.find_element_by_id("increase")
        increase.click()
        self.assertEqual(driver.find_element_by_tag_name("h1").text, "1")

    def test_decrease(self):
        """Make sure header updated to -1 after 1 click of decrease button"""
        driver.get(file_uri("counter.html"))
        decrease = driver.find_element_by_id("decrease")
        decrease.click()
        self.assertEqual(driver.find_element_by_tag_name("h1").text, "-1")

    def test_multiple_increase(self):
        """Make sure header updated to 3 after 3 clicks of increase button"""
        driver.get(file_uri("counter.html"))
        increase = driver.find_element_by_id("increase")
        for i in range(3):
            increase.click()
        self.assertEqual(driver.find_element_by_tag_name("h1").text, "3")

if __name__ == "__main__":
    unittest.main()
```

Sekarang, jika kita jalankan `python tests.py`, simulasi kita akan dilakukan di browser, lalu hasil pengujian akan dicetak ke konsol. Berikut adalah contoh dari apa yang mungkin terlihat ketika kita memiliki bug dalam kode pengujian gagal:

![tes selenium gagal](https://cs50.harvard.edu/web/2020/notes/7/images/fail.gif)

## [CI/CD](https://cs50.harvard.edu/web/2020/notes/7/#cicd)

**CI/CD**, which stands for **Continuous Integration and Continuous Delivery**, is a set of software development best practices that dictate how code is written by a team of people, and how that code is later delivered to users of the application. As the name implies, this method consists of two main parts:

-   Continuous Integration:
    -   Frequent merges to the main branch
    -   Automated unit testing with each merge
-   Continuous Delivery:
    -   Short release schedules, meaning new versions of an application are released frequently.

CI/CD has become more and more popular among software development teams for a number of reasons:

-   When different team members are working on different features, many compatibility issues can arise when multiple features are combined at the same time. Continuous integration allows teams to tackle small conflicts as they come.
-   Because unit tests are run with each Merge, when a test fails it is easier to isolate the part of the code that is causing the problem.
-   Frequently releasing new versions of an application allows developers to isolate problems if they arise after launch.
-   Releasing small, incremental changes allows users to slowly get used to new app features rather than being overwhelmed with an entirely different version
-   Not waiting to release new features allows companies to stay ahead in a competitive market.

## [GitHub Actions](https://cs50.harvard.edu/web/2020/notes/7/#github-actions)

One popular tool used to help with continuous integration is known as [GitHub Actions](https://github.com/features/actions). GitHub Actions will allow us to create workflows where we can specify certain actions to be performed every time someone pushes to a git repository. For example, we might want to check with every push that a style guide is adhered to, or that a set of unit tests is passed.

In order to set up a GitHub action, we’ll use a configuration language called **YAML**. YAML structures its data around key-value pairs (like a JSON object or Python Dictionary). Here’s an example of a simple YAML file:

```
key1: value1
key2: value2
key3:
    - item1
    - item2
    - item3
```

Sekarang, mari kita lihat contoh bagaimana kita mengonfigurasi file YAML (yang mengambil bentuk `name.yml`atau `name.yaml`) yang berfungsi dengan GitHub Actions. Untuk melakukan ini, saya akan membuat `.github`direktori di repositori saya, lalu `workflows`direktori di dalamnya, dan terakhir `ci.yml`file di dalamnya. Dalam file itu, kami akan menulis:

```
name: Testing
on: push

jobs:
  test_project:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Run Django unit tests
      run: |
        pip3 install --user django
        python3 manage.py test
```

Karena ini adalah pertama kalinya kita menggunakan GitHub Actions, mari kita lihat apa yang dilakukan setiap bagian dari file ini:

-   Pertama, kami memberikan alur kerja a `name`, yang dalam kasus kami adalah Testing.
-   Selanjutnya, dengan `on`kunci, kami menentukan kapan alur kerja harus dijalankan. Dalam kasus kami, kami ingin melakukan pengujian setiap kali seseorang mendorong ke repositori.
-   File lainnya terdapat di dalam `jobs`kunci, yang menunjukkan pekerjaan mana yang harus dijalankan pada setiap dorongan.
    -   Dalam kasus kami, satu-satunya pekerjaan adalah `test_project`. Setiap pekerjaan harus mendefinisikan dua komponen
        -   Kuncinya `runs-on`menentukan mesin virtual GitHub mana yang kita inginkan untuk menjalankan kode kita.
        -   Kuncinya `steps`menyediakan tindakan yang harus dilakukan saat pekerjaan ini dijalankan
            -   Di `uses`kunci kami menentukan tindakan GitHub mana yang ingin kami gunakan. `actions/checkout@v2`adalah tindakan yang ditulis oleh GitHub yang dapat kita gunakan.
            -   Kuncinya `name`di sini memungkinkan kami memberikan deskripsi tentang tindakan yang kami lakukan
            -   Setelah `run`kunci, kami mengetik perintah yang ingin kami jalankan di server GitHub. Dalam kasus kami, kami ingin menginstal Django dan kemudian menjalankan file pengujian.

Sekarang, mari buka repositori kita di GitHub dan lihat beberapa tab di dekat bagian atas halaman:

-   **Kode** : Ini adalah tab yang paling sering kami gunakan, karena ini memungkinkan kami untuk melihat file dan folder di dalam direktori kami.
-   **Masalah** : Di sini kita dapat membuka dan menutup masalah, yang merupakan permintaan untuk perbaikan bug atau fitur baru. Kita dapat menganggap ini sebagai daftar tugas untuk aplikasi kita.
-   **Tarik Permintaan** : Permintaan dari orang yang ingin menggabungkan beberapa kode dari satu cabang ke cabang lainnya. Ini adalah alat yang berguna, karena memungkinkan orang untuk melakukan **tinjauan kode** di mana mereka berkomentar dan memberikan saran sebelum kode diintegrasikan ke dalam cabang master.
-   **GitHub Actions** : Ini adalah tab yang akan kita gunakan saat mengerjakan continuous integration, karena tab ini menyediakan log tindakan yang telah dilakukan setelah setiap push.

Di sini, mari kita bayangkan bahwa kita mendorong perubahan kita _sebelum_ memperbaiki bug yang kita miliki dalam `is_valid_flight`fungsi di `models.py`dalam proyek kita `airport`. Kami sekarang dapat menavigasi ke tab **GitHub Actions** , klik pada push terbaru kami, klik pada tindakan yang gagal, dan lihat log:

![tindakan](https://cs50.harvard.edu/web/2020/notes/7/images/action.gif)

Sekarang, setelah memperbaiki bug, kami dapat melakukan bushing lagi dan menemukan hasil yang lebih baik:

![keberhasilan tindakan](https://cs50.harvard.edu/web/2020/notes/7/images/action_success.gif)

## [Buruh pelabuhan](https://cs50.harvard.edu/web/2020/notes/7/#docker)

Masalah dapat muncul dalam dunia pengembangan perangkat lunak ketika konfigurasi di komputer Anda berbeda dengan konfigurasi yang sedang dijalankan aplikasi Anda. Anda mungkin memiliki versi Python yang berbeda atau beberapa paket tambahan yang diinstal yang memungkinkan aplikasi berjalan dengan lancar di komputer Anda, sementara itu akan macet di server Anda. Untuk menghindari masalah ini, kami memerlukan cara untuk memastikan semua orang yang mengerjakan proyek menggunakan lingkungan yang sama. Salah satu cara untuk melakukannya adalah dengan menggunakan alat yang disebut **Docker** , yang merupakan perangkat lunak kontainerisasi, artinya ia menciptakan lingkungan yang terisolasi di dalam komputer Anda yang dapat distandarisasi di antara banyak kolaborator dan server tempat situs Anda dijalankan. Sementara Docker agak mirip dengan **Mesin Virtual**, mereka sebenarnya adalah teknologi yang berbeda. Mesin virtual (seperti yang digunakan pada GitHub Actions atau saat Anda meluncurkan server [AWS](https://cs50.harvard.edu/web/2020/notes/7/) ) secara efektif adalah seluruh komputer virtual dengan sistem operasinya sendiri, yang berarti ia akan memakan banyak ruang di mana pun ia dijalankan. Docker, di sisi lain, bekerja dengan menyiapkan wadah di dalam komputer yang ada, sehingga memakan lebih sedikit ruang.

Sekarang kita memiliki gagasan tentang apa itu wadah Docker, mari kita lihat bagaimana kita dapat mengonfigurasinya di komputer kita. Langkah pertama kita dalam melakukan ini adalah membuat **File Docker** yang akan kita beri nama `Dockerfile`. Di dalam file ini, kami akan memberikan petunjuk tentang cara membuat **Gambar Docker** yang menjelaskan pustaka dan binari yang ingin kami sertakan dalam wadah kami. Berikut ini contoh `Dockerfile`tampilan kami:

```
FROM python:3
COPY .  /usr/src/app
WORKDIR /usr/src/app
RUN pip install -r requirements.txt
CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]
```

Di sini, kita akan melihat secara mendalam apa yang sebenarnya dilakukan oleh file di atas:

-   `FROM python3`: ini menunjukkan bahwa kami mendasarkan gambar ini dari gambar standar tempat Python 3 dipasang. Ini cukup umum saat menulis File Docker, karena memungkinkan Anda menghindari pekerjaan mendefinisikan ulang pengaturan dasar yang sama dengan setiap gambar baru.
-   `COPY . /usr/src/app`: Ini menunjukkan bahwa kami ingin menyalin semuanya dari direktori kami saat ini ( `.`) dan menyimpannya di `/usr/src/app`direktori di wadah baru kami.
-   `WORKDIR /usr/src/app`: Ini mengatur di mana kita akan menjalankan perintah di dalam wadah. (Agak seperti `cd`di terminal)
-   `RUN pip install -r requirements.txt`: Di baris ini, dengan asumsi Anda telah memasukkan semua persyaratan Anda ke file bernama `requirements.txt`, semuanya akan dipasang di dalam penampung.
-   `CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]`: Akhirnya, kami menentukan perintah yang harus dijalankan saat kami memulai wadah.

Sejauh ini di kelas ini, kami hanya menggunakan SQLite karena itu adalah sistem manajemen database default untuk Django. Dalam aplikasi langsung dengan pengguna nyata, SQLite hampir tidak pernah digunakan, karena tidak mudah diskalakan seperti sistem lain. Untungnya, jika kita ingin menjalankan server terpisah untuk database kita, kita cukup menambahkan wadah Docker lain, dan menjalankannya bersama-sama menggunakan fitur bernama **Docker Compose** . Ini akan memungkinkan dua server berbeda berjalan dalam wadah terpisah, tetapi juga dapat berkomunikasi satu sama lain. Untuk menentukan ini, kami akan menggunakan file YAML bernama `docker-compose.yml`:

```
version: '3'

services:
    db:
        image: postgres

    web:
        build: .
        volumes:
            - .:/usr/src/app
        ports:
            - "8000:8000"
```

Dalam file di atas kita:

-   Tentukan bahwa kami menggunakan Docker Compose versi 3
-   Garis besar dua layanan:
    -   `db`menyiapkan wadah basis data kami berdasarkan gambar yang sudah ditulis oleh Postgres.
    -   `web`menyiapkan wadah server kami dengan menginstruksikan Docker untuk:
        -   Gunakan Dockerfile di dalam direktori saat ini.
        -   Gunakan jalur yang ditentukan di dalam wadah.
        -   Tautkan port 8000 di dalam wadah ke port 8000 di komputer kita.

Sekarang, kami siap memulai layanan kami dengan perintah `docker-compose up`. Ini akan meluncurkan kedua server kami di dalam wadah Docker baru.

Pada titik ini, kita mungkin ingin menjalankan perintah di dalam wadah Docker kita untuk menambahkan entri basis data atau menjalankan pengujian. Untuk melakukannya, pertama-tama kita akan menjalankan `docker ps`untuk menampilkan semua kontainer buruh pelabuhan yang sedang berjalan. Kemudian, kita akan menemukan `CONTAINER ID`wadah yang ingin kita masuki dan jalankan `docker exec -it CONTAINER_ID bash -l`. Ini akan memindahkan Anda ke dalam `usr/src/app`direktori yang kami siapkan di dalam wadah kami. Kita dapat menjalankan perintah apa pun yang kita inginkan di dalam wadah itu dan kemudian keluar dengan menjalankan `CTRL-D`.

Itu saja untuk kuliah ini! Lain kali, kami akan berupaya meningkatkan proyek kami dan memastikannya aman.
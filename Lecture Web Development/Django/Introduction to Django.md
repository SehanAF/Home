# [Kuliah 3](https://cs50.harvard.edu/web/2020/notes/3/#lecture-3)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/3/#introduction)
-   [Aplikasi Web](https://cs50.harvard.edu/web/2020/notes/3/#web-applications)
-   [HTTP](https://cs50.harvard.edu/web/2020/notes/3/#http)
-   [Django](https://cs50.harvard.edu/web/2020/notes/3/#django)
-   [Rute](https://cs50.harvard.edu/web/2020/notes/3/#routes)
-   [Templat](https://cs50.harvard.edu/web/2020/notes/3/#templates)
    -   [Persyaratan:](https://cs50.harvard.edu/web/2020/notes/3/#conditionals)
    -   [Styling](https://cs50.harvard.edu/web/2020/notes/3/#styling)
-   [Tugas](https://cs50.harvard.edu/web/2020/notes/3/#tasks)
-   [Formulir](https://cs50.harvard.edu/web/2020/notes/3/#forms)
    -   [Formulir Django](https://cs50.harvard.edu/web/2020/notes/3/#django-forms)
-   [Sesi](https://cs50.harvard.edu/web/2020/notes/3/#sessions)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/3/#introduction)

-   Sejauh ini, kita telah membahas cara membuat halaman web sederhana menggunakan HTML dan CSS, serta cara menggunakan Git dan GitHub untuk melacak perubahan pada kode kita dan berkolaborasi dengan orang lain. Kami juga membiasakan diri dengan bahasa pemrograman Python.
-   Hari ini, kita akan menggunakan `Django`framework Python untuk membuat aplikasi dinamis.

## [Aplikasi Web](https://cs50.harvard.edu/web/2020/notes/3/#web-applications)

Sejauh ini, semua aplikasi web yang kami tulis bersifat **statis** . Ini berarti bahwa setiap kali kita membuka halaman web itu, tampilannya persis sama. Namun, banyak situs web yang kami kunjungi setiap hari berubah setiap kali kami mengunjunginya. Jika Anda mengunjungi situs web [New York Times](https://www.nytimes.com/) atau [Facebook](https://www.facebook.com/) , misalnya, kemungkinan besar Anda akan melihat hal yang berbeda hari ini daripada besok. Untuk situs besar seperti itu, tidak masuk akal bagi karyawan untuk mengedit file HTML besar secara manual setiap kali ada perubahan, di mana **dinamis**situs web bisa sangat berguna. Situs web dinamis adalah situs web yang memanfaatkan bahasa pemrograman (seperti Python) untuk menghasilkan file HTML dan CSS secara dinamis. Selama kuliah ini, kita akan belajar cara membuat aplikasi dinamis pertama kita.

## [HTTP](https://cs50.harvard.edu/web/2020/notes/3/#http)

HTTP, atau HyperText Transfer Protocol, adalah protokol yang diterima secara luas untuk bagaimana pesan ditransfer bolak-balik di internet. Biasanya, informasi online dilewatkan antara klien (pengguna) dan server. ![Klien dan Server](https://cs50.harvard.edu/web/2020/notes/3/images/client_server.png)

Dalam protokol ini, klien akan mengirim **permintaan** ke server, yang mungkin terlihat seperti di bawah ini. Pada contoh di bawah ini, `GET`hanyalah sebuah jenis permintaan, satu dari tiga yang akan kita bahas dalam kursus ini. Biasanya `/`menunjukkan bahwa kami sedang mencari beranda situs web, dan tiga titik menunjukkan bahwa kami juga dapat menyampaikan lebih banyak informasi. ![Meminta](https://cs50.harvard.edu/web/2020/notes/3/images/request.png)

Setelah menerima permintaan, server kemudian akan mengirimkan kembali respons HTTP, yang mungkin terlihat seperti di bawah ini. Tanggapan seperti itu akan menyertakan versi HTTP, kode status (200 berarti OK), deskripsi konten, dan kemudian beberapa informasi tambahan. ![Tanggapan](https://cs50.harvard.edu/web/2020/notes/3/images/response.png)

200 hanyalah salah satu dari banyak kode status, beberapa di antaranya mungkin pernah Anda lihat sebelumnya: ![Kode](https://cs50.harvard.edu/web/2020/notes/3/images/codes.png)

## [Django](https://cs50.harvard.edu/web/2020/notes/3/#django)

[Django](https://www.djangoproject.com/) adalah kerangka web berbasis Python yang memungkinkan kita menulis kode Python yang secara dinamis menghasilkan HTML dan CSS. Keuntungan menggunakan kerangka kerja seperti Django adalah banyak kode yang telah ditulis untuk kita yang dapat kita manfaatkan.

-   Untuk memulai, kita harus menginstal Django, yang berarti Anda juga harus [menginstal pip](https://pip.pypa.io/en/stable/installing/) jika Anda belum melakukannya.
-   Setelah Anda menginstal Pip, Anda dapat menjalankan `pip3 install Django`di terminal Anda untuk menginstal Django.

Setelah menginstal Django, kita dapat melalui langkah-langkah membuat proyek Django baru:

1.  Jalankan `django-admin startproject PROJECT_NAME`untuk membuat sejumlah file awal untuk proyek kami.
2.  Jalankan `cd PROJECT_NAME`untuk menavigasi ke direktori proyek baru Anda.
3.  Buka direktori di editor teks pilihan Anda. Anda akan melihat bahwa beberapa file telah dibuat untuk Anda. Kita tidak perlu melihat sebagian besar untuk saat ini, tetapi ada tiga yang akan sangat penting sejak awal:
    -   `manage.py`adalah apa yang kami gunakan untuk menjalankan perintah di terminal kami. Kami tidak perlu mengeditnya, tetapi kami akan sering menggunakannya.
    -   `settings.py`berisi beberapa pengaturan konfigurasi penting untuk proyek baru kami. Ada beberapa pengaturan default, tetapi kami mungkin ingin mengubahnya dari waktu ke waktu.
    -   `urls.py`berisi petunjuk ke mana pengguna harus diarahkan setelah menavigasi ke URL tertentu.
4.  Mulai proyek dengan menjalankan `python manage.py runserver`. Ini akan membuka server pengembangan, yang dapat Anda akses dengan mengunjungi URL yang disediakan. Server pengembangan ini dijalankan secara lokal di mesin Anda, artinya orang lain tidak dapat mengakses situs web Anda. Ini akan membawa Anda ke halaman arahan default: ![Halaman arahan](https://cs50.harvard.edu/web/2020/notes/3/images/landing.png)
5.  Selanjutnya, kita harus membuat aplikasi. Proyek Django dibagi menjadi satu atau lebih **aplikasi** . Sebagian besar proyek kami hanya memerlukan satu aplikasi, tetapi situs yang lebih besar dapat memanfaatkan kemampuan ini untuk membagi situs menjadi beberapa aplikasi. Untuk membuat aplikasi, kami menjalankan `python manage.py startapp APP_NAME`. Ini akan membuat beberapa direktori dan file tambahan yang akan segera berguna, termasuk `views.py`.
6.  Sekarang, kita harus menginstal aplikasi baru kita. Untuk melakukan ini, kita pergi ke `settings.py`, gulir ke bawah ke daftar `INSTALLED_APPS`, dan tambahkan nama aplikasi baru kita ke daftar ini. ![aplikasi terinstal](https://cs50.harvard.edu/web/2020/notes/3/images/installed.png)

## [Rute](https://cs50.harvard.edu/web/2020/notes/3/#routes)

Sekarang, untuk memulai dengan aplikasi kita:

1.  Selanjutnya, kita akan menuju ke `views.py`. File ini akan berisi sejumlah tampilan yang berbeda, dan kita dapat menganggap tampilan untuk saat ini sebagai satu halaman yang mungkin ingin dilihat pengguna. Untuk membuat tampilan pertama kita, kita akan menulis sebuah fungsi yang menggunakan `request`. Untuk saat ini, kami hanya akan mengembalikan `HttpResponse`(Respons yang sangat sederhana yang menyertakan kode respons 200 dan serangkaian teks yang dapat ditampilkan di browser web) "Halo, Dunia". Untuk melakukan ini, kami telah menyertakan `from django.http import HttpResponse`. File kami sekarang terlihat seperti:
    
    ```
     from django.shortcuts import render
     from django.http import HttpResponse
    
     # Create your views here.
    
     def index(request):
         return HttpResponse("Hello, world!")
    ```
    
2.  Sekarang, kita perlu mengaitkan tampilan yang baru saja kita buat dengan URL tertentu. Untuk melakukan ini, kami akan membuat file lain yang disebut `urls.py`di direktori yang sama dengan `views.py`. Kami sudah memiliki `urls.py`file untuk keseluruhan proyek, tetapi yang terbaik adalah memiliki file terpisah untuk masing-masing aplikasi.
3.  Di dalam `urls.py`, kami akan membuat daftar pola url yang mungkin dikunjungi pengguna saat menggunakan situs web kami. Untuk melakukan ini:
    
    1.  Kami harus melakukan beberapa impor: `from django.urls import path`akan memberi kami kemampuan untuk merutekan ulang URL, dan `from . import views`akan mengimpor fungsi apa pun yang telah kami buat di `views.py`.
    2.  Buat daftar yang disebut`urlpatterns`
    3.  Untuk setiap URL yang diinginkan, tambahkan item ke daftar `urlpatterns`yang berisi panggilan ke `path`fungsi dengan dua atau tiga argumen: Sebuah string yang mewakili jalur URL, sebuah fungsi yang `views.py`ingin kita panggil saat URL itu dikunjungi, dan (opsional) a nama untuk jalur itu, dalam format `name="something"`. Misalnya, inilah tampilan aplikasi sederhana kami sekarang:
    
    ```
     from django.urls import path
     from . import views
    
     urlpatterns = [
         path("", views.index, name="index")
     ]
    ```
    
4.  Sekarang, kami telah membuat `urls.py`untuk aplikasi khusus ini, dan saatnya mengedit yang `urls.py`dibuat untuk kami untuk keseluruhan proyek. Saat Anda membuka file ini, Anda akan melihat bahwa sudah ada jalur bernama `admin`yang akan kita bahas di kuliah nanti. Kami ingin menambahkan jalur lain untuk aplikasi baru kami, jadi kami akan menambahkan item ke daftar `urlpatterns`. Ini mengikuti pola yang sama dengan jalur kami sebelumnya, kecuali alih-alih menambahkan fungsi dari `views.py`sebagai argumen kedua kami, kami ingin dapat menyertakan _semua_ jalur dari `urls.py`file di dalam aplikasi kami. Untuk melakukan ini, kami menulis: `include("APP_NAME.urls")`, di mana `include`fungsi yang kami akses juga dengan mengimpor `include`dari `django.urls`seperti yang ditunjukkan di `urls.py`bawah ini:
    
    ```
    from django.contrib import admin
    from django.urls import path, include
    
    urlpatterns = [
        path('admin/', admin.site.urls),
        path('hello/', include("hello.urls"))
    ]
    ```
    
5.  Dengan melakukan ini, kami telah menetapkan bahwa ketika pengguna mengunjungi situs kami, dan kemudian menambahkan ke URL di bilah pencarian `/hello`, mereka akan dialihkan ke jalur di dalam aplikasi baru kami.

Sekarang, ketika saya memulai aplikasi saya menggunakan `python manage.py runserver`dan mengunjungi url yang disediakan, saya bertemu dengan layar ini: ![url salah](https://cs50.harvard.edu/web/2020/notes/3/images/404.png) Tapi ini karena kami hanya mendefinisikan URL `localhost:8000/hello`, tetapi kami belum menentukan URL `localhost:8000`tanpa menambahkan apa pun di bagian akhir. Jadi, ketika saya menambahkan `/hello`ke URL di bilah pencarian saya: ![Halo Dunia](https://cs50.harvard.edu/web/2020/notes/3/images/helloworld.png) Sekarang setelah kita berhasil, mari kita bahas apa yang baru saja terjadi untuk membawa kita ke titik itu:

1.  Saat kami mengakses URL `localhost:8000/hello/`, Django melihat apa yang muncul setelah URL dasar ( `localhost:8000/`) dan pergi ke berkas proyek kami `urls.py`dan mencari pola yang cocok `hello`.
2.  It found that extension because we defined it, and saw that when met with that extension, it should `include` our `urls.py` file from within our application.
3.  Then, Django ignored the parts of the URL it has already used in rerouting (`localhost:8000/hello/`, or all of it) and looked inside our other `urls.py` file for a pattern that matches the remaining part of the URL.
4.  It found that our only path so far (`""`) matched what was left of the URL, and so it directed us to the function from `views.py` associated with that path.
5.  Finally, Django ran that function within `views.py`, and returned the result (`HttpResponse("Hello, world!")`) to our web browser.

Sekarang, jika kita mau, kita dapat mengubah `index`fungsi di dalamnya `views.py`untuk mengembalikan apa pun yang kita inginkan! Kami bahkan dapat melacak variabel dan melakukan perhitungan dalam fungsi sebelum akhirnya mengembalikan sesuatu.

Sekarang, mari kita lihat bagaimana kita bisa menambahkan lebih dari satu tampilan ke aplikasi kita. Kita dapat mengikuti banyak langkah yang sama dalam aplikasi kita untuk membuat halaman yang menyapa Brian dan David.

Di dalam `views.py`:

```
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here.

def index(request):
    return HttpResponse("Hello, world!")

def brian(request):
    return HttpResponse("Hello, Brian!")

def david(request):
    return HttpResponse("Hello, David!")
```

Di dalam `urls.py`(dalam aplikasi kita)

```
from django.urls import path
from . import views

urlpatterns = [
    path("", views.index, name="index"),
    path("brian", views.brian, name="brian"),
    path("david", views.david, name="david")
]
```

Sekarang, situs kami tetap tidak berubah saat kami mengunjungi `localhost:8000/hello`, tetapi kami mendapatkan halaman yang berbeda saat kami menambahkan `brian`atau `david`ke URL: ![Brian](https://cs50.harvard.edu/web/2020/notes/3/images/brian.png) ![Daud](https://cs50.harvard.edu/web/2020/notes/3/images/david.png)

Banyak situs diberi parameter berdasarkan item yang disertakan dalam URL. Misalnya, membuka [www.twitter.com/cs50](https://twitter.com/cs50) akan menampilkan semua tweet CS50, dan membuka [www.github.com/cs50](https://github.com/cs50) akan membawa Anda ke halaman GitHub CS50. Anda bahkan dapat menemukan repositori GitHub publik Anda sendiri dengan menavigasi ke `www.github.com/YOUR_USERNAME`!

Dalam memikirkan bagaimana ini diterapkan, tampaknya tidak mungkin situs seperti GitHub dan Twitter memiliki jalur URL individual untuk setiap penggunanya, jadi mari kita lihat bagaimana kita bisa membuat jalur yang sedikit lebih fleksibel. Kita akan mulai dengan menambahkan fungsi yang lebih umum, yang disebut `greet`, ke `views.py`:

```
def greet(request, name):
    return HttpResponse(f"Hello, {name}!")
```

Fungsi ini tidak hanya menerima permintaan, tetapi juga argumen tambahan dari nama pengguna, lalu mengembalikan Respons HTTP khusus berdasarkan nama itu. Selanjutnya, kita harus membuat jalur yang lebih fleksibel di `urls.py`, yang mungkin terlihat seperti ini:

```
path("<str:name>", views.greet, name="greet")
```

Ini adalah beberapa sintaks baru, tetapi pada dasarnya yang terjadi di sini adalah kita tidak lagi mencari kata atau nama tertentu di URL, tetapi string apa pun yang mungkin dimasukkan pengguna. Sekarang, kita dapat mencoba situs tersebut dengan beberapa URL lain: ![menyerobot](https://cs50.harvard.edu/web/2020/notes/3/images/harry.png) ![connor](https://cs50.harvard.edu/web/2020/notes/3/images/connor.png)

Saya bahkan dapat membuat ini terlihat sedikit lebih bagus, dengan menambah fungsi `greet`untuk memanfaatkan fungsi Python `capitalize`yang mengkapitalisasi string:

```
def greet(request, name):
    return HttpResponse(f"Hello, {name.capitalize()}!")
```

![Menyerobot](https://cs50.harvard.edu/web/2020/notes/3/images/harryc.png) ![Connor](https://cs50.harvard.edu/web/2020/notes/3/images/connorc.png)

Ini adalah ilustrasi yang bagus tentang bagaimana setiap fungsionalitas yang kita miliki di Python dapat digunakan di Django sebelum dikembalikan.

## [Templat](https://cs50.harvard.edu/web/2020/notes/3/#templates)

Sejauh ini, Respons HTTP kami hanya berupa teks, tetapi kami dapat menyertakan elemen HTML apa pun yang kami inginkan! Misalnya, saya dapat memutuskan untuk mengembalikan tajuk biru alih-alih hanya teks dalam `index`fungsi kami:

```
def index(request):
    return HttpResponse("<h1 style=\"color:blue\">Hello, world!</h1>")
```

![Biru](https://cs50.harvard.edu/web/2020/notes/3/images/bluehello.png)

Akan sangat membosankan untuk menulis seluruh halaman HTML di dalamnya `views.py`. Ini juga merupakan desain yang buruk, karena kami ingin menyimpan bagian terpisah dari proyek kami dalam file terpisah jika memungkinkan.

Ini sebabnya kami sekarang akan memperkenalkan [templat Django](https://docs.djangoproject.com/en/4.0/topics/templates/) , yang memungkinkan kami untuk menulis HTML dan CSS dalam berkas terpisah dan merender berkas tersebut menggunakan Django. Sintaks yang akan kita gunakan untuk merender template terlihat seperti ini:

```
def index(request):
    return render(request, "hello/index.html")
```

Sekarang, kita perlu membuat template itu. Untuk melakukan ini, kita akan membuat folder bernama `templates`di dalam aplikasi kita, lalu membuat folder bernama `hello`(atau apa pun nama aplikasi kita) di dalamnya, lalu menambahkan file bernama `index.html`.

![File](https://cs50.harvard.edu/web/2020/notes/3/images/files.png)

Selanjutnya, kami akan menambahkan apa pun yang kami inginkan ke file baru itu:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello</title>
    </head>
    <body>
        <h1>Hello, World!</h1>
    </body>
</html>
```

Sekarang, ketika kita mengunjungi halaman utama aplikasi kita, kita dapat melihat header dan judul telah diperbarui: ![templat0](https://cs50.harvard.edu/web/2020/notes/3/images/template0.png)

Sebagai tambahan untuk menulis beberapa halaman HTML statis, kita juga dapat menggunakan [bahasa cetakan Django](https://docs.djangoproject.com/en/4.0/ref/templates/language/) untuk mengubah isi berkas HTML kita berdasarkan URL yang dikunjungi. Mari kita coba dengan mengubah `greet`fungsi kita dari sebelumnya:

```
def greet(request, name):
    return render(request, "hello/greet.html", {
        "name": name.capitalize()
    })
```

Perhatikan bahwa kita memberikan argumen ketiga ke dalam `render`fungsi di sini, yang dikenal sebagai **context** . Dalam konteks ini, kami dapat memberikan informasi yang ingin kami sediakan dalam file HTML kami. Konteks ini berbentuk kamus Python. Sekarang, kita dapat membuat `greet.html`file:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello</title>
    </head>
    <body>
        <h1>Hello, {{ name }}!</h1>
    </body>
</html>
```

Anda akan melihat bahwa kami menggunakan beberapa sintaks baru: kurung kurawal ganda. Sintaks ini memungkinkan kita untuk mengakses variabel yang telah kita berikan dalam argumen `context`. Sekarang, ketika kita mencobanya: ![Templat 1](https://cs50.harvard.edu/web/2020/notes/3/images/template1.png) ![Templat 2](https://cs50.harvard.edu/web/2020/notes/3/images/template2.png)

Sekarang, kita telah melihat bagaimana kita dapat memodifikasi template HTML kita berdasarkan konteks yang kita sediakan. Namun, bahasa cetakan Django bahkan lebih hebat dari itu, jadi mari kita lihat beberapa cara lain yang bisa membantu:

### [Persyaratan:](https://cs50.harvard.edu/web/2020/notes/3/#conditionals)

Kami mungkin ingin mengubah apa yang ditampilkan di situs web kami tergantung pada beberapa kondisi. Misalnya, jika Anda mengunjungi situs [www.isitchristmas.com](https://www.isitchristmas.com/) , Anda mungkin akan bertemu dengan halaman yang terlihat seperti ini: ![TIDAK](https://cs50.harvard.edu/web/2020/notes/3/images/isitno.png) Tetapi situs web ini akan berubah pada hari Natal, ketika situs web tersebut akan mengatakan **YA** . Untuk membuat sesuatu seperti ini untuk diri kita sendiri, mari kita coba membuat aplikasi serupa, di mana kita memeriksa apakah ini Hari Tahun Baru atau tidak. Mari buat aplikasi baru untuk melakukannya, mengingat kembali proses kita untuk membuat aplikasi baru:

1.  jalankan `python manage.py startapp newyear`di terminal.
2.  Edit `settings.py`, tambahkan "tahun baru" sebagai salah satu dari kami`INSTALLED_APPS`
3.  Edit file proyek kami `urls.py`, dan sertakan jalur yang mirip dengan yang kami buat untuk aplikasi `hello`:

```
path('newyear/', include("newyear.urls"))
```

1.  Buat `urls.py`file lain di dalam direktori aplikasi baru kita, dan perbarui untuk menyertakan jalur yang mirip dengan jalur indeks di `hello`:

```
from django.urls import path
from . import views

urlpatterns = [
    path("", views.index, name="index"),
]
```

1.  Buat fungsi indeks di `views.py`.

Sekarang setelah kita menyiapkan aplikasi baru kita, mari cari tahu cara memeriksa apakah ini Hari Tahun Baru atau tidak. [Untuk melakukan ini, kita dapat mengimpor modul datetime](https://docs.python.org/3/library/datetime.html) Python . Untuk memahami bagaimana modul ini bekerja, kita dapat melihat dokumentasi [,](https://docs.python.org/3/library/datetime.html) dan kemudian mengujinya di luar Django menggunakan juru bahasa Python.

-   Interpreter **Python** adalah alat yang dapat kita gunakan untuk menguji potongan kecil kode Python. Untuk menggunakan ini, jalankan `python`di terminal Anda, dan kemudian Anda akan dapat mengetik dan menjalankan kode Python di dalam terminal Anda. Setelah selesai menggunakan juru bahasa, lari `exit()`untuk pergi. ![penerjemah](https://cs50.harvard.edu/web/2020/notes/3/images/datetime.png)
-   Kita dapat menggunakan pengetahuan ini untuk membuat ekspresi boolean yang akan bernilai True jika dan hanya jika hari ini adalah Hari Tahun Baru:`now.day == 1 and now.month == 1`
-   Sekarang kita memiliki ekspresi yang dapat kita gunakan untuk mengevaluasi apakah ini Hari Tahun Baru atau tidak, kita dapat memperbarui fungsi indeks kita di `views.py`:

```
def index(request):
    now = datetime.datetime.now()
    return render(request, "newyear/index.html", {
        "newyear": now.month == 1 and now.day == 1
    })
```

Sekarang, mari buat `index.html`template kita. Kita harus membuat lagi folder baru bernama `templates`, folder di dalamnya bernama `newyear`, dan file di dalamnya bernama `index.html`. Di dalam file itu, kami akan menulis sesuatu seperti ini:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Is it New Year's?</title>
    </head>
    <body>
        {% if newyear %}
            <h1>YES</h1>
        {% else %}
            <h1>NO</h1>
        {% endif %}
    </body>
</html>
```

Pada kode di atas, perhatikan bahwa ketika kita ingin menyertakan logika dalam file HTML kita, kita menggunakan `{%`dan `%}`sebagai tag pembuka dan penutup di sekitar pernyataan logis. Perhatikan juga bahwa bahasa pemformatan Django mengharuskan Anda menyertakan tag penutup yang menunjukkan bahwa kami selesai dengan `if-else`blok kami. Sekarang, kita dapat membuka halaman kita untuk melihat:

![TIDAK](https://cs50.harvard.edu/web/2020/notes/3/images/no.png)

Sekarang, untuk mendapatkan gambaran yang lebih baik tentang apa yang terjadi di balik layar, mari periksa elemen halaman ini:

![Sumber](https://cs50.harvard.edu/web/2020/notes/3/images/source.png)

Perhatikan bahwa HTML yang benar-benar dikirim ke peramban web Anda hanya mencakup tajuk NO, yang berarti bahwa Django menggunakan templat HTML yang kami tulis untuk membuat berkas HTML baru, dan kemudian mengirimkannya ke peramban web kami. Jika kita mencontek sedikit dan memastikan bahwa kondisi kita selalu benar, kita melihat bahwa kasus sebaliknya terisi:

```
def index(request):
    now = datetime.datetime.now()
    return render(request, "newyear/index.html", {
        "newyear": True
    })
```

![Ya](https://cs50.harvard.edu/web/2020/notes/3/images/yes.png) ![Sumber 0](https://cs50.harvard.edu/web/2020/notes/3/images/source0.png)

### [Styling](https://cs50.harvard.edu/web/2020/notes/3/#styling)

Jika kita ingin menambahkan file CSS, yang merupakan file _statis_ karena tidak berubah, pertama-tama kita akan membuat folder bernama `static`, lalu membuat `newyear`folder di dalamnya, lalu `styles.css`file di dalamnya. Dalam file ini, kita dapat menambahkan gaya apapun yang kita inginkan seperti yang kita lakukan pada kuliah pertama:

```
h1 {
    font-family: sans-serif;
    font-size: 90px;
    text-align: center;
}
```

Sekarang, untuk menyertakan gaya ini dalam file HTML kita, kita menambahkan baris `{% load static %}`ke bagian atas template HTML kita, yang menandakan ke Django bahwa kita ingin memiliki akses ke file dalam `static`folder kita. Kemudian, daripada mengkodekan tautan ke lembar gaya seperti yang kita lakukan sebelumnya, kita akan menggunakan beberapa sintaks khusus Django:

```
<link rel="stylesheet" href="{% static 'newyear/styles.css' %}">
```

Sekarang, jika kita me-restart server, kita dapat melihat bahwa perubahan gaya sebenarnya diterapkan: ![besar tidak](https://cs50.harvard.edu/web/2020/notes/3/images/bigno.png)

## [Tugas](https://cs50.harvard.edu/web/2020/notes/3/#tasks)

Sekarang, mari ambil apa yang telah kita pelajari sejauh ini dan terapkan pada proyek mini: membuat daftar TODO. Mari kita mulai, sekali lagi, membuat aplikasi baru:

1.  jalankan `python manage.py startapp tasks`di terminal.
2.  Edit `settings.py`, tambahkan "tugas" sebagai salah satu dari kami`INSTALLED_APPS`
3.  Edit file proyek kami `urls.py`, dan sertakan jalur yang mirip dengan yang kami buat untuk aplikasi `hello`:
    
    ```
     path('tasks/', include("tasks.urls"))
    ```
    
4.  Buat `urls.py`file lain di dalam direktori aplikasi baru kita, dan perbarui untuk menyertakan jalur yang mirip dengan jalur indeks di `hello`:
    
    ```
     from django.urls import path
     from . import views
    
     urlpatterns = [
         path("", views.index, name="index"),
     ]
    ```
    
5.  Buat fungsi indeks di `views.py`.

Sekarang, mari kita mulai dengan mencoba membuat daftar tugas dan kemudian menampilkannya ke halaman. Mari buat daftar Python di bagian atas `views.py`tempat kita akan menyimpan tugas kita. Kemudian, kita dapat mengupdate `index`fungsi kita untuk merender template, dan memberikan daftar yang baru kita buat sebagai konteks.

```
from django.shortcuts import render

tasks = ["foo", "bar", "baz"]

# Create your views here.
def index(request):
    return render(request, "tasks/index.html", {
        "tasks": tasks
    })
```

Sekarang, mari bekerja membuat file HTML template kita:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Tasks</title>
    </head>
    <body>
        <ul>
            {% for task in tasks %}
                <li>{{ task }}</li>
            {% endfor %}
        </ul>
    </body>
</html>
```

Perhatikan di sini bahwa kita dapat mengulang tugas kita menggunakan sintaks yang mirip dengan kondisional kita sebelumnya, dan juga mirip dengan loop Python dari Kuliah 2. Saat kita masuk ke halaman tugas sekarang, kita bisa melihat daftar kita sedang dirender: ![tugas0](https://cs50.harvard.edu/web/2020/notes/3/images/tasks0.png)

## [Formulir](https://cs50.harvard.edu/web/2020/notes/3/#forms)

Sekarang kita dapat melihat semua tugas kita saat ini sebagai daftar, kita mungkin ingin menambahkan beberapa tugas baru. Untuk melakukannya, kita akan mulai melihat penggunaan formulir untuk memperbarui halaman web. Mari kita mulai dengan menambahkan fungsi lain `views.py`yang akan merender halaman dengan formulir untuk menambahkan tugas baru:

```
# Add a new task:
def add(request):
    return render(request, "tasks/add.html")
```

Selanjutnya, pastikan untuk menambahkan jalur lain ke `urls.py`:

```
path("add", views.add, name="add")
```

Sekarang, kita akan membuat `add.html`file kita, yang cukup mirip dengan `index.html`, kecuali bahwa di badan kita akan menyertakan formulir daripada daftar:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Tasks</title>
    </head>
    <body>
        <h1>Add Task:</h1>
        <form action="">
            <input type="text" name="task">
            <input type="submit">
        </form>
    </body>
</html>
```

Namun, apa yang baru saja kita lakukan belum tentu merupakan desain terbaik, karena kita baru saja mengulangi sebagian besar HTML tersebut dalam dua file berbeda. Bahasa templat Django memberi kita cara untuk menghilangkan desain buruk ini: [pewarisan templat](https://tutorial.djangogirls.org/en/template_extending/) . Ini memungkinkan kami membuat `layout.html`file yang berisi struktur umum halaman kami:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Tasks</title>
    </head>
    <body>
        {% block body %}
        {% endblock %}
    </body>
</html>
```

Perhatikan bahwa kami sekali lagi digunakan `{%...%}`untuk menunjukkan semacam logika non-HTML, dan dalam kasus ini, kami memberi tahu Django untuk mengisi "blok" ini dengan beberapa teks dari file lain. Sekarang, kita dapat mengubah dua file HTML kita yang lain agar terlihat seperti:

`index.html`:

```
{% extends "tasks/layout.html" %}

{% block body %}
    <h1>Tasks:</h1>
    <ul>
        {% for task in tasks %}
            <li>{{ task }}</li>
        {% endfor %}
    </ul>
{% endblock %}
```

`add.html`:

```
{% extends "tasks/layout.html" %}

{% block body %}
    <h1>Add Task:</h1>
    <form action="">
        <input type="text" name="task">
        <input type="submit">
    </form>
{% endblock %}
```

Perhatikan bagaimana kita sekarang dapat membuang banyak kode berulang dengan _memperluas_ file tata letak kita. Sekarang, halaman indeks kita tetap sama, dan sekarang kita juga memiliki halaman tambahan:

![Menambahkan](https://cs50.harvard.edu/web/2020/notes/3/images/add.png)

Selanjutnya, tidak ideal untuk mengetik "/add" di URL setiap kali kita ingin menambahkan tugas baru, jadi kita mungkin ingin menambahkan beberapa tautan antar halaman. Alih-alih tautan hard-coding, kita sekarang dapat menggunakan `name`variabel yang kita tetapkan untuk setiap jalur di `urls.py`, dan membuat tautan yang terlihat seperti ini:

```
<a href="{% url 'add' %}">Add a New Task</a>
```

di mana 'tambah' adalah nama jalur itu. Kita dapat melakukan hal serupa di `add.html`:

```
<a href="{% url 'index' %}">View Tasks</a>
```

Ini berpotensi menimbulkan masalah, karena kami memiliki beberapa rute yang dinamai `index`di seluruh aplikasi kami yang berbeda. Kita bisa menyelesaikan ini dengan masuk ke setiap `urls.py`file aplikasi kita, dan menambahkan `app_name`variabel, sehingga file tersebut sekarang terlihat seperti ini:

```
from django.urls import path
from . import views

app_name = "tasks"
urlpatterns = [
    path("", views.index, name="index"),
    path("add", views.add, name="add")
]
```

Kami kemudian dapat mengubah tautan kami dari sederhana `index`dan `add`menjadi `tasks:index`dan`tasks:add`

```
<a href="{% url 'tasks:index' %}">View Tasks</a>

<a href="{% url 'tasks:add' %}">Add a New Task</a>
```

Sekarang, mari bekerja untuk memastikan formulir benar-benar melakukan sesuatu saat pengguna mengirimkannya. Kita dapat melakukan ini dengan menambahkan an `action`ke formulir yang telah kita buat di `add.html`:

```
<form action="{% url 'tasks:add' %}" method="post">
```

Artinya, setelah formulir dikirimkan, kami akan diarahkan kembali ke `add`URL. Di sini kami telah menetapkan bahwa kami akan menggunakan metode _posting_ daripada metode _get_ , yang biasanya akan kami gunakan kapan pun formulir dapat mengubah keadaan halaman web itu.

Kami perlu menambahkan sedikit lebih banyak ke formulir ini sekarang, karena Django memerlukan token untuk mencegah [Serangan Pemalsuan Permintaan Situs Lintas (CSRF)](https://portswigger.net/web-security/csrf) . Ini adalah serangan di mana pengguna jahat mencoba mengirim permintaan ke server Anda dari tempat lain selain situs Anda. Ini bisa menjadi masalah yang sangat besar untuk beberapa situs web. Misalnya, situs web perbankan memiliki formulir bagi satu pengguna untuk mentransfer uang ke pengguna lain. Akan menjadi bencana jika seseorang dapat mengirimkan transfer dari luar situs web bank!

Untuk mengatasi masalah ini, ketika Django mengirimkan sebuah tanggapan membuat cetakan, itu juga menyediakan **token CSRF** yang unik dengan setiap sesi baru di situs. Kemudian, ketika permintaan dikirimkan, Django memeriksa untuk memastikan token CSRF terkait dengan permintaan cocok dengan yang baru saja disediakan. Oleh karena itu, jika pengguna jahat di situs lain mencoba mengirimkan permintaan, mereka akan diblokir karena token CSRF yang tidak valid. Validasi CSRF ini dibangun ke dalam kerangka [Django Middleware](https://docs.djangoproject.com/en/4.0/topics/http/middleware/) , yang dapat campur tangan dalam pemrosesan permintaan-respons dari aplikasi Django. Kami tidak akan membahas detail lebih lanjut tentang Middleware dalam kursus ini, tetapi lihat dokumentasinya [jika](https://docs.djangoproject.com/en/4.0/topics/http/middleware/) tertarik!

Untuk memasukkan teknologi ini ke dalam kode kita, kita harus menambahkan baris ke formulir kita di `add.html`.

```
<form action="{% url 'tasks:add' %}" method="post">
    {% csrf_token %}
    <input type="text" name="task">
    <input type="submit">
</form>
```

Baris ini menambahkan bidang input tersembunyi dengan token CSRF yang disediakan oleh Django, sehingga ketika kami memuat ulang halaman, sepertinya tidak ada yang berubah. Namun, jika kami memeriksa elemen, kami akan melihat bahwa kolom masukan baru telah ditambahkan: ![CSRF](https://cs50.harvard.edu/web/2020/notes/3/images/csrf.png)

### [Formulir Django](https://cs50.harvard.edu/web/2020/notes/3/#django-forms)

Sementara kita dapat membuat formulir dengan menulis HTML mentah seperti yang baru saja kita lakukan, Django menyediakan cara yang lebih mudah untuk mengumpulkan informasi dari pengguna: [Django Forms](https://docs.djangoproject.com/en/4.0/ref/forms/api/) . Untuk menggunakan metode ini, kami akan menambahkan yang berikut ke bagian atas `views.py`untuk mengimpor `forms`modul:

```
from django import forms
```

Sekarang, kita bisa membuat form baru di dalamnya `views.py`dengan membuat class Python bernama `NewTaskForm`:

```
class NewTaskForm(forms.Form):
    task = forms.CharField(label="New Task")
```

Sekarang, mari kita lihat apa yang terjadi di kelas itu:

-   Di dalam tanda kurung setelah `NewTaskForm`, kita melihat bahwa kita memiliki `forms.Form`. Ini karena form baru kita [mewarisi](https://www.w3schools.com/python/python_inheritance.asp) dari class bernama `Form`yang disertakan dalam `forms`modul. Kita telah melihat bagaimana pewarisan dapat digunakan dalam bahasa cetakan Django dan untuk gaya menggunakan Sass. Ini adalah contoh lain bagaimana warisan digunakan untuk mengambil deskripsi yang lebih umum ( `forms.Form`kelas) dan mempersempitnya menjadi apa yang kita inginkan (Bentuk baru kita). Pewarisan adalah bagian penting dari Pemrograman Berorientasi Objek yang tidak akan kita bahas secara mendetail selama kursus ini, tetapi ada [banyak sumber online](https://www.w3schools.com/python/python_inheritance.asp) yang tersedia untuk mempelajari topik tersebut!
-   Di dalam kelas ini, kita dapat menentukan informasi apa yang ingin kita kumpulkan dari pengguna, dalam hal ini nama tugas.
-   Kami menentukan bahwa ini harus menjadi masukan tekstual dengan menulis `forms.CharField`, tetapi ada [banyak bidang masukan lain](https://docs.djangoproject.com/en/4.0/ref/forms/fields/#built-in-field-classes) yang disertakan dalam modul formulir Django yang dapat kami pilih.
-   Di dalam this `CharField`, kami menentukan a `label`, yang akan muncul kepada pengguna saat mereka memuat halaman. A `label`hanyalah salah satu dari [banyak argumen](https://docs.djangoproject.com/en/4.0/ref/forms/fields/#core-field-arguments) yang bisa kita berikan ke bidang formulir.

Sekarang setelah kita membuat `NewTaskForm`kelas, kita bisa memasukkannya ke dalam konteks saat merender `add`halaman:

```
# Add a new task:
def add(request):
    return render(request, "tasks/add.html", {
        "form": NewTaskForm()
    })
```

Sekarang, di dalam `add.html`, kita dapat mengganti field input kita dengan form yang baru saja kita buat:

```
{% extends "tasks/layout.html" %}

{% block body %}
    <h1>Add Task:</h1>
    <form action="{% url 'tasks:add' %}" method="post">
        {% csrf_token %}
        {{ form }}
        <input type="submit">
    </form>
    <a href="{% url 'tasks:index' %}">View Tasks</a>
{% endblock %}
```

Ada beberapa keuntungan menggunakan `forms`modul daripada menulis formulir HTML secara manual:

-   Jika kami ingin menambahkan bidang baru ke formulir, kami cukup menambahkannya `views.py`tanpa mengetikkan HTML tambahan.
-   Django secara otomatis melakukan [validasi sisi-klien](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation) , atau validasi lokal ke mesin pengguna. artinya tidak akan mengizinkan pengguna untuk mengirimkan formulir mereka jika tidak lengkap.
-   Django menyediakan [validasi sisi-server](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation) sederhana , atau validasi yang terjadi setelah data formulir mencapai server.
-   Di kuliah berikutnya, kita akan mulai menggunakan **model** untuk menyimpan informasi, dan Django membuatnya sangat sederhana untuk membuat bentuk berdasarkan model.

Sekarang setelah kita menyiapkan formulir, mari kita kerjakan apa yang terjadi saat pengguna mengklik tombol kirim. Saat pengguna menavigasi ke halaman tambah dengan mengeklik tautan atau mengetik URL, mereka mengirimkan permintaan `GET`ke server, yang telah kami tangani dalam `add`fungsi kami. Namun, ketika pengguna mengirimkan formulir, mereka mengirim `POST`permintaan ke server, yang saat ini tidak ditangani dalam `add`fungsi tersebut. Kita dapat menangani `POST`metode dengan menambahkan kondisi berdasarkan argumen `request`yang digunakan fungsi kita. Komentar dalam kode di bawah ini menjelaskan tujuan setiap baris:

```
# Add a new task:
def add(request):

    # Check if method is POST
    if request.method == "POST":

        # Take in the data the user submitted and save it as form
        form = NewTaskForm(request.POST)

        # Check if form data is valid (server-side)
        if form.is_valid():

            # Isolate the task from the 'cleaned' version of form data
            task = form.cleaned_data["task"]

            # Add the new task to our list of tasks
            tasks.append(task)

            # Redirect user to list of tasks
            return HttpResponseRedirect(reverse("tasks:index"))

        else:

            # If the form is invalid, re-render the page with existing information.
            return render(request, "tasks/add.html", {
                "form": form
            })

    return render(request, "tasks/add.html", {
        "form": NewTaskForm()
    })
```

Catatan singkat: untuk mengalihkan pengguna setelah pengiriman berhasil, kami memerlukan beberapa impor lagi:

```
from django.urls import reverse
from django.http import HttpResponseRedirect
```

## [Sesi](https://cs50.harvard.edu/web/2020/notes/3/#sessions)

Pada titik ini, kami telah berhasil membuat aplikasi yang memungkinkan kami menambahkan tugas ke daftar yang terus bertambah. Namun, mungkin menjadi masalah jika kami menyimpan tugas ini sebagai variabel global, karena ini berarti bahwa semua pengguna yang mengunjungi halaman melihat daftar yang persis sama. Untuk mengatasi masalah ini, kami akan menggunakan alat yang disebut [sesi.](https://docs.djangoproject.com/en/4.0/topics/http/sessions/)

Sesi adalah cara untuk menyimpan data unik di sisi server untuk setiap kunjungan baru ke situs web.

Untuk menggunakan sesi dalam aplikasi kita, pertama-tama kita akan menghapus `tasks`variabel global kita, kemudian mengubah `index`fungsi kita, dan akhirnya memastikan bahwa di tempat lain kita telah menggunakan variabel tersebut `tasks`, kita menggantinya dengan`request.session["tasks"]`

```
def index(request):

    # Check if there already exists a "tasks" key in our session

    if "tasks" not in request.session:

        # If not, create a new list
        request.session["tasks"] = []

    return render(request, "tasks/index.html", {
        "tasks": request.session["tasks"]
    })

# Add a new task:
def add(request):
    if request.method == "POST":

        # Take in the data the user submitted and save it as form
        form = NewTaskForm(request.POST)

        # Check if form data is valid (server-side)
        if form.is_valid():

            # Isolate the task from the 'cleaned' version of form data
            task = form.cleaned_data["task"]

            # Add the new task to our list of tasks
            request.session["tasks"] += [task]

            # Redirect user to list of tasks
            return HttpResponseRedirect(reverse("tasks:index"))
        else:

            # If the form is invalid, re-render the page with existing information.
            return render(request, "tasks/add.html", {
                "form": form
            })

    return render(request, "tasks/add.html", {
        "form": NewTaskForm()
    })
```

Terakhir, sebelum Django dapat menyimpan data ini, kita harus menjalankan `python manage.py migrate`di terminal. Minggu depan kita akan berbicara lebih banyak tentang apa itu migrasi, tetapi untuk saat ini ketahuilah bahwa perintah di atas memungkinkan kita untuk menyimpan sesi.

Itu saja untuk kuliah ini! Lain kali kita akan bekerja menggunakan Django untuk menyimpan, mengakses, dan memanipulasi data.
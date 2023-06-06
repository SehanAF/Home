# [Kuliah 8](https://cs50.harvard.edu/college/2022/fall/notes/8/#lecture-8)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/8/#welcome)
-   [Router](https://cs50.harvard.edu/college/2022/fall/notes/8/#routers)
-   [DNS](https://cs50.harvard.edu/college/2022/fall/notes/8/#dns)
-   [HTTP](https://cs50.harvard.edu/college/2022/fall/notes/8/#http)
-   [HTML](https://cs50.harvard.edu/college/2022/fall/notes/8/#html)
-   [CSS](https://cs50.harvard.edu/college/2022/fall/notes/8/#css)
-   [Kerangka kerja](https://cs50.harvard.edu/college/2022/fall/notes/8/#frameworks)
-   [JavaScript](https://cs50.harvard.edu/college/2022/fall/notes/8/#javascript)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/8/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/8/#welcome)

-   Di minggu-minggu sebelumnya, kami memperkenalkan Anda ke Python, bahasa pemrograman tingkat tinggi yang menggunakan blok penyusun yang sama dengan yang kami pelajari di C. Hari ini, kami akan memperluas blok penyusun tersebut lebih jauh dalam HTML, CSS, dan JavaScript.
-   Internet adalah teknologi yang kita semua gunakan.
-   Dengan menggunakan keterampilan kami dari minggu sebelumnya, kami dapat membuat halaman web dan aplikasi kami sendiri.
-   ARPANET menghubungkan titik-titik pertama di internet satu sama lain _._
-   Titik-titik di antara dua titik dapat dianggap sebagai _router_ .

## [Router](https://cs50.harvard.edu/college/2022/fall/notes/8/#routers)

-   Untuk merutekan data dari satu tempat ke tempat lain, kita perlu membuat _keputusan perutean_ . Artinya, seseorang perlu memprogram bagaimana data ditransfer dari titik A ke titik B.
-   Anda dapat membayangkan bagaimana data dapat mengambil beberapa jalur dari titik A dan titik B, sehingga saat router mengalami kemacetan, data dapat mengalir melalui jalur lain.
-   _TCP/IP_ adalah dua protokol yang memungkinkan komputer untuk mentransfer data antara mereka melalui internet.
-   _IP_ atau _protokol internet_ adalah cara dimana komputer dapat mengidentifikasi satu sama lain di internet. Setiap komputer memiliki alamat unik di dunia. Alamat dalam bentuk ini:
    
    ```
      #.#.#.#
    ```
    
-   Angka berkisar dari `0`hingga `255`. Alamat IP adalah 32-bit, artinya alamat ini dapat menampung lebih dari 4 miliar alamat. Versi alamat IP yang lebih baru dapat menampung lebih banyak komputer!
-   Di dunia nyata, server melakukan banyak pekerjaan untuk kita.
-   _emTCP_ , atau protokol kontrol transmisi, digunakan untuk membedakan layanan web satu sama lain. Misalnya, `80`digunakan untuk menunjukkan HTTP dan `443`digunakan untuk menunjukkan HTTPS. Angka-angka ini adalah _nomor port_ .
-   Ketika informasi dikirim dari satu lokasi ke lokasi lain, alamat IP dan nomor port TCP dikirim.
-   Protokol-protokol ini juga digunakan untuk memecah-mecah file besar menjadi beberapa bagian yang disebut _paket_ . Misalnya, foto kucing berukuran besar dapat dikirim dalam beberapa paket. Ketika sebuah paket hilang, TCP/IP dapat meminta kembali paket yang hilang dari server asal.
-   TCP akan mengakui ketika semua data telah dikirim dan diterima.

## [DNS](https://cs50.harvard.edu/college/2022/fall/notes/8/#dns)

-   Akan sangat membosankan jika Anda harus mengingat nomor alamat untuk mengunjungi sebuah website.
-   _DNS_ , atau _sistem nama domain_ , adalah kumpulan server di internet yang digunakan untuk merutekan alamat situs web seperti _harvard.edu_ ke alamat IP tertentu.
-   DNS hanya menyimpan tabel atau database yang menautkan nama domain tertentu yang memenuhi syarat ke alamat IP tertentu.

## [HTTP](https://cs50.harvard.edu/college/2022/fall/notes/8/#http)

-   _Protokol transfer_ _HTTP_ atau hypertext adalah protokol tingkat aplikasi yang digunakan pengembang untuk membangun hal-hal yang kuat dan berguna.
-   Saat Anda melihat alamat seperti `https://www.example.com`Anda sebenarnya secara implisit mengunjungi alamat itu dengan a `/`di bagian akhir.
-   Jalannya adalah apa yang ada _setelah_ tebasan itu. Misalnya, `https://www.example.com/folder/file.html`mengunjungi `example.com`dan menelusuri folder `folder`lalu mengunjungi file bernama `file.html`.
-   `https`di alamat ini adalah protokol yang digunakan untuk terhubung ke alamat web itu. Yang kami maksud dengan protokol adalah bahwa HTTP menggunakan `GET`atau `POST` _meminta_ untuk meminta informasi dari server. Misalnya, Anda dapat meluncurkan Google Chrome, klik kanan, dan klik `inspect`. Ketika Anda membuka `developer tools`dan mengunjungi `Network`, memilih `Preserve log`, Anda akan melihat `Request Headers`. Anda akan melihat penyebutan `GET`. Ini juga dimungkinkan di browser lain, menggunakan metode yang sedikit berbeda.
-   Umumnya, setelah membuat permintaan ke server, Anda akan menerima yang berikut ini di `Response Headers`:
    
    ```
      HTTP/1.1 200 OK
      Content-Type: text/html
    ```
    
-   Pendekatan untuk memeriksa log ini mungkin sedikit lebih rumit dari yang seharusnya. Anda dapat menganalisis pekerjaan protokol HTTP di [code.cs50.io](https://code.cs50.io/) . Misalnya, ketik berikut ini di jendela terminal Anda:
    
    ```
      curl -I https://www.harvard.edu
    ```
    
    Perhatikan bahwa output dari perintah ini mengembalikan semua nilai header dari respons server.
    
-   Demikian pula, jalankan yang berikut di jendela terminal Anda:
    
    ```
      curl -I http://www.harvard.edu
    ```
    
    Perhatikan bahwa `s`in `https`telah dihapus. Respons server akan menunjukkan bahwa responsnya `301`bukan `100`, artinya situs web telah dipindahkan secara permanen.
    
-   Selanjutnya, jalankan perintah berikut di jendela terminal Anda:
    
    ```
      curl -I https://harvard.edu
    ```
    
    Perhatikan bahwa Anda akan melihat `301`respons yang sama, memberikan petunjuk ke browser di mana ia dapat menemukan situs web yang benar.
    
-   Mirip dengan `301`, kode berarti `404`URL yang ditentukan belum ditemukan. Ada banyak kode respons lainnya, seperti:
    
    ```
      200 OK
      301 Moved Permanently
      302 Found
      304 Not Modified
      304 Temporary Redirect
      401 Unauthorized
      403 Forbidden
      404 Not Found
      418 I'm a Teapot
      500 Internal Server Error
      503 Service Unavailable
    ```
    
-   Perlu disebutkan bahwa `500`kesalahan selalu menjadi kesalahan Anda sebagai pengembang. Ini akan sangat penting untuk pset minggu depan, dan berpotensi untuk proyek akhir Anda!
-   Kami dapat mengirimkan perintah yang lebih rumit ke server. Misalnya, kita dapat mencoba yang berikut ini:
    
    ```
      GET /search?q=cats HTTP/1.1
      Host: www.google.com
    ```
    
    Perhatikan bahwa kita tidak hanya menentukan jalur tetapi juga masukan pengguna menggunakan `?`tanda. `q`digunakan untuk menunjukkan _query_ , meneruskannya `cats`.
    
-   Jika Anda mengetik secara manual `google.com/search?=cats`di bilah alamat peramban web, peramban akan secara manual meminta Google untuk hasil yang terkait dengan `cats`.

## [HTML](https://cs50.harvard.edu/college/2022/fall/notes/8/#html)

-   _HTML_ atau _bahasa markup hypertext_ terdiri dari _tag_ , yang masing-masing mungkin memiliki beberapa _atribut_ yang menggambarkannya.
-   Di terminal Anda, ketik `code hello.html`dan tulis kode sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates HTML -->
    
    <html lang="en">
        <head>
            <title>hello, title</title>
        </head>
        <body>
            hello, body
        </body>
    </html>
    ```
    
    Perhatikan bahwa `html`tag membuka dan menutup file ini. Selanjutnya, perhatikan atributnya `lang`, yang mengubah perilaku `html`tag. Juga, perhatikan bahwa ada `head`tag dan `body`tag. Lekukan tidak diperlukan tetapi menyarankan hierarki.
    
-   Anda dapat menyajikan kode Anda dengan mengetik `http-server`. Servis ini sekarang tersedia di URL yang sangat panjang. Jika Anda mengkliknya, Anda dapat mengunjungi situs web dengan kode Anda sendiri.
-   Saat Anda mengunjungi URL ini, perhatikan bahwa nama file `hello.html`muncul di akhir URL ini.
-   Hirarki tag dapat direpresentasikan sebagai berikut:
    
    ![kode html di sebelah hierarki yang menunjukkan node induk dan anak](https://cs50.harvard.edu/college/2022/fall/notes/8/cs50Week8Slide065.png "DOM")
    
-   Browser akan membaca file HTML Anda dari atas ke bawah dan dari kiri ke kanan.
-   Karena spasi putih secara efektif diabaikan dalam HTML, Anda perlu menggunakan `<p>`tag paragraf untuk membuka dan menutup paragraf. Pertimbangkan hal berikut:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates paragraphs -->
    
    <html lang="en">
        <head>
            <title>paragraphs</title>
        </head>
        <body>
            <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus convallis scelerisque quam, vel hendrerit lectus viverra eu. Praesent posuere eget lectus ut faucibus. Etiam eu velit laoreet, gravida lorem in, viverra est. Cras ut purus neque. In porttitor non lorem id lobortis. Mauris gravida metus libero, quis maximus dui porta at. Donec lacinia felis consectetur venenatis scelerisque. Nulla eu nisl sollicitudin, varius velit sit amet, vehicula erat. Curabitur sollicitudin felis sit amet orci mattis, a tempus nulla pulvinar. Aliquam erat volutpat.
            </p>
            <p>
                Mauris ut dui in eros semper hendrerit. Morbi vel elit mi. Sed sit amet ex non quam dignissim dignissim et vel arcu. Pellentesque eget elementum orci. Morbi ac cursus ex. Pellentesque quis turpis blandit orci dapibus semper sed non nunc. Nulla et dolor nec lacus finibus volutpat. Sed non lorem diam. Donec feugiat interdum interdum. Vivamus et justo in enim blandit fermentum vel at elit. Phasellus eu ante vitae ligula varius aliquet. Etiam id posuere nibh.
            </p>
            <p>
                Aenean venenatis convallis ante a rhoncus. Nullam in metus vel diam vehicula tincidunt. Donec lacinia metus sem, sit amet egestas elit blandit sit amet. Nunc egestas sem quis nisl mattis semper. Pellentesque ut magna congue lorem eleifend sodales. Donec tortor tortor, aliquam vitae mollis sed, interdum ut lectus. Mauris non purus quis ipsum lacinia tincidunt.
            </p>
            <p>
                Integer at justo lacinia libero blandit aliquam ut ut dui. Quisque tincidunt facilisis venenatis. Nullam dictum odio quis lorem luctus, vel malesuada dolor luctus. Aenean placerat faucibus enim a facilisis. Maecenas eleifend quis massa sed eleifend. Ut ultricies, dui ac vulputate hendrerit, ex metus iaculis diam, vitae fermentum libero dui et ante. Phasellus suscipit, arcu ut consequat sagittis, massa urna accumsan massa, eu aliquet nulla lorem vitae arcu. Pellentesque rutrum felis et metus porta semper. Nam ac consectetur mauris.
            </p>
            <p>
                Suspendisse rutrum vestibulum odio, sed venenatis purus condimentum sed. Morbi ornare tincidunt augue eu auctor. Vivamus sagittis ac lectus at aliquet. Nulla urna mauris, interdum non nibh in, vehicula porta enim. Donec et posuere sapien. Pellentesque ultrices scelerisque ipsum, vel fermentum nibh tincidunt et. Proin gravida porta ipsum nec scelerisque. Vestibulum fringilla erat at turpis laoreet, nec hendrerit nisi scelerisque.
            </p>
            <p>
                Sed quis malesuada mi. Nam id purus quis augue sagittis pharetra. Nulla facilisi. Maecenas vel fringilla ante. Cras tristique, arcu sit amet blandit auctor, urna elit ultricies lacus, a malesuada eros dui id massa. Aliquam sem odio, pretium vel cursus eget, scelerisque at urna. Vestibulum posuere a turpis consectetur consectetur. Cras consequat, risus quis tempor egestas, nulla ipsum ornare erat, nec accumsan nibh lorem nec risus. Integer at iaculis lacus. Integer congue nunc massa, quis molestie felis pellentesque vestibulum. Nulla odio tortor, aliquam nec quam in, ornare aliquet sapien.
            </p>
        </body>
    </html>
    ```
    
    Perhatikan bahwa paragraf dimulai dengan `<p>`tag dan diakhiri dengan `</p>`tag.
    
-   HTML memungkinkan representasi judul:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates headings (for chapters, sections, subsections, etc.) -->
    
    <html lang="en">
    
        <head>
            <title>headings</title>
        </head>
    
        <body>
    
            <h1>One</h1>
            <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus convallis scelerisque quam, vel hendrerit lectus viverra eu. Praesent posuere eget lectus ut faucibus. Etiam eu velit laoreet, gravida lorem in, viverra est. Cras ut purus neque. In porttitor non lorem id lobortis. Mauris gravida metus libero, quis maximus dui porta at. Donec lacinia felis consectetur venenatis scelerisque. Nulla eu nisl sollicitudin, varius velit sit amet, vehicula erat. Curabitur sollicitudin felis sit amet orci mattis, a tempus nulla pulvinar. Aliquam erat volutpat.
            </p>
    
            <h2>Two</h2>
            <p>
                Mauris ut dui in eros semper hendrerit. Morbi vel elit mi. Sed sit amet ex non quam dignissim dignissim et vel arcu. Pellentesque eget elementum orci. Morbi ac cursus ex. Pellentesque quis turpis blandit orci dapibus semper sed non nunc. Nulla et dolor nec lacus finibus volutpat. Sed non lorem diam. Donec feugiat interdum interdum. Vivamus et justo in enim blandit fermentum vel at elit. Phasellus eu ante vitae ligula varius aliquet. Etiam id posuere nibh.
            </p>
    
            <h3>Three</h3>
            <p>
                Aenean venenatis convallis ante a rhoncus. Nullam in metus vel diam vehicula tincidunt. Donec lacinia metus sem, sit amet egestas elit blandit sit amet. Nunc egestas sem quis nisl mattis semper. Pellentesque ut magna congue lorem eleifend sodales. Donec tortor tortor, aliquam vitae mollis sed, interdum ut lectus. Mauris non purus quis ipsum lacinia tincidunt.
            </p>
    
            <h4>Four</h4>
            <p>
                Integer at justo lacinia libero blandit aliquam ut ut dui. Quisque tincidunt facilisis venenatis. Nullam dictum odio quis lorem luctus, vel malesuada dolor luctus. Aenean placerat faucibus enim a facilisis. Maecenas eleifend quis massa sed eleifend. Ut ultricies, dui ac vulputate hendrerit, ex metus iaculis diam, vitae fermentum libero dui et ante. Phasellus suscipit, arcu ut consequat sagittis, massa urna accumsan massa, eu aliquet nulla lorem vitae arcu. Pellentesque rutrum felis et metus porta semper. Nam ac consectetur mauris.
            </p>
    
            <h5>Five</h5>
            <p>
                Suspendisse rutrum vestibulum odio, sed venenatis purus condimentum sed. Morbi ornare tincidunt augue eu auctor. Vivamus sagittis ac lectus at aliquet. Nulla urna mauris, interdum non nibh in, vehicula porta enim. Donec et posuere sapien. Pellentesque ultrices scelerisque ipsum, vel fermentum nibh tincidunt et. Proin gravida porta ipsum nec scelerisque. Vestibulum fringilla erat at turpis laoreet, nec hendrerit nisi scelerisque.
            </p>
    
            <h6>Six</h6>
            <p>
                Sed quis malesuada mi. Nam id purus quis augue sagittis pharetra. Nulla facilisi. Maecenas vel fringilla ante. Cras tristique, arcu sit amet blandit auctor, urna elit ultricies lacus, a malesuada eros dui id massa. Aliquam sem odio, pretium vel cursus eget, scelerisque at urna. Vestibulum posuere a turpis consectetur consectetur. Cras consequat, risus quis tempor egestas, nulla ipsum ornare erat, nec accumsan nibh lorem nec risus. Integer at iaculis lacus. Integer congue nunc massa, quis molestie felis pellentesque vestibulum. Nulla odio tortor, aliquam nec quam in, ornare aliquet sapien.
            </p>
    
        </body>
    
    </html>
    ```
    
    Perhatikan bahwa `<h1>`, `<h2>`, dan `<h3>`menunjukkan tingkatan judul yang berbeda.
    
-   Kami juga dapat membuat daftar dalam HTML:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates (ordered) lists -->
    
    <html lang="en">
        <head>
            <title>list</title>
        </head>
        <body>
            <ol>
                <li>foo</li>
                <li>bar</li>
                <li>baz</li>
            </ol>
        </body>
    </html>
    ```
    
    Perhatikan bahwa `<ol>`tag membuat daftar terurut yang berisi tiga item.
    
-   Kami juga dapat membuat tabel dalam HTML:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates table -->
    
    <html lang="en">
        <head>
            <title>table</title>
        </head>
        <body>
            <table>
                <tr>
                    <td>1</td>
                    <td>2</td>
                    <td>3</td>
                </tr>
                <tr>
                    <td>4</td>
                    <td>5</td>
                    <td>6</td>
                </tr>
                <tr>
                    <td>7</td>
                    <td>8</td>
                    <td>9</td>
                </tr>
                <tr>
                    <td>*</td>
                    <td>0</td>
                    <td>#</td>
                </tr>
            </table>
        </body>
    </html>
    ```
    
    Tabel juga memiliki tag yang membuka dan menutup setiap elemen di dalamnya.
    
-   Gambar juga dapat digunakan dalam HTML:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates image -->
    
    <html lang="en">
        <head>
            <title>image</title>
        </head>
        <body>
            <!-- https://www.harvard.edu/ -->
            <img alt="Harvard University" src="harvard.jpg">
        </body>
    </html>
    ```
    
    Perhatikan yang `src="harvard.jpg"`menunjukkan jalur tempat file gambar dapat ditemukan.
    
-   Video juga dapat disertakan dalam HTML:
    
    ```HTML
    <!DOCTYPE html>
    
    <!-- Demonstrates video -->
    
    <html lang="en">
        <head>
            <title>video</title>
        </head>
        <body>
            <!-- https://www.harvard.edu/ -->
            <video autoplay loop muted playsinline width="1280">
                <source src="halloween.mp4" type="video/mp4">
            </video>
        </body>
    </html>
    ```
    
    Perhatikan bahwa `width`atribut menentukan lebar video.
    
-   Anda juga dapat menautkan antara berbagai halaman web:
    
    ```HTML
    <!DOCTYPE html>
    
    <!-- Demonstrates link -->
    
    <html lang="en">
        <head>
            <title>link</title>
        </head>
        <body>
           Visit <a href="image.html">Harvard</a>.
        </body>
    </html>
    ```
    
    Perhatikan bahwa tag `<a>`atau _jangkar_ digunakan untuk membuat `Harvard`teks yang dapat ditautkan.
    
-   Tag meta digunakan untuk menyimpan informasi tentang data dalam file HTML. Pertimbangkan hal berikut:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates responsive design -->
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>meta</title>
        </head>
        <body>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus convallis scelerisque quam, vel hendrerit lectus viverra eu. Praesent posuere eget lectus ut faucibus. Etiam eu velit laoreet, gravida lorem in, viverra est. Cras ut purus neque. In porttitor non lorem id lobortis. Mauris gravida metus libero, quis maximus dui porta at. Donec lacinia felis consectetur venenatis scelerisque. Nulla eu nisl sollicitudin, varius velit sit amet, vehicula erat. Curabitur sollicitudin felis sit amet orci mattis, a tempus nulla pulvinar. Aliquam erat volutpat.
        </body>
    </html>
    ```
    
    Perhatikan kumpulan `meta`atribut ini membuat halaman ini mobile-friendly.
    
-   Ada banyak `meta`key-value pair yang dapat Anda gunakan:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates Open Graph tags -->
    
    <html lang="en">
        <head>
            <meta property="og:title" content="CS50">
            <meta property="og:description" content="Introduction to the intellectual enterprises of computer science and the art of programming.">
            <meta property="og:image" content="cat.jpg">
            <title>meta</title>
        </head>
        <body>
            ...
        </body>
    </html>
    ```
    
    Perhatikan bahwa pasangan nilai kunci ini berhubungan dengan dan `title`dari `description`halaman web.
    
-   Anda juga dapat membuat formulir yang mengingatkan pada pencarian Google:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates form -->
    
    <html lang="en">
        <head>
            <title>search</title>
        </head>
        <body>
            <form action="https://www.google.com/search" method="get">
                <input name="q" type="search">
                <input type="submit" value="Google Search">
            </form>
        </body>
    </html>
    ```
    
    Perhatikan bahwa `form`tag terbuka dan memberikan atribut dari apa `action`yang diperlukan. Bidang `input`disertakan, meneruskan nama `q`dan jenisnya sebagai `search`.
    
-   Kami dapat menjadikan pencarian ini lebih baik sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates additional form attributes -->
    
    <html lang="en">
        <head>
            <title>search</title>
        </head>
        <body>
            <form action="https://www.google.com/search" method="get">
                <input autocomplete="off" autofocus name="q" placeholder="Query" type="search">
                <button>Google Search</button>
            </form>
        </body>
    </html>
    ```
    
    Perhatikan bahwa `autocomplete`berbalik `off`. `autofocus`diaktifkan.
    
-   Kami telah melihat beberapa elemen HTML yang dapat Anda tambahkan ke situs Anda. Jika Anda memiliki ide untuk menambahkan sesuatu ke situs Anda yang belum kami lihat (tombol, file audio, dll.) coba Googling "X dalam HTML" untuk menemukan sintaks yang tepat!

## [CSS](https://cs50.harvard.edu/college/2022/fall/notes/8/#css)

-   `CSS`, atau _cascading style sheet_ , adalah bahasa markup yang memungkinkan Anda menyempurnakan estetika file HTML.
-   Di terminal Anda, ketik `code home.html`dan tulis kode sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates inline CSS with P tags -->
    
    <html lang="en">
        <head>
            <title>css</title>
        </head>
        <body>
            <p style="font-size: large; text-align: center;">
                John Harvard
            </p>
            <p style="font-size: medium; text-align: center;">
                Welcome to my home page!
            </p>
            <p style="font-size: small; text-align: center;">
                Copyright &#169; John Harvard
            </p>
        </body>
    </html>
    ```
    
    Perhatikan bahwa beberapa `style`atribut disediakan untuk `<p>`tag. Diset `font-size`ke `large`, `medium`, atau `small`. Kemudian `text-align`diatur ke tengah.
    
-   Meskipun benar, hal di atas tidak dirancang dengan baik. Kami dapat menghapus redundansi dengan memodifikasi kode kami sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <!-- Removes outer DIV -->
    
    <html lang="en">
        <head>
            <title>css</title>
        </head>
        <body style="text-align: center">
            <div style="font-size: large">
                John Harvard
            </div>
            <div style="font-size: medium">
                Welcome to my home page!
            </div>
            <div style="font-size: small">
                Copyright &#169; John Harvard
            </div>
        </body>
    </html>
    ```
    
    Perhatikan bahwa `<div>`tag digunakan untuk membagi file HTML ini ke dalam wilayah tertentu. `text-align: center`dipanggil di seluruh tubuh file HTML.
    
-   Ternyata ada teks semantik yang lebih baru yang disertakan dalam HTML. Kita dapat memodifikasi kode kita sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <!-- Uses semantic tags instead of DIVs -->
    
    <html lang="en">
        <head>
            <title>css</title>
        </head>
        <body style="text-align: center">
            <header style="font-size: large">
                John Harvard
            </header>
            <main style="font-size: medium">
                Welcome to my home page!
            </main>
            <footer style="font-size: small">
                Copyright &#169; John Harvard
            </footer>
        </body>
    </html>
    ```
    
    Perhatikan bahwa `header`dan `footer`keduanya memiliki gaya berbeda yang ditetapkan padanya.
    
-   Praktik menempatkan gaya dan informasi di lokasi yang sama bukanlah praktik yang baik. Kita bisa memindahkan elemen gaya ke bagian atas file sebagai berikut:
    
    ```
    <!-- Demonstrates class selectors -->
    
    <html lang="en">
        <head>
            <style>
    
                .centered
                {
                    text-align: center;
                }
    
                .large
                {
                    font-size: large;
                }
    
                .medium
                {
                    font-size: medium;
                }
    
                .small
                {
                    font-size: small;
                }
    
            </style>
            <title>css</title>
        </head>
        <body class="centered">
            <header class="large">
                John Harvard
            </header>
            <main class="medium">
                Welcome to my home page!
            </main>
            <footer class="small">
                Copyright &#169; John Harvard
            </footer>
        </body>
    </html>
    ```
    
    Perhatikan semua tag gaya ditempatkan di dalam `head`pembungkus `style`tag. Perhatikan juga bahwa kita telah menetapkan _class_ , yang disebut `centered`, `large`, `medium`, dan `small`ke elemen kita, dan kita memilih class tersebut dengan menempatkan titik di depan nama, seperti pada`.centered`
    
-   Ternyata kita bisa memindahkan semua kode gaya kita ke dalam file khusus yang disebut file _CSS_ . Kita dapat membuat file bernama `style.css`dan menempelkan kelas kita di sana:
    
    ```
    .centered
    {
        text-align: center;
    }
    
    .large
    {
        font-size: large;
    }
    
    .medium
    {
        font-size: medium;
    }
    
    .small
    {
        font-size: small;
    }
    ```
    
    Perhatikan bahwa ini adalah kata demi kata yang muncul di file HTML kita.
    
-   Kami kemudian dapat memberi tahu browser di mana menemukan CSS untuk file HTML ini:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates external stylesheets -->
    
    <html lang="en">
        <head>
            <link href="style.css" rel="stylesheet">
            <title>css</title>
        </head>
        <body class="centered">
            <header class="large">
                John Harvard
            </header>
            <main class="medium">
                Welcome to my home page!
            </main>
            <footer class="small">
                Copyright &#169; John Harvard
            </footer>
        </body>
    </html>
    ```
    
    Perhatikan yang `style.css`ditautkan ke file HTML ini sebagai lembar gaya, memberi tahu browser di mana menemukan gaya yang kita buat.
    

## [Kerangka kerja](https://cs50.harvard.edu/college/2022/fall/notes/8/#frameworks)

-   Mirip dengan pustaka pihak ketiga yang dapat kita manfaatkan dengan Python, ada pustaka pihak ketiga yang disebut _kerangka kerja_ yang dapat kita manfaatkan dengan file HTML kita.
-   _Bootstrap_ adalah salah satu kerangka kerja yang dapat kita gunakan untuk mempercantik HTML kita dan dengan mudah menyempurnakan elemen desain sehingga halaman kita lebih mudah dibaca.
-   Bootstrap dapat digunakan dengan menambahkan `link`tag berikut di `head`file html Anda:
    
    ```
    <head>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
        <title>favorites</title>
    </head>
    ```
    
-   Anda dapat mempelajari lebih lanjut tentang ini di [Dokumentasi Bootstrap](https://getbootstrap.com/docs/4.1/getting-started/introduction/) .

## [JavaScript](https://cs50.harvard.edu/college/2022/fall/notes/8/#javascript)

-   JavaScript adalah bahasa pemrograman lain yang memungkinkan interaktivitas dalam halaman web.
-   JavaScript mendukung persyaratan:
    
    ```
    if (x < y)
    {
    
    }
    else
    {
    
    }
    ```
    
-   Variabel juga didukung:
    
    ```
    let counter = 0;
    ```
    
-   Anda juga dapat meningkatkan:
    
    ```
    counter++
    ```
    
-   Loop sangat mirip dengan apa yang telah Anda lihat sebelumnya di C:
    
    ```
    for (let i = 0; i < 3; i++)
    {
    
    }
    ```
    
-   JavaScript memungkinkan Anda untuk secara dinamis membaca dan memodifikasi dokumen html yang dimuat ke dalam memori sehingga pengguna tidak perlu memuat ulang untuk melihat perubahan.
-   Pertimbangkan HTML berikut:
    
    ```
    <!DOCTYPE html>
    
    <!-- Demonstrates programmatic changes to style -->
    
    <html lang="en">
        <head>
            <title>background</title>
        </head>
        <body>
            <button id="red">R</button>
            <button id="green">G</button>
            <button id="blue">B</button>
            <script>
    
                let body = document.querySelector('body');
                document.querySelector('#red').addEventListener('click', function() {
                    body.style.backgroundColor = 'red';
                });
                document.querySelector('#green').addEventListener('click', function() {
                    body.style.backgroundColor = 'green';
                });
                document.querySelector('#blue').addEventListener('click', function() {
                    body.style.backgroundColor = 'blue';
                });
    
            </script>
        </body>
    </html>
    ```
    
    Perhatikan bahwa JavaScript mendengarkan ketika tombol tertentu diklik. Setelah klik seperti itu, atribut gaya tertentu pada halaman diubah. `body`didefinisikan sebagai badan halaman. Kemudian, pendengar acara menunggu untuk mengklik salah satu tombol. Kemudian, `body.style.backgroundColor`diubah.
    
-   Demikian pula, pertimbangkan hal berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <script>
    
                // Toggles visibility of greeting
                function blink()
                {
                    let body = document.querySelector('body');
                    if (body.style.visibility == 'hidden')
                    {
                        body.style.visibility = 'visible';
                    }
                    else
                    {
                        body.style.visibility = 'hidden';
                    }
                }
    
                // Blink every 500ms
                window.setInterval(blink, 500);
    
            </script>
            <title>blink</title>
        </head>
        <body>
            hello, world
        </body>
    </html>
    ```
    
    Contoh ini mengedipkan teks pada interval yang ditentukan. Perhatikan bahwa `window.setInterval`terdapat dua argumen: 1) Fungsi yang akan dipanggil dan 2) masa tunggu (dalam milidetik) antara pemanggilan fungsi.
    
-   Pertimbangkan hal berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
    
        <head>
            <title>autocomplete</title>
        </head>
    
        <body>
    
            <input autocomplete="off" autofocus placeholder="Query" type="text">
    
            <ul></ul>
    
            <script src="large.js"></script>
            <script>
    
                let input = document.querySelector('input');
                input.addEventListener('keyup', function(event) {
                    let html = '';
                    if (input.value) {
                        for (word of WORDS) {
                            if (word.startsWith(input.value)) {
                                html += `<li>${word}</li>`;
                            }
                        }
                    }
                    document.querySelector('ul').innerHTML = html;
                });
    
            </script>
    
        </body>
    </html>
    ```
    
    Ini adalah implementasi JavaScript dari pelengkapan otomatis.
    
-   Menariknya, kami juga dapat melakukan geolokasi menggunakan JavaScript:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <title>geolocation</title>
        </head>
        <body>
            <script>
    
                navigator.geolocation.getCurrentPosition(function(position) {
                    document.write(position.coords.latitude + ", " + position.coords.longitude);
                });
    
            </script>
        </body>
    </html>
    ```
    
    Perhatikan yang `navigator.geolocation`digunakan untuk `getCurrentPosition`. Ini tidak akan berfungsi jika komputer atau browser Anda tidak mengizinkan pelacakan lokasi.
    
-   Kemampuan JavaScript sangat banyak dan dapat ditemukan di [Dokumentasi JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) .

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/8/#summing-up)

Dalam pelajaran ini, Anda belajar cara membuat file HTML Anda sendiri, menatanya, memanfaatkan kerangka kerja pihak ketiga, dan memanfaatkan JavaScript. Secara khusus, kami membahas…

-   TCP/IP
-   DNS
-   HTML
-   CSS
-   Kerangka kerja
-   JavaScript

Sampai jumpa lain waktu
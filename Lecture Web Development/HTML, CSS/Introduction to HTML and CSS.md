# [Kuliah 0](https://cs50.harvard.edu/web/2020/notes/0/#lecture-0)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/0/#introduction)
-   [Pemrograman Web](https://cs50.harvard.edu/web/2020/notes/0/#web-programming)
-   [HTML (Bahasa Markup Hiperteks)](https://cs50.harvard.edu/web/2020/notes/0/#html-hypertext-markup-language)
    -   [Model Objek Dokumen (DOM)](https://cs50.harvard.edu/web/2020/notes/0/#document-object-model-dom)
    -   [Lebih Banyak Elemen HTML](https://cs50.harvard.edu/web/2020/notes/0/#more-html-elements)
    -   [Formulir](https://cs50.harvard.edu/web/2020/notes/0/#forms)
-   [CSS (Cascading Style Sheets)](https://cs50.harvard.edu/web/2020/notes/0/#css-cascading-style-sheets)
-   [Desain responsif](https://cs50.harvard.edu/web/2020/notes/0/#responsive-design)
-   [Bootstrap](https://cs50.harvard.edu/web/2020/notes/0/#bootstrap)
-   [Sass (Style Sheets yang Mengagumkan Secara Sintaktis)](https://cs50.harvard.edu/web/2020/notes/0/#sass-syntactically-awesome-style-sheets)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/0/#introduction)

Dalam kursus ini, kami mengambil bagian terakhir dari CS50 dan mendalami desain dan pembuatan aplikasi web. Kami akan membangun keterampilan desain web kami dengan mengerjakan sejumlah proyek selama kursus, termasuk proyek akhir terbuka di mana Anda akan memiliki kesempatan untuk membuat situs web Anda sendiri!

Dalam kursus ini, Anda memerlukan editor teks tempat Anda dapat menulis kode secara lokal di komputer Anda. Beberapa yang populer termasuk [Visual Studios Code](https://code.visualstudio.com/) , [Sublime Text](https://www.sublimetext.com/) , [Atom](https://atom.io/) , dan [Vim](https://www.vim.org/) , tetapi masih banyak lagi yang bisa dipilih!

## [Pemrograman Web](https://cs50.harvard.edu/web/2020/notes/0/#web-programming)

**Topik Kursus:** Kami akan membahas lebih detail nanti, tetapi berikut adalah ikhtisar singkat tentang apa yang akan kami kerjakan selama kursus ini:

1.  **HTML dan CSS** (bahasa markup yang digunakan untuk menguraikan halaman web, dan prosedur untuk membuat situs kami lebih menarik secara visual)
2.  **Git** (digunakan untuk kontrol versi dan kolaborasi)
3.  **Python** (bahasa pemrograman yang banyak digunakan yang akan kami gunakan untuk membuat situs kami lebih dinamis)
4.  **Django** (kerangka kerja web populer yang akan kami gunakan untuk backend situs kami)
5.  **SQL, Model, dan Migrasi** (bahasa yang digunakan untuk menyimpan dan mengambil data, dan metode khusus Django yang membuatnya lebih mudah untuk berinteraksi dengan basis data SQL)
6.  **JavaScript** (bahasa pemrograman yang digunakan untuk membuat situs web lebih cepat dan lebih interaktif)
7.  **Antarmuka Pengguna** (metode yang digunakan untuk membuat situs web semudah mungkin digunakan)
8.  **Pengujian, CI, CD** (mempelajari tentang berbagai metode yang digunakan untuk memastikan pembaruan halaman web berjalan lancar)
9.  **Skalabilitas dan Keamanan** (memastikan situs web kami dapat diakses oleh banyak pengguna sekaligus, dan aman dari niat jahat)

## [HTML (Bahasa Markup Hiperteks)](https://cs50.harvard.edu/web/2020/notes/0/#html-hypertext-markup-language)

-   HTML adalah bahasa markup yang mendefinisikan struktur halaman web. Itu ditafsirkan oleh browser web Anda (Safari, Google Chrome, Firefox, dll.) Untuk menampilkan konten di layar Anda.
-   Mari kita mulai dengan menulis file HTML sederhana!

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
    </head>
    <body>
        Hello, world!
    </body>
<html>
```

-   Ketika kami membuka file ini di browser kami, kami mendapatkan:

![Halo Halaman](https://cs50.harvard.edu/web/2020/notes/0/images/hello0.png)

-   Sekarang, mari luangkan waktu untuk membahas tentang file yang baru saja kita tulis, yang tampaknya cukup rumit untuk halaman yang sederhana.
    -   Di baris pertama, kami menyatakan (ke browser web) bahwa kami sedang menulis dokumen dalam versi HTML terbaru: HTML5.
    -   Setelah itu, halaman terdiri dari **elemen HTML** bersarang (seperti html dan body), masing-masing dengan **tag pembuka dan penutup** yang ditandai `<element>`dengan pembuka dan `</element>`penutup.
    -   Perhatikan bagaimana masing-masing elemen dalam diindentasi sedikit lebih jauh dari yang terakhir. Meskipun hal ini belum tentu diperlukan oleh browser, akan sangat membantu jika Anda menyimpannya dalam kode Anda sendiri.
    -   Elemen HTML dapat menyertakan **atribut** , yang memberi browser informasi tambahan tentang elemen tersebut. Misalnya, saat kami menyertakan `lang="en"`tag awal kami, kami memberi tahu browser bahwa kami menggunakan bahasa Inggris sebagai bahasa utama kami.
    -   Di dalam elemen HTML, kami biasanya ingin menyertakan tag `head`dan a `body`. Elemen kepala akan menyertakan informasi tentang halaman Anda yang belum tentu ditampilkan, dan elemen tubuh akan berisi apa yang sebenarnya terlihat oleh pengguna yang mengunjungi situs tersebut.
    -   Di bagian atas, kami telah menyertakan `title`untuk halaman web kami, yang akan Anda lihat ditampilkan di tab di bagian atas browser web kami.
    -   Terakhir, kami menyertakan teks "Halo, dunia!" di body, yang merupakan bagian yang terlihat dari halaman kita.

### [Model Objek Dokumen (DOM)](https://cs50.harvard.edu/web/2020/notes/0/#document-object-model-dom)

![DOM](https://cs50.harvard.edu/web/2020/notes/0/images/dom.png)

-   DOM adalah cara mudah untuk memvisualisasikan cara elemen HTML berhubungan satu sama lain menggunakan struktur seperti pohon. Di atas adalah contoh tata letak DOM untuk halaman yang baru saja kita tulis.

### [Lebih Banyak Elemen HTML](https://cs50.harvard.edu/web/2020/notes/0/#more-html-elements)

-   Ada banyak elemen HTML yang mungkin ingin Anda gunakan untuk menyesuaikan halaman Anda, termasuk judul, daftar, dan bagian yang dicetak tebal. Dalam contoh berikutnya, kita akan melihat beberapa di antaranya beraksi.
-   Satu hal lagi yang perlu diperhatikan: `<!-- -->`beri kami komentar dalam HTML, jadi kami akan menggunakannya di bawah untuk menjelaskan beberapa elemen.

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>HTML Elements</title>
    </head>
    <body>
        <!-- We can create headings using h1 through h6 as tags. -->
        <h1>A Large Heading</h1>
        <h2>A Smaller Heading</h2>
        <h6>The Smallest Heading</h6>

        <!-- The strong and i tags give us bold and italics respectively. -->
        A <strong>bold</strong> word and an <i>italicized</i> word!

        <!-- We can link to another page (such as cs50's page) using a. -->
        View the <a href="https://cs50.harvard.edu/">CS50 Website</a>!

        <!-- We used ul for an unordered list and ol for an ordered one. both ordered and unordered lists contain li, or list items. -->
        An unordered list:
        <ul>
            <li>foo</li>
            <li>bar</li>
            <li>baz</li>
        </ul>
        An ordered list:
        <ol>
            <li>foo</li>
            <li>bar</li>
            <li>baz</li>
        </ol>

        <!-- Images require a src attribute, which can be either the path to a file on your computer or the link to an image online. It also includes an alt attribute, which gives a description in case the image can't be loaded. -->
        An image:
        <img src="../../images/duck.jpeg" alt="Rubber Duck Picture">
        <!-- We can also see above that for some elements that don't contain other ones, closing tags are not necessary. -->

        <!-- Here, we use a br tag to add white space to the page. -->
        <br/> <br/>

        <!-- A few different tags are necessary to create a table. -->
        <table>
            <thead>
                <th>Ocean</th>
                <th>Average Depth</th>
                <th>Maximum Depth</th>
            </thead>
            <tbody>
                <tr>
                    <td>Pacific</td>
                    <td>4280 m</td>
                    <td>10911 m</td>
                </tr>
                <tr>
                    <td>Atlantic</td>
                    <td>3646 m</td>
                    <td>8486 m</td>
                </tr>
            </tbody>
        </table>
    </body>
<html>
```

Halaman ini, ketika dirender, terlihat seperti ini:

![Elemen](https://cs50.harvard.edu/web/2020/notes/0/images/elements.png)

-   Jika Anda mengkhawatirkannya, ketahuilah bahwa Anda tidak perlu menghafal elemen-elemen ini. Sangat mudah untuk mencari sesuatu seperti "gambar dalam HTML" untuk menemukan `img`tag. Salah satu sumber daya yang sangat membantu untuk mempelajari elemen ini adalah [W3 Schools](https://www.w3schools.com/html/html_elements.asp) .

### [Formulir](https://cs50.harvard.edu/web/2020/notes/0/#forms)

-   Kumpulan elemen lain yang sangat penting saat membuat situs web adalah cara mengumpulkan informasi dari pengguna. Anda dapat mengizinkan pengguna untuk memasukkan informasi menggunakan formulir HTML, yang dapat berisi beberapa jenis input yang berbeda. Nanti dalam kursus ini, kita akan mempelajari tentang cara menangani informasi setelah formulir dikirimkan.
-   Sama seperti elemen HTML lainnya, tidak perlu menghafalnya, dan W3 Schools adalah sumber yang bagus untuk mempelajarinya!

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Forms</title>
</head>
<body>
    <form>
        <input type="text" placeholder="First Name" name="first">
        <input type="password" placeholder="Password" name="password">
        <div>
            Favorite Color:
            <input name="color" type="radio" value="blue"> Blue
            <input name="color" type="radio" value="green"> Green
            <input name="color" type="radio" value="yellow"> Yellow
            <input name="color" type="radio" value="red"> Red

        </div>
        <input type="submit">
    </form>
</body>
</html>
```

![membentuk](https://cs50.harvard.edu/web/2020/notes/0/images/form.png)

## [CSS (Cascading Style Sheets)](https://cs50.harvard.edu/web/2020/notes/0/#css-cascading-style-sheets)

-   CSS digunakan untuk menyesuaikan tampilan website.
-   Sementara kita baru memulai, kita bisa menambahkan atribut style ke elemen HTML apa pun untuk menerapkan beberapa CSS ke dalamnya.
-   Kami mengubah gaya dengan mengubah properti CSS dari suatu elemen, menulis sesuatu seperti `color: blue`atau`text-align: center`
-   Dalam contoh di bawah ini, kami membuat sedikit perubahan pada file pertama kami untuk memberinya tajuk warna-warni:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
    </head>
    <body>
        <h1 style="color: blue; text-align: center;">A Colorful Heading!</h1>
        Hello, world!
    </body>
<html>
```

![judul biru](https://cs50.harvard.edu/web/2020/notes/0/images/style0.png)

-   Jika kita memberi gaya pada elemen luar, semua elemen dalam secara otomatis mengambil gaya itu. Kita dapat melihat ini jika kita memindahkan gaya yang baru saja kita terapkan dari tag header ke tag body:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
    </head>
    <body style="color: blue; text-align: center;">
        <h1 >A Colorful Heading!</h1>
        Hello, world!
    </body>
<html>
```

![biru dimana-mana](https://cs50.harvard.edu/web/2020/notes/0/images/style1.png)

-   Meskipun kita dapat memberi gaya pada halaman web kita seperti yang telah kita lakukan di atas, untuk mendapatkan desain yang lebih baik, kita harus dapat memindahkan gaya kita dari garis individu.
    
    -   Salah satu cara untuk melakukannya adalah dengan menambahkan gaya Anda di antara `<style>`tag dalam file `head`. Di dalam tag ini, kita menulis jenis elemen apa yang ingin kita beri gaya, dan gaya yang ingin kita terapkan padanya. Misalnya:
    
    ```
      <html lang="en">
      <!DOCTYPE html>
      <head>
          <title>Hello!</title>
          <style>
              h1 {
                  color: blue;
                  text-align: center;
              }
          </style>
      </head>
      <body>
          <h1 >A Colorful Heading!</h1>
          Hello, world!
      </body>
      </html>
    ```
    
    -   Cara lain adalah dengan menyertakan `<link>`elemen di Anda `head`dengan link ke file styles.css yang berisi beberapa gaya. Ini berarti file HTML akan terlihat seperti:
    
    ```
      <html lang="en">
      <!DOCTYPE html>
      <head>
          <title>Hello!</title>
          <link rel="stylesheet" href="styles.css">
      </head>
      <body>
          <h1 >A Colorful Heading!</h1>
          Hello, world!
      </body>
      </html>
    ```
    
    Dan file kami bernama `styles.css`akan terlihat seperti:
    
    ```
      h1 {
          color: blue;
          text-align: center;
      }
    ```
    
-   Ada terlalu banyak properti CSS untuk dibahas di sini, tetapi seperti elemen HTML, biasanya mudah untuk Google sesuatu seperti "mengubah font menjadi CSS biru" untuk mendapatkan hasilnya. Beberapa yang paling umum adalah:
    -   `color`: warna teks
    -   `text-align`: di mana elemen ditempatkan pada halaman
    -   `background-color`: dapat diatur ke warna apa pun
    -   `width`: dalam piksel atau persen halaman
    -   `height`: dalam piksel atau persen halaman
    -   `padding`: berapa banyak ruang yang harus tersisa di dalam elemen
    -   `margin`: berapa banyak ruang yang harus ditinggalkan di luar elemen
    -   `font-family`: jenis font untuk teks pada halaman
    -   `font-size`: dalam piksel
    -   `border`: jenis ukuran (padat, putus-putus, dll) warna
-   Mari kita gunakan beberapa dari apa yang baru saja kita pelajari untuk memperbaiki tabel lautan kita dari atas. Inilah beberapa HTML untuk memulai kami:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Nicer Table</title>
    </head>
    <body>
        <table>
            <thead>
                <th>Ocean</th>
                <th>Average Depth</th>
                <th>Maximum Depth</th>
            </thead>
            <tbody>
                <tr>
                    <td>Pacific</td>
                    <td>4280 m</td>
                    <td>10911 m</td>
                </tr>
                <tr>
                    <td>Atlantic</td>
                    <td>3646 m</td>
                    <td>8486 m</td>
                </tr>
            </tbody>
        </table>
    </body>
<html>
```

![meja buruk](https://cs50.harvard.edu/web/2020/notes/0/images/table0.png)

-   Di atas sangat mirip dengan apa yang kita miliki sebelumnya, tapi sekarang, baik dengan memasukkan `style`tag atau `link`ke stylesheet di elemen head, kita menambahkan css berikut:

```
table {
    border: 1px solid black;
    border-collapse: collapse;
}

td {
    border: 1px solid black;
    padding: 2px;
}

th {
    border: 1px solid black;
    padding: 2px;
}
```

Yang meninggalkan kita dengan tabel yang tampak lebih bagus ini:

![meja bagus](https://cs50.harvard.edu/web/2020/notes/0/images/table1.png)

-   Anda mungkin sudah berpikir bahwa ada pengulangan yang tidak perlu di CSS kita saat ini, karena `td`dan `th`memiliki gaya yang sama. Kita dapat (dan harus) memadatkan ini menjadi kode berikut, menggunakan koma untuk menunjukkan gaya harus berlaku untuk lebih dari satu jenis elemen.

```
table {
    border: 1px solid black;
    border-collapse: collapse;
}

td, th {
    border: 1px solid black;
    padding: 2px;
}
```

-   Ini adalah pengantar yang bagus tentang apa yang dikenal sebagai [penyeleksi CSS](https://www.w3schools.com/cssref/css_selectors.asp) . Ada banyak cara untuk menentukan elemen HTML mana yang Anda gaya, beberapa di antaranya akan kami sebutkan di sini:
    -   **element type** : inilah yang telah kita lakukan sejauh ini: menata semua elemen dengan tipe yang sama.
    -   **id**: Another option is to give our HTML elements an id like so: `<h1 id="first-header">Hello!</h1>` and then applying styling using `#first-header{...}` using the hashtag to show that we’re searching by id. Importantly, no two elements can have the same id, and no element can have more than one id.
    -   **class**: This is similar to id, but a class can be shared by more than one element, and a single element can have more than one class. We add classes to an HTML element like this: `<h1 class="page-text muted">Hello!</h1>` (note that we just added two classes to the element: `page-text` and `muted`). We then style based on class using a period instead of a hashtag: `.muted {...}`
-   Now, we also have to deal with the problem of potentially conflicting CSS. What happens when a header should be red based on its class but blue based on its id? CSS has a specificity order that goes:
    1.  Gaya in-line
    2.  pengenal
    3.  kelas
    4.  tipe elemen
-   Selain koma untuk beberapa penyeleksi, ada beberapa cara lain untuk menentukan elemen mana yang ingin Anda beri gaya. Tabel dari kuliah ini menyediakan beberapa, dan kita akan melihat beberapa contoh di bawah ini:

![penyeleksi](https://cs50.harvard.edu/web/2020/notes/0/images/selectors.png)

**Pemilih Keturunan** : Di sini, kami menggunakan pemilih keturunan untuk hanya menerapkan gaya pada item daftar yang ditemukan dalam daftar tidak berurutan:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Using Selectors</title>
        <style>
            ul li {
                color: blue;
            }
        </style>
    </head>
    <body>
        <ol>
            <li>foo</li>
            <li> bar
                <ul>
                    <li>hello</li>
                    <li>goodbye</li>
                    <li>hello</li>
                </ul>
            </li>
            <li>baz</li>
        </ol>

    </body>
<html>
```

![pemilih daftar](https://cs50.harvard.edu/web/2020/notes/0/images/selectors0.png)

**Atribut sebagai Pemilih** : Kita juga dapat mempersempit pilihan kita berdasarkan atribut yang kita tetapkan ke elemen HTML menggunakan tanda kurung. Misalnya, dalam daftar tautan berikut, kami memilih untuk hanya membuat tautan ke Amazon berwarna merah:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Using Selectors</title>
        <style>
            a[href="https://www.amazon.com/"] {
                color: red;
            }
        </style>
    </head>
    <body>
        <ol>
            <li><a href="https://www.google.com/">Google</a></li>
            <li><a href="https://www.amazon.com/">Amazon</a> </li>
            <li><a href="https://www.facebook.com/">Facebook</a></li>
        </ol>

    </body>
<html>
```

![pemilih tautan](https://cs50.harvard.edu/web/2020/notes/0/images/selectors2.png)

-   Kita tidak hanya dapat menggunakan CSS untuk mengubah tampilan elemen secara permanen, tetapi juga tampilannya dalam kondisi tertentu. Misalnya, bagaimana jika kita ingin sebuah tombol berubah warna saat kita mengarahkan kursor ke atasnya? Kita dapat mencapainya dengan menggunakan [CSS pseudoclass](https://www.w3schools.com/css/css_pseudo_classes.asp) , yang memberikan gaya tambahan selama keadaan khusus. Kami menulis ini dengan menambahkan titik dua setelah pemilih kami, dan kemudian menambahkan keadaan setelah titik dua itu.
-   Dalam kasus tombol, kami akan menambahkan `:hover`pemilih tombol untuk menentukan desain hanya saat melayang:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Pseudoclasses</title>
        <style>
            button {
                background-color: red;
                width: 200px;
                height: 50px;
                font-size: 24px;
            }

            button:hover {
                background-color: green;
            }
        </style>
    </head>
    <body>
        <button>Button 1</button>
        <button>Button 2</button>
        <button>Button 3</button>

    </body>
<html>
```

![tombol](https://cs50.harvard.edu/web/2020/notes/0/images/buttons.gif)

## [Desain responsif](https://cs50.harvard.edu/web/2020/notes/0/#responsive-design)

-   Saat ini, banyak orang melihat situs web di perangkat selain komputer, seperti smartphone dan tablet. Penting untuk memastikan situs web Anda dapat dibaca oleh orang-orang di semua perangkat.
-   Salah satu cara kita dapat mencapainya adalah melalui pengetahuan tentang **area pandang** . Area pandang adalah bagian layar yang benar-benar terlihat oleh pengguna pada waktu tertentu. Secara default, banyak halaman web berasumsi bahwa viewport sama pada perangkat apa pun, yang menyebabkan banyak situs (terutama yang lama) menjadi sulit untuk berinteraksi dengan perangkat seluler.
-   Salah satu cara sederhana untuk meningkatkan tampilan situs di perangkat seluler adalah dengan menambahkan baris berikut di kepala file HTML kita. Baris ini memberi tahu perangkat seluler untuk menggunakan area pandang yang lebarnya sama dengan perangkat yang Anda gunakan, bukan yang jauh lebih besar.

```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

-   Cara lain kita dapat menangani perangkat yang berbeda adalah melalui [kueri media](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp) . Kueri media adalah cara mengubah gaya halaman berdasarkan cara halaman dilihat.
-   Sebagai contoh kueri media, mari coba ubah warna layar saat menyusut ke ukuran tertentu. Kami memberi sinyal kueri media dengan mengetik `@media`diikuti dengan jenis kueri dalam tanda kurung:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Screen Size</title>
        <style>
            @media (min-width: 600px) {
                body {
                    background-color: red;
                }
            }

            @media (max-width: 599px) {
                body {
                    background-color: blue;
                }
            }
        </style>
    </head>
    <body>
        <h1>Welcome to the page!</h1>
    </body>
</html>
```

![ukuran layar](https://cs50.harvard.edu/web/2020/notes/0/images/responsive0.gif)

-   Cara lain untuk mengatasi ukuran layar yang berbeda adalah menggunakan atribut CSS baru yang dikenal sebagai [flexbox](https://www.w3schools.com/css/css3_flexbox.asp) . Ini memungkinkan kita untuk dengan mudah membungkus elemen ke baris berikutnya jika tidak pas secara horizontal. Kami melakukan ini dengan meletakkan semua elemen kami di wadah `div`yang kami sebut wadah kami. Kami kemudian menambahkan beberapa gaya ke div yang menentukan bahwa kami ingin menggunakan tampilan kotak fleksibel untuk elemen di dalamnya. Kami juga telah menambahkan beberapa gaya tambahan ke div bagian dalam untuk mengilustrasikan pembungkusan yang terjadi di sini dengan lebih baik.

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Screen Size</title>
        <style>
            #container {
                display: flex;
                flex-wrap: wrap;
            }

            #container > div {
                background-color: green;
                font-size: 20px;
                margin: 20px;
                padding: 20px;
                width: 200px;
            }
        </style>
    </head>
    <body>
        <div id="container">
            <div>Some text 1!</div>
            <div>Some text 2!</div>
            <div>Some text 3!</div>
            <div>Some text 4!</div>
            <div>Some text 5!</div>
            <div>Some text 6!</div>
            <div>Some text 7!</div>
            <div>Some text 8!</div>
            <div>Some text 9!</div>
            <div>Some text 10!</div>
            <div>Some text 11!</div>
            <div>Some text 12!</div>
        </div>
    </body>
</html>
```

![flexbox](https://cs50.harvard.edu/web/2020/notes/0/images/flexbox.gif)

-   Cara lain yang populer untuk menata halaman adalah dengan menggunakan [kotak](https://www.w3schools.com/css/css_grid.asp) HTML . Dalam kisi ini, kita dapat menentukan atribut gaya seperti lebar kolom dan celah antara kolom dan baris, seperti yang ditunjukkan di bawah ini. Perhatikan bahwa ketika kami menentukan lebar kolom, kami mengatakan yang ketiga adalah `auto`, artinya harus mengisi sisa halaman.

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>My Web Page!</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <style>
            .grid {
                background-color: green;
                display: grid;
                padding: 20px;
                grid-column-gap: 20px;
                grid-row-gap: 10px;
                grid-template-columns: 200px 200px auto;
            }

            .grid-item {
                background-color: white;
                font-size: 20px;
                padding: 20px;
                text-align: center;
            }
        </style>
    </head>
    <body>
        <div class="grid">
            <div class="grid-item">1</div>
            <div class="grid-item">2</div>
            <div class="grid-item">3</div>
            <div class="grid-item">4</div>
            <div class="grid-item">5</div>
            <div class="grid-item">6</div>
            <div class="grid-item">7</div>
            <div class="grid-item">8</div>
            <div class="grid-item">9</div>
            <div class="grid-item">10</div>
            <div class="grid-item">11</div>
            <div class="grid-item">12</div>
        </div>
    </body>
</html>
```

![kisi](https://cs50.harvard.edu/web/2020/notes/0/images/grid.gif)

## [Bootstrap](https://cs50.harvard.edu/web/2020/notes/0/#bootstrap)

-   Ternyata ada banyak pustaka yang telah ditulis orang lain yang dapat membuat gaya halaman web menjadi lebih sederhana. Salah satu pustaka populer yang akan kita gunakan sepanjang kursus ini dikenal sebagai [bootstrap](https://getbootstrap.com/) .
-   Kami dapat menyertakan bootstrap dalam kode kami dengan menambahkan satu baris ke kepala file HTML kami:

```
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">
```

-   Selanjutnya, kita dapat melihat beberapa fitur bootstrap dengan membuka bagian [dokumentasi](https://getbootstrap.com/docs/4.5/components/) di situs web mereka. Di halaman ini, Anda akan menemukan banyak contoh kelas yang bisa Anda tambahkan ke elemen yang memungkinkannya ditata dengan bootstrap.
-   [Salah satu fitur bootstrap yang populer adalah sistem grid](https://getbootstrap.com/docs/4.0/layout/grid/) mereka . Bootstrap secara otomatis membagi halaman menjadi 12 kolom, dan kita dapat memutuskan berapa banyak kolom yang dibutuhkan elemen dengan menambahkan kelas `col-x`di mana `x`angka antara 1 dan 12. Misalnya, di halaman berikut, kita memiliki deretan kolom dengan lebar yang sama , lalu baris dengan kolom tengah lebih besar:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>My Web Page!</title>
        <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
        <style>
            .row > div {
                padding: 20px;
                background-color: teal;
                border: 2px solid black;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="row">
                <div class="col-4">
                    This is a section.
                </div>
                <div class="col-4">
                    This is another section.
                </div>
                <div class="col-4">
                    This is a third section.
                </div>
            </div>
        </div>
        <br/>
        <div class="container">
            <div class="row">
                <div class="col-3">
                    This is a section.
                </div>
                <div class="col-6">
                    This is another section.
                </div>
                <div class="col-3">
                    This is a third section.
                </div>
            </div>
        </div>
    </body>
</html>
```

![kolom](https://cs50.harvard.edu/web/2020/notes/0/images/cols1.gif)

-   Untuk meningkatkan daya tanggap seluler, bootstrap juga memungkinkan kita untuk menentukan ukuran kolom yang berbeda tergantung ukuran layar. Dalam contoh berikut, kami menggunakan `col-lg-3`untuk menunjukkan bahwa sebuah elemen harus mengambil 3 kolom pada layar besar, dan `col-sm-6`untuk menunjukkan sebuah elemen harus mengambil 6 kolom saat layar kecil:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>My Web Page!</title>
        <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
        <style>
            .row > div {
                padding: 20px;
                background-color: teal;
                border: 2px solid black;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="row">
                <div class="col-lg-3 col-sm-6">
                    This is a section.
                </div>
                <div class="col-lg-3 col-sm-6">
                    This is another section.
                </div>
                <div class="col-lg-3 col-sm-6">
                    This is a third section.
                </div>
                <div class="col-lg-3 col-sm-6">
                    This is a fourth section.
                </div>
            </div>
        </div>
    </body>
</html>
```

![bungkus kolom](https://cs50.harvard.edu/web/2020/notes/0/images/cols2.gif)

## [Sass (Style Sheets yang Mengagumkan Secara Sintaktis)](https://cs50.harvard.edu/web/2020/notes/0/#sass-syntactically-awesome-style-sheets)

-   Sejauh ini, kami telah menemukan beberapa cara untuk menghilangkan redundansi di CSS seperti memindahkannya ke file terpisah atau menggunakan bootstrap, tetapi masih ada beberapa tempat yang masih dapat kami tingkatkan. Misalnya, bagaimana jika kita ingin beberapa elemen memiliki gaya yang berbeda, tetapi semuanya memiliki warna yang sama? Jika nanti kami memutuskan ingin mengubah warna, maka kami harus mengubahnya dalam beberapa elemen berbeda.
-   [Sass](https://sass-lang.com/) adalah bahasa yang memungkinkan kita menulis CSS dengan lebih efisien dalam beberapa cara, salah satunya adalah dengan mengizinkan kita memiliki variabel, seperti pada contoh berikut.
-   Saat menulis di Sass, kami membuat file baru dengan ekstensi `filename.scss`. Dalam file ini, kita dapat membuat variabel baru dengan menambahkan `$`sebelum nama, lalu titik dua, lalu nilai. Misalnya, kita akan menulis `$color: red`untuk menyetel warna variabel ke nilai merah. Kami kemudian mengakses variabel itu menggunakan `$color`. Berikut adalah contoh file variable.scss kami:

```
$color: red;

ul {
    font-size: 14px;
    color: $color;
}

ol {
    font-size: 18px;
    color: $color;
}
```

-   Sekarang, untuk menautkan gaya ini ke file HTML kita, kita tidak bisa hanya menautkan ke file `.scss`karena sebagian besar browser web hanya mengenali `.css`file. Untuk mengatasi masalah ini, kita harus [mengunduh program bernama Sass](https://sass-lang.com/install) ke komputer kita. Kemudian, di terminal kami, kami menulis `sass variables.scss:variables.css`Perintah ini akan mengkompilasi file .scss bernama `variables.scss`menjadi file .css bernama `variables.css`, yang dapat Anda tambahkan tautan di halaman HTML Anda.
-   Untuk mempercepat proses ini, kita dapat menggunakan perintah `sass --watch variables.scss:variables.css`yang secara otomatis mengubah `.css`file setiap kali terdeteksi perubahan pada `.scss`file.
-   Saat menggunakan Sass, kita juga dapat secara fisik menyusun gaya kita daripada menggunakan pemilih CSS yang kita bicarakan sebelumnya. Misalnya, jika kita ingin menerapkan beberapa gaya hanya pada paragraf dan daftar tidak berurutan di dalam div, kita dapat menulis sebagai berikut:

```
div {
    font-size: 18px;

    p {
        color: blue;
    }

    ul {
        color: green;
    }
}
```

Setelah dikompilasi ke dalam CSS, kita akan mendapatkan file yang terlihat seperti:

```
div {
    font-size: 18px;
}

div p {
    color: blue;
}

div ul {
    color: green;
}
```

-   Satu lagi fitur yang diberikan Sass kepada kita dikenal sebagai [warisan](https://sass-lang.com/guide) . Ini memungkinkan kita untuk membuat satu set gaya dasar yang dapat digunakan bersama oleh beberapa elemen berbeda. Kami melakukan ini dengan menambahkan `%`sebelum nama kelas, menambahkan beberapa gaya, dan kemudian menambahkan baris `@extend %classname`ke awal beberapa gaya. Misalnya, kode berikut menerapkan gaya di dalam `message`kelas ke masing-masing kelas berbeda di bawah, menghasilkan laman web yang terlihat seperti di bawah ini.

```
%message {
    font-family: sans-serif;
    font-size: 18px;
    font-weight: bold;
    border: 1px solid black;
    padding: 20px;
    margin: 20px;
}

.success {
    @extend %message;
    background-color: green;
}

.warning {
    @extend %message;
    background-color: orange;
}

.error {
    @extend %message;
    background-color: red;
}
```

![warisan](https://cs50.harvard.edu/web/2020/notes/0/images/inherit.png)

-   Itu mengakhiri konten kita untuk hari ini!
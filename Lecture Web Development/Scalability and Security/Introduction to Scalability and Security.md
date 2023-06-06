# [Kuliah 8](https://cs50.harvard.edu/web/2020/notes/8/#lecture-8)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/8/#introduction)
-   [Skalabilitas](https://cs50.harvard.edu/web/2020/notes/8/#scalability)
-   [Penskalaan](https://cs50.harvard.edu/web/2020/notes/8/#scaling)
-   [Penyeimbang beban](https://cs50.harvard.edu/web/2020/notes/8/#load-balancing)
-   [Penskalaan otomatis](https://cs50.harvard.edu/web/2020/notes/8/#autoscaling)
    -   [Kegagalan Server](https://cs50.harvard.edu/web/2020/notes/8/#server-failure)
-   [Penskalaan Database](https://cs50.harvard.edu/web/2020/notes/8/#scaling-databases)
    -   [Replikasi Basis Data](https://cs50.harvard.edu/web/2020/notes/8/#database-replication)
-   [Caching](https://cs50.harvard.edu/web/2020/notes/8/#caching)
-   [Keamanan](https://cs50.harvard.edu/web/2020/notes/8/#security)
    -   [Git dan GitHub](https://cs50.harvard.edu/web/2020/notes/8/#git-and-github)
-   [HTML](https://cs50.harvard.edu/web/2020/notes/8/#html)
-   [HTTPS](https://cs50.harvard.edu/web/2020/notes/8/#https)
    -   [Kriptografi Kunci Rahasia](https://cs50.harvard.edu/web/2020/notes/8/#secret-key-cryptography)
    -   [Kriptografi Kunci Publik](https://cs50.harvard.edu/web/2020/notes/8/#public-key-cryptography)
-   [Database](https://cs50.harvard.edu/web/2020/notes/8/#databases)
    -   [Lebah](https://cs50.harvard.edu/web/2020/notes/8/#apis)
    -   [Variabel Lingkungan](https://cs50.harvard.edu/web/2020/notes/8/#environment-variables)
-   [JavaScript](https://cs50.harvard.edu/web/2020/notes/8/#javascript)
    -   [Pemalsuan Permintaan Lintas Situs](https://cs50.harvard.edu/web/2020/notes/8/#cross-site-request-forgery)
-   [Apa berikutnya?](https://cs50.harvard.edu/web/2020/notes/8/#whats-next)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/8/#introduction)

-   Sejauh ini, kita telah membahas cara membuat halaman web sederhana menggunakan HTML dan CSS, serta cara menggunakan Git dan GitHub untuk melacak perubahan pada kode kita dan berkolaborasi dengan orang lain. Kami juga membiasakan diri dengan bahasa pemrograman Python, mulai menggunakan Django untuk membuat aplikasi web, dan mempelajari cara menggunakan model Django untuk menyimpan informasi di situs kami. Kami kemudian memperkenalkan JavaScript dan belajar bagaimana menggunakannya untuk membuat halaman web lebih interaktif, dan berbicara tentang penggunaan animasi dan React untuk lebih meningkatkan Antarmuka Pengguna kami. Kami kemudian berbicara tentang beberapa praktik terbaik dalam pengembangan perangkat lunak dan beberapa teknologi yang biasa digunakan untuk mencapai praktik terbaik tersebut.
-   Hari ini, dalam kuliah terakhir kita, kita akan membahas masalah penskalaan dan pengamanan aplikasi web kita.

## [Skalabilitas](https://cs50.harvard.edu/web/2020/notes/8/#scalability)

Sejauh ini dalam kursus ini, kami telah membuat aplikasi yang hanya dijalankan secara lokal di komputer kami, tetapi pada akhirnya, kami ingin meluncurkan situs kami agar dapat diakses oleh siapa saja di internet. Untuk melakukan ini, kami menjalankan situs kami di **server** , yang merupakan perangkat keras fisik yang didedikasikan untuk menjalankan aplikasi. Server dapat berada di tempat (Kami memiliki dan memelihara server fisik tempat aplikasi kami dihosting) atau di cloud (server dimiliki oleh perusahaan lain seperti Amazon atau Google, dan kami membayar untuk menyewa ruang server tempat aplikasi kami dihosting ). Ada keuntungan dan kerugian dari kedua opsi tersebut:

-   **Kustomisasi** : Hosting server Anda sendiri memberi Anda kemampuan untuk memutuskan dengan tepat bagaimana mereka bekerja, memungkinkan lebih banyak fleksibilitas daripada hosting berbasis cloud.
-   **Keahlian** : Menghosting aplikasi di cloud jauh lebih mudah daripada memelihara server Anda sendiri.
-   **Biaya** : Karena situs hosting server perlu mendapat untung, mereka akan menagih Anda lebih dari biaya untuk memelihara server di tempat mereka, membuat server berbasis cloud lebih mahal. Namun, biaya awal untuk menjalankan server di lokasi bisa tinggi, karena Anda perlu membeli server fisik dan berpotensi mempekerjakan seseorang dengan keahlian untuk menyiapkannya.
-   **Skalabilitas** : Penskalaan biasanya lebih mudah saat hosting di cloud. Misalnya, jika kami menghosting situs di tempat yang mendapat 500 kunjungan per hari, lalu mulai mendapatkan 500.000 kunjungan per hari, kami harus memesan dan menyiapkan lebih banyak server fisik untuk menangani permintaan, dan sementara itu banyak dari kami pengguna tidak akan dapat mengakses situs tersebut. Sebagian besar situs cloud hosting memungkinkan Anda untuk menyewa ruang server secara fleksibel, membayar berdasarkan seberapa banyak aktivitas yang dilihat situs Anda.

Saat pengguna mengirim permintaan HTTP ke server ini, server harus mengirim kembali respons. Namun, pada kenyataannya, sebagian besar server mendapatkan lebih dari satu permintaan sekaligus, seperti yang digambarkan di bawah ini:

![server banyak masukan](https://cs50.harvard.edu/web/2020/notes/8/images/server0.png)

Di sinilah kami mengalami masalah skalabilitas. Satu server hanya dapat menangani begitu banyak permintaan sekaligus, memaksa kami untuk membuat rencana tentang apa yang harus dilakukan ketika satu server kami terlalu banyak bekerja. Apakah kami memutuskan untuk menghosting di tempat atau di cloud, kami harus menentukan berapa banyak permintaan yang dapat ditangani server tanpa mogok, yang dapat dilakukan menggunakan sejumlah alat **pembandingan** termasuk Apache Bench.

## [Penskalaan](https://cs50.harvard.edu/web/2020/notes/8/#scaling)

Setelah kami memiliki batas atas berapa banyak permintaan yang dapat ditangani oleh server kami, kami dapat mulai memikirkan tentang bagaimana kami ingin menangani penskalaan aplikasi kami. Dua pendekatan berbeda untuk penskalaan meliputi:

1.  **Penskalaan Vertikal** : Dalam penskalaan vertikal, ketika server kami kewalahan, kami cukup membeli atau membangun server yang lebih besar. Namun strategi ini terbatas, karena ada batas atas seberapa kuat server tunggal.
2.  **Penskalaan Horizontal** : Dalam penskalaan horizontal, ketika server kami kewalahan, kami membeli atau membangun lebih banyak server, dan kemudian membagi permintaan di antara beberapa server kami.

## [Penyeimbang beban](https://cs50.harvard.edu/web/2020/notes/8/#load-balancing)

Saat kami menggunakan penskalaan horizontal, kami dihadapkan pada masalah tambahan tentang bagaimana kami memutuskan server mana yang ditugaskan untuk permintaan mana. Kami menjawab pertanyaan itu dengan menggunakan **load balancer** , yang merupakan perangkat keras lain yang mencegat permintaan masuk, dan kemudian menetapkan permintaan tersebut ke salah satu server kami. Ada sejumlah metode berbeda untuk memutuskan server mana yang menerima permintaan mana, tetapi berikut beberapa di antaranya:

-   **Acak** : Dalam metode sederhana ini, penyeimbang beban akan memutuskan secara acak server mana yang harus ditetapkan permintaannya.
-   **Round-Robin** : Dalam metode ini, penyeimbang beban akan bergantian server mana yang menerima permintaan masuk. Jika kita memiliki tiga server, permintaan pertama mungkin ke server A, yang kedua ke server B, yang ketiga ke server C, dan yang keempat kembali ke server A.
-   **Koneksi Paling Sedikit** : Dalam metode ini, penyeimbang beban mencari server yang saat ini menangani permintaan paling sedikit, dan menetapkan permintaan yang masuk ke server tersebut. Hal ini memungkinkan kami untuk memastikan bahwa kami tidak terlalu banyak bekerja pada satu server tertentu, tetapi penyeimbang beban juga membutuhkan waktu lebih lama untuk menghitung jumlah permintaan yang saat ini ditangani oleh setiap server daripada hanya memilih server acak.

Tidak ada metode load balancing yang benar-benar lebih baik dari semua metode lainnya, dan ada banyak metode berbeda yang digunakan dalam praktiknya. Satu masalah yang dapat muncul saat menskalakan secara horizontal adalah kami mungkin memiliki sesi yang disimpan di satu server tetapi tidak di server lain, dan kami tidak ingin pengguna harus memasukkan kembali informasi hanya karena penyeimbang beban mendorong permintaan mereka ke server baru . Seperti banyak masalah skalabilitas, ada beberapa pendekatan untuk memecahkan masalah sesi:

-   **Sesi Sticky** : Setelah pengguna mengunjungi situs, penyeimbang beban mengingat server mana yang mereka kirim terlebih dahulu, dan memastikan untuk mengirim mereka ke server yang sama. Salah satu kekhawatiran besar dengan metode ini adalah bahwa kami dapat berakhir dengan sejumlah besar pengguna yang menempel pada satu server, menyebabkannya macet.
-   **Sesi Database** : Semua sesi disimpan dalam database yang dapat diakses oleh semua server. Dengan cara ini, informasi pengguna akan tersedia terlepas dari server mana mereka ditugaskan. Kelemahannya di sini adalah dibutuhkan waktu tambahan dan daya komputasi untuk membaca dari dan menulis ke database.
-   **Sesi Sisi Klien** : Daripada menyimpan informasi di server kami, kami dapat memilih untuk menyimpannya secara lokal di browser web pengguna sebagai cookie. Kelemahan dari metode ini termasuk masalah keamanan pengguna yang membuat cookie palsu yang memungkinkan mereka masuk sebagai pengguna lain, dan masalah komputasi untuk mengirim informasi cookie bolak-balik dengan setiap permintaan.

Seperti dengan penyeimbangan beban, tidak ada jawaban terbaik untuk masalah sesi, dan metode yang Anda pilih seringkali bergantung pada keadaan khusus Anda.

## [Penskalaan otomatis](https://cs50.harvard.edu/web/2020/notes/8/#autoscaling)

Masalah lain yang mungkin kita temui adalah banyak situs web yang lebih sering dikunjungi pada waktu-waktu tertentu. Misalnya, jika kami memutuskan untuk meluncurkan "Is it New Year's?" aplikasi dari sebelumnya, kami mungkin mengharapkannya mendapatkan lebih banyak lalu lintas di akhir Desember hingga awal Januari dibandingkan waktu lainnya sepanjang tahun. Jika kami membeli cukup banyak server agar situs tetap aktif selama musim dingin, server tersebut akan menganggur selama sisa tahun, membuang-buang ruang dan energi. Skenario ini telah menghasilkan ide **penskalaan otomatis**yang telah menjadi hal umum dalam komputasi awan, di mana jumlah server yang digunakan oleh situs Anda dapat bertambah dan menyusut berdasarkan jumlah permintaan yang didapat. Penskalaan otomatis bukanlah solusi yang sempurna, karena butuh waktu untuk menentukan bahwa server baru diperlukan dan untuk meluncurkan server tersebut. Masalah potensial lainnya adalah semakin banyak server yang Anda jalankan, semakin banyak peluang untuk gagal.

### [Kegagalan Server](https://cs50.harvard.edu/web/2020/notes/8/#server-failure)

Namun, memiliki banyak server, dapat membantu menghindari apa yang dikenal sebagai **Titik Kegagalan Tunggal** , yang merupakan perangkat keras yang, setelah gagal, akan menyebabkan seluruh situs mogok. Saat menskalakan secara horizontal, penyeimbang beban dapat mendeteksi server mana yang mogok dengan mengirimkan permintaan **detak jantung** berkala ke setiap server, lalu berhenti menetapkan permintaan baru ke server yang mogok. Pada titik ini, tampaknya kami hanya memindahkan satu titik kegagalan kami dari server ke penyeimbang beban, tetapi kami dapat menjelaskan hal ini dengan menyediakan penyeimbang beban cadangan jika sumber asli kami mogok.

## [Penskalaan Database](https://cs50.harvard.edu/web/2020/notes/8/#scaling-databases)

Selain menskalakan server kami yang memproses permintaan, kami juga ingin memikirkan cara untuk menskalakan Basis Data kami. Dalam kursus ini kami menggunakan SQLite yang menyimpan data di dalam file di server, tetapi karena kami menyimpan semakin banyak data, terkadang lebih masuk akal untuk menyimpan data di sejumlah file berbeda, dan bahkan mungkin di server terpisah. Ini memunculkan masalah tentang apa yang harus dilakukan ketika server basis data kami tidak dapat lagi menangani semua permintaan yang masuk. Seperti dalam masalah skalabilitas lainnya, ada sejumlah metode yang dapat kami gunakan untuk mengurangi masalah ini:

-   **Partisi Vertikal** : Ini adalah metode yang mirip dengan yang kami gunakan ketika pertama kali membahas SQL, di mana kami membagi data kami menjadi beberapa tabel berbeda daripada memiliki informasi yang berlebihan dalam satu tabel. (Jangan ragu untuk melihat kembali kuliah 4 di mana kami membagi `flights`tabel menjadi `flights`tabel dan `airports`tabel).
-   **Partisi Horizontal** : Metode ini melibatkan penyimpanan banyak tabel dengan format yang sama, tetapi informasi berbeda. Misalnya, kita dapat membagi `flights`tabel menjadi `domestic_flights`tabel dan `international_flights`tabel. Dengan begitu, saat kita ingin mencari penerbangan dari JFK ke LHR, kita tidak perlu membuang waktu mencari di meja yang penuh dengan penerbangan domestik. Salah satu kelemahan dari metode ini adalah biayanya mahal untuk menggabungkan beberapa tabel setelah dipisahkan.

### [Replikasi Basis Data](https://cs50.harvard.edu/web/2020/notes/8/#database-replication)

Bahkan setelah kami menskalakan basis data, tampaknya kami masih memiliki satu titik kegagalan. Jika server database kita crash, semua data kita bisa hilang. Sama seperti kami menambahkan lebih banyak server untuk menghindari satu titik kegagalan, kami dapat menambahkan salinan database kami untuk memastikan kegagalan satu database tidak mematikan aplikasi kami. Juga seperti sebelumnya ada berbagai metode replikasi basis data, dua di antaranya yang paling populer adalah:

-   **Replikasi Single-Primary** : Dalam metode ini ada banyak database, tetapi hanya satu yang dianggap sebagai database utama, artinya Anda dapat membaca dari dan menulis ke salah satu database, tetapi hanya membaca dari database lainnya. Ketika database utama diperbarui, database lain kemudian diperbarui agar cocok dengan yang utama. Salah satu kelemahan dari metode ini adalah masih mengandung satu titik kegagalan saat menulis ke database.

![visual primer tunggal](https://cs50.harvard.edu/web/2020/notes/8/images/single_primary.png)

-   **Replikasi Multi-Primer** : Dalam metode ini, semua database dapat dibaca dan ditulis. Ini memecahkan masalah satu titik kegagalan, tetapi disertai dengan pengorbanan: sekarang jauh lebih sulit untuk memperbarui semua database karena setiap database harus mengetahui perubahan pada semua database lainnya. Sistem ini juga mengatur kami untuk kemungkinan beberapa konflik:
    -   **Perbarui Konflik** : Dengan banyak basis data, satu pengguna dapat mencoba mengedit baris dalam satu basis data sementara pengguna lain mencoba mengedit baris yang sama di basis data yang berbeda, menyebabkan masalah saat basis data disinkronkan.
    -   **Konflik Keunikan** : Setiap baris dalam database SQL harus memiliki pengidentifikasi unik, dan kami mungkin mengalami masalah saat kami menetapkan id yang sama ke dua entri berbeda di dua database berbeda.
    -   **Hapus Konflik** : Satu pengguna dapat menghapus baris sementara pengguna lain mencoba memperbaruinya.

![visual multi primer](https://cs50.harvard.edu/web/2020/notes/8/images/multi_primary.png)

## [Caching](https://cs50.harvard.edu/web/2020/notes/8/#caching)

Whenever we’re working with larger databases, it is important to recognize that every interaction we have with a database is costly. Therefore, we wish to minimize the number of calls to our database server. Let’s look, for example, at the [New York Times](https://www.nytimes.com/) website. The New York Times may have some database with all of their articles which is queried and some template that is rendered every time someone loads the home page, but this would be a waste of resources, as the articles displayed on the home page likely do not change much from second to second. One way we can deal with this problem is by using **Caching**, which is the idea of storing some information in a more accessible location if we anticipate needing it again in the near future.

One way that caching can be implemented is by storing data on the user’s web browser, so that when a user loads certain pages, no request to the server even needs to be sent. One way to do this is by including this line in the header of an HTTP response:

```
Cache-Control: max-age=86400
```

This will tell the browser that when visiting a page, as long as I have visited that page within the last 86400 milliseconds, no request has to be made to the server. This method is used commonly by web browsers especially with files that are less likely to change over short periods such as a CSS file. To take more control over this process, we can also add an `ETag` to the HTTP response header, which is a unique sequence of characters that represents a specific version of a document. This is useful because future requests can include this tag and compare it to the tag of the latest document on the server, only returning an entire document when the two differ.

In addition to the client-side caching discussed above, it can often be helpful to include a cache on the server side. With this cache, our backend setup will look a bit like the one below, where all servers have access to a cache.

![caching server](https://cs50.harvard.edu/web/2020/notes/8/images/server_cache.png)

Django provides its own [cache framework](https://docs.djangoproject.com/en/4.0/topics/cache/) which will allow us to incorporate caching in our projects. This framework offers several ways of implementing a cache:

-   **Per-View Caching**: This allows us to decide that once a specific view has been loaded, that same view can be rendered without going through the function for the next specified amount of time.
-   **Template-Fragment Caching**: This caches specific parts of a template so they do not have to be re-rendered. For example, we may have a navigation bar that rarely changes, meaning we could save time by not reloading it.
-   **Low-Level Cache API**: This allows you to do more flexible caching, essentially storing any information you would like to.

We won’t go into the details here of how to implement caching in Django, but do take a look at the [documentation](https://docs.djangoproject.com/en/4.0/topics/cache/) if you’re interested!

## [Security](https://cs50.harvard.edu/web/2020/notes/8/#security)

Now, we’ll begin to discuss how to make sure our web applications are secure, which will involve many different measures that span nearly every topic we’ve discussed in this course.

### [Git and GitHub](https://cs50.harvard.edu/web/2020/notes/8/#git-and-github)

One of the greatest strengths of Git and GitHub is how easy they make it to share and contribute to **open-source software**, which can be seen and contributed to by anyone on the internet. One drawback to this is that if at any point you commit a file that includes some private credentials like a password or API key, those credentials could be publicly available.

## [HTML](https://cs50.harvard.edu/web/2020/notes/8/#html)

There are many vulnerabilities that arise from using HTML. One common weakness is known as a **Phishing Attack**, which occurs when a user who thinks they are going to one page is actually taken to another. These are not necesarily things we can account for when designing a website, but we should definitely keep them in mind when interacting with the web ourselves. For example, a malicious user might write out this HTML:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Link</title>
    </head>
    <body>
        <a href="https://cs50.harvard.edu/">https://www.google.com/</a>
    </body>
</html>
```

Yang bertindak seperti ini:

![serangan phishing](https://cs50.harvard.edu/web/2020/notes/8/images/phishing.gif)

Fakta bahwa HTML benar-benar dikirim ke pengguna sebagai bagian dari permintaan membuka lebih banyak kerentanan, karena setiap orang memiliki akses ke tata letak dan gaya yang memungkinkan Anda membuat situs Anda. Misalnya, seorang peretas dapat membuka [bankofamerica.com](https://cs50.harvard.edu/) , menyalin semua HTML mereka, dan menempelkannya di situs mereka sendiri, membuat situs yang terlihat persis seperti milik Bank of America. Peretas kemudian dapat mengalihkan formulir login di halaman sehingga semua nama pengguna dan kata sandi dikirimkan kepada mereka. (Juga, inilah [tautan Bank of America asli](https://www.bankofamerica.com/) – hanya ingin melihat apakah Anda memeriksa url sebelum mengklik!)

## [HTTPS](https://cs50.harvard.edu/web/2020/notes/8/#https)

Seperti yang telah kita bahas sebelumnya dalam kursus ini, sebagian besar interaksi yang terjadi secara online mengikuti protokol HTTP, meskipun sekarang semakin banyak transaksi menggunakan HTTPS, yang merupakan versi HTTP terenkripsi. Saat menggunakan protokol ini, informasi ditransfer dari satu komputer ke komputer lain melalui serangkaian server seperti yang digambarkan di bawah ini.

![mentransfer](https://cs50.harvard.edu/web/2020/notes/8/images/servers.png)

Seringkali tidak ada cara untuk memastikan bahwa semua transfer ini aman, jadi penting bahwa semua informasi yang ditransfer ini dienkripsi **,** artinya karakter pesan diubah sehingga pengirim dan penerima pesan dapat memahaminya, tapi tidak ada orang lain yang bisa.

### [Kriptografi Kunci Rahasia](https://cs50.harvard.edu/web/2020/notes/8/#secret-key-cryptography)

One approach to this is known as **Secret-Key Cryptography**. In this approach, the sender and receiver both have access to a secret key that only they know. Then, the secret key is used by the sender to encrypt a message which is then sent to the recipient who uses the secret key to decrypt the message. This method is extremely secure, but it produces a big problem when it comes to practicality. In order for it to work, both the sender and the receiver must have access to the secret key, which means they must meet in person to exchange a key securely. With the number of different websites we interact with on a daily basis, it is clear that in-person meetups are not an option.

### [Public-Key Cryptography](https://cs50.harvard.edu/web/2020/notes/8/#public-key-cryptography)

An incredible advancement in cryptography that allows the internet to function as it does today is known as **Public-Key Cryptography**. In this method, there are two keys: one is public and can be shared, and the other must be kept private. Once these keys are established (there are several different mathematical methods for creating pairs of keys which could make up an entire course on their own, so we won’t discuss them here), a sender could look up the public key of a recipient and use it to encrypt a message, and then the recipient could use their private key to decrypt the message. When we use HTTPS rather than HTTP, we know that our request is being secured using public-key encryption.

## [Databases](https://cs50.harvard.edu/web/2020/notes/8/#databases)

In addition to our requests and responses, we must also make sure that our databases are secure. One common thing we’ll need to store is user information, including usernames and passwords as in the table below:

![meja yang buruk](https://cs50.harvard.edu/web/2020/notes/8/images/passwords.png)

However, you never actually want to store passwords in plaintext in case an unauthorized person gets access to your database. Instead, we’ll want to use a **hash function**, a function that takes in some text and outputs a seemingly random string, to create a hash of each password, as in the table below:

![meja bagus](https://cs50.harvard.edu/web/2020/notes/8/images/hashes.png)

Penting untuk dicatat bahwa fungsi hash adalah **satu arah** , artinya dapat mengubah kata sandi menjadi hash, tetapi tidak dapat mengubah hash kembali menjadi kata sandi. Ini berarti bahwa perusahaan mana pun yang menyimpan informasi pengguna dengan cara ini sebenarnya tidak mengetahui kata sandi pengguna, yang berarti setiap kali pengguna mencoba masuk, kata sandi yang dimasukkan akan di-hash dan dibandingkan dengan hash yang ada. Syukurlah, proses ini sudah ditangani untuk kita oleh Django. Salah satu implikasi dari teknik penyimpanan ini adalah ketika pengguna lupa kata sandinya, perusahaan tidak memiliki cara untuk memberi tahu mereka apa kata sandi lama mereka sekarang, artinya mereka harus membuat yang baru.

Ada beberapa kasus di mana sebagai pengembang Anda harus memutuskan berapa banyak informasi yang ingin Anda bocorkan. Misalnya, banyak situs memiliki halaman lupa kata sandi yang terlihat seperti ini:

![password yang terlupakan?](https://cs50.harvard.edu/web/2020/notes/8/images/forgot0.png)

Sebagai pengembang, Anda mungkin ingin menyertakan pesan sukses atau pesan kesalahan setelah pengiriman:

![pesan sukses](https://cs50.harvard.edu/web/2020/notes/8/images/sent.png)

![pesan eror](https://cs50.harvard.edu/web/2020/notes/8/images/error.png)

Namun perhatikan bagaimana dengan mengetikkan email, siapa pun dapat menentukan siapa yang memiliki email yang terdaftar di situs itu. Ini bisa sangat baik dalam kasus di mana apakah seseorang menggunakan situs itu tidak penting atau tidak (mungkin Facebook), tetapi sangat ceroboh jika fakta bahwa Anda adalah anggota dari situs tertentu dapat membahayakan Anda (mungkin grup dukungan online untuk korban pelecehan).

Cara lain data bisa bocor adalah dalam waktu yang dibutuhkan untuk respon untuk kembali. Mungkin perlu waktu lebih sedikit untuk menolak seseorang dengan email yang tidak valid daripada orang dengan alamat email yang benar dan kata sandi yang salah.

Seperti yang telah kita bahas sebelumnya dalam kursus ini, kita harus berhati-hati terhadap Serangan Injeksi SQL setiap kali kita menggunakan kueri SQL langsung dalam kode kita.

### [Lebah](https://cs50.harvard.edu/web/2020/notes/8/#apis)

Kami sering menggunakan JavaScript bersama dengan API untuk membangun aplikasi satu halaman. Jika kita membangun API kita sendiri, ada beberapa metode yang dapat kita gunakan untuk menjaga keamanan API kita:

-   **Kunci API** : Hanya memproses permintaan dari klien API yang memiliki kunci yang telah Anda berikan kepada mereka.
-   **Pembatasan Tingkat** : Batasi jumlah permintaan yang dapat dibuat oleh satu pengguna dalam jangka waktu tertentu. Ini membantu melindungi terhadap **Serangan Denial of Service (DOS)** , di mana pengguna jahat membuat begitu banyak panggilan ke API Anda sehingga macet.
-   **Otentikasi Rute** : Ada banyak kasus di mana kami tidak ingin memberikan semua orang akses ke semua data kami, jadi kami dapat menggunakan otentikasi rute untuk memastikan hanya pengguna tertentu yang dapat melihat data tertentu.

### [Variabel Lingkungan](https://cs50.harvard.edu/web/2020/notes/8/#environment-variables)

Sama seperti kita ingin menghindari menyimpan kata sandi dalam teks biasa, kita juga ingin menghindari menyertakan kunci API dalam kode sumber kita. Salah satu cara umum untuk menghindari hal ini adalah dengan menggunakan **variabel lingkungan** , atau variabel yang disimpan di sistem operasi atau lingkungan server Anda. Kemudian, daripada menyertakan string teks dalam kode sumber kami, kami dapat menyertakan referensi ke variabel lingkungan.

## [JavaScript](https://cs50.harvard.edu/web/2020/notes/8/#javascript)

Ada beberapa jenis serangan yang mungkin dicoba oleh pengguna jahat menggunakan JavaScript. Salah satu contohnya adalah knwon sebagai **Cross-Site Scripting** , yaitu saat pengguna menulis kode JavaScript mereka sendiri dan menjalankannya di situs web Anda. Misalnya, bayangkan kita memiliki aplikasi Django dengan satu URL:

```
urlpatterns = [
    path("<path:path>", views.index, name="index")
]
```

dan satu tampilan:

```
def index(request, path):
    return HttpResponse(f"Requested Path: {path}")
```

Situs web ini pada dasarnya memberi tahu pengguna URL apa yang telah mereka tuju:

![jalan yang baik](https://cs50.harvard.edu/web/2020/notes/8/images/pathworks.png)

Tetapi pengguna sekarang dapat dengan mudah memasukkan beberapa Javascript ke halaman dengan mengetikkannya di url:

![jalan yang buruk](https://cs50.harvard.edu/web/2020/notes/8/images/inject.gif)

Meskipun `alert`contoh ini cukup tidak berbahaya, tidak akan terlalu sulit untuk menyertakan beberapa JavaScript yang memanipulasi DOM atau digunakan `fetch`untuk mengirim permintaan.

### [Pemalsuan Permintaan Lintas Situs](https://cs50.harvard.edu/web/2020/notes/8/#cross-site-request-forgery)

Kita sudah membahas bagaimana kita bisa menggunakan Django untuk mencegah serangan CSRF, tapi mari kita lihat apa yang bisa terjadi tanpa perlindungan ini. Sebagai contoh, bayangkan sebuah bank memiliki URL yang dapat Anda kunjungi yang mentransfer uang dari rekening Anda. Seseorang dapat dengan mudah membuat tautan yang akan melakukan transfer ini:

```
<a href="http://yourbank.com/transfer?to=brian&amt=2800">
    Click Here!
</a> 
```

Serangan ini bahkan bisa lebih halus daripada tautan. Jika URL dimasukkan ke dalam gambar, maka itu akan diakses saat browser Anda mencoba memuat gambar:

```
 <img src="http://yourbank.com/transfer?to=brian&amt=2800"> 
```

Oleh karena itu, setiap kali Anda membuat aplikasi yang dapat menerima beberapa perubahan status, itu harus dilakukan dengan menggunakan permintaan POST. Bahkan jika bank memerlukan permintaan POST, bidang formulir tersembunyi masih dapat mengelabui pengguna agar tidak sengaja mengirimkan permintaan. Formulir berikut bahkan tidak menunggu pengguna mengklik; itu secara otomatis mengirimkan!

```
 <body onload="document.forms[0].submit()">
    <form action="https://yourbank.com/transfer"
    method="post">
        <input type="hidden" name="to" value="brian">
        <input type="hidden" name="amt" value="2800">
        <input type="submit" value="Click Here!">
    </form>
</body>
```

Di atas adalah contoh seperti apa **Pemalsuan Permintaan Lintas Situs** . Kami dapat menghentikan serangan seperti ini dengan membuat token CSRF saat memuat halaman web, lalu hanya menerima formulir dengan token yang valid.

## [Apa berikutnya?](https://cs50.harvard.edu/web/2020/notes/8/#whats-next)

Kami telah membahas banyak kerangka kerja web di kelas ini seperti Django dan React, tetapi ada lebih banyak kerangka kerja yang mungkin menarik untuk Anda coba:

-   Sisi server
    -   [Express.js](https://expressjs.com/)
    -   [Ruby di Rel](https://rubyonrails.org/)
    -   [Labu](https://flask.palletsprojects.com/en/1.1.x/)
    -   …
-   Sisi klien
    -   [Sudut JS](https://angularjs.org/)
    -   [Reaksi](https://reactjs.org/)
    -   [Vue.js](https://vuejs.org/)
    -   [Bereaksi Asli](https://reactnative.dev/)
    -   …

Di masa mendatang, Anda mungkin juga ingin dapat menerapkan situs Anda ke web, yang dapat Anda lakukan melalui sejumlah layanan berbeda:

-   [Layanan Web Amazon](https://aws.amazon.com/getting-started/hands-on/websites/)
-   [GitHub](https://github.com/)
-   [Heroku](https://www.heroku.com/)
-   [Netlify](https://app.netlify.com/)
-   [Google Cloud](https://cloud.google.com/)
-   [Microsoft Azure](https://azure.microsoft.com/en-gb/)
-   …

Kami telah menempuh perjalanan jauh dan membahas banyak materi sejak awal kursus ini, tetapi masih banyak yang harus dipelajari di dunia pemrograman web. Meskipun kadang-kadang bisa membuat kewalahan, salah satu cara terbaik untuk mempelajari lebih lanjut adalah dengan terjun ke proyek dan melihat seberapa jauh Anda dapat menjalankannya. Kami percaya bahwa pada titik ini Anda memiliki dasar yang kuat dalam konsep desain web, dan Anda memiliki apa yang diperlukan untuk mengubah ide menjadi situs web kerja Anda sendiri!
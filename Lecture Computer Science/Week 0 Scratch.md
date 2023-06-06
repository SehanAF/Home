# [Kuliah 0](https://cs50.harvard.edu/college/2022/fall/notes/0/#lecture-0)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/0/#welcome)
-   [Apa yang Ada di Depan](https://cs50.harvard.edu/college/2022/fall/notes/0/#whats-ahead)
-   [Masyarakat!](https://cs50.harvard.edu/college/2022/fall/notes/0/#community)
-   [Berpikir Komputasi](https://cs50.harvard.edu/college/2022/fall/notes/0/#computational-thinking)
-   [Teks](https://cs50.harvard.edu/college/2022/fall/notes/0/#text)
-   [Emoji](https://cs50.harvard.edu/college/2022/fall/notes/0/#emojis)
-   [RGB](https://cs50.harvard.edu/college/2022/fall/notes/0/#rgb)
-   [Gambar, Video dan Suara](https://cs50.harvard.edu/college/2022/fall/notes/0/#images-video-and-sound)
-   [Algoritma](https://cs50.harvard.edu/college/2022/fall/notes/0/#algorithms)
-   [Pseudocode dan Blok Bangunan Dasar Pemrograman](https://cs50.harvard.edu/college/2022/fall/notes/0/#pseudocode-and-the-basic-building-blocks-of-programming)
-   [Menggores](https://cs50.harvard.edu/college/2022/fall/notes/0/#scratch)
-   [Abstraksi](https://cs50.harvard.edu/college/2022/fall/notes/0/#abstraction)
-   [Jika](https://cs50.harvard.edu/college/2022/fall/notes/0/#if)
-   [Memperluas Imajinasi Anda](https://cs50.harvard.edu/college/2022/fall/notes/0/#expanding-your-imagination)
-   [Gerakan Sprite](https://cs50.harvard.edu/college/2022/fall/notes/0/#sprite-movement)
-   [Lebih Banyak Sprite](https://cs50.harvard.edu/college/2022/fall/notes/0/#more-sprites)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/0/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/0/#welcome)

-   Kelas ini lebih dari sekadar pemrograman komputer!
-   Memang, kelas ini adalah tentang pemecahan masalah dengan cara yang sangat memberdayakan! Anda mungkin akan mengambil pemecahan masalah yang Anda pelajari di sini kemungkinan besar akan langsung diterapkan pada pekerjaan Anda di luar kursus ini dan bahkan karier Anda secara keseluruhan!
-   Namun, itu tidak akan mudah! Anda akan “meminum dari firehose” pengetahuan selama kursus ini. Anda akan kagum dengan apa yang dapat Anda capai dalam beberapa minggu mendatang.
-   Kursus ini jauh lebih tentang Anda memajukan "Anda" dari "di mana Anda hari ini" daripada mencapai standar yang dibayangkan.
-   Pertimbangan pembukaan yang paling penting dalam kursus ini: Berikan waktu yang Anda butuhkan untuk belajar melalui kursus ini. Setiap orang belajar secara berbeda. Jika sesuatu tidak berjalan dengan baik di awal, ketahuilah bahwa seiring waktu Anda akan tumbuh dan berkembang dalam keahlian Anda.

## [Apa yang Ada di Depan](https://cs50.harvard.edu/college/2022/fall/notes/0/#whats-ahead)

-   Anda akan belajar minggu ini tentang Scratch, bahasa pemrograman visual.
-   Kemudian, di minggu-minggu mendatang, Anda akan belajar tentang C. Itu akan terlihat seperti ini:
    
    ```
      #include <stdio.h>
    
      int main(void)
      {
          printf("hello, world\n");
      }
    ```
    
-   Selanjutnya, seiring berjalannya minggu, Anda akan belajar tentang algoritme.
-   Anda akan belajar tentang memori.
-   Anda akan belajar tentang kode buggy dan apa yang menyebabkan komputer crash.
-   Anda akan belajar tentang struktur data seperti tabel hash.
-   Kemudian, kita akan bertransisi ke bahasa tingkat baru yang lebih tinggi bernama _Python_ . Kode Anda akan terlihat seperti ini:
    
    ```
      print("hello, world")
    ```
    
-   Kelas ini akan memberi Anda pemahaman yang kuat tentang bagaimana bahasa pemrograman terbaru berkembang dari yang sebelumnya.
-   Kami juga akan melihat bagaimana kami dapat menggunakan basis data dan kerangka kerja pihak ketiga untuk membuat aplikasi web.

## [Masyarakat!](https://cs50.harvard.edu/college/2022/fall/notes/0/#community)

-   Anda adalah bagian dari komunitas yang mengikuti kursus ini di Harvard College, Harvard Extension School, dan melalui edX.org.
-   Puzzle Day dan Pameran CS50

## [Berpikir Komputasi](https://cs50.harvard.edu/college/2022/fall/notes/0/#computational-thinking)

-   Pada dasarnya, pemrograman komputer adalah tentang mengambil beberapa masukan dan membuat beberapa keluaran - dengan demikian memecahkan masalah. Apa yang terjadi di antara input dan output, yang bisa kita sebut _kotak hitam,_ adalah fokus dari kursus ini.
    
    ![Kotak hitam dengan input dan output](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide38.png "Kotak hitam dengan input dan output")
    
-   Misalnya, kita mungkin perlu mengambil kehadiran untuk kelas. Kita bisa menggunakan sistem yang disebut _unary_ untuk menghitung, satu jari pada satu waktu. Komputer saat ini menghitung menggunakan sistem yang disebut _biner_ . Dari istilah _digit biner_ itulah kita mendapatkan istilah yang akrab disebut _bit_ . Sedikit adalah nol atau satu _._
-   Komputer hanya berbicara dalam bentuk nol dan satu. Nol mewakili _off._ Ones mewakili _._ Komputer adalah jutaan, dan mungkin miliaran, transistor yang dihidupkan dan dimatikan.
-   Jika Anda membayangkan menggunakan bola lampu, satu bola lampu hanya dapat menghitung dari nol hingga satu.
-   Namun, jika Anda memiliki tiga bola lampu, ada lebih banyak pilihan yang terbuka untuk Anda!
-   Menggunakan tiga bola lampu, berikut ini bisa mewakili nol:
    
    ```
      0 0 0
    ```
    
-   Demikian pula, berikut ini akan mewakili satu:
    
    ```
      0 0 1
    ```
    
-   Dengan logika ini, kita dapat mengusulkan bahwa yang berikut ini sama dengan dua:
    
    ```
      0 1 0
    ```
    
-   Memperluas logika ini lebih jauh, berikut ini mewakili tiga:
    
    ```
      0 1 1
    ```
    
-   Empat akan muncul sebagai:
    
    ```
      1 0 0
    ```
    
-   Faktanya, kami hanya dapat menggunakan tiga bola lampu yang dihitung hingga tujuh!
    
    ```
      1 1 1
    ```
    
-   Sebagai heuristik, kita dapat membayangkan bahwa nilai-nilai berikut mewakili setiap kemungkinan tempat dalam _digit biner_ kita :
    
    ```
      4 2 1
    ```
    
-   Komputer menggunakan 'basis-2' untuk menghitung. Hal ini dapat digambarkan sebagai berikut:
    
    ```
      2^2  2^1  2^0
      4    2    1
    ```
    
-   Oleh karena itu, Anda dapat mengatakan bahwa diperlukan tiga bit (tempat empat, tempat dua, dan tempat satu) untuk mewakili angka setinggi tujuh.
    
-   Komputer umumnya menggunakan delapan bit untuk mewakili angka. Misalnya, `00000101`adalah angka 5 dalam _biner_ .

## [Teks](https://cs50.harvard.edu/college/2022/fall/notes/0/#text)

-   Sama seperti angka adalah pola biner dari satu dan nol, huruf juga diwakili menggunakan satu dan nol!
-   Karena ada tumpang tindih antara satu dan nol yang mewakili angka dan huruf, standar _ASCII_ dibuat untuk memetakan huruf tertentu ke angka tertentu.
-   Misalnya, surat itu `A`diputuskan untuk dipetakan ke angka 65.
-   Jika Anda menerima pesan teks, biner di bawah pesan tersebut mungkin mewakili angka 72, 73, dan 33. Jika dipetakan ke ASCII, pesan Anda akan terlihat seperti berikut:
    
    ```
      H   I   !
      72  73  33
    ```
    
-   Syukurlah untuk standar seperti ASCII yang memungkinkan kami menyepakati nilai-nilai ini!
-   Berikut adalah peta nilai ASCII yang diperluas:
    
    ![peta ASCII](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide93.png "peta ASCII")
    
-   Jika mau, Anda dapat mempelajari lebih lanjut tentang [ASCII](https://en.wikipedia.org/wiki/ASCII) .

## [Emoji](https://cs50.harvard.edu/college/2022/fall/notes/0/#emojis)

-   Seiring berjalannya waktu, semakin banyak cara untuk berkomunikasi melalui teks.
-   Karena tidak ada cukup digit dalam biner untuk mewakili berbagai karakter yang dapat diwakili oleh manusia, standar _Unicode_ memperluas jumlah bit yang dapat ditransmisikan dan dipahami oleh komputer.
-   Ada emoji yang mungkin Anda gunakan setiap hari. Berikut ini mungkin terlihat familier bagi Anda:
    
    ![emoji](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide103.png "emoji")
    
-   Ilmuwan komputer menghadapi tantangan ketika ingin menetapkan berbagai warna kulit untuk setiap emoji agar komunikasi dapat lebih dipersonalisasi. Dalam hal ini, pembuat dan kontributor emoji memutuskan bahwa bit awal akan menjadi struktur emoji itu sendiri, diikuti dengan warna kulit.
-   Semakin banyak fitur ditambahkan ke standar Unicode untuk mewakili karakter dan emoji lebih lanjut.
-   Jika mau, Anda dapat mempelajari lebih lanjut tentang [Unicode](https://en.wikipedia.org/wiki/Unicode) .
-   Jika mau, Anda dapat mempelajari lebih lanjut tentang [emoji](https://en.wikipedia.org/wiki/Emoji) .

## [RGB](https://cs50.harvard.edu/college/2022/fall/notes/0/#rgb)

-   Merah, hijau, dan biru (disebut `RGB`) merupakan kombinasi dari tiga angka.
    
    ![kotak merah hijau biru](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide118.png "kotak merah hijau biru")
    
-   Mengambil 72, 73, dan 33 yang kami gunakan sebelumnya, yang dikatakan `HI!`melalui teks, akan ditafsirkan oleh pembaca gambar sebagai warna kuning muda. Nilai merah adalah 72, nilai hijau adalah 73, dan biru adalah 33.
    
    ![kotak kuning](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide120.png "kotak kuning")
    

## [Gambar, Video dan Suara](https://cs50.harvard.edu/college/2022/fall/notes/0/#images-video-and-sound)

-   Gambar hanyalah kumpulan nilai RGB.
-   Video adalah urutan dari banyak gambar yang disimpan bersama, seperti flipbook.
-   Musik dapat direpresentasikan melalui data MIDI.

## [Algoritma](https://cs50.harvard.edu/college/2022/fall/notes/0/#algorithms)

-   Pemecahan masalah adalah inti dari ilmu komputer dan pemrograman komputer.
-   Bayangkan masalah mendasar mencoba menemukan satu nama di buku telepon.
-   Bagaimana Anda melakukannya?
-   Salah satu pendekatannya bisa dengan hanya membaca dari halaman satu ke halaman berikutnya hingga mencapai halaman terakhir.
-   Pendekatan lain bisa dengan mencari dua halaman sekaligus.
-   Pendekatan terakhir dan mungkin lebih baik adalah pergi ke tengah buku telepon dan bertanya, "Apakah nama yang saya cari di kiri atau di kanan?" Kemudian, ulangi proses ini, potong masalahnya menjadi setengah dan setengah.
-   Masing-masing pendekatan ini bisa disebut algoritma. Kecepatan masing-masing algoritma tersebut dapat digambarkan sebagai berikut dalam apa yang disebut _notasi O-besar_ :
    
    ![notasi o besar](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide141.png "notasi o besar") Perhatikan bahwa algoritme pertama, yang disorot dengan warna merah, memiliki O besar `n`karena jika ada 100 nama di buku telepon, diperlukan hingga 100 kali percobaan untuk menemukan nama yang benar. Algoritme kedua, di mana dua halaman dicari sekaligus, memiliki O besar 'n/2' karena kami menelusuri halaman dua kali lebih cepat. Algoritme terakhir memiliki O besar dari log 2 n karena menggandakan masalah hanya akan menghasilkan satu langkah lagi untuk menyelesaikan masalah.
    

## [Pseudocode dan Blok Bangunan Dasar Pemrograman](https://cs50.harvard.edu/college/2022/fall/notes/0/#pseudocode-and-the-basic-building-blocks-of-programming)

-   Kemampuan untuk membuat _kodesemu_ merupakan pusat kesuksesan seseorang baik di kelas ini maupun dalam pemrograman komputer.
-   Pseudocode adalah versi kode Anda yang dapat dibaca manusia. Sebagai contoh, mengingat algoritma ketiga di atas, kita dapat membuat pseudocode sebagai berikut:
    
    ```
      1  Pick up phone book
      2  Open to middle of phone book
      3  Look at page
      4  If person is on page
      5      Call person
      6  Else if person is earlier in book
      7      Open to middle of left half of book
      8      Go back to line 3
      9  Else if person is later in book
      10     Open to middle of right half of book
      11     Go back to line 3
      12 Else
      13     Quit
    ```
    
-   Pseudocoding adalah keterampilan yang sangat penting setidaknya karena dua alasan. Pertama, ketika Anda membuat pseudocode sebelum Anda membuat kode formal, ini memungkinkan Anda memikirkan logika masalah Anda terlebih dahulu. Kedua, ketika Anda mem-pseudocode, nanti Anda dapat memberikan informasi ini kepada orang lain yang ingin memahami keputusan pengkodean Anda dan cara kerja kode Anda.
-   Perhatikan bahwa bahasa dalam kodesemu kita memiliki beberapa fitur unik. Pertama, beberapa baris ini dimulai dengan kata kerja seperti _ambil,_ _buka,_ _lihat._ Nanti, kita akan memanggil _fungsi-fungsi_ ini .
-   Kedua, perhatikan bahwa beberapa baris menyertakan pernyataan like `if`atau `else if.`These disebut _conditional_ .
-   Ketiga, perhatikan bagaimana ada ungkapan yang dapat dinyatakan sebagai _benar_ atau _salah,_ seperti “orang di awal buku”. Kami menyebutnya _ekspresi boolean_ .
-   Terakhir, perhatikan bagaimana pernyataan seperti "kembali ke baris 3". Kami menyebutnya _loop_ ini .
-   Dalam konteks _Scratch_ , yang dibahas di bawah ini, kita akan menggunakan masing-masing blok bangunan dasar pemrograman di atas.

## [Menggores](https://cs50.harvard.edu/college/2022/fall/notes/0/#scratch)

-   _Scratch_ adalah bahasa pemrograman visual yang dikembangkan oleh MIT.
-   Scratch menggunakan blok bangunan pengkodean penting yang sama yang telah kita bahas sebelumnya dalam kuliah ini.
-   Scatch adalah cara yang bagus untuk masuk ke pemrograman komputer karena memungkinkan Anda untuk bermain dengan blok penyusun ini secara visual, tidak harus khawatir tentang sintaks kurung kurawal, titik koma, tanda kurung, dan sejenisnya.
-   Scatch `IDE`(lingkungan pengembangan terintegrasi) terlihat seperti berikut:
    
    ![antarmuka awal](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide162.png "antarmuka awal") Perhatikan bahwa di sebelah kiri, ada _blok penyusun_ yang dapat Anda gunakan dalam pemrograman Anda. Di sebelah kanan blok penyusun, ada area tempat Anda dapat menyeret blok untuk membuat program. Di sebelah kanannya, Anda melihat _panggung_ tempat seekor kucing berdiri. Panggung adalah tempat pemrograman Anda menjadi hidup.
    
-   Scratch beroperasi pada sistem koordinat sebagai berikut:
    
    ![sistem koordinat goresan](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide167.png "sistem koordinat goresan") Perhatikan bahwa pusat panggung berada pada koordinat (0,0). Saat ini, posisi kucing berada di posisi yang sama.
    
-   Untuk memulai, seret blok bangunan "ketika bendera hijau diklik" ke area pemrograman. Kemudian, seret `say`blok penyusun ke area pemrograman dan tempelkan ke blok sebelumnya.
    
    whenclickedsayhello, world
    
    Perhatikan bahwa saat Anda mengeklik bendera hijau sekarang, di atas panggung, kucing itu berkata, "halo dunia".
    
-   Ini mengilustrasikan dengan baik apa yang telah kita diskusikan sebelumnya tentang pemrograman:
    
    ![gores dengan kotak hitam](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Slide172.png "gores dengan kotak hitam") Perhatikan bahwa input `hello world`diteruskan ke fungsi `say`, dan _efek samping_ dari menjalankan fungsi tersebut adalah ucapan kucing `hello world`.
    
-   Kami dapat membuat program Anda lebih interaktif dengan membuat kucing berbicara `hello`kepada seseorang secara spesifik. Ubah program Anda seperti di bawah ini:
    
    whenclickedaskWhat's your name?andwaitsayjoinhello,answer
    
    Perhatikan bahwa ketika bendera hijau diklik, fungsi `ask`dijalankan. Program meminta Anda, pengguna, `What's your name?`kemudian menyimpan nama itu dalam _variabel_ bernama `answer`. Program kemudian beralih `answer`ke fungsi khusus bernama `join`, yang menggabungkan dua string teks `hello`, dan nama apa pun yang diberikan. Ini secara kolektif diteruskan ke `say`fungsi. Kata kucing itu, `Hello,`dan sebuah nama. Program Anda sekarang interaktif.
    
-   Sama halnya, kita dapat memodifikasi program kita sebagai berikut:
    
    whenclickedaskWhat's your name?andwaitspeakjoinhello,answer
    
    Perhatikan bahwa program ini, ketika bendera hijau diklik, meneruskan variabel yang sama, digabungkan dengan `hello`, ke fungsi bernama `speak`.
    

## [Abstraksi](https://cs50.harvard.edu/college/2022/fall/notes/0/#abstraction)

-   Seiring dengan pseudocoding, _abstraksi_ adalah keterampilan dan konsep penting dalam pemrograman komputer.
-   Abstraksi adalah tindakan menyederhanakan masalah menjadi masalah yang lebih kecil dan lebih kecil.
-   Misalnya, jika Anda mengadakan makan malam besar untuk teman-teman Anda, masalah _karena_ harus memasak seluruh makanan bisa sangat membuat kewalahan! Namun, jika Anda membagi tugas memasak makanan menjadi tugas (atau masalah) yang lebih kecil dan lebih kecil, tugas besar untuk membuat makanan lezat ini mungkin terasa kurang menantang.
-   Dalam pemrograman, dan bahkan dalam Scratch, kita dapat melihat abstraksi beraksi. Di area pemrograman Anda, programkan sebagai berikut:
    
    whenclickedplaysoundMeowuntildonewait1secondsplaysoundMeowuntildonewait1secondsplaysoundMeowuntildone
    
    Perhatikan bahwa Anda melakukan hal yang sama berulang kali. Memang, jika Anda melihat diri Anda berulang kali mengkodekan pernyataan yang sama, kemungkinan besar Anda dapat memprogram dengan lebih terampil – mengabstraksikan kode berulang ini.
    
-   Anda dapat memodifikasi kode Anda sebagai berikut:
    
    whenclickedrepeat3playsoundMeowuntildonewait1seconds
    
    Perhatikan bahwa loop melakukan persis seperti yang dilakukan program sebelumnya. Namun, masalahnya disederhanakan dengan meringkas pengulangan ke blok yang _mengulang_ kode untuk kita.
    
-   Kami bahkan dapat memajukan ini lebih jauh dengan menggunakan `define`blok, di mana Anda dapat membuat blok Anda sendiri (fungsi Anda sendiri)! Tulis kode sebagai berikut:
    
    ![definisi awal](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Scratch6.png "definisi awal") Perhatikan bahwa kita mendefinisikan blok kita sendiri yang disebut `meow`. Fungsi memutar suara `meow`, lalu menunggu satu detik. Di bawahnya, Anda dapat melihat bahwa ketika bendera hijau diklik, fungsi meow kita diulang tiga kali.
    
-   Kami bahkan dapat menyediakan cara agar fungsi dapat mengambil input `n`dan mengulang beberapa kali:
    
    definemeowplaysoundMeowuntildonewait1secondswhenclickedrepeat3meow
    
    Perhatikan bagaimana `n`diambil dari “meow n times.” `n`diteruskan ke fungsi meow melalui `define`blok.
    
-   Ngomong-ngomong, kucing bisa kita sebut a `sprite`– istilah umum yang digunakan dalam pemrograman game untuk objek atau karakter di layar yang akan berinteraksi dengan pemain.

## [Jika](https://cs50.harvard.edu/college/2022/fall/notes/0/#if)

-   _persyaratan_ adalah blok bangunan penting dari pemrograman, di mana program mencari untuk melihat apakah kondisi tertentu telah terpenuhi. Jika suatu kondisi terpenuhi, program melakukan sesuatu.
-   Untuk mengilustrasikan kondisional, tulis kode sebagai berikut:
    
    whenclickedforeveriftouchingmouse-pointer?thenplaysoundMeowuntildone
    
    Perhatikan bahwa `forever`blok digunakan sedemikian rupa sehingga `if`blok dipicu berulang kali, sehingga dapat memeriksa terus menerus jika kucing menyentuh penunjuk tetikus.
    
-   Kami dapat memodifikasi program kami sebagai berikut untuk mengintegrasikan penginderaan video:
    
    whenvideomotion>50playsoundMeowuntildone
    
-   Ingat, pemrograman seringkali merupakan proses coba-coba. Jika Anda merasa frustrasi, luangkan waktu untuk membicarakan masalah yang dihadapi. Apa masalah spesifik yang sedang Anda kerjakan saat ini? Apa yang bekerja? Apa yang tidak berfungsi?

## [Memperluas Imajinasi Anda](https://cs50.harvard.edu/college/2022/fall/notes/0/#expanding-your-imagination)

-   Kami menunjukkan kepada Anda dalam kuliah ini sejumlah program Scratch untuk membangkitkan imajinasi Anda.
-   _Oscartime_ adalah salah satu program Scratch David sendiri - meskipun musik mungkin menghantuinya karena jumlah jam dia mendengarkannya saat membuat program ini. Luangkan beberapa saat untuk bermain melalui permainan sendiri.
-   Membangun Oscartime sendiri, pertama-tama kami menambahkan tiang lampu.
    
    ![antarmuka oscartime](https://cs50.harvard.edu/college/2022/fall/notes/0/cs50Week0Scratch10.png "antarmuka oscartime")
    
-   Kemudian, tulis kode sebagai berikut:
    
    whenclickedswitchcostumetooscar1foreveriftouchingmouse-pointer?thenswitchcostumetooscar2elseswitchcostumetooscar1
    
    Perhatikan bahwa menggerakkan mouse Anda ke atas Oscar akan mengubah kostumnya. Anda dapat mempelajari lebih lanjut dengan [menjelajahi blok kode ini](https://scratch.mit.edu/projects/565100517) .
    
-   Kemudian, ubah kode Anda sebagai berikut untuk membuat potongan sampah yang berjatuhan:
    
    whenclickedgotox:pickrandom-240to240y:180foreverifdistancetofloor>0thenchangeyby-3
    
    Perhatikan bahwa posisi tempat sampah pada sumbu y selalu dimulai dari 180. Posisi x diacak. Saat sampah berada di atas lantai, ia turun 3 piksel sekaligus. Anda dapat mempelajari lebih lanjut dengan [menjelajahi blok kode ini](https://scratch.mit.edu/projects/565117390) .
    
-   Selanjutnya, ubah kode Anda sebagai berikut untuk memungkinkan kemungkinan menyeret sampah.
    
    whenclickedforeverifmousedown?andtouchingmouse-pointer?thengotomouse-pointer
    
    Anda dapat mempelajari lebih lanjut dengan [menjelajahi blok kode ini](https://scratch.mit.edu/projects/565119737) .
    
-   Selanjutnya, kita dapat mengimplementasikan variabel penilaian sebagai berikut:
    
    whenclickedforeveriftouchingOscar?thenchangescoreby1gotox:pickrandom-240to240y:180
    
    Anda dapat mempelajari lebih lanjut dengan [menjelajahi blok kode ini](https://scratch.mit.edu/projects/565472267) .
    

## [Gerakan Sprite](https://cs50.harvard.edu/college/2022/fall/notes/0/#sprite-movement)

-   Beralih dari Oscartime ke Ivy's Hardest Game, sekarang kita dapat membayangkan bagaimana menerapkan gerakan dalam program kita.
-   Program kami memiliki tiga komponen utama.
-   Pertama, tulis kode sebagai berikut:
    
    whenclickedgotox:0y:0foreverlistenforkeyboardfeelforwalls
    
    Perhatikan bahwa ketika bendera hijau diklik, sprite kita bergerak ke tengah panggung pada koordinat (0,0) dan kemudian mendengarkan keyboard dan memeriksa dinding selamanya.
    
-   Kedua, tambahkan grup blok kode kedua ini:
    
    definelistenforkeyboardifkeyup arrowpressed?thenchangeyby1ifkeydown arrowpressed?thenchangeyby-1ifkeyright arrowpressed?thenchangexby1ifkeyleft arrowpressed?thenchangexby-1
    
    Perhatikan bagaimana kami membuat `listen for keyboard`skrip khusus. Untuk setiap tombol panah kami di keyboard, itu akan memindahkan sprite di sekitar layar.
    
-   Terakhir, tambahkan grup blok kode ini:
    
    definefeelforwallsiftouchingleft wall?thenchangexby1iftouchingright wall?thenchangexby-1
    
    Perhatikan bagaimana kami juga memiliki `feel for walls`skrip khusus. Saat sprite menyentuh dinding, ia memindahkannya kembali ke posisi aman – mencegahnya keluar dari layar.
    
-   Anda dapat mempelajari lebih lanjut dengan [menjelajahi blok kode ini](https://scratch.mit.edu/projects/565121265) .
-   Cobalah game lengkap [Oscartime](https://scratch.mit.edu/projects/277537196) .

## [Lebih Banyak Sprite](https://cs50.harvard.edu/college/2022/fall/notes/0/#more-sprites)

-   Scratch memungkinkan banyak sprite berada di layar sekaligus.
-   Menambahkan sprite lain, tambahkan blok kode berikut ke program Anda:
    
    whenclickedgotox:0y:0pointindirection90foreveriftouchingleft wall?ortouchingright wall?thenturn180degreesmove1steps
    
    Perhatikan bagaimana sprite Yale tampaknya menghalangi sprite Harvard dengan bergerak bolak-balik. Saat menabrak dinding, ia berbalik hingga menabrak dinding lagi. Anda dapat mempelajari lebih lanjut dengan [menjelajahi blok kode ini](https://scratch.mit.edu/projects/565127193) .
    
-   Anda bahkan dapat membuat sprite mengikuti sprite lain. Menambahkan sprite lain, tambahkan blok kode berikut ke program Anda:
    
    whenclickedgotorandom positionforeverpointtowardsHarvardmove1steps
    
    Perhatikan bagaimana logo MIT sekarang tampaknya mengikuti logo Harvard. Anda dapat mempelajari lebih lanjut dengan [menjelajahi blok kode ini](https://scratch.mit.edu/projects/565479840) .
    
-   Cobalah game lengkap [Ivy's Hardest Game](https://scratch.mit.edu/projects/565742837) .

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/0/#summing-up)

Dalam pelajaran ini, Anda mempelajari bagaimana kursus ini berada di dunia luas ilmu komputer dan pemrograman. Anda belajar…

-   Beberapa siswa datang ke kelas ini dengan pengalaman coding sebelumnya!
-   Anda tidak sendiri! Anda adalah bagian dari komunitas.
-   Pemecahan masalah adalah inti dari karya ilmuwan komputer.
-   Kursus ini bukan hanya tentang pemrograman – kursus ini akan memperkenalkan Anda pada cara belajar baru yang dapat Anda terapkan di hampir setiap bidang kehidupan.
-   Bagaimana angka, teks, gambar, musik, dan video dipahami oleh komputer.
-   Keterampilan pemrograman dasar pseudocoding.
-   Bagaimana abstraksi akan berperan dalam pekerjaan Anda di masa depan dalam kursus ini.
-   Blok bangunan dasar pemrograman, termasuk fungsi, kondisional, loop, dan variabel.
-   Cara membangun proyek di Scratch.

Sampai jumpa lain waktu!
# ⭐️ Course Contents ⭐️ 

[0:25](https://www.youtube.com/watch?v=8hly31xKli0&t=25s) - What Is an Algorithm
[6:50](https://www.youtube.com/watch?v=8hly31xKli0&t=410s) - Guess the Number
[12:46](https://www.youtube.com/watch?v=8hly31xKli0&t=766s) - Defining an Algorithm
[21:15](https://www.youtube.com/watch?v=8hly31xKli0&t=1275s) - Evaluating Linear Search
[29:58](https://www.youtube.com/watch?v=8hly31xKli0&t=1798s) - Evaluating Binary Search

# Introduction to Algorithms I ( Playing a Counting Game )

## What Is an Algorithm

![[Pasted image 20230508112814.png]]

### Pendahuluan

Nama saya Passan, saya adalah seorang instruktur di Treehouse. Selamat datang di kursus "Pengenalan Algoritma". Apakah kamu seorang pelajar SMA, mahasiswa, developer di industri atau sedang belajar coding? Pasti kamu pernah mendengar tentang istilah algoritma. Bagi beberapa orang, algoritma terdengar menakutkan dan sulit dipahami. Namun, kursus ini bertujuan untuk membuat kamu nyaman dengan dasar-dasar algoritma.

### Apa yang akan kamu pelajari?

Kursus ini akan membahas pengetahuan dasar yang diperlukan untuk memahami algoritma. Kursus ini lebih tentang tools yang akan kamu gunakan untuk mengevaluasi algoritma, memahami cara kerjanya, membandingkannya satu sama lain, dan membuat pernyataan tentang kegunaan algoritma dalam konteks tertentu. Kursus ini juga akan mempelajari konsep-konsep tersebut dengan menggunakan algoritma yang sudah dikenal. Kursus ini akan menggunakan bahasa pemrograman Python, yang mudah dipelajari, tetapi tetap memerlukan pengalaman pemrograman.

### Apa itu Algoritma? 

Algoritma adalah serangkaian langkah atau instruksi untuk menyelesaikan tugas tertentu. Ini seperti resep masakan, rutinitas pagi, atau petunjuk arah saat berkendara. Di bidang ilmu komputer, algoritma lebih spesifik, yaitu serangkaian langkah yang diambil oleh sebuah program untuk menyelesaikan tugas.

![[Pasted image 20230508113031.png]]

###  Mengapa Belajar Algoritma Penting?

Setiap masalah dalam ilmu komputer memiliki banyak solusi. Namun, tidak semua solusi sama baiknya. Belajar algoritma membantu kamu untuk memilih solusi yang paling efisien. Selain itu, memahami algoritma membantu kamu mengetahui kapan harus menerapkannya, yang merupakan hal yang sangat penting.

![[Pasted image 20230508113437.png]]

### Kesimpulan

-   Kursus ini bertujuan untuk membuat kamu nyaman dengan dasar-dasar algoritma.
-   Kamu akan mempelajari tools yang digunakan untuk mengevaluasi, memahami cara kerja, membandingkan, dan membuat pernyataan tentang kegunaan algoritma dalam konteks tertentu.
-   Algoritma adalah serangkaian instruksi untuk menyelesaikan tugas tertentu. Belajar algoritma penting untuk memilih solusi yang paling efisien dan mengetahui kapan harus menerapkannya.

## Guess the Number

### Bermain Tebak Angka dan Berpikir Algoritmik

Bermain tebak angka adalah permainan sederhana di mana seseorang akan memikirkan sebuah angka antara 1 dan 10 dan pemain harus menebak angka itu. Pemain diberi petunjuk jika tebakannya terlalu tinggi atau terlalu rendah. Pemenangnya adalah pemain yang menebak angka dengan jumlah kesempatan terendah. Permainan ini dimainkan oleh tiga orang, dan dalam setiap putaran, pemain harus memperkirakan angka yang dipikirkan oleh pemain lain.

Batasan masalah adalah hal yang penting dalam berpikir algoritmik. Dalam tebak angka, penting untuk menetapkan batasan masalah dengan jelas dan memastikan nilai-nilai yang dianggap sebagai input. Pada putaran pertama, kedua pemain membutuhkan jumlah kesempatan yang sama untuk menebak angka karena jawabannya cukup mudah. Namun, pada putaran kedua, ketika angkanya lebih besar, strategi keduanya berbeda. Hasilnya, tidak ada strategi yang lebih baik daripada yang lain, tetapi penting untuk memahami di mana angka yang dicari berada dalam rentang.

Dalam berpikir algoritmik, tidak ada satu solusi yang lebih baik daripada yang lain. Yang penting adalah menemukan solusi yang cocok untuk masalah yang sedang dihadapi. Selain itu, penting untuk memahami batasan masalah dan memastikan bahwa input dipahami dengan jelas.

### Takeaways:

-   Batasan masalah adalah hal yang penting dalam berpikir algoritmik.
-   Tidak ada satu strategi yang lebih baik daripada yang lain dalam bermain tebak angka.
-   Dalam berpikir algoritmik, penting untuk memahami batasan masalah dan mencari solusi yang cocok untuk masalah yang sedang dihadapi.

## Defining an Algorithm

### Searching: the Basics

#### Pengertian Latihan

Pada video terakhir, kami telah melakukan latihan di mana rekan kerja saya menebak angka yang saya pikirkan. Poin dari latihan tersebut adalah untuk memberikan contoh situasi nyata yang akan Anda temui ketika membangun situs web, aplikasi, dan menulis kode. Pendekatan John dan Brittany untuk menemukan angka yang saya pikirkan adalah contoh dari pencarian, yang merupakan salah satu aspek dasar dalam pemrograman.

### Berbeda-beda dalam Pencarian

Meskipun mencari sesuatu mungkin terlihat sederhana, ada beberapa cara yang berbeda untuk mencari sesuatu, tergantung pada situasinya. Pada contoh permainan angka, kecepatan dalam menemukan angka yang dimaksud berbeda antara John dan Brittany. Jangan lupa bahwa kecepatan pencarian ini sangat penting ketika Anda mencari di aplikasi yang kompleks, seperti pada Facebook. Ketika mencari seseorang di Facebook, aplikasi harus mencari melintasi 2,19 miliar catatan pengguna aktif untuk menemukan seseorang dengan cepat. Oleh karena itu, mencari algoritma yang berbeda menjadi sangat penting bagi perusahaan seperti Facebook.

### Linear Search Algorithm

Pendekatan John untuk menemukan angka yang saya pikirkan disebut Linear Search Algorithm. Algoritma pencarian ini sangat sederhana dan dapat didefinisikan sebagai berikut: kita mulai dari awal daftar atau rentang nilai kemudian bandingkan nilai saat ini dengan target. Jika nilai saat ini adalah nilai target, maka kita selesai. Jika tidak, kita akan teruskan secara berurutan ke nilai berikutnya dalam daftar dan mengulangi langkah 2. Jika kita mencapai akhir daftar, maka nilai target tidak ada dalam daftar. Linear Search Algorithm dapat digunakan dalam kehidupan nyata, seperti saat mencari buku di toko buku.

![[Pasted image 20230508113821.png]]

### Tiga Pedoman dalam Algoritma

Ada tiga pedoman dalam membuat sebuah algoritma. Pertama, harus ada pernyataan masalah yang jelas. Kedua, definisi algoritma harus mengandung serangkaian instruksi yang spesifik dalam urutan tertentu. Ketiga, setiap instruksi harus dijalankan dengan urutan yang jelas. Pedoman-pedoman ini sangat penting untuk memastikan bahwa algoritma dapat bekerja secara efektif dan efisien.

![[Pasted image 20230508114018.png]]

### Takeaways

- Pencarian adalah salah satu aspek dasar dalam pemrograman yang melibatkan beberapa cara pencarian yang berbeda.
- Linear Search Algorithm adalah salah satu jenis pencarian yang sederhana dan sering digunakan dalam kehidupan sehari-hari.
- Ada tiga pedoman dalam membuat algoritma: pernyataan masalah yang jelas, definisi algoritma yang spesifik, dan instruksi yang dijalankan dengan urutan yang jelas.

## Evaluating Linear Search

### Defining Correctness and Efficiency in Algorithms

#### Preliminary Definitions

Dalam menyelesaikan suatu permasalahan, kita memerlukan algoritma yang baik. Algoritma yang baik memerlukan input yang terdefinisi dengan jelas, output yang juga terdefinisi dengan jelas, serta dapat berakhir atau "terminate" apapun input yang diberikan. Jika algoritma yang kita buat tidak memenuhi ketiga kriteria tersebut, maka algoritma kita tidak benar.

![[Pasted image 20230508114302.png]]

#### Proof through Induction

Untuk membuktikan bahwa suatu algoritma benar, dibutuhkan suatu bentuk pemikiran matematika yang disebut induksi matematis. Konsep ini terkadang membuat kita merasa takut, tetapi kita tetap bisa memahami algoritma tanpa mempelajari hal tersebut.

#### Efficiency in Algorithms

Selain memastikan kebenaran algoritma, kita juga harus memperhatikan efisiensi algoritma tersebut. Efisiensi algoritma dapat diukur dari dua sisi, yakni waktu dan ruang. Waktu yang diukur dalam efisiensi algoritma adalah waktu yang dibutuhkan untuk menjalankan algoritma, sedangkan ruang yang diukur adalah seberapa banyak memori yang digunakan oleh algoritma tersebut.

![[Pasted image 20230508114409.png]]

### The Main Takeaways

- Algoritma yang baik harus memenuhi tiga kriteria, yakni input dan output yang terdefinisi dengan jelas, serta dapat berakhir apapun input yang diberikan.
- Untuk membuktikan bahwa suatu algoritma benar, dapat digunakan konsep induksi matematis. Namun, kita tetap bisa memahami algoritma tanpa mempelajari hal tersebut.
- Efisiensi algoritma dapat diukur dari waktu dan ruang. Waktu diukur dari waktu yang dibutuhkan untuk menjalankan algoritma, sedangkan ruang diukur dari seberapa banyak memori yang digunakan.

![[Pasted image 20230508114558.png]]

## Evaluating Binary Search

### Cara John dan Brittany Mencari Nilai Menggunakan Algoritma Pencarian

Algoritma pencarian adalah sebuah metode yang digunakan untuk mencari suatu nilai dalam kumpulan data. John menggunakan metode pencarian linear, di mana nilai-nilai diurutkan secara berurutan dan dicari dengan satu per satu, sedangkan Brittany menggunakan metode binary search, di mana dia memulai pencariannya dari nilai tengah dari rentang nilai yang diberikan. Kemudian, dengan membandingkan nilai ini dengan nilai yang dicari, dia dapat mengeliminasi setengah dari nilai yang ada setiap kali dia melakukan perulangan pencarian. Algoritma pencarian binary search memerlukan input yang sudah diurutkan terlebih dahulu sebelum melakukan pencarian.

### Tiga Kata Sulit:

1. Metode - sebuah cara atau teknik yang digunakan untuk melakukan suatu tindakan tertentu.
2. Rentang - sebuah area atau wilayah antara dua titik atau nilai.
3. Eliminasi - menghapus atau membuang sesuatu yang tidak diperlukan atau tidak diinginkan.

![[Pasted image 20230508114816.png]]

### Kesimpulan Utama:

1. Algoritma pencarian linear dan binary search adalah dua metode yang berbeda dalam mencari nilai di dalam kumpulan data.
2. Algoritma pencarian binary search memerlukan input yang sudah diurutkan terlebih dahulu sebelum melakukan pencarian.
3. Binary search lebih efisien dalam mencari nilai karena dapat mengeliminasi setengah dari nilai yang ada setiap kali melakukan perulangan pencarian.

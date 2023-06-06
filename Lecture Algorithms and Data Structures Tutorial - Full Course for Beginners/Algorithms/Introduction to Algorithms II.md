# ⭐️ Course Contents ⭐️ 

[36:11](https://www.youtube.com/watch?v=8hly31xKli0&t=2171s) - Efficiency of an Algorithm
[42:39](https://www.youtube.com/watch?v=8hly31xKli0&t=2559s) - Constant and Logarithmic Time
[49:11](https://www.youtube.com/watch?v=8hly31xKli0&t=2951s) - Linear & Quadratic Time
[53:48](https://www.youtube.com/watch?v=8hly31xKli0&t=3228s) - Quasilinear Time
[56:23](https://www.youtube.com/watch?v=8hly31xKli0&t=3383s) - Exponential Time
[1:04:23](https://www.youtube.com/watch?v=8hly31xKli0&t=3863s) - Determining Complexity

# Introduction to Algorithms ( Time Complexity )


## Efficiency of an Algorithm

### Menilai Efisiensi Algoritma Menggunakan Big O

![[Pasted image 20230509131738.png]]

Algoritma dapat dinilai dari segi efisiensi atau seberapa cepat mereka dapat menyelesaikan suatu tugas. Untuk mengevaluasi ini, kita menggunakan kompleksitas waktu sebagai patokan dan melihat bagaimana algoritma berperforma dalam skenario terburuk. Meskipun beberapa algoritma mungkin berperforma baik dalam konteks tertentu, penting untuk mengukur efisiensi dari sudut kompleksitas waktu.

![[Pasted image 20230509131916.png]]

Saat membandingkan linear search dan binary search, yang terakhir biasanya lebih efisien. Kita dapat memplot efisiensi kedua algoritma ini pada grafik dengan jumlah percobaan atau runtime algoritma pada sumbu y dan jumlah maksimum nilai dalam seri pada sumbu x. Ketika n semakin besar, performa kedua algoritma ini berbeda secara signifikan, dengan binary search menjadi lebih cepat.

![[Pasted image 20230509132033.png]]

Kita dapat menggunakan notasi big O untuk menggambarkan kompleksitas suatu algoritma sebagai fungsi dari ukurannya. Big O adalah notasi yang digunakan untuk menggambarkan urutan besarnya kompleksitas, dan itu menyederhanakan semua yang telah kita bicarakan menjadi satu variabel. Dengan menggunakan big O, kita mendapatkan gambaran besar tentang performa algoritma tanpa harus menjalankan melalui titik data dan grafik.

![[Pasted image 20230509132207.png]]

Kompleksitas algoritma adalah relatif saat dievaluasi dengan big O, dan berguna untuk memahami baik kompleksitas waktu maupun kompleksitas ruang, namun hanya saat membandingkan algoritma yang memecahkan masalah yang sama.

Poin penting:

- Efisiensi algoritma diukur dari sudut kompleksitas waktu pada skenario terburuk.
- Binary search biasanya lebih efisien daripada linear search.
- Notasi big O menyederhanakan kompleksitas dengan menggunakan satu variabel dan digunakan untuk membandingkan algoritma yang memecahkan masalah yang sama.

## Constant and Logarithmic Time

### Complexity Algoritma: Konstan dan Logaritmik

Algoritma memiliki ukuran kompleksitas sendiri-sendiri pada setiap langkahnya. Pada algoritma pencarian linier, ukuran kompleksitas waktu nya adalah konstan, artinya waktu yang dibutuhkan selalu sama meskipun jumlah data yang dicari berbeda-beda. Pada algoritma pencarian biner, waktu yang dibutuhkan untuk mencari data berbanding lurus dengan logaritma dari ukuran data. Logaritma adalah operasi kebalikan dari pangkat, dan bisa digunakan untuk memprediksi jumlah langkah yang diperlukan untuk menyelesaikan masalah.

![[Pasted image 20230509132336.png]]

### Takeaways:

- Setiap algoritma memiliki ukuran kompleksitas sendiri-sendiri pada setiap langkahnya.
- Ukuran kompleksitas waktu algoritma linier adalah konstan, sedangkan algoritma pencarian biner adalah logaritmik.
- Logaritma bisa digunakan untuk memprediksi jumlah langkah yang diperlukan untuk menyelesaikan masalah.

## Linear & Quadratic Time

![[Pasted image 20230509141216.png]]

### Algoritma Pencarian: Linear, Binary, Quadratic, dan Cubic

1. Linear Search
	Pada video ini, kita melihat bagaimana algoritma pencarian linear bekerja. Pada kasus terburuk, untuk menemukan jawaban, John memerlukan upaya sebanyak nilai n. Jadi, ketika jumlah operasi untuk menemukan hasil pada kasus terburuk sama dengan n, maka kita katakan algoritma ini berjalan dalam waktu linear. Representasi ini adalah big O dari n atau biasa disebut sebagai waktu linear. Algoritma yang membaca masukan secara berurutan akan memiliki waktu linear.

2. Binary Search
	Strategi Brittany dengan menggunakan binary search jelas lebih baik. Jika kita melihatnya pada grafik, waktu yang dibutuhkan oleh binary search jelas lebih sedikit. Namun, binary search memiliki syarat awal, yakni himpunan input harus diurutkan terlebih dahulu. Kita harus melakukan kerja tambahan sebelum menggunakan binary search. Oleh karena itu, pada prakteknya, linear search lebih efisien hingga sejumlah n tertentu.

3. Quadratic dan Cubic Runtimes
	Kita juga membahas waktu eksekusi pada algoritma quadratic dan cubic. Secara matematika, quadratic berarti operasi dikuadratkan atau dipangkatkan dua. Sementara, pada cubic, operasi dipangkatkan tiga. Kita dapat memperhatikan grafik pada video ini dan melihat bahwa perubahan kecil pada nilai n akan menyebabkan perubahan signifikan pada jumlah operasi yang harus dilakukan. Algoritma dengan waktu eksekusi quadratic dan cubic menjadi semakin mahal secara komputasional. 
	![[Pasted image 20230509141050.png]]

### Takeaways:

- Linear search memerlukan upaya sebanyak nilai n pada kasus terburuk, sehingga waktu yang dibutuhkan sebanding dengan jumlah masukan. 
- Binary search lebih efisien, tetapi membutuhkan himpunan input yang diurutkan terlebih dahulu.
- Waktu eksekusi algoritma yang semakin tinggi seperti quadratic dan cubic semakin mahal secara komputasional.

## Quasilinear Time

![[Pasted image 20230509141441.png]]

### Runtime Quasi-Linear: Pengertian, Contoh, dan Implementasi

Runtime quasi-linear adalah jenis waktu proses yang dihitung dengan notasi big O of n kali log n. Ini berarti bahwa setiap kali nilai n bertambah, jumlah operasi hanya bertambah sebesar faktor kecil dari log n. Dalam praktiknya, runtime ini dapat digunakan dalam algoritma pengurutan seperti merge sort.

![[Pasted image 20230509142229.png]]

Contoh Implementasi Merge Sort
	Merge sort adalah salah satu contoh algoritma pengurutan yang menggunakan runtime quasi-linear. Algoritma ini memulai dengan membagi daftar menjadi dua bagian secara berulang hingga akhirnya terbentuk daftar dengan satu elemen. Kemudian, algoritma ini melakukan operasi pengurutan pada setiap elemen dan menggabungkan dua bagian tersebut secara berurutan.

### Log n dan N Times Log n

Log n adalah operasi matematika yang menghasilkan hasil logaritma dari n. Sedangkan N times log n mengacu pada waktu proses yang dihitung dengan mengalikan nilai n dengan nilai log n. Contoh penggunaan N times log n adalah pada algoritma merge sort, di mana algoritma ini membutuhkan log n waktu untuk membagi setiap elemen dan n waktu untuk melakukan operasi pengurutan. 

### Takeaways:
- Runtime quasi-linear dihitung dengan notasi big O of n kali log n.
- Algoritma pengurutan seperti merge sort menggunakan runtime quasi-linear.
- N times log n mengacu pada waktu proses yang dihitung dengan mengalikan nilai n dengan nilai log n.

## Exponential Time

### Algoritma Runtime: Polinomial dan Eksponensial

Polinomial dan eksponensial adalah dua kategori runtime algoritma yang dapat digunakan untuk menentukan efisiensi suatu algoritma. Algoritma dengan runtime polinomial dianggap efisien dan digunakan dalam praktek, sedangkan algoritma dengan runtime eksponensial dianggap tidak efisien dan biasanya tidak digunakan.

1. Runtime Polinomial
	Algoritma dianggap memiliki runtime polinomial jika runtime terburuknya untuk nilai n tertentu berbentuk n pangkat k, di mana k adalah suatu bilangan. Karena itu, runtime algoritma yang dibatasi oleh grafik n pangkat k dianggap sebagai polinomial. Algoritma dengan batas atas atau runtime dengan nilai big O yang polinomial dianggap sebagai algoritma efisien.

2. Runtime Eksponensial
	Algoritma dengan nilai big O yang terbentuk dari suatu bilangan yang dipangkatkan dengan n, di mana n adalah ukuran masukan, dianggap sebagai algoritma eksponensial. Saat n meningkat sedikit, jumlah operasi yang diperlukan meningkat secara eksponensial. Algoritma eksponensial biasanya terlalu mahal untuk digunakan dalam praktik.

3. Brute Force
	Strategi Brute Force adalah sebuah strategi yang digunakan untuk memecahkan suatu masalah dengan mencoba setiap kemungkinan. Algoritma brute force membutuhkan jumlah operasi yang besar dan memiliki runtime eksponensial.

### Takeaways:

- Runtime algoritma dapat digunakan untuk menentukan efisiensi suatu algoritma.
- Algoritma dengan runtime polinomial dianggap efisien dan digunakan dalam praktek.
- Algoritma dengan runtime eksponensial dianggap tidak efisien dan terlalu mahal untuk digunakan dalam praktik.

## Determining Complexity

### Menjelaskan Binary Search dan Analisis Kompleksitas Waktu

Binary Search adalah algoritma pencarian yang digunakan untuk mencari elemen tertentu dalam daftar yang diurutkan. Algoritma ini bekerja dengan membagi daftar menjadi dua bagian setiap kali dan memeriksa apakah elemen yang dicari berada di bagian kiri atau kanan. Ini terus berlanjut hingga elemen ditemukan atau tidak ditemukan.

Langkah Binary Search:
1. Tentukan posisi tengah daftar.
2. Bandingkan elemen pada posisi tengah dengan elemen yang dicari.
3. Jika cocok, algoritma selesai.
4. Jika tidak cocok, bagi daftar menjadi dua bagian dan periksa bagian yang sesuai dengan elemen yang dicari. Ulangi langkah 1 hingga 3 pada bagian yang dipilih.

Analisis Kompleksitas Waktu:
- Waktu terbaik algoritma Binary Search adalah O(1) atau waktu konstan, di mana elemen yang dicari tepat berada pada posisi tengah daftar.
- Waktu terburuk algoritma Binary Search adalah O(log n) atau waktu logaritmik, di mana daftar terus dibagi menjadi dua bagian hingga elemen yang dicari ditemukan atau tidak ditemukan.
- Waktu rata-rata algoritma Binary Search dapat berbeda-beda, tetapi untuk analisis kompleksitas waktu, fokus hanya pada waktu terburuk.

Kesimpulan:
- Binary Search adalah algoritma pencarian untuk daftar yang diurutkan.
- Algoritma ini memiliki waktu terbaik O(1) dan waktu terburuk O(log n).
- Analisis kompleksitas waktu fokus pada waktu terburuk algoritma.
- Waktu rata-rata algoritma dapat berbeda-beda, tetapi diabaikan dalam analisis kompleksitas waktu.
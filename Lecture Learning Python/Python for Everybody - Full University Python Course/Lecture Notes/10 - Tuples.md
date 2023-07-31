## ⭐️ Course Contents ⭐️

⌨️ ([5:22:46](https://www.youtube.com/watch?v=8DvywoWv6fI&t=19366s)) Tuples 
⌨️ ([5:32:18](https://www.youtube.com/watch?v=8DvywoWv6fI&t=19938s)) Tuples - Sorting
⌨️ ([5:44:26](https://www.youtube.com/watch?v=8DvywoWv6fI&t=20666s)) Tuples - Sorting a Dictionary Using Tuples 

## Slides

![[Pythonlearn-10-Tuples.pdf]]

# Summary Tuples A

📝 Fakta-fakta penting yang dapat diambil dari video ini adalah:

1. Tuple merupakan jenis koleksi ketiga dalam Python yang mirip dengan list, tetapi dengan perbedaan menggunakan tanda kurung buka dan tutup ().
2. Tuple mempertahankan urutan elemen dan akses elemen dengan indeks yang dimulai dari 0.
3. Tidak mungkin mengubah elemen dalam tuple setelah tuple dibuat karena sifatnya yang tidak dapat diubah (immutable).
4. Tuple lebih efisien dalam hal penggunaan memori dan akses data, sehingga cocok digunakan untuk menyimpan data yang tidak akan diubah.
5. Beberapa operasi yang dapat dilakukan pada list, seperti mengurutkan dan menambahkan elemen, tidak bisa dilakukan pada tuple.
6. Tuple dapat digunakan sebagai bagian kiri dari pernyataan assignment, di mana nilai-nilai dalam tuple akan ditugaskan ke variabel-variabel terkait.
7. Tuple juga terkait dengan kamus (dictionary) dalam Python, di mana tuple dapat digunakan untuk mengiterasi pasangan kunci-nilai dalam kamus.

📜 Ringkasan:
Video ini menjelaskan tentang tuple dalam bahasa pemrograman Python. Tuple adalah jenis koleksi yang mirip dengan list, tetapi tidak dapat diubah setelah dibuat. Mereka lebih efisien dalam penggunaan memori dan cocok untuk menyimpan data yang tidak akan diubah. Tuple juga dapat digunakan dalam operasi seperti penguraian nilai ke variabel dan pengulangan pasangan kunci-nilai dalam kamus.

🔖 Topik-topik terkait: 
#Python #Tuple #List #Immutable #Kamus

## [Tuples](https://www.youtube.com/watch?v=8DvywoWv6fI&t=19366s)

<iframe width="560" height="315" src="https://www.youtube.com/embed/3Lxpladfh2k" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Tuple adalah jenis koleksi ketiga dalam bahasa pemrograman Python. Mereka mirip dengan list, tetapi dengan perbedaan utama dalam sintaksis. Tuple menggunakan tanda kurung buka dan tutup () daripada tanda kurung siku [] yang digunakan oleh list. Berikut adalah penjelasan lebih detail mengenai tuple:

1. Sifat dan Fungsi Tuple:
   - Tuple mempertahankan urutan elemen seperti list. Artinya, elemen-elemennya diindeks mulai dari 0, 1, 2, dan seterusnya.
   - Tuple juga dapat diakses menggunakan indeks, mirip dengan list. Contohnya, jika terdapat tuple `x` dan kita ingin mengakses elemen ketiga, kita dapat menggunakan `x[2]`.
   - Mirip dengan list, kita juga dapat menggunakan berbagai fungsi yang berlaku untuk list pada tuple, seperti `len()`, `min()`, `max()`, dan sebagainya.

2. Immutable (Tidak Dapat Diubah):
   - Perbedaan utama antara tuple dan list terletak pada sifatnya. Setelah tuple dibuat, elemen-elemennya tidak dapat diubah. Ini berarti kita tidak dapat menambah, menghapus, atau mengubah nilai elemen dalam tuple.
   - Contoh: 
     ```python
     x = (1, 2, 3)  # Membuat tuple
     x[0] = 4      # Akan menghasilkan error karena tidak dapat mengubah nilai elemen dalam tuple
     ```

3. Efisiensi dan Penggunaan Memori:
   - Tuple lebih efisien dalam penggunaan memori dibandingkan list. Mereka membutuhkan ruang penyimpanan yang lebih kecil.
   - Karena sifatnya yang tidak dapat diubah, Python dapat mengoptimalkan penggunaan memori untuk tuple.
   - Oleh karena itu, jika kita memiliki data yang tidak perlu diubah, menggunakan tuple daripada list dapat meningkatkan kinerja program.

4. Perbedaan dengan List:
   - Beberapa operasi yang dapat dilakukan pada list, seperti mengurutkan elemen atau menambahkan elemen baru, tidak dapat dilakukan pada tuple.
   - Contoh: 
     ```python
     x = (1, 2, 3)
     sorted(x)      # Akan menghasilkan tuple baru yang terurut
     x.append(4)    # Akan menghasilkan error karena tuple tidak dapat diubah
     ```

5. Penggunaan Tuple dalam Assignment:
   - Kita dapat menggunakan tuple pada sisi kiri dari pernyataan assignment untuk menugaskan nilai ke beberapa variabel sekaligus.
   - Contoh: 
     ```python
     x, y = (1, 2)  # Menggunakan tuple untuk menugaskan nilai ke variabel x dan y
     ```

6. Tuple dalam Hubungannya dengan Kamus:
   - Tuple juga memiliki hubungan dengan kamus (dictionary) dalam Python.
   - Kita dapat menggunakan fungsi `.items()` pada kamus untuk mendapatkan pasangan kunci-nilai dalam bentuk tuple.
   - Contoh: 
     ```python
     d = {'a': 1, 'b': 2, 'c': 3}
     items = d.items()  # Mengambil pasangan kunci-nilai dalam bentuk tuple
     print(items)      # Output: dict_items([('a', 1), ('b', 2), ('c', 3)])
     ```

7. Penggunaan Tuple dalam Fungsi:
   - Tuple juga sering digunakan dalam fungsi untuk mengembalikan beberapa nilai sebagai satu keluaran.
   - Dalam kasus ini, fungsi dapat mengembalikan tuple yang berisi beberapa nilai yang dapat diakses oleh pemanggil fungsi.
   - Contoh: 
     ```python
     def hitung(a, b):
         tambah = a + b
         kurang = a - b
         kali = a * b
         bagi = a / b
         return tambah, kurang, kali, bagi

     hasil = hitung(5, 3)
     print(hasil)  # Output: (8, 2, 15, 1.6666666666666667)
     ```

8. Penggunaan Tuple sebagai Argumen dalam Fungsi:
   - Kita juga dapat menggunakan tuple sebagai argumen dalam pemanggilan fungsi.
   - Dalam kasus ini, tuple dapat digunakan untuk mengirim sejumlah nilai sebagai argumen dalam satu kali pemanggilan fungsi.
   - Contoh: 
     ```python
     def tulis_data(nama, usia, alamat):
         print("Nama:", nama)
         print("Usia:", usia)
         print("Alamat:", alamat)

     data = ("John Doe", 25, "Jalan Raya No. 123")
     tulis_data(*data)
     # Output:
     # Nama: John Doe
     # Usia: 25
     # Alamat: Jalan Raya No. 123
     ```

9. Penggunaan Tuple dalam Perulangan:
   - Tuple juga dapat digunakan dalam perulangan `for` untuk mengiterasi melalui elemen-elemennya.
   - Contoh: 
     ```python
     buah = ("apel", "jeruk", "nanas")
     for buah in buah:
         print(buah)
     # Output:
     # apel
     # jeruk
     # nanas
     ```

10. Tuple dalam Pembongkaran Nilai (Unpacking):
    - Tuple juga dapat digunakan untuk melakukan pembongkaran nilai (unpacking) dalam Python.
    - Kita dapat memecah tuple menjadi beberapa variabel terpisah untuk mengakses setiap elemen secara individual.
    - Contoh:
      ```python
      tup = (1, 2, 3)
      a, b, c = tup
      print(a)  # Output: 1
      print(b)  # Output: 2
      print(c)  # Output: 3
      ```

Dengan demikian, kita telah menyelesaikan penjelasan tentang tuple dalam Python hingga nomor 10. Tuple adalah struktur data yang berguna dalam berbagai situasi, seperti penyimpanan data yang tidak dapat diubah, pengembalian nilai dari fungsi, pembongkaran nilai, dan banyak lagi. Jika Anda memiliki pertanyaan lebih lanjut, silakan tanyakan!

# Summary Tuples B

- Tuple digunakan untuk membandingkan dan mengurutkan item di dalam dictionary.
- Dapat mengonversi dictionary menjadi list of tuples, kemudian mengurutkan list tersebut.
- Tuple yang dibuat dari dictionary akan diurutkan berdasarkan kunci (key).
- Tuples dapat diurutkan secara menurun (descending order) dengan menggunakan fungsi `sorted` dan argumen `reverse=True`.
- Untuk mengurutkan dictionary berdasarkan nilai (value), kita perlu membuat data structure berupa list of tuples dengan posisi value di depan dan key di belakang.
- Dalam Python, kita dapat menggunakan ekspresi lambda dan list comprehension untuk menghasilkan solusi yang lebih singkat dan elegan.
- Konsep penggunaan tuples dalam mengurutkan dictionary juga dapat diterapkan dalam mengurutkan kata-kata yang paling umum dalam sebuah file.

#Python #Tuples #Sorting #Dictionary #ListComprehension

## Tuples B

<iframe width="560" height="315" src="https://www.youtube.com/embed/dZXzBXUxxCs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Berikut adalah penjelasan lebih detail dan contoh kode Python untuk setiap sub bab:

1. Mengurutkan Dictionary Berdasarkan Kunci (Key)
   Untuk mengurutkan dictionary berdasarkan kunci (key), kita dapat menggunakan fungsi `sorted` tanpa argumen tambahan. Fungsi ini akan menghasilkan list of tuples yang diurutkan berdasarkan kunci.

   Contoh Kode:
   ```python
   my_dict = {'b': 2, 'a': 1, 'c': 3}
   sorted_tuples = sorted(my_dict.items())
   print(sorted_tuples)
   ```
   Output:
   ```
   [('a', 1), ('b', 2), ('c', 3)]
   ```

2. Mengurutkan Dictionary Berdasarkan Nilai (Value)
   Untuk mengurutkan dictionary berdasarkan nilai (value), kita perlu memberikan argumen `key` pada fungsi `sorted` yang menentukan kriteria pengurutan. Kita dapat menggunakan ekspresi lambda untuk mengambil nilai (value) dari setiap tuple sebagai kriteria pengurutan.

   Contoh Kode:
   ```python
   my_dict = {'b': 2, 'a': 1, 'c': 3}
   sorted_tuples = sorted(my_dict.items(), key=lambda x: x[1])
   print(sorted_tuples)
   ```
   Output:
   ```
   [('a', 1), ('b', 2), ('c', 3)]
   ```

3. Mengurutkan Dictionary secara Menurun (Descending Order) Berdasarkan Nilai (Value)
   Untuk mengurutkan dictionary secara menurun (descending order) berdasarkan nilai (value), kita dapat menggunakan argumen `reverse=True` pada fungsi `sorted`. Kembali, kita menggunakan ekspresi lambda untuk mengambil nilai (value) dari setiap tuple sebagai kriteria pengurutan.

   Contoh Kode:
   ```python
   my_dict = {'b': 2, 'a': 1, 'c': 3}
   sorted_tuples = sorted(my_dict.items(), key=lambda x: x[1], reverse=True)
   print(sorted_tuples)
   ```
   Output:
   ```
   [('c', 3), ('b', 2), ('a', 1)]
   ```

4. Mengurutkan Kata-kata yang Paling Umum dalam Sebuah File
   Untuk mengurutkan kata-kata yang paling umum dalam sebuah file, kita dapat menggunakan struktur data dictionary untuk menghitung frekuensi kemunculan setiap kata. Kemudian, kita mengonversi dictionary tersebut menjadi list of tuples dan mengurutkannya berdasarkan nilai (frekuensi kemunculan) secara menurun (descending order) menggunakan ekspresi lambda dan fungsi `sorted`.

   Contoh Kode:
   ```python
   def count_words(file_path):
       word_count = {}
       with open(file_path, 'r') as file:
           for line in file:
               words = line.strip().split()
               for word in words:
                   word_count[word] = word_count.get(word, 0) + 1
       sorted_tuples = sorted(word_count.items(), key=lambda x: x[1], reverse=True)
       return sorted_tuples

   file_path = 'contoh.txt'
   common_words = count_words(file_path)
   print(common_words)
   ```
   
   Output:
   ```
   [('the', 3), ('is', 2), ('example', 2), ('of', 2), ('text', 1), ('in', 1), ('a', 1), ('file', 1)]
   ```

5. Mengonversi Dictionary menjadi List of Tuples dan Mengurutkannya
   Untuk mengonversi dictionary menjadi list of tuples dan mengurutkannya, kita dapat menggunakan fungsi `sorted` dengan argumen `items()` pada dictionary. Fungsi `items()` mengembalikan pasangan key-value dalam bentuk tuple yang kemudian dapat diurutkan.

   Contoh Kode:
   ```python
   my_dict = {'b': 2, 'a': 1, 'c': 3}
   sorted_tuples = sorted(my_dict.items())
   print(sorted_tuples)
   ```
   Output:
   ```
   [('a', 1), ('b', 2), ('c', 3)]
   ```

6. Menggunakan Ekspresi Lambda dan List Comprehension untuk Solusi yang Singkat
   Dalam Python, kita dapat menggunakan ekspresi lambda dan list comprehension untuk menghasilkan solusi yang lebih singkat dan elegan dalam mengurutkan dictionary atau melakukan operasi terkait tuples.

   Contoh Kode:
   ```python
   my_dict = {'b': 2, 'a': 1, 'c': 3}
   sorted_tuples = sorted(my_dict.items(), key=lambda x: x[1], reverse=True)
   values = [x[1] for x in sorted_tuples]
   print(values)
   ```
   Output:
   ```
   [3, 2, 1]
   ```

Dengan mengikuti konsep-konsep di atas, kita dapat mengurutkan dan memanipulasi dictionary serta tuples dengan menggunakan berbagai operasi dan metode yang tersedia dalam bahasa pemrograman Python.
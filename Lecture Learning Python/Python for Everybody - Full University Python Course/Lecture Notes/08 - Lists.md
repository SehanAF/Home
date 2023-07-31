# ⭐️ Course Contents ⭐️

## ⌨️ ([3:48:42](https://www.youtube.com/watch?v=8DvywoWv6fI&t=13722s)) Python Lists 

<iframe width="560" height="315" src="https://www.youtube.com/embed/Y0cvfDpYC_c" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## ⌨️ ([3:59:27](https://www.youtube.com/watch?v=8DvywoWv6fI&t=14367s)) Python Lists - Loop Operations 

<iframe width="560" height="315" src="https://www.youtube.com/embed/lCnHfTHkhbE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## ⌨️ ([4:08:52](https://www.youtube.com/watch?v=8DvywoWv6fI&t=14932s)) Python Lists - Strings vs. Lists

<iframe width="560" height="315" src="https://www.youtube.com/embed/lxcFa7ldCi0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## ⌨️ ([4:16:42](https://www.youtube.com/watch?v=8DvywoWv6fI&t=15402s)) Python Lists - Strings, Files, Lists & the Guardian Pattern 

<iframe width="560" height="315" src="https://www.youtube.com/embed/8DvywoWv6fI?start=15417" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



# Slides 

![[Pythonlearn-08-Lists.pdf]]

# Summary I

📌 Pengantar
- Bab 8 membahas tentang list dalam pemrograman.
- Sebelumnya, kita telah membahas tentang algoritma dalam ilmu komputer.
- Algoritma adalah langkah-langkah yang digunakan untuk memecahkan masalah menggunakan bahasa pemrograman.

📌 Struktur Data
- Data structures adalah cara cerdas dalam menyusun dan memanipulasi data.
- List adalah struktur data pertama dan paling sederhana.
- List berbeda dengan variabel yang hanya dapat menyimpan satu nilai pada suatu waktu.
- List dapat berisi banyak elemen dengan cara yang terorganisir.

📌 Contoh List
- List dapat berisi tipe data yang berbeda seperti string, integer, dan floating point number.
- List dapat berisi list lainnya, yang mengarahkan pada struktur data yang lebih kompleks.
- Ada juga konsep empty list yang tidak memiliki elemen.

📌 Penggunaan List
- List sering digunakan dalam pengulangan menggunakan pernyataan "for".
- Dengan menggunakan perulangan "for", kita dapat mengakses setiap elemen dalam list secara berurutan.
- List juga dapat diubah (mutable), sedangkan string tidak dapat diubah (immutable).

📌 Fungsi-fungsi
- Fungsi "len" digunakan untuk menghitung jumlah elemen dalam suatu list.
- Fungsi "range" digunakan untuk membuat list berisi angka yang diperlukan dalam pengulangan.

📌 Perulangan pada List
- Ada dua cara umum untuk mengulang elemen dalam list: menggunakan pernyataan "for" dan menggunakan pernyataan "range" bersama dengan "len".

#Pemrograman #StrukturData #List #Perulangan #Fungsi

## [Python List](https://www.youtube.com/watch?v=8DvywoWv6fI&t=13722s)

Berikut adalah penjelasan secara detail mengenai list dalam pemrograman dengan contoh kode Python dan penggunaan header dan bullet untuk setiap sub bab:

##  Pengantar

- Bab 8 membahas tentang list dalam pemrograman.
- Sebelumnya, kita telah membahas tentang algoritma dalam ilmu komputer.
- Algoritma adalah langkah-langkah yang digunakan untuk memecahkan masalah menggunakan bahasa pemrograman.

## Struktur Data

- Struktur data adalah cara cerdas dalam menyusun dan memanipulasi data.
- List adalah struktur data pertama dan paling sederhana.
- List berbeda dengan variabel yang hanya dapat menyimpan satu nilai pada suatu waktu.
- List dapat berisi banyak elemen dengan cara yang terorganisir.
 
## Contoh List
 
- List dapat berisi tipe data yang berbeda seperti string, integer, dan floating point number.
- List juga dapat berisi list lainnya, yang mengarahkan pada struktur data yang lebih kompleks.
- Ada juga konsep empty list yang tidak memiliki elemen.

Contoh kode Python:
```python
# List dengan tipe data yang berbeda
my_list = ['apel', 123, 3.14]

# List yang berisi list lainnya
nested_list = [[1, 2, 3], ['a', 'b', 'c']]

# Empty list
empty_list = []
```

## Penggunaan List

- List sering digunakan dalam pengulangan menggunakan pernyataan "for".
- Dengan menggunakan perulangan "for", kita dapat mengakses setiap elemen dalam list secara berurutan.
- List juga dapat diubah (mutable), sedangkan string tidak dapat diubah (immutable).

Contoh kode Python:
```python
fruits = ['apel', 'pisang', 'jeruk']

# Menggunakan perulangan for untuk mengakses setiap elemen dalam list
for fruit in fruits:
    print(fruit)

# Output:
# apel
# pisang
# jeruk

# Mengubah elemen dalam list
fruits[1] = 'mangga'
print(fruits)

# Output: ['apel', 'mangga', 'jeruk']
```

## Fungsi-fungsi

- Fungsi "len" digunakan untuk menghitung jumlah elemen dalam suatu list.
- Fungsi "range" digunakan untuk membuat list berisi angka yang diperlukan dalam pengulangan.

Contoh kode Python:
```python
fruits = ['apel', 'pisang', 'jeruk']

# Menggunakan fungsi len untuk menghitung jumlah elemen dalam list
length = len(fruits)
print(length)

# Output: 3

# Menggunakan fungsi range untuk membuat list angka dalam rentang tertentu
numbers = list(range(1, 5))
print(numbers)

# Output: [1, 2, 3, 4]
```

## Perulangan pada List

- Ada dua cara umum untuk mengulang elemen dalam list: menggunakan pernyataan "for" dan menggunakan pernyataan "range" bersama dengan "len".

Contoh kode Python:
```python
# Menggunakan pernyataan "for" untuk mengulang elemen dalam list
for fruit in fruits:
    print(fruit)

# Output:
# apel
# pisang
# jeruk

# Menggunakan pernyataan "range" bersama dengan "len" untuk mengulang elemen dalam list
for i in range(len(fruits)):
    print(fruits[i])

# Output:
# apel
# pisang
# jeruk
```

Dengan menggunakan header dan bullet pada setiap sub bab, penjelasan tentang list dalam pemrograman telah diberikan bersama dengan contoh kode Python yang relevan. List merupakan struktur data penting dalam pemrograman yang memungkinkan penyimpanan dan manipulasi data yang lebih kompleks.

## Manipulasi List

- List adalah struktur data yang mutable, artinya elemen-elemennya dapat diubah.
- Beberapa operasi manipulasi list meliputi penambahan elemen, penghapusan elemen, dan penggantian elemen.

## Penambahan Elemen

- Untuk menambahkan elemen baru ke dalam list, dapat menggunakan metode `append()` atau operator penambahan `+`.
- Metode `append()` digunakan untuk menambahkan elemen ke akhir list.
- Operator penambahan `+` digunakan untuk menggabungkan dua list.

Contoh:
```python
fruits = ['apel', 'pisang', 'jeruk']
fruits.append('mangga')
print(fruits)
# Output: ['apel', 'pisang', 'jeruk', 'mangga']

numbers1 = [1, 2, 3]
numbers2 = [4, 5, 6]
combined = numbers1 + numbers2
print(combined)
# Output: [1, 2, 3, 4, 5, 6]
```

## Penghapusan Elemen

- Untuk menghapus elemen dari list, dapat menggunakan metode `remove()` atau pernyataan `del`.
- Metode `remove()` digunakan untuk menghapus elemen berdasarkan nilainya.
- Pernyataan `del` digunakan untuk menghapus elemen berdasarkan indeksnya.

Contoh:
```python
fruits = ['apel', 'pisang', 'jeruk']
fruits.remove('pisang')
print(fruits)
# Output: ['apel', 'jeruk']

numbers = [1, 2, 3, 4, 5]
del numbers[2]
print(numbers)
# Output: [1, 2, 4, 5]
```

## Penggantian Elemen

- Untuk menggantikan nilai elemen dalam list, dapat mengakses elemen menggunakan indeks dan mengubah nilainya.

Contoh:
```python
fruits = ['apel', 'pisang', 'jeruk']
fruits[1] = 'mangga'
print(fruits)
# Output: ['apel', 'mangga', 'jeruk']
```

Dalam bagian ini, telah dijelaskan tentang operasi manipulasi list, yaitu penambahan elemen, penghapusan elemen, dan penggantian elemen. Contoh kode Python juga diberikan untuk masing-masing operasi tersebut.

## Pencarian dan Pemeriksaan Elemen pada List

- Untuk mencari elemen tertentu dalam list, dapat menggunakan pernyataan `in` atau metode `index()`.
- Pernyataan `in` digunakan untuk memeriksa apakah suatu nilai ada dalam list.
- Metode `index()` digunakan untuk mendapatkan indeks dari elemen pertama yang ditemukan dalam list.

Contoh:
```python
fruits = ['apel', 'pisang', 'jeruk']
print('pisang' in fruits)
# Output: True

numbers = [1, 2, 3, 4, 5]
print(numbers.index(3))
# Output: 2
```

## Slicing pada List

- Slicing adalah teknik untuk mengambil sepotong sublist dari list utama.
- Dapat menggunakan operator slicing `:` untuk mengambil elemen dari indeks awal hingga indeks akhir.
- Indeks awal termasuk dalam slicing, sedangkan indeks akhir tidak termasuk dalam slicing.

Contoh:
```python
fruits = ['apel', 'pisang', 'jeruk', 'mangga', 'melon']
sublist = fruits[1:4]
print(sublist)
# Output: ['pisang', 'jeruk', 'mangga']
```

## Perulangan pada List dengan Menggunakan `for`

- Perulangan `for` dapat digunakan untuk mengakses setiap elemen dalam list secara berurutan.
- Dapat menggunakan sintaks `for item in list` untuk mengiterasi melalui setiap elemen dalam list.

Contoh:
```python
fruits = ['apel', 'pisang', 'jeruk']
for fruit in fruits:
    print(fruit)
# Output:
# apel
# pisang
# jeruk
```

Dalam bagian ini, telah dijelaskan tentang pencarian dan pemeriksaan elemen pada list, slicing pada list, serta perulangan pada list menggunakan pernyataan `for`. Contoh kode Python juga diberikan untuk setiap konsep tersebut.

# Summary II

- Operator "+" dalam Python dapat digunakan untuk menggabungkan (concatenate) list. Contohnya, ketika kita menambahkan list [1, 2, 3] dan [4, 5, 6], hasilnya akan menjadi [1, 2, 3, 4, 5, 6].
- Slicing pada list dapat dilakukan dengan menggunakan angka sebagai indeks. Indeks dimulai dari 0, dan saat melakukan slicing, angka pertama merupakan posisi awal, dan angka kedua (tapi tidak termasuk) adalah posisi akhir.
- Terdapat beberapa metode yang bisa digunakan pada list, seperti append (menambahkan elemen ke akhir list), count (menghitung jumlah kemunculan nilai tertentu dalam list), extend (menambahkan elemen-elemen dari list lain ke akhir list), dll.
- Dalam list, dapat dilakukan operasi in untuk mencari apakah suatu nilai ada dalam list, dan operasi sort untuk mengurutkan elemen-elemen dalam list.
- Terdapat beberapa fungsi bawaan (built-in functions) yang dapat digunakan pada list, seperti len (untuk menghitung jumlah elemen dalam list), max (untuk mencari nilai terbesar dalam list), min (untuk mencari nilai terkecil dalam list), dan sum (untuk menjumlahkan semua elemen dalam list).
- Terdapat dua cara yang dapat digunakan untuk menghitung rata-rata dari sejumlah angka yang dimasukkan oleh pengguna, yaitu menggunakan loop atau menggunakan list.

Fakta-fakta penting:
- Operator "+" dapat digunakan untuk menggabungkan (concatenate) list.
- Slicing pada list memungkinkan pengambilan sebagian elemen dari list berdasarkan indeks.
- Terdapat berbagai metode yang dapat digunakan pada list, seperti append, count, extend, index, insert, pop, remove, reverse, dan sort.
- Operasi in dapat digunakan untuk mencari apakah suatu nilai ada dalam list, sedangkan operasi sort dapat digunakan untuk mengurutkan elemen-elemen dalam list.
- Terdapat fungsi bawaan yang dapat digunakan pada list, seperti len, max, min, dan sum.
- Terdapat dua cara yang dapat digunakan untuk menghitung rata-rata dari sejumlah angka, yaitu menggunakan loop atau menggunakan list.

Topik terkait: #Python #List #Operator #Metode #FungsiBawaan

## [Python Lists - Loop Operations](https://www.youtube.com/watch?v=8DvywoWv6fI&t=14367s)

## Penjelasan tentang Operator "+" dalam Python untuk Menggabungkan List

Operator "+" dalam Python digunakan untuk menggabungkan (concatenate) list. Ketika kita menggunakan operator "+" pada dua list, elemen-elemen dari kedua list tersebut akan digabungkan menjadi satu list baru.

Contoh:

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]
hasil = list1 + list2
print(hasil)
```

Output:
```
[1, 2, 3, 4, 5, 6]
```

Dalam contoh di atas, list1 berisi elemen [1, 2, 3] dan list2 berisi elemen [4, 5, 6]. Ketika kita menggunakan operator "+" untuk menggabungkan kedua list tersebut, hasilnya akan menjadi list baru [1, 2, 3, 4, 5, 6].

## Penjelasan tentang Slicing pada List

Slicing pada list merupakan proses pengambilan sebagian elemen dari list berdasarkan indeks. Indeks pada list dimulai dari 0, sehingga elemen pertama memiliki indeks 0, elemen kedua memiliki indeks 1, dan seterusnya.

Slicing pada list dilakukan dengan menggunakan angka sebagai indeks. Angka pertama yang diberikan merupakan posisi awal dari slicing, sedangkan angka kedua (tetapi tidak termasuk) merupakan posisi akhir dari slicing.

Contoh:

```python
list = [1, 2, 3, 4, 5]
sliced_list = list[1:4]
print(sliced_list)
```

Output:
```
[2, 3, 4]
```

Dalam contoh di atas, kita memiliki list [1, 2, 3, 4, 5]. Ketika kita melakukan slicing dengan menggunakan [1:4], kita akan mengambil elemen mulai dari indeks 1 (elemen kedua) hingga sebelum indeks 4 (elemen kelima), sehingga elemen yang diambil adalah [2, 3, 4].

## Penjelasan tentang Metode pada List

Terdapat beberapa metode yang dapat digunakan pada list untuk melakukan berbagai operasi, antara lain:

1. **append**: Metode append digunakan untuk menambahkan elemen baru ke akhir list.

   Contoh:
   ```python
   list = [1, 2, 3]
   list.append(4)
   print(list)
   ```

   Output:
   ```
   [1, 2, 3, 4]
   ```

2. **count**: Metode count digunakan untuk menghitung jumlah kemunculan nilai tertentu dalam list.

   Contoh:
   ```python
   list = [1, 2, 2, 3, 3, 3]
   count = list.count(3)
   print(count)
   ```

   Output:
   ```
   3
   ```

3. **extend**: Metode extend digunakan untuk menambahkan elemen-elemen dari list lain ke akhir list.

   Contoh:
   ```python
   list1 = [1, 2, 3]
   list2 = [4, 5, 6]
   list1.extend(list2)
   print(list1)
   ```

   Output:
   ```
   [1, 2, 3, 4, 5, 6 
   ```

4. **index**: Metode index digunakan untuk mencari indeks pertama dari suatu nilai dalam list.

   Contoh:
   ```python
   list = [1, 2, 3, 4, 3]
   index = list.index(3)
   print(index)
   ```

   Output:
   ```
   2
   ```

   Dalam contoh di atas, kita mencari indeks pertama dari nilai 3 dalam list. Hasilnya adalah 2, karena nilai 3 pertama kali muncul pada indeks ke-2.

5. **insert**: Metode insert digunakan untuk menyisipkan elemen baru pada posisi yang ditentukan dalam list.

   Contoh:
   ```python
   list = [1, 2, 3]
   list.insert(1, 4)
   print(list)
   ```

   Output:
   ```
   [1, 4, 2, 3]
   ```

   Dalam contoh di atas, elemen 4 disisipkan pada indeks 1, sehingga menghasilkan list baru [1, 4, 2, 3].

6. **pop**: Metode pop digunakan untuk menghapus elemen pada posisi tertentu dalam list dan mengembalikan nilainya.

   Contoh:
   ```python
   list = [1, 2, 3]
   popped_value = list.pop(1)
   print(popped_value)
   print(list)
   ```

   Output:
   ```
   2
   [1, 3]
   ```

   Dalam contoh di atas, elemen pada indeks 1 (elemen kedua) yaitu 2 dihapus dari list dan dikembalikan sebagai nilai yang disimpan dalam variabel `popped_value`. Setelah itu, list menjadi [1, 3].

7. **remove**: Metode remove digunakan untuk menghapus kemunculan pertama dari suatu nilai dalam list.

   Contoh:
   ```python
   list = [1, 2, 3, 2]
   list.remove(2)
   print(list)
   ```

   Output:
   ```
   [1, 3, 2]
   ```

   Dalam contoh di atas, kemunculan pertama nilai 2 dihapus dari list, sehingga menghasilkan list baru [1, 3, 2].

8. **reverse**: Metode reverse digunakan untuk membalik urutan elemen dalam list.

   Contoh:
   ```python
   list = [1, 2, 3]
   list.reverse()
   print(list)
   ```

   Output:
   ```
   [3, 2, 1]
   ```

   Dalam contoh di atas, urutan elemen dalam list [1, 2, 3] dibalik menjadi [3, 2, 1].

9. **sort**: Metode sort digunakan untuk mengurutkan elemen-elemen dalam list secara ascending (secara default) atau descending.

   Contoh:
   ```python
   list = [3, 1, 2]
   list.sort()
   print(list)
   ```

   Output:
   ```
   [1, 2, 3]
   ```

   Dalam contoh di atas, elemen-elemen dalam list [3, 1, 2] diurutkan secara ascending menjadi [1, 2, 3].

## Penjelasan tentang Operasi "in" dan "sort" pada List

1. **Operasi "in" pada List**: Operasi "in" dapat digunakan pada list untuk mencari apakah suatu nilai ada dalam list atau tidak. Jika nilai tersebut ada dalam list, maka hasilnya akan True. Jika tidak, maka hasilnya akan False.

   Contoh:
   ```python
   list = [1, 2, 3, 4, 5]
   print(3 in list)   # True
   print(6 in list)   # False
   ```

   Output:
   ```
   True
   False
   ```

   Dalam contoh di atas, operasi "in" digunakan untuk mencari nilai 3 dan 6 dalam list. Karena nilai 3 ada dalam list, maka hasilnya True. Namun, nilai 6 tidak ada dalam list, sehingga hasilnya False.

2. **Operasi "sort" pada List**: Operasi "sort" digunakan untuk mengurutkan elemen-elemen dalam list secara ascending (secara default) atau descending. Setelah operasi "sort" dilakukan, elemen-elemen dalam list akan terurut sesuai dengan aturan pengurutan yang ditentukan.

   Contoh:
   ```python
   list = [4, 2, 1, 3, 5]
   list.sort()
   print(list)
   ```

   Output:
   ```
   [1, 2, 3, 4, 5]
   ```

   Dalam contoh di atas, elemen-elemen dalam list [4, 2, 1, 3, 5] diurutkan secara ascending menggunakan operasi "sort", sehingga menghasilkan list baru [1, 2, 3, 4, 5].

## Penjelasan tentang Fungsi Bawaan pada List

Terdapat beberapa fungsi bawaan (built-in functions) yang dapat digunakan pada list untuk melakukan operasi tertentu, antara lain:

1. **len**: Fungsi len digunakan untuk menghitung jumlah elemen dalam list.

   Contoh:
   ```python
   list = [1, 2, 3, 4, 5]
   length = len(list)
   print(length)
   ```

   Output:
   ```
   5
   ```

   Dalam contoh di atas, fungsi len digunakan untuk menghitung jumlah elemen dalam list, yaitu 5.

2. **max**: Fungsi max digunakan untuk mencari nilai terbesar dalam list.

   Contoh:
   ```python
   list = [1, 4, 2, 5, 3]
   maximum = max(list)
   print(maximum)
   ```

   Output:
   ```
   5
   ```

   Dalam contoh di atas, fungsi max digunakan untuk mencari nilai terbesar dalam list [1, 4, 2, 5, 3], yaitu 5.

3. **min**: Fungsi min digunakan untuk mencari nilai terkecil dalam list.

   Contoh:
   ```python
   list = [1, 4, 2, 5, 3]
   minimum = min(list)
   print(minimum)
   ```

   Output:
   ```
   1
   ```

   Dalam contoh di atas, fungsi min digunakan untuk mencari nilai terkecil dalam list [1, 4, 2, 5, 3], yaitu 1.

4. **sum**: Fungsi sum digunakan untuk menjumlahkan semua elemen dalam list yang berisi angka.

   Contoh:
   ```python
   list = [1, 2, 3, 4, 5]
   total = sum(list)
   print(total)
   ```

   Output:
   ```
   15
   ```

   Dalam contoh di atas, fungsi sum digunakan untuk menjumlahkan semua elemen dalam list [1, 2, 3, 4, 5], yaitu 15.

## Penjelasan tentang Menghitung Rata-rata menggunakan List

Terdapat dua cara yang dapat digunakan untuk menghitung rata-rata dari sejumlah angka yang dimasukkan oleh pengguna, yaitu menggunakan loop atau menggunakan list.

1. **Menghitung Rata-rata menggunakan Loop**: Dalam metode ini, kita meminta pengguna memasukkan sejumlah angka, kemudian menggunakan loop untuk menjumlahkan angka-angka tersebut dan menghitung rata-ratanya.

   Contoh:
   ```python
   n = int(input("Masukkan jumlah angka: "))
   numbers = []
   for i in range(n):
       angka = float(input("Masukkan angka: "))
       numbers.append(angka)
   
   total = sum(numbers)
   rata_rata = total / n
   print("Rata-rata:", rata_rata)
   ```

   Dalam contoh di atas, kita meminta pengguna memasukkan jumlah angka yang akan dihitung rata-ratanya. Selanjutnya, kita menggunakan loop for untuk meminta pengguna memasukkan angka-angka tersebut dan menyimpannya dalam list `numbers`. Setelah itu, kita menjumlahkan semua angka dalam list menggunakan fungsi `sum`, dan menghitung rata-ratanya dengan membagi jumlah total dengan jumlah angka.

2. **Menghitung Rata-rata menggunakan List**: Dalam metode ini, kita meminta pengguna memasukkan sejumlah angka, kemudian menggunakan list untuk menyimpan angka-angka tersebut. Selanjutnya, kita menggunakan fungsi `sum` dan fungsi `len` untuk menghitung rata-ratanya.

   Contoh:
   ```python
   angka_str = input("Masukkan angka-angka yang dipisahkan oleh spasi: ")
   angka_list = angka_str.split()
   angka_list = [float(angka) for angka in angka_list]
   
   total = sum(angka_list)
   n = len(angka_list)
   rata_rata = total / n
   print("Rata-rata:", rata_rata)
   ```

   Dalam contoh di atas, kita meminta pengguna memasukkan angka-angka yang dipisahkan oleh spasi. Kita menggunakan metode `split` untuk memisahkan angka-angka tersebut menjadi elemen-elemen dalam list `angka_list`. Selanjutnya, kita menggunakan list comprehension untuk mengonversi setiap elemen dalam `angka_list` menjadi tipe float. Setelah itu, kita menjumlahkan semua angka dalam list menggunakan fungsi `sum`, dan menghitung rata-ratanya dengan membagi jumlah total dengan jumlah angka.

Dengan menggunakan salah satu dari dua metode di atas, kita dapat menghitung rata-rata dari sejumlah

# Summary III

Ringkasan:
Dalam video ini, dijelaskan tentang hubungan antara string dan list dalam Python. Salah satu fitur yang menarik adalah fungsi split yang memecah string menjadi list berdasarkan spasi. Fungsi ini sangat berguna dalam memisahkan kata-kata dalam sebuah kalimat. Selain itu, video ini juga menjelaskan bahwa split dapat dilakukan tidak hanya berdasarkan spasi, tetapi juga karakter lainnya seperti titik koma. 

Poin-poin penting:
1. 🧵 Strings dan lists terkait dalam Python.
2. 🔄 Fungsi split memisahkan string menjadi list berdasarkan spasi.
3. 📚 Split juga bisa dilakukan berdasarkan karakter selain spasi.
4. 🔍 Dalam split, karakter-karakter seperti tab dan baris baru juga dianggap sebagai spasi.
5. 📂 Fungsi split sangat berguna dalam memproses data seperti alamat email.
6. 📝 Split memungkinkan kita mengakses kata-kata atau bagian-bagian tertentu dari sebuah string.
7. ⚡️ Pemahaman konsep split dan penggunaannya akan sangat membantu dalam mengolah data di masa depan.

Hashtags:
#Python #String #List #Split #DataStruktur

##  [Python Lists - Strings vs. Lists](https://www.youtube.com/watch?v=8DvywoWv6fI&t=14932s)

**Pendahuluan**
Dalam video ini, dijelaskan tentang hubungan antara string (teks) dan list (daftar) dalam bahasa pemrograman Python. String adalah tipe data yang digunakan untuk merepresentasikan teks, sedangkan list adalah tipe data yang digunakan untuk menyimpan kumpulan nilai.

**1. String dan List**
- String: Merupakan urutan karakter yang diapit oleh tanda kutip, seperti 'Hello World'.
- List: Merupakan kumpulan nilai yang diapit oleh tanda kurung siku, seperti [1, 2, 3, 4, 5].

**2. Fungsi Split**
- Fungsi split() adalah fungsi bawaan Python yang digunakan untuk memecah sebuah string menjadi bagian-bagian yang lebih kecil berdasarkan separator tertentu.
- Separator biasanya berupa spasi, tetapi bisa juga karakter lain seperti titik koma atau tanda koma.
- Contoh penggunaan fungsi split() untuk memecah string menjadi list:

```python
kalimat = "Halo, nama saya John Doe"
kata_kunci = kalimat.split(", ")
print(kata_kunci)
```
Output:
```python
['Halo', 'nama saya John Doe']
```

**3. Penggunaan Split pada Data Selain Spasi**
- Fungsi split() tidak hanya dapat digunakan untuk memecah string berdasarkan spasi, tetapi juga karakter lain.
- Contoh penggunaan split() dengan karakter pemisah berupa titik koma:

```python
data = "Apple;Banana;Orange;Grape"
buah = data.split(";")
print(buah)
```
Output:
```python
['Apple', 'Banana', 'Orange', 'Grape']
```

**4. Karakter Spasi**
- Fungsi split() memperlakukan karakter spasi sebagai pemisah utama, tetapi juga menghapus karakter spasi yang berlebihan dan karakter whitespace lainnya seperti tab atau baris baru.
- Contoh penggunaan split() dengan karakter spasi sebagai pemisah:

```python
kalimat = "Ini   adalah   contoh   kalimat"
kata = kalimat.split(" ")
print(kata)
```
Output:
```python
['Ini', 'adalah', 'contoh', 'kalimat']
```

**5. Pengolahan Alamat Email**
- Fungsi split() sangat berguna dalam pengolahan data seperti alamat email.
- Contoh penggunaan split() untuk memperoleh bagian-bagian dari alamat email:

```python
email = "john.doe@example.com"
bagian = email.split("@")
nama_pengguna = bagian[0]
domain = bagian[1]
print("Nama Pengguna:", nama_pengguna)
print("Domain:", domain)
```
Output:
```python
Nama Pengguna: john.doe
Domain: example.com
```

**Kesimpulan**
Dalam video ini, dijelaskan tentang hubungan antara string dan list dalam Python. Fungsi split() memungkinkan kita untuk memecah string menjadi list berdasarkan separator tertentu, seperti spasi atau karakter khusus lainnya. Pemahaman konsep split dan penggunaannya akan sangat membantu dalam mengolah data di masa depan.

Hashtags:
#Python #String #List #Split #DataStruktur

**6. Mengakses Kata-kata atau Bagian Tertentu dari String**
- Setelah memisahkan string menjadi list menggunakan fungsi split(), kita dapat mengakses kata-kata atau bagian-bagian tertentu dari string tersebut menggunakan indeks pada list.
- Indeks dimulai dari 0, sehingga kata pertama memiliki indeks 0, kata kedua memiliki indeks 1, dan seterusnya.
- Contoh penggunaan indeks untuk mengakses kata-kata dari string yang telah dipisahkan:

```python
kalimat = "Ini adalah contoh kalimat"
kata = kalimat.split(" ")
print("Kata pertama:", kata[0])
print("Kata kedua:", kata[1])
print("Kata ketiga:", kata[2])
```
Output:
```python
Kata pertama: Ini
Kata kedua: adalah
Kata ketiga: contoh
```

**7. Manfaat dalam Pengolahan Data di Masa Depan**
- Pemahaman tentang konsep split dan penggunaannya sangat berguna dalam mengolah data di masa depan.
- Dalam pemrograman, seringkali kita perlu memisahkan teks atau string menjadi bagian-bagian yang lebih kecil untuk melakukan operasi atau analisis lebih lanjut.
- Fungsi split() memberikan fleksibilitas dalam memisahkan string berdasarkan separator tertentu, sehingga mempermudah pengolahan data yang kompleks.
- Dengan memahami dan menguasai penggunaan split(), kita dapat meningkatkan produktivitas dan efisiensi dalam pemrograman Python.

**Kesimpulan**
Dalam video ini, kita telah mempelajari hubungan antara string dan list dalam Python. Fungsi split() memungkinkan kita untuk memisahkan string menjadi list berdasarkan separator tertentu, seperti spasi atau karakter khusus lainnya. Kita juga dapat mengakses kata-kata atau bagian-bagian tertentu dari string yang telah dipisahkan menggunakan indeks pada list. Pemahaman konsep split dan penggunaannya akan sangat membantu dalam mengolah data di masa depan, meningkatkan produktivitas dan efisiensi dalam pemrograman Python.

Hashtags:
#Python #String #List #Split #DataStruktur
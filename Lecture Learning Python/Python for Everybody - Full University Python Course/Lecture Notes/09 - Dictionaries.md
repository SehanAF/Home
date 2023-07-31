## ⭐️ Course Contents ⭐️

⌨️ ([4:28:44](https://www.youtube.com/watch?v=8DvywoWv6fI&t=16124s)) Dictionaries
⌨️ ([4:36:32](https://www.youtube.com/watch?v=8DvywoWv6fI&t=16592s)) Dictionaries - Counting
⌨️ ([4:45:43](https://www.youtube.com/watch?v=8DvywoWv6fI&t=17143s)) Dictionaries - Counting Words in Text
⌨️ ([4:58:21](https://www.youtube.com/watch?v=8DvywoWv6fI&t=17901s)) Dictionaries - Counting Word Frequency Using a Dictionary

## Slides

![[Pythonlearn-09-Dictionaries.pdf]]

# Summary I

- Python Dictionaries adalah salah satu jenis koleksi yang paling disukai oleh para programer karena kekuatannya.
- Python Dictionaries adalah seperti database kecil di dalam memori dan merupakan jenis koleksi terbaik.
- Dalam Python Dictionaries, tidak ada urutan yang jelas dan setiap elemen memiliki kunci.
- Kunci berfungsi sebagai penanda untuk menempatkan dan mengambil elemen dari Python Dictionaries.
- Dictionaries disebut juga sebagai Associative Arrays dan memungkinkan penempatan lebih dari satu elemen.
- Dictionaries memungkinkan penambahan, penghapusan, dan pembaruan elemen.
- Dictionaries menggunakan pasangan kunci-nilai untuk mengasosiasikan data.

Fakta dalam poin-poin:
- Python Dictionaries adalah jenis koleksi yang paling disukai oleh para programer.
- Dictionaries tidak memiliki urutan yang jelas, tetapi setiap elemen memiliki kunci.
- Kunci digunakan untuk menempatkan dan mengambil elemen dari Dictionaries.
- Dictionaries dapat menampung lebih dari satu elemen.
- Dictionaries disebut juga sebagai Associative Arrays.
- Dictionaries memungkinkan penambahan, penghapusan, dan pembaruan elemen.
- Dictionaries menggunakan pasangan kunci-nilai untuk mengasosiasikan data.

Emoji yang sesuai:
- 💡 Python Dictionaries adalah kekuatan Python.
- 🔄 Dictionaries memungkinkan penambahan, penghapusan, dan pembaruan.
- 🗃️ Dictionaries adalah seperti database kecil di dalam memori.
- 🔑 Dictionaries menggunakan kunci untuk mengakses elemen.
- 📊 Dictionaries adalah koleksi yang berguna untuk menghitung dan mengelompokkan data.
- 💻 Dictionaries adalah jenis koleksi yang populer di banyak bahasa pemrograman.
- 🎯 Dictionaries memudahkan pengelolaan data dengan pasangan kunci-nilai.

Topik terkait (#hashtags):
#Python #Dictionaries #AssociativeArrays #Koleksi #KunciNilai

##  [Dictionaries](https://www.youtube.com/watch?v=8DvywoWv6fI&t=16124s)

<iframe width="560" height="315" src="https://www.youtube.com/embed/dnzvfimrRMg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

### Pendahuluan

Python Dictionaries adalah salah satu jenis koleksi yang paling disukai oleh para programer. Dictionaries berperan sebagai database kecil di dalam memori dan merupakan jenis koleksi terbaik dalam Python. Dalam bahasa pemrograman, koleksi digunakan untuk menyimpan beberapa informasi dalam satu variabel, menggantikan penggunaan variabel tunggal. Pada bagian ini, kita akan membahas secara detail mengenai Python Dictionaries.

### 1. Konsep Koleksi

Sebelum memahami Dictionaries, penting untuk memahami konsep dasar dari koleksi. Koleksi memungkinkan kita untuk menyimpan beberapa informasi dalam satu variabel, seperti daftar atau kamus. Sebelum adanya koleksi, kita harus menyimpan informasi secara terpisah dalam variabel, yang dapat menimbulkan masalah jika informasi tersebut harus diperbarui atau diakses secara bersamaan.

### 2. Mengapa Python Dictionaries Populer?

Python Dictionaries sangat populer karena kekuatannya. Dictionaries menyediakan fleksibilitas yang tinggi dalam mengelola dan mengakses data. Beberapa alasan mengapa Dictionaries begitu disukai oleh para programer antara lain:

- **Struktur Data yang Efisien**: Dictionaries menyimpan data dalam bentuk pasangan kunci-nilai, sehingga memungkinkan pengelolaan data yang efisien.
- **Tidak Ada Urutan yang Jelas**: Dictionaries tidak mengikuti urutan tertentu, sehingga memungkinkan penambahan dan penghapusan elemen secara bebas tanpa memengaruhi urutan yang ada.
- **Pengaksesan Data Berbasis Kunci**: Dictionaries menggunakan kunci sebagai penanda untuk mengakses elemen. Hal ini memungkinkan akses langsung ke elemen yang diinginkan, tanpa harus melalui proses pencarian berdasarkan posisi.
- **Penamaan Data yang Mudah**: Dictionaries memungkinkan pemberian nama atau label pada setiap elemen, sehingga data dapat diorganisir dan diakses dengan mudah berdasarkan kunci yang ditentukan.
- **Fleksibilitas dalam Mengelompokkan Data**: Dictionaries memungkinkan pengelompokkan data yang beragam dengan menggunakan kunci yang berbeda-beda.
- **Pembaruan dan Pemrosesan Data yang Mudah**: Dictionaries memungkinkan penambahan, penghapusan, dan pembaruan elemen dengan mudah. Operasi-operasi ini dapat dilakukan dengan cepat dan efisien.
- **Dukungan pada Banyak Bahasa Pemrograman**: Konsep Dictionaries juga dikenal dengan sebutan Associative Arrays dan didukung oleh banyak bahasa pemrograman modern. Hal ini menjadikan Dictionaries sebagai komponen umum yang dapat digunakan dalam berbagai proyek.

### Contoh Kode Python:
```python
# Contoh penggunaan Python Dictionaries
data_mahasiswa = {
    'nim': '12345',
    'nama': 'John Doe',
    'jurusan': 'Informatika',
    'angkatan': 2020
}

# Mengakses elemen menggunakan kunci
print(data_mahasiswa['nama'])  # Output: John Doe

# Menambahkan elemen baru ke dalam Dictionaries
data_mahasiswa['email'] = 'john.doe@example.com'

# Mengubah nilai dari elemen yang ada
data_mahasiswa['angkatan'] = 2021

# Menghapus elemen dari Dictionaries
del data_mahasiswa['jurusan']

# Mengakses seluruh elemen dalam Dictionaries
for key, value in data_mahasiswa.items():
    print(key + ':', value)
```

Output:
```
nim: 12345
nama: John Doe
angkatan: 2021
email: john.doe@example.com
```

Dalam contoh kode di atas, kita membuat sebuah Dictionaries yang menyimpan informasi tentang seorang mahasiswa. Setiap elemen dalam Dictionaries memiliki kunci yang unik, seperti 'nim', 'nama', 'jurusan', dan 'angkatan'. Kunci tersebut digunakan untuk mengakses nilai-nilai yang terkait.

Kode `print(data_mahasiswa['nama'])` digunakan untuk mengakses elemen dengan kunci 'nama' dalam Dictionaries dan mencetak nilainya, yaitu 'John Doe'.

Kemudian, kita menambahkan elemen baru ke dalam Dictionaries menggunakan sintaksis `data_mahasiswa['email'] = 'john.doe@example.com'`. Elemen baru ini memiliki kunci 'email' dan nilai 'john.doe@example.com'.

Selanjutnya, kita mengubah nilai dari elemen 'angkatan' menggunakan sintaksis `data_mahasiswa['angkatan'] = 2021`. Nilai dari elemen 'angkatan' diperbarui menjadi 2021.

Selanjutnya, kita menghapus elemen 'jurusan' menggunakan sintaksis `del data_mahasiswa['jurusan']`.

Terakhir, kita menggunakan loop `for` untuk mengakses dan mencetak seluruh elemen dalam Dictionaries menggunakan metode `.items()`. Setiap elemen dicetak dengan format "kunci: nilai".

### Kesimpulan

Python Dictionaries adalah jenis koleksi yang populer dalam bahasa pemrograman Python. Dictionaries menyediakan struktur data yang efisien dengan menggunakan pasangan kunci-nilai. Dictionaries memungkinkan penambahan, penghapusan, dan pembaruan elemen dengan mudah. Mereka juga sangat fleksibel dalam mengelola dan mengakses data, serta dapat digunakan dalam berbagai proyek pemrograman.

# Summary II

- Dalam video ini, dibahas penggunaan kamus (dictionaries) dalam membuat histogram.
- Histogram digunakan untuk menghitung frekuensi kemunculan suatu hal.
- Kamus digunakan untuk menyimpan nama dan jumlah kemunculannya.
- Metode `get()` pada kamus digunakan untuk memeriksa keberadaan kunci dan mengambil nilai default jika kunci belum ada.
- Penggunaan kamus dengan metode `get()` adalah idiom umum dalam Python.

Fakta-fakta:
- Histogram adalah grafik yang menggambarkan frekuensi kemunculan suatu hal. 📊
- Dalam video ini, digunakan kamus untuk menghitung frekuensi kemunculan nama-nama. 📚
- Penghitungan dilakukan secara iteratif, satu nama per satu nama. ⏳
- Metode `get()` pada kamus digunakan untuk memeriksa apakah kunci sudah ada atau belum. ✅
- Jika kunci belum ada, metode `get()` mengembalikan nilai default yang ditentukan. 🔑
- Penggunaan kamus dengan metode `get()` adalah idiom yang umum digunakan dalam Python untuk menghitung frekuensi kemunculan. 💡

Topik terkait:
#Histogram #Kamus #Frekuensi #Iterasi #MetodeGet

## [Dictionaries - Counting](https://www.youtube.com/watch?v=8DvywoWv6fI&t=16592s)

<iframe width="560" height="315" src="https://www.youtube.com/embed/f17xPfIXct0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Penggunaan Kamus (Dictionaries) dalam Membuat Histogram

Dalam video ini, kita akan membahas penggunaan kamus (dictionaries) dalam membuat histogram. Histogram digunakan untuk menghitung frekuensi kemunculan suatu hal. Dalam konteks ini, kita akan menggunakan kamus untuk menyimpan nama dan jumlah kemunculannya.

## Histogram: Grafik Frekuensi Kemunculan
Histogram adalah grafik yang menggambarkan frekuensi kemunculan suatu hal. Misalnya, jika kita memiliki sejumlah data nama, histogram akan menunjukkan berapa kali setiap nama muncul. Dalam contoh ini, kita akan menggunakan kamus untuk menghitung frekuensi kemunculan nama-nama.

## Penghitungan Iteratif
Penghitungan frekuensi dilakukan secara iteratif, yaitu satu nama per satu nama. Kita akan melihat setiap nama secara berurutan dan menghitung berapa kali nama tersebut muncul. Pada setiap iterasi, kita akan memperbarui kamus dengan menambahkan jumlah kemunculan nama tersebut.

## Metode `get()` pada Kamus
Dalam kode Python, kita akan menggunakan metode `get()` pada kamus untuk memeriksa apakah kunci (nama) sudah ada atau belum. Jika kunci belum ada dalam kamus, metode `get()` akan mengembalikan nilai default yang ditentukan (biasanya 0). Jika kunci sudah ada, metode `get()` akan mengembalikan nilai yang terkait dengan kunci tersebut.

Contoh Kode Python:
```python
names = ["csev", "cwen", "csev", "zqian"]  # Contoh data nama

counts = {}  # Membuat kamus kosong untuk menyimpan jumlah kemunculan nama

for name in names:
    counts[name] = counts.get(name, 0) + 1
    # Memperbarui kamus dengan menggunakan metode `get()`
    # Jika nama belum ada dalam kamus, tambahkan nama ke kamus dengan nilai 1
    # Jika nama sudah ada dalam kamus, tambahkan 1 ke nilai yang sudah ada

print(counts)
# Output: {'csev': 2, 'cwen': 1, 'zqian': 1}
```

Penjelasan Kode:
- `names` adalah sebuah list yang berisi nama-nama contoh.
- `counts` adalah kamus yang akan digunakan untuk menghitung frekuensi kemunculan nama-nama.
- Dalam loop `for`, setiap nama akan diperiksa:
  - Metode `get()` digunakan untuk memeriksa apakah nama sudah ada dalam kamus.
  - Jika nama belum ada dalam kamus, metode `get()` mengembalikan nilai default yaitu 0.
  - Jika nama sudah ada dalam kamus, metode `get()` mengembalikan nilai yang terkait dengan kunci tersebut.
  - Kita menambahkan 1 ke nilai yang diperoleh dari metode `get()` dan memperbarui kamus dengan nilai baru.
- Pada akhirnya, kamus `counts` akan berisi frekuensi kemunculan nama-nama.

Dalam Python, penggunaan kamus dengan metode `get()` adalah sebuah idiom yang umum digunakan untuk menghitung frekuensi kemunculan suatu hal. Dalam contoh ini, kami menggunakannya untuk membuat histogram dalam bentuk kamus.

## Idiom Umum dengan Metode `get()`
Penggunaan kamus dengan metode `get()` adalah sebuah idiom yang umum digunakan dalam Python untuk menghitung frekuensi kemunculan. Idiom ini memungkinkan kita untuk menghindari kesalahan jika kunci belum ada dalam kamus, sehingga menghasilkan kode yang lebih aman dan lebih mudah dibaca.

Contoh Kode Python:
```python
def hitung_frekuensi(data):
    frekuensi = {}  # Kamus untuk menyimpan frekuensi kemunculan

    for item in data:
        frekuensi[item] = frekuensi.get(item, 0) + 1

    return frekuensi

# Contoh penggunaan fungsi hitung_frekuensi()
data = ["apel", "apel", "jeruk", "mangga", "jeruk", "apel"]
hasil = hitung_frekuensi(data)
print(hasil)
# Output: {'apel': 3, 'jeruk': 2, 'mangga': 1}
```

Penjelasan Kode:
- Fungsi `hitung_frekuensi()` menerima parameter `data` yang merupakan list yang berisi data contoh.
- Kamus `frekuensi` digunakan untuk menyimpan frekuensi kemunculan.
- Dalam loop `for`, setiap item dalam `data` diperiksa:
  - Metode `get()` digunakan untuk memeriksa apakah item sudah ada dalam kamus.
  - Jika item belum ada dalam kamus, metode `get()` mengembalikan nilai default yaitu 0.
  - Jika item sudah ada dalam kamus, metode `get()` mengembalikan nilai yang terkait dengan kunci tersebut.
  - Kita menambahkan 1 ke nilai yang diperoleh dari metode `get()` dan memperbarui kamus dengan nilai baru.
- Pada akhirnya, fungsi mengembalikan kamus `frekuensi` yang berisi frekuensi kemunculan item dalam `data`.

Dengan menggunakan idiom ini, kita dapat dengan mudah menghitung frekuensi kemunculan suatu hal dalam data tanpa perlu khawatir tentang keberadaan kunci dalam kamus. Metode `get()` memberikan fleksibilitas untuk menangani situasi ketika kunci belum ada, sehingga membuat kode lebih tangguh dan efisien.

Dalam video ini, kita telah menjelaskan penggunaan kamus dalam membuat histogram serta menggunakan metode `get()` untuk menghitung frekuensi kemunculan. Kami juga memberikan contoh kode Python yang menggambarkan penggunaan kamus dan metode `get()`. Semoga penjelasan ini bermanfaat untuk Anda dalam memahami konsep dan praktik penggunaan kamus dalam Python.

# Summary III

- Dalam video ini, dijelaskan bagaimana melakukan looping melalui file teks dan menghitung kata yang paling umum.
- Pengguna diminta untuk mencoba membagi teks menjadi kata-kata, menghitung kemunculan kata, dan menemukan kata yang paling umum.
- Penjelasan tentang looping melalui kamus (dictionary) juga diberikan, dengan contoh sederhana menggunakan kamus.
- Dijelaskan cara mengambil kunci dan nilai dari kamus, serta mengkonversi kunci dan nilai menjadi daftar.
- Ditunjukkan bagaimana menggunakan metode "items" untuk mendapatkan pasangan kunci dan nilai dari kamus.
- Terakhir, dijelaskan bagaimana membaca file, menghitung kata-kata di dalamnya, dan mencari kata yang paling umum menggunakan kamus.

Fakta-fakta penting:
- Video ini menjelaskan cara melakukan looping melalui file teks dan menghitung kata yang paling umum.
- Pengguna diminta untuk membagi teks menjadi kata-kata, menghitung kemunculan kata, dan menemukan kata yang paling umum.
- Dalam looping melalui kamus (dictionary), pengguna dapat mengambil kunci dan nilai menggunakan metode "items".
- Ada tiga metode yang dapat digunakan untuk mengakses kunci, nilai, atau pasangan kunci dan nilai dari kamus: metode "keys", metode "values", dan metode "items".
- Kamus adalah jenis koleksi yang kuat dalam Python yang digunakan untuk menyimpan pasangan kunci-nilai.
- Kamus dapat digunakan untuk menghitung kemunculan kata dalam teks dan menemukan kata yang paling umum.

Topik terkait:
- Looping
- Splitting
- Kamus (dictionary)
- Metode "items"
- Menghitung kata-kata

#Python #Looping #Splitting #Kamus #MetodeItems #MenghitungKata

## [Dictionaries - Counting Words in Text](https://www.youtube.com/watch?v=8DvywoWv6fI&t=17143s)

<iframe width="560" height="315" src="https://www.youtube.com/embed/EEmekKiKG70" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Dalam video ini, kita akan belajar tentang cara melakukan looping melalui file teks, menghitung kemunculan kata-kata, dan menemukan kata yang paling umum. Berikut ini adalah penjelasan dan contoh kode Python yang akan kita bahas.

1. Membagi Teks menjadi Kata-Kata:
   Untuk membagi teks menjadi kata-kata, kita dapat menggunakan metode `split()` pada objek string. Metode ini akan membagi teks berdasarkan spasi defaultnya. Berikut adalah contoh kode untuk membagi teks menjadi kata-kata:

   ```python
   text = "Halo, ini adalah contoh teks untuk dipecah menjadi kata-kata"
   words = text.split()  # Memecah teks menjadi kata-kata
   print(words)  # Output: ['Halo,', 'ini', 'adalah', 'contoh', 'teks', 'untuk', 'dipecah', 'menjadi', 'kata-kata']
   ```

2. Menghitung Kemunculan Kata:
   Untuk menghitung kemunculan kata dalam teks, kita dapat menggunakan kamus (dictionary) dalam Python. Kita akan menggunakan setiap kata sebagai kunci dan menginkrementasi nilainya setiap kali kata tersebut muncul. Berikut adalah contoh kode untuk menghitung kemunculan kata dalam teks:

   ```python
   word_count = {}  # Membuat kamus kosong untuk menghitung kemunculan kata
   for word in words:
       if word in word_count:
           word_count[word] += 1
       else:
           word_count[word] = 1

   print(word_count)
   ```

   Output dari contoh kode di atas akan tergantung pada teks yang digunakan. Misalnya, jika teksnya adalah "Halo, ini adalah contoh teks untuk dipecah menjadi kata-kata," outputnya akan menjadi:

   ```
   {'Halo,': 1, 'ini': 1, 'adalah': 1, 'contoh': 1, 'teks': 1, 'untuk': 1, 'dipecah': 1, 'menjadi': 1, 'kata-kata': 1}
   ```

   Dalam contoh ini, setiap kata hanya muncul satu kali, jadi nilai-nilai dalam kamus semuanya adalah 1.

3. Menemukan Kata yang Paling Umum:
   Untuk menemukan kata yang paling umum, kita dapat menggunakan metode `items()` pada kamus. Metode ini mengembalikan daftar berisi pasangan kunci dan nilai dari kamus. Kita kemudian dapat menggunakan fungsi `max()` untuk mencari pasangan dengan nilai terbesar. Berikut adalah contoh kode untuk menemukan kata yang paling umum:

   ```python
   most_common_word = max(word_count.items(), key=lambda x: x[1])
   print("Kata yang paling umum:", most_common_word[0])
   print("Jumlah kemunculan:", most_common_word[1])
   ```

   Outputnya akan menunjukkan kata yang paling umum dan jumlah kemunculannya berdasarkan kamus yang telah kita buat sebelumnya.

   Contoh output:

   ```
   Kata yang paling umum: Halo,
   Jumlah kemunculan: 1
   ```

Dengan menggunakan metode-metode tersebut, kita dapat melakukan looping dengan menggunakan metode-metode tersebut, kita dapat melakukan looping melalui file teks, menghitung kata-kata di dalamnya, dan mencari kata yang paling umum. Berikut adalah contoh lengkap yang menggabungkan langkah-langkah tersebut:

```python
# Membaca file teks
file_path = "teks.txt"
with open(file_path, "r") as file:
    text = file.read()

# Memecah teks menjadi kata-kata
words = text.split()

# Menghitung kemunculan kata dalam teks
word_count = {}
for word in words:
    if word in word_count:
        word_count[word] += 1
    else:
        word_count[word] = 1

# Menemukan kata yang paling umum
most_common_word = max(word_count.items(), key=lambda x: x[1])

# Menampilkan hasil
print("Kata yang paling umum:", most_common_word[0])
print("Jumlah kemunculan:", most_common_word[1])
```

Pastikan kamu memiliki file teks yang ingin kamu proses, dan sesuaikan `file_path` dengan path file teks yang kamu miliki. Setelah itu, jalankan kode tersebut, dan outputnya akan menampilkan kata yang paling umum dan jumlah kemunculannya dalam teks tersebut.

Contoh output:

```
Kata yang paling umum: contoh
Jumlah kemunculan: 3
```

Dalam contoh ini, kata "contoh" muncul sebanyak 3 kali dalam teks yang dibaca dari file. Kamu dapat mengubah teks atau menggunakan file teks yang berbeda untuk melihat hasil yang berbeda pula.

Dengan cara ini, kamu dapat melakukan looping melalui file teks, menghitung kata-kata di dalamnya, dan menemukan kata yang paling umum menggunakan kamus.
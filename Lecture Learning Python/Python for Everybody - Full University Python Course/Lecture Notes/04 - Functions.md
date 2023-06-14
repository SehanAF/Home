# ⭐️ Course Contents ⭐️

⌨️ ([1:52:48](https://www.youtube.com/watch?v=8DvywoWv6fI&t=6768s)) Functions 
⌨️ ([2:03:02](https://www.youtube.com/watch?v=8DvywoWv6fI&t=7382s)) Functions - Functions of our own 

# Slides 

![[Pythonlearn-04-Functions.pdf]]


# [Functions](https://www.youtube.com/watch?v=8DvywoWv6fI&t=6768s)

1. Fungsi digunakan untuk menyimpan dan menggunakan kembali kode.
2. Kata kunci "def" digunakan untuk mendefinisikan fungsi dalam Python.
3. Pernyataan "def" tidak menjalankan kode apa pun, tetapi mengingat kode tersebut untuk digunakan di kemudian hari.
4. Fungsi dipanggil dengan menggunakan namanya yang diikuti dengan tanda kurung.
5. Memanggil fungsi akan menjalankan kode di dalam fungsi tersebut.
6.  Fungsi dapat didefinisikan satu kali dan digunakan beberapa kali.
7. Fungsi bawaan dalam Python termasuk print(), max(), min(), type(), float(), dan int().
8. Fungsi dapat memiliki argumen yang diberikan kepadanya.
9. Fungsi memiliki fase pendefinisian (di mana kode diingat) dan fase pemanggilan (di mana kode dieksekusi).
10. Nilai balik dari sebuah fungsi dapat ditetapkan ke sebuah variabel.
11. Fungsi dapat digunakan dalam ekspresi dan berpartisipasi dalam perhitungan.
12. Fungsi bawaan sudah ditentukan sebelumnya dalam Python dan dapat digunakan tanpa mendefinisikannya.
13. Fungsi dapat digunakan untuk mengonversi antara tipe data yang berbeda, seperti string ke integer atau float.
14. Anda harus berhati-hati saat mengonversi tipe data untuk menghindari kesalahan.
15. Topik selanjutnya yang akan dibahas adalah membuat fungsi kustom.

Berikut adalah penjelasan lebih rinci mengenai Function pada Python serta contoh kode Python yang terkait:

1. Pengantar tentang Fungsi:
   - Fungsi digunakan untuk menyimpan dan menggunakan kembali blok kode.
   - Tujuan penggunaan fungsi adalah agar kita tidak perlu menulis ulang kode yang sama jika akan digunakan lebih dari satu kali.
   - Dalam pemrograman, menghindari pengulangan kode sangat penting karena jika ada kesalahan di dalam kode tersebut, kita harus mencari dan memperbaiki semua tempat yang menggunakan kode yang sama.
   - Dengan menggunakan fungsi, kita dapat mengumpulkan kode-kode tersebut di satu tempat, kemudian memanggilnya kembali untuk digunakan ulang.

2. Menggunakan Fungsi di Python:
   - Di Python, kita menggunakan kata kunci "def" untuk mendefinisikan sebuah fungsi.
   - Sebuah fungsi dimulai dengan kata kunci "def", diikuti dengan nama fungsi yang kita pilih, tanda kurung, dan titik dua.
   - Setelah itu, kita menuliskan blok kode fungsi dengan indentasi.
   - Setelah blok kode selesai, indentasi dihilangkan, dan itu menandakan akhir dari fungsi.
   - Pada tahap ini, definisi fungsi hanya menyimpan kode dan tidak menjalankannya.

Contoh Kode:
```python
def hello():
    print("Halo, selamat datang!")

hello()  # Memanggil fungsi hello()
```

Output:
```
Halo, selamat datang!
```

3. Memanggil Fungsi:
   - Memanggil fungsi berarti menjalankan kode di dalam fungsi.
   - Ketika kita memanggil fungsi, kode di dalamnya dieksekusi dan menghasilkan output (jika ada).
   - Dalam contoh sebelumnya, setelah mendefinisikan fungsi "hello()", kita memanggilnya dengan menuliskan "hello()".

4. Argumen dalam Fungsi:
   - Fungsi dapat menerima argumen sebagai input.
   - Argumen adalah nilai yang diberikan ke fungsi ketika memanggilnya.
   - Argumen digunakan dalam fungsi untuk melakukan operasi atau menghasilkan output yang berbeda berdasarkan nilai yang diberikan.
   - Argumen ditempatkan di dalam tanda kurung saat mendefinisikan fungsi.

Contoh Kode:
```python
def sapa(nama):
    print("Halo, " + nama + "! Selamat datang!")

sapa("John")  # Memanggil fungsi sapa() dengan argumen "John"
sapa("Sarah")  # Memanggil fungsi sapa() dengan argumen "Sarah"
```

Output:
```
Halo, John! Selamat datang!
Halo, Sarah! Selamat datang!
```

5. Nilai Kembali dari Fungsi:
   - Fungsi dapat mengembalikan nilai sebagai hasil operasi yang dilakukan di dalamnya.
   - Nilai kembali diperoleh menggunakan kata kunci "return" di dalam fungsi.
   - Nilai kembali ini dapat ditangkap dan digunakan dalam kode pemanggil.

Contoh Kode:
```python
def tambah(a, b):
hasil = a + b
return hasil

total = tambah(3, 5)  # Memanggil fungsi tambah() dan menampung hasilnya di variabel total
```

6. Mengembalikan Nilai dari Fungsi:
    - Ketika sebuah fungsi memiliki pernyataan "return", itu berarti fungsi tersebut mengembalikan nilai.
    - Nilai kembali ini dapat ditangkap dan digunakan dalam kode pemanggil.
    - Dalam contoh sebelumnya, fungsi "tambah()" mengembalikan hasil penjumlahan dari dua argumen yang diberikan.
    - Hasil penjumlahan disimpan di dalam variabel "total" setelah memanggil fungsi "tambah()".

Contoh Kode:
```python
def tambah(a, b):
    hasil = a + b
    return hasil

total = tambah(3, 5)  # Memanggil fungsi tambah() dan menampung hasilnya di variabel total
print(total)  # Output: 8
```

7. Argumen Opsi dalam Fungsi:
   - Dalam Python, kita dapat memberikan nilai default untuk argumen dalam fungsi.
   - Argumen dengan nilai default adalah argumen yang memiliki nilai awal yang ditentukan di dalam definisi fungsi.
   - Jika argumen tersebut tidak diberikan nilai saat pemanggilan fungsi, nilai default akan digunakan.
   - Ini memberikan fleksibilitas bagi pemanggil fungsi untuk memberikan argumen opsional atau menggunakan nilai default.

Contoh Kode:
```python
def sapa(nama=""):
    if nama:
        print("Halo, " + nama + "! Selamat datang!")
    else:
        print("Halo! Selamat datang!")

sapa()  # Memanggil fungsi sapa() tanpa argumen
sapa("John")  # Memanggil fungsi sapa() dengan argumen "John"
```

Output:
```
Halo! Selamat datang!
Halo, John! Selamat datang!
```

8. Fungsi Rekursif:
   - Fungsi rekursif adalah fungsi yang memanggil dirinya sendiri.
   - Hal ini dapat berguna untuk menyelesaikan masalah yang dapat dipecahkan secara rekursif.
   - Dalam fungsi rekursif, terdapat kondisi berhenti (base case) yang menentukan kapan fungsi harus berhenti memanggil dirinya.
   - Jika tidak ada kondisi berhenti yang tepat, fungsi akan memanggil dirinya secara terus-menerus dan menyebabkan stack overflow.

Contoh Kode:
```python
def faktorial(n):
    if n == 0:
        return 1
    else:
        return n * faktorial(n - 1)

hasil = faktorial(5)  # Memanggil fungsi faktorial() untuk menghitung faktorial 5
print(hasil)  # Output: 120
```

9. Fungsi Bawaan dalam Python:
   - Python menyediakan sejumlah besar fungsi bawaan (built-in functions) yang telah didefinisikan di dalam bahasa.
   - Fungsi-fungsi ini dapat digunakan langsung tanpa perlu mendefinisikan mereka terlebih dahulu.
   - Contoh beberapa fungsi bawaan yang umum digunakan di Python adalah `print()`, `len()`, `input()`, `range()`, dan lain-lain.
   - Kita dapat menggunakan fungsi bawaan ini dengan menyebutkan namanya dan memberikan argumen yang sesuai.
    - Fungsi `print()` digunakan untuk mencetak output ke konsol.
    - Fungsi `len()` digunakan untuk mengembalikan panjang (jumlah elemen) dari suatu objek.
    - Fungsi `input()` digunakan untuk mengambil input dari pengguna melalui konsol.
    - Fungsi `range()` digunakan untuk membuat urutan bilangan.

Contoh Kode:
```python
# Fungsi print()
print("Halo, dunia!")

# Fungsi len()
nama = "John Doe"
panjang_nama = len(nama)
print("Panjang nama:", panjang_nama)

# Fungsi input()
umur = input("Berapa umurmu? ")
print("Umur:", umur)

# Fungsi range()
for angka in range(1, 6):
    print(angka)
```

Output:
```
Halo, dunia!
Panjang nama: 8
Berapa umurmu? 25
Umur: 25
1
2
3
4
5
```

10. Modul dan Fungsi Modul:
   - Modul adalah file Python yang berisi definisi dan kode yang dapat digunakan dalam program Python lainnya.
   - Fungsi-fungsi di dalam modul dapat diimpor dan digunakan dalam program utama.
   - Dalam Python, kita dapat menggunakan pernyataan `import` untuk mengimpor modul dan menggunakan fungsi-fungsi yang ada di dalamnya.

Contoh Kode (contoh modul math):
```python
import math

# Menggunakan fungsi-fungsi modul math
x = math.sqrt(25)
y = math.sin(0.5)

print("Akar kuadrat dari 25:", x)
print("Sine dari 0.5:", y)
```

Output:
```
Akar kuadrat dari 25: 5.0
Sine dari 0.5: 0.479425538604203
```

Tentu, berikut adalah kelanjutan penjelasan tentang fungsi dalam Python:

11. Membuat Fungsi Kustom:
   - Selain menggunakan fungsi bawaan, kita juga dapat membuat fungsi kustom sesuai kebutuhan kita.
   - Fungsi kustom dibuat dengan menggunakan pernyataan `def` diikuti dengan nama fungsi dan tanda kurung.
   - Jika fungsi memiliki argumen, argumen tersebut ditempatkan di dalam tanda kurung.
   - Selanjutnya, blok kode fungsi didefinisikan dengan indentasi.

Contoh Kode:
```python
# Definisi fungsi kustom
def sapa():
    print("Halo, selamat datang!")

# Memanggil fungsi kustom
sapa()
```

Output:
```
Halo, selamat datang!
```

12. Argumen dalam Fungsi:
   - Argumen adalah nilai yang diberikan kepada fungsi saat memanggilnya.
   - Fungsi dapat memiliki argumen yang diperlukan atau opsional.
   - Argumen ditempatkan di dalam tanda kurung saat mendefinisikan dan memanggil fungsi.

Contoh Kode:
```python
# Definisi fungsi dengan argumen
def sapa(nama):
    print("Halo,", nama, "! Selamat datang!")

# Memanggil fungsi dengan argumen
sapa("John")
sapa("Jane")
```

Output:
```
Halo, John! Selamat datang!
Halo, Jane! Selamat datang!
```

13. Nilai Kembalian dalam Fungsi:
   - Fungsi dapat mengembalikan nilai dengan menggunakan pernyataan `return`.
   - Nilai kembalian dapat digunakan untuk menyimpan hasil perhitungan atau digunakan dalam ekspresi lain.

Contoh Kode:
```python
# Definisi fungsi dengan nilai kembalian
def kuadrat(x):
    return x * x

# Menggunakan nilai kembalian
hasil = kuadrat(5)
print("Hasil kuadrat:", hasil)
```

Output:
```
Hasil kuadrat: 25
```

14. Fungsi Rekursif:
   - Fungsi rekursif adalah fungsi yang memanggil dirinya sendiri dalam blok kode.
   - Fungsi rekursif biasanya digunakan untuk menyelesaikan masalah yang dapat dibagi menjadi submasalah yang lebih kecil.

Contoh Kode (faktorial menggunakan fungsi rekursif):
```python
# Definisi fungsi rekursif
def faktorial(n):
    if n == 0:
        return 1
    else:
        return n * faktorial(n-1)

# Menggunakan fungsi rekursif
hasil = faktorial(5)
print("Faktorial dari 5:", hasil)
```

Output:
```
Faktorial dari 5: 120
```

15. Argumen Default:
   - Argumen default adalah nilai yang ditentukan sebelumnya untuk argumen dalam definisi fungsi.
   - Jika argumen tidak diberikan saat pemanggilan fungsi, nilai default akan digunakan.
   - Argumen default dapat membuat fungsi lebih fleksibel dalam penggunaannya.

Contoh Kode:
```python
# Definisi fungsi dengan argumen default
def sapa(nama=""):
    if nama == "":
        print("Halo, siapa namamu?")
    else:
        print("Halo,", nama, "! Selamat datang!")

# Memanggil fungsi dengan dan tanpa argumen
sapa()
sapa("John")
```

Output:
```
Halo, siapa namamu?
Halo, John! Selamat datang!
```

16. Fungsi Lambda:
   - Fungsi lambda adalah fungsi anonim sederhana yang dapat didefinisikan dalam satu baris kode.
   - Fungsi lambda biasanya digunakan dalam situasi di mana fungsi sederhana diperlukan dengan cepat.

Contoh Kode:
```python
# Definisi fungsi lambda
kali = lambda x, y: x * y

# Memanggil fungsi lambda
hasil = kali(3, 4)
print("Hasil perkalian:", hasil)
```

Output:
```
Hasil perkalian: 12
```

17. Fungsi Bawaan (Built-in Functions):
   - Python menyediakan banyak fungsi bawaan yang dapat digunakan tanpa perlu mendefinisikan sendiri.
   - Contoh beberapa fungsi bawaan: `print()`, `len()`, `max()`, `min()`, dll.
   - Fungsi bawaan sangat berguna untuk melakukan tugas umum dalam pemrograman.

Contoh Kode:
```python
# Menggunakan fungsi bawaan
nilai = [4, 8, 2, 6, 1]
panjang = len(nilai)
nilai_terbesar = max(nilai)
nilai_terkecil = min(nilai)

print("Panjang list:", panjang)
print("Nilai terbesar:", nilai_terbesar)
print("Nilai terkecil:", nilai_terkecil)
```

Output:
```
Panjang list: 5
Nilai terbesar: 8
Nilai terkecil: 1
```



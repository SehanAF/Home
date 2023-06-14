# ⭐️ Course Contents ⭐️

⌨️ ([1:26:00](https://www.youtube.com/watch?v=8DvywoWv6fI&t=5160s)) Conditional Execution 
⌨️ ([1:39:13](https://www.youtube.com/watch?v=8DvywoWv6fI&t=5953s)) Conditional Execution - More Conditional Structures 

# Slides

![[Pythonlearn-03-Conditional.pdf]]

# [Eksekusi Kondisional dalam Python](https://www.youtube.com/watch?v=8DvywoWv6fI&t=5160s)

1. Pengenalan bab tiga, Eksekusi Bersyarat.
2. Pernyataan if digunakan untuk membuat Python membuat keputusan.
3. Pernyataan if memiliki kata kunci "if" dan sebuah pertanyaan yang diajukan.
4. Jika pertanyaan bernilai benar, baris kode di dalam blok terindentasi akan dieksekusi.
5. Python menyediakan beberapa operator perbandingan, seperti kurang dari, kurang dari sama dengan, sama dengan, lebih dari sama dengan, lebih dari, dan tidak sama dengan.
6. Contoh-contoh perbandingan menggunakan operator-operator tersebut.
7. Penggunaan indentasi (penggeseran baris ke kanan) penting dalam Python untuk menandai blok kode yang terkait dengan pernyataan if.
8. Kesalahan indentasi dapat menyebabkan kesalahan sintaks.
9. Setiap peningkatan indentasi menandakan awal blok, sedangkan pengurangan indentasi menandakan akhir blok.
10. Contoh blok bersarang dan penggunaan indentasi ganda.
11. Konsep if, then, else digunakan untuk bercabang dalam pengambilan keputusan.
12. Hanya satu dari dua cabang yang akan dieksekusi, tergantung pada hasil pertanyaan if.
13. Penggunaan sintaks if, then, else dalam Python.
14. Contoh penggunaan if, then, else untuk mengambil keputusan yang bercabang.

Berikut adalah penjelasan lebih rinci mengenai kondisional pada Python serta contoh kode Python yang terkait:

1. Pengenalan pernyataan if
   - Pernyataan if memungkinkan Anda untuk menjalankan blok kode berdasarkan kondisi tertentu.
   - Sintaks: `if kondisi:`
   
2. Langkah-langkah Kondisional dan Penggunaan Pernyataan if
   - Anda dapat menentukan langkah-langkah yang berbeda untuk dieksekusi berdasarkan kondisi yang berbeda menggunakan pernyataan if.
   - Contoh:
     ```python
     x = 5
     if x > 0:
         print("x adalah bilangan positif")
     ```

3. Operator Perbandingan: kurang dari, kurang dari sama dengan, sama dengan, lebih dari sama dengan, lebih dari, tidak sama
   - Operator perbandingan digunakan untuk membandingkan nilai dan mengevaluasi kondisi.
   - Contoh operator perbandingan:
     - Kurang dari: `<`
     - Kurang dari sama dengan: `<=`
     - Sama dengan: `==`
     - Lebih dari sama dengan: `>=`
     - Lebih dari: `>`
     - Tidak sama: `!=`

4. Contoh kondisi benar menggunakan operator perbandingan
   - Operator perbandingan dapat digunakan dalam pernyataan if untuk memeriksa apakah suatu kondisi benar.
   - Contoh:
     ```python
     usia = 20
     if usia >= 18:
         print("Anda adalah dewasa")
     ```

5. Indentasi dan Blok dalam Python
   - Indentasi digunakan untuk mendefinisikan blok kode dalam Python.
   - Semua pernyataan dalam satu blok harus di-indentasi pada level yang sama.

6. Kesalahan sintaks karena indentasi yang salah
   - Indentasi yang salah dapat menyebabkan kesalahan sintaks dalam Python.
   - Contoh:
     ```python
     if x > 0:
     print("x adalah bilangan positif")  # Indentasi salah
     ```

7. Penggunaan spasi bukan tab untuk indentasi
   - Disarankan menggunakan spasi untuk indentasi daripada tab untuk menghindari kesalahan indentasi.

8. Blok-blok bertingkat dan pernyataan if bersarang
   - Blok dapat bertingkat di dalam blok lain dalam Python.
   - Ini memungkinkan untuk eksekusi kondisional yang lebih kompleks.
   - Contoh:
     ```python
     if x > 0:
         if x < 10:
             print("x berada antara 0 dan 10")
     ```

9. Pernyataan if-else dengan dua cabang
   - Sintaks if-else memungkinkan dua cabang kode dieksekusi berdasarkan kondisi.
   - Sintaks:
     ```
     if kondisi:
         # Kode yang dieksekusi jika kondisi benar
     else:
         # Kode yang dieksekusi jika kondisi salah
     ```

10. Eksekusi blok if atau blok else
    - Berdasarkan kondisi, baik blok if atau blok else akan dieksekusi, tetapi tidak keduanya.

11. Menggambar blok untuk memvisualisasikan struktur kode
   - Memvisualisasikan struktur kode menggunakan indentasi dapat membantu memahami alur eksekusi.
   - Contoh:
     ```python
     if kondisi1:
         if kondisi2:
             # Blok kode A
         else:
             # Blok kode B
     else:
         # Blok kode C
     ```
12. Penjelasan tentang sintaks if-else dan cabang-cabangnya
    - Sintaks if-else memberikan cara untuk menangani jalur alternatif dalam eksekusi kode.
    - Cabang if akan dieksekusi jika kondisinya benar, jika tidak, cabang else akan dieksekusi.

1. Contoh eksekusi pernyataan if-else
    - Contoh penggunaan pernyataan if-else untuk mengontrol eksekusi kode.
    - Contoh:
      ```python
      x = 10
      if x > 0:
          print("Positif")
      else:
          print("Non-positif")
      ```
    - Output: "Positif"

14. Menambahkan kondisi lanjutan dengan elif
   - Dalam beberapa kasus, kita perlu menambahkan kondisi lanjutan setelah if dan sebelum else menggunakan elif.
   - Syntax:
     ```
     if kondisi1:
         # Kode yang dieksekusi jika kondisi1 benar
     elif kondisi2:
         # Kode yang dieksekusi jika kondisi2 benar
     else:
         # Kode yang dieksekusi jika semua kondisi salah
     ```

   - Contoh:
     ```python
     x = 10
     if x > 0:
         print("Positif")
     elif x == 0:
         print("Nol")
     else:
         print("Negatif")
     ```
     - Output jika x = 10: "Positif"

15. Kombinasi kondisi dengan operator logika
   - Kita dapat mengombinasikan beberapa kondisi dengan menggunakan operator logika seperti and dan or.
   - Operator and: mengembalikan True jika kedua kondisi benar.
   - Operator or: mengembalikan True jika salah satu kondisi benar.
   - Contoh:
     ```python
     x = 10
     if x > 0 and x < 100:
         print("Antara 0 dan 100")
     ```
     - Output jika x = 10: "Antara 0 dan 100"

16. Menggunakan statement if dalam perulangan
   - Statement if dapat digunakan dalam perulangan untuk melakukan aksi berdasarkan kondisi tertentu.
   - Contoh:
     ```python
     for i in range(5):
         if i % 2 == 0:
             print(i, "adalah angka genap")
     ```
     - Output: 0 adalah angka genap, 2 adalah angka genap, 4 adalah angka genap

17. Menggabungkan kondisi dengan operator in
   - Operator in digunakan untuk memeriksa apakah suatu nilai ada dalam suatu rangkaian atau koleksi.
   - Contoh:
     ```python
     fruits = ["apel", "pisang", "jeruk"]
     if "apel" in fruits:
         print("Apel ada dalam list buah")
     ```
     - Output: "Apel ada dalam list buah"

18. Menulis kondisi yang kompleks
   - Kita dapat menulis kondisi yang lebih kompleks dengan menggabungkan operator perbandingan, operator logika, dan operator in.
   - Contoh:
     ```python
     x = 15
     if (x > 0 and x < 10) or x == 20:
         print("Kondisi kompleks terpenuhi")
     ```
     - Output jika x = 15: "Kondisi kompleks terpenuhi"

# [More Conditional Structures](https://www.youtube.com/watch?v=8DvywoWv6fI&t=5953s) 

1. Pengenalan penanganan kesalahan (error handling)
2. Pernyataan `try-except` dalam Python
3. Menangani kesalahan dengan blok `except`
4. Menangani kesalahan spesifik dengan menggunakan tipe kesalahan
5. Menangani kesalahan umum dengan menggunakan tipe `Exception`
6. Menampilkan pesan kesalahan
7. Menangani beberapa tipe kesalahan sekaligus
8. Menambahkan blok `else` setelah blok `try-except`
9. Menggunakan blok `finally` untuk membersihkan sumber daya
10. Menampilkan traceback (jejak jejak) kesalahan
11. Contoh penggunaan `try-except` dengan satu baris kode
12. Contoh dunia nyata penggunaan masukan pengguna dan penanganan kesalahan

Berikut adalah penjelasan lebih rinci mengenai kondisional pada Python serta contoh kode Python yang terkait:

1. Pernyataan multi-arah (`multi-way branch`) adalah pernyataan yang memungkinkan pemilihan salah satu dari beberapa kondisi. Biasanya, pernyataan ini menggunakan kata kunci `elif` untuk mengecek kondisi tambahan setelah kondisi utama tidak terpenuhi.

Contoh kode:
```python
x = 5
if x < 2:
    print("x kurang dari 2")
elif x < 10:
    print("x kurang dari 10")
elif x < 20:
    print("x kurang dari 20")
else:
    print("x lebih besar atau sama dengan 20")
```
Output:
```
x kurang dari 10
```

2. Kondisi di pernyataan multi-arah diperiksa secara berurutan. Ketika satu kondisi terpenuhi, blok kode yang terkait akan dijalankan, dan pernyataan multi-arah akan segera keluar. Kondisi yang tersisa tidak akan diperiksa.

Contoh kode:
```python
x = 15
if x < 10:
    print("x kurang dari 10")
elif x < 20:
    print("x kurang dari 20")
elif x < 30:
    print("x kurang dari 30")
else:
    print("x lebih besar atau sama dengan 30")
```
Output:
```
x kurang dari 20
```

3. Anda dapat menggunakan lebih dari satu pernyataan `elif` dalam pernyataan multi-arah. Pastikan untuk memperhatikan urutan kondisi karena pernyataan akan diperiksa dari atas ke bawah. Kondisi pertama yang terpenuhi akan dijalankan, dan kondisi lainnya akan diabaikan.

Contoh kode:
```python
x = 25
if x < 10:
    print("x kurang dari 10")
elif x < 20:
    print("x kurang dari 20")
elif x < 30:
    print("x kurang dari 30")
elif x < 40:
    print("x kurang dari 40")
else:
    print("x lebih besar atau sama dengan 40")
```
Output:
```
x kurang dari 30
```

4. Anda juga dapat menggunakan pernyataan `else` sebagai blok penanganan jika tidak ada kondisi sebelumnya yang terpenuhi.

Contoh kode:
```python
x = 50
if x < 10:
    print("x kurang dari 10")
elif x < 20:
    print("x kurang dari 20")
else:
    print("x lebih besar atau sama dengan 20")
```
Output:
```
x lebih besar atau sama dengan 20
```

5. Dalam situasi tertentu, Anda mungkin tidak ingin memiliki blok `else`. Jika tidak ada kondisi yang terpenuhi, tidak ada blok yang dijalankan.

Contoh kode:
```python
x = 50
if x < 10:
    print("x kurang dari 10")
elif x < 20:
    print("x kurang dari 20")
elif x < 30:
    print("x kurang dari 30")
```
Output: (tanpa output)

6. Pernyataan `try` dan `except` digunakan untuk menangani pengecualian (`exception`) atau kesalahan yang mungkin terjadi saat menjalankan suatu blok kode. Dengan menggunakan pernyataan ini, Anda dapat menjalankan blok kode yang mungkin memunculkan kesalahan dan menangani kesalahan tersebut dengan cara yang sesuai.

Contoh kode:
```python
try:
    x = 10 / 0  # Operasi pembagian oleh nol akan memunculkan ZeroDivisionError
    print(x)
except ZeroDivisionError:
    print("Terjadi kesalahan pembagian oleh nol")
```
Output:
```
Terjadi kesalahan pembagian oleh nol
```

Dalam contoh tersebut, blok kode di dalam `try` mencoba untuk membagi angka 10 dengan 0. Ini akan memunculkan `ZeroDivisionError` karena tidak mungkin melakukan pembagian oleh nol. Namun, daripada menjalankan keseluruhan program, program akan melompat ke blok `except` yang sesuai dengan jenis kesalahan yang muncul. Di sini, kita menangani `ZeroDivisionError` dengan mencetak pesan kesalahan yang sesuai.

Anda juga dapat menggunakan blok `except` tanpa menentukan jenis kesalahan tertentu. Ini akan menangani semua jenis kesalahan yang mungkin terjadi.

Contoh kode:
```python
try:
    x = 10 / 0
    print(x)
except:
    print("Terjadi kesalahan")
```
Output:
```
Terjadi kesalahan
```

Anda juga dapat menggunakan blok `else` setelah blok `try-except`. Blok `else` akan dijalankan hanya jika tidak ada kesalahan yang terjadi di dalam blok `try`.

Contoh kode:
```python
try:
    x = 10 / 2
except ZeroDivisionError:
    print("Terjadi kesalahan pembagian oleh nol")
else:
    print("Hasil pembagian:", x)
```
Output:
```
Hasil pembagian: 5.0
```

Dalam contoh ini, karena tidak ada kesalahan saat melakukan pembagian, maka blok `else` dijalankan dan hasil pembagian dicetak.

7. Selain `except`, Anda juga dapat menggunakan blok `finally` setelah blok `try-except`. Blok `finally` akan dijalankan selalu, baik terjadi kesalahan maupun tidak.

Contoh kode:
```python
try:
    x = 10 / 2
    print("Hasil pembagian:", x)
except ZeroDivisionError:
    print("Terjadi kesalahan pembagian oleh nol")
finally:
    print("Pernyataan finally")
```
Output:
```
Hasil pembagian: 5.0
Pernyataan finally
```

Dalam contoh ini, blok `finally` akan selalu dijalankan setelah blok `try-except`, tanpa memperdulikan apakah terjadi kesalahan atau tidak.

Itu adalah penjelasan lebih rinci mengenai penggunaan pernyataan `try`, `except`, `else`, dan `finally` dalam menangani pengecualian di Python.

8. Penanganan kode yang dapat menyebabkan traceback:
Ketika Anda menjalankan suatu blok kode, terkadang ada kemungkinan kode tersebut menyebabkan traceback atau kesalahan. Dalam situasi-situasi ini, Anda dapat menggunakan pernyataan `try-except` untuk menangani kesalahan dan mencegah program berhenti secara tiba-tiba.

Contoh kode:
```python
try:
    # Kode yang mungkin menyebabkan traceback
    x = int(input("Masukkan sebuah angka: "))
    hasil = 10 / x
    print("Hasil pembagian:", hasil)
except:
    print("Terjadi kesalahan")
```

Dalam contoh di atas, kita mengambil input pengguna menggunakan fungsi `input()`, kemudian mencoba melakukan pembagian dengan angka yang diinputkan. Jika pengguna memasukkan angka 0, maka akan terjadi pembagian oleh nol dan `ZeroDivisionError` akan muncul. Namun, dengan menggunakan blok `try-except`, program tidak akan berhenti secara tiba-tiba saat traceback terjadi. Sebaliknya, pesan "Terjadi kesalahan" akan dicetak.

9. Mengabaikan blok `except` jika tidak ada kesalahan:
Dalam beberapa kasus, Anda mungkin ingin menjalankan beberapa kode secara normal tanpa menangani kesalahan yang mungkin terjadi. Untuk melakukan ini, Anda dapat menggunakan pernyataan `try-except` tanpa blok `except`.

Contoh kode:
```python
try:
    # Kode yang tidak mungkin menyebabkan kesalahan
    x = 10 / 2
    print("Hasil pembagian:", x)
except:
    pass
```

Dalam contoh di atas, kita membagi angka 10 dengan 2, yang tidak akan menyebabkan kesalahan pembagian oleh nol. Namun, kita menggunakan blok `try-except` tanpa blok `except` untuk mengabaikan kesalahan apa pun yang mungkin terjadi. Dalam hal ini, program akan menjalankan pernyataan `print` tanpa mencetak pesan kesalahan.

10. Penggunaan `try-except` dengan hati-hati:
Ketika menggunakan pernyataan `try-except`, penting untuk menentukan jenis kesalahan yang ingin ditangani dengan tepat. Jika Anda menangkap semua jenis kesalahan secara umum, Anda mungkin tidak akan tahu jenis kesalahan yang sebenarnya terjadi, sehingga membuat debugging lebih sulit. Sebaiknya, spesifikasikan jenis kesalahan yang ingin Anda tangani untuk memberikan informasi yang lebih akurat.

Contoh kode yang tidak disarankan:
```python
try:
    # Kode yang mungkin menyebabkan traceback
    x = int(input("Masukkan sebuah angka: "))
    hasil = 10 / x
    print("Hasil pembagian:", hasil)
except Exception:
    print("Terjadi kesalahan")
```

Dalam contoh di atas, kita menggunakan blok `except Exception` yang menangani semua jenis kesalahan. Hal ini dapat menyebabkan informasi kesalahan yang tidak spesifik dan membuat debugging menjadi sulit. Sebaiknya, gunakan jenis kesalahan yang tepat, seperti `ValueError`, `ZeroDivisionError`, atau jenis kesalahan lain yang relevan.

11. Contoh penggunaan `try-except` dengan satu baris kode:
Pada beberapa kasus sederhana, Anda dapat menggunakan pernyataan `try-except` dalam satu baris kode untuk menangani kesalahan yang mungkin terjadi.

Contoh kode:
```python
hasil = None
try: hasil = 10 / x
except: pass
```

Dalam contoh di atas, kita mencoba melakukan pembagian 10 dengan nilai `x`. Jika terjadi kesalahan pembagian oleh nol, pernyataan `except` akan diabaikan dan variabel `hasil` tetap bernilai `None`. Ini adalah contoh sederhana di mana pernyataan `try-except` digunakan dalam satu baris kode untuk menangani kesalahan.

12. Contoh dunia nyata penggunaan masukan pengguna dan penanganan kesalahan:
Dalam banyak kasus, kita perlu mengambil masukan dari pengguna dan memastikan bahwa masukan tersebut valid. Dalam contoh berikut, kita akan mengambil masukan pengguna untuk membagi dua angka dan menangani kesalahan yang mungkin terjadi.

Contoh kode:
```python
try:
    num1 = float(input("Masukkan angka pertama: "))
    num2 = float(input("Masukkan angka kedua: "))
    hasil = num1 / num2
    print("Hasil pembagian:", hasil)
except ValueError:
    print("Masukan harus berupa angka")
except ZeroDivisionError:
    print("Pembagian oleh nol tidak diizinkan")
except Exception as e:
    print("Terjadi kesalahan:", str(e))
```

Dalam contoh di atas, kita menggunakan fungsi `float()` untuk mengubah masukan pengguna menjadi bilangan pecahan. Jika masukan pengguna tidak dapat dikonversi menjadi angka, `ValueError` akan terjadi. Jika pengguna memasukkan angka 0 sebagai angka kedua, `ZeroDivisionError` akan terjadi. Jika terjadi kesalahan lain yang tidak terduga, blok `except Exception` akan menangkapnya dan mencetak pesan kesalahan yang diberikan.

Ini adalah contoh nyata penggunaan `try-except` untuk mengambil masukan pengguna, memvalidasi masukan, dan menangani berbagai jenis kesalahan yang mungkin terjadi.

# Summary 

1. Operator Perbandingan: Operator perbandingan digunakan untuk membandingkan nilai antara dua variabel atau ekspresi. Contoh penggunaan operator perbandingan adalah:

```python
x = 5
y = 10

if x < y:
    print("x lebih kecil dari y")
```

2. Indentasi: Indentasi digunakan dalam Python untuk menandai blok kode yang terkait. Indentasi yang konsisten penting untuk menjaga struktur dan kejelasan program. Contoh penggunaan indentasi:

```python
x = 5

if x > 0:
    print("x adalah bilangan positif")
else:
    print("x adalah bilangan negatif")
```

3. Keputusan Satu Arah: Keputusan satu arah, juga dikenal sebagai pernyataan `if`, digunakan untuk melakukan tindakan jika suatu kondisi terpenuhi. Contoh penggunaan keputusan satu arah:

```python
x = 5

if x > 0:
    print("x adalah bilangan positif")
```

4. Keputusan Dua Arah (if dan else): Keputusan dua arah digunakan untuk melakukan tindakan berbeda tergantung pada apakah suatu kondisi terpenuhi atau tidak. Contoh penggunaan keputusan dua arah:

```python
x = 5

if x > 0:
    print("x adalah bilangan positif")
else:
    print("x adalah bilangan negatif")
```

5. Keputusan Bertingkat: Keputusan bertingkat, juga dikenal sebagai keputusan bersarang, digunakan ketika ada beberapa kondisi yang harus dipertimbangkan secara berurutan. Contoh penggunaan keputusan bertingkat:

```python
x = 5
y = 10

if x > 0:
    print("x adalah bilangan positif")
elif x < 0:
    print("x adalah bilangan negatif")
else:
    print("x adalah nol")
```

6. Keputusan Banyak Arah (elif): Keputusan banyak arah digunakan ketika ada beberapa kondisi yang harus dipertimbangkan secara berurutan, dengan tindakan yang berbeda untuk setiap kondisi. Contoh penggunaan keputusan banyak arah:

```python
x = 5

if x > 0:
    print("x adalah bilangan positif")
elif x < 0:
    print("x adalah bilangan negatif")
elif x == 0:
    print("x adalah nol")
else:
    print("x tidak valid")
```

7. Penggunaan try/except untuk mengatasi kesalahan: Pernyataan `try-except` digunakan untuk menangani kesalahan yang mungkin terjadi saat menjalankan kode. Contoh penggunaan try/except:

```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("Terjadi pembagian dengan nol")
```


# ⭐️ Course Contents ⭐️

⌨️ ([0:56:55](https://www.youtube.com/watch?v=8DvywoWv6fI&t=3415s)) Variables, Expressions, and Statements 
⌨️ ([1:06:20](https://www.youtube.com/watch?v=8DvywoWv6fI&t=3980s)) Variables, Expressions, and Statements - Expressions

# Slides

![[Pythonlearn-02-Expressions2.pdf]]

# [Python for Pemula: Konstanta, Kata Kunci, dan Variabel](https://www.youtube.com/watch?v=8DvywoWv6fI&t=3415s)

Dalam bahasa pemrograman Python, terdapat konsep-konsep dasar yang perlu dipahami, yaitu konstanta, kata kunci, dan variabel. Mari kita bahas lebih detail mengenai ketiga konsep ini.

1. Konstanta:
   Konstanta adalah nilai yang tidak berubah dalam program. Dalam Python, konstanta dapat berupa angka atau string. Contohnya adalah 123, 98.6, dan "Hello, World!". Konstanta digunakan untuk memulai perhitungan atau sebagai acuan dalam kondisi eksekusi program.

2. Kata Kunci:
   Kata kunci (reserved words) adalah kata-kata khusus yang telah dipesan oleh Python. Kata kunci ini memiliki makna tertentu dalam bahasa Python dan tidak dapat digunakan sebagai nama variabel. Beberapa contoh kata kunci dalam Python antara lain "if", "else", "for", "while", dan "print". Kata kunci ini digunakan untuk mengendalikan alur program dan memberikan instruksi kepada Python.

3. Variabel:
   Variabel adalah tempat di dalam memori komputer yang diberi nama dan dapat diisi dengan nilai. Dalam Python, kita dapat membuat variabel dengan cara menugaskan nilai ke dalamnya. Variabel memungkinkan kita untuk menyimpan dan mengakses data dengan mudah. Setiap variabel memiliki tipe data tertentu, seperti angka, string, atau koleksi data lainnya. Kita dapat menggunakan variabel untuk melakukan operasi matematika, manipulasi string, dan banyak lagi.

   Dalam penamaan variabel, terdapat beberapa aturan yang perlu diikuti. Variabel dapat dimulai dengan huruf atau garis bawah (_). 
   
   Selanjutnya, kita dapat menggunakan huruf, angka, atau garis bawah dalam penamaan variabel. Variabel bersifat case-sensitive, artinya huruf kapital dan huruf kecil dianggap berbeda oleh Python. Namun, sebaiknya kita menghindari menggunakan karakter garis bawah sebagai karakter pertama dalam penamaan variabel, kecuali untuk variabel yang digunakan secara khusus oleh Python itu sendiri.

## Poin-poin penting:

- Konstanta adalah nilai yang tidak berubah dalam program.
- Kata kunci adalah kata-kata khusus yang memiliki makna tertentu dalam Python.
- Variabel adalah tempat di dalam memori komputer yang diberi nama dan dapat diisi dengan nilai. Variabel memungkinkan kita untuk menyimpan dan mengakses data.

# [Expressions](https://www.youtube.com/watch?v=8DvywoWv6fI&t=3980s)

1. Tipe Data: Tipe data adalah jenis nilai yang dapat disimpan dan dioperasikan dalam bahasa pemrograman. Contoh tipe data umum meliputi:
   - Integer: digunakan untuk merepresentasikan bilangan bulat, seperti 1, 2, -3.
   - Float: digunakan untuk merepresentasikan bilangan desimal, seperti 3.14, -0.5.
   - String: digunakan untuk merepresentasikan teks atau karakter, seperti "Halo", 'OpenAI', "123".
   - Boolean: digunakan untuk merepresentasikan nilai kebenaran, yaitu True atau False.

2. Kata Kunci (Reserved Words): Kata kunci adalah kata-kata yang memiliki makna khusus dalam bahasa pemrograman. Contoh kata kunci dalam Python meliputi: if, else, for, while, def, dan lain-lain. Kata kunci ini tidak dapat digunakan sebagai nama variabel atau fungsi.

3. Variabel: Variabel adalah tempat penyimpanan untuk nilai-nilai dalam pemrograman. Setiap variabel memiliki tipe data tertentu dan diberi nama yang unik. Contoh penggunaan variabel:
   ```python
   umur = 25
   nama = "John Doe"
   pi = 3.14
   ```

4. Operator: Operator adalah simbol-simbol khusus yang digunakan untuk melakukan operasi pada nilai atau variabel. Contoh operator:
   - Operator Aritmatika: + (penjumlahan), - (pengurangan), * (perkalian), / (pembagian), % (modulus), dan lain-lain.
   - Operator Perbandingan: == (sama dengan), != (tidak sama dengan), > (lebih besar dari), < (lebih kecil dari), >= (lebih besar atau sama dengan), <= (lebih kecil atau sama dengan), dan lain-lain.
   - Operator Logika: and (dan), or (atau), not (negasi).

5. Precedence Operator: Operator precedence adalah aturan yang menentukan urutan evaluasi dalam sebuah ekspresi. Misalnya, dalam ekspresi 4 + 2 * 3, perkalian akan dievaluasi terlebih dahulu sebelum penjumlahan, karena operator perkalian memiliki precedence yang lebih tinggi.

6. Pembagian Bilangan Bulat: Dalam beberapa bahasa pemrograman, seperti Python, pembagian menggunakan operator // menghasilkan hasil pembagian yang merupakan bilangan bulat tanpa pecahan. Contoh:
   ```python
   hasil = 7 // 3
   print(hasil)  # Output: 2
   ```

7. Konversi Antar Tipe (Conversion between Types): Dalam pemrograman, seringkali perlu mengubah tipe data dari satu jenis ke jenis lain. Contoh konversi tipe data:
   ```python
   angka = 10
   teks = str(angka)  # Mengkonversi angka menjadi string
   print(teks)  # Output: "10"
   ```

8. Input Pengguna (User Input): Dalam pemrograman, kita dapat meminta input dari pengguna menggunakan fungsi input(). Fungsi ini akan mengambil input dari pengguna dalam bentuk string. Contoh penggunaan input pengguna:
   ```python
   nama = input("Masukkan nama Anda: ")
   print("Halo, " + nama + "! Selamat datang!")
   ```

   Pada contoh di atas, program akan meminta pengguna untuk memasukkan namanya. Kemudian, program akan mencetak pesan selamat datang yang mencakup nama yang diinputkan oleh pengguna.

9. Perintah (Command): Dalam pemrograman, perintah adalah instruksi-instruksi yang diberikan kepada komputer untuk menjalankan tugas tertentu. Contoh perintah yang umum digunakan dalam pemrograman Python meliputi:
   - print(): digunakan untuk mencetak atau menampilkan output ke layar.
   - if-else: digunakan untuk membuat keputusan berdasarkan kondisi tertentu.
   - for dan while: digunakan untuk mengulang atau melakukan iterasi terhadap sejumlah tindakan.
   - def: digunakan untuk mendefinisikan fungsi.
   - import: digunakan untuk mengimpor modul atau pustaka tambahan.

   Contoh penggunaan perintah:
   ```python
   # Contoh penggunaan perintah print()
   print("Halo, dunia!")

   # Contoh penggunaan perintah if-else
   umur = 18
   if umur >= 18:
       print("Anda sudah cukup umur.")
   else:
       print("Anda masih di bawah umur.")

   # Contoh penggunaan perintah for
   for i in range(5):
       print(i)

   # Contoh penggunaan perintah def
   def sapa(nama):
       print("Halo, " + nama + "! Selamat datang!")

   sapa("John")
   ```

   Pada contoh-contoh di atas, berbagai perintah digunakan untuk mencetak pesan, membuat keputusan berdasarkan kondisi, melakukan iterasi, mendefinisikan fungsi, dan lain-lain.


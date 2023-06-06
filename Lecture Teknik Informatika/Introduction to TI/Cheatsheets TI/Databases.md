### Column Constraints

Batasan kolom adalah aturan yang diterapkan pada nilai masing-masing kolom:

-   `PRIMARY KEY` kendala dapat digunakan untuk mengidentifikasi baris secara unik.
-   `UNIQUE` kolom memiliki nilai yang berbeda untuk setiap baris.
-   `NOT NULL` kolom harus memiliki nilai.
-   `DEFAULT` memberikan nilai default untuk kolom ketika tidak ada nilai yang ditentukan.

Hanya ada satu `PRIMARY KEY` kolom per tabel dan beberapa `UNIQUE` kolom.
![[Pasted image 20230330212359.png]]

Lebih detail tentang [[Column Constraint]].

### `CREATE TABLE` Statement

The `CREATE TABLE` statement membuat tabel baru dalam database. Ini memungkinkan seseorang untuk menentukan nama tabel dan nama setiap kolom dalam tabel.
![[Pasted image 20230330212628.png]]

Lebih detail tentang [[`CREATE TABLE` Statement]].

### `INSERT` Statement

The `INSERT INTO` statement digunakan untuk menambahkan record baru (baris) ke tabel.

Ini memiliki dua bentuk seperti yang ditunjukkan:
-   Insert into columns in order.
-   Insert into columns by name.
![[Pasted image 20230330212730.png]]

Lebih detail tentang [[`INSERT` Statement]].

### `ALTER TABLE` Statement

The `ALTER TABLE` statement digunakan untuk memodifikasi kolom dari tabel yang ada. Ketika dikombinasikan dengan `ADD COLUMN` klausa, digunakan untuk menambahkan kolom baru.
![[Pasted image 20230330212803.png]]

Lebih detail tentang [[`ALTER TABLE` Statement]].

### `DELETE` Statement

The `DELETE` statement digunakan untuk menghapus catatan (baris) dalam tabel. Klausa `WHERE`menentukan catatan atau catatan mana yang harus dihapus. Jika `WHERE`klausa dihilangkan, semua catatan akan dihapus.
![[Pasted image 20230330212902.png]]

Lebih detail tentang [[`DELETE` Statement]].

### `UPDATE` Statement

The `UPDATE` statement digunakan untuk mengedit catatan (baris) dalam tabel. Ini termasuk `SET`klausa yang menunjukkan kolom yang akan diedit dan `WHERE`klausa untuk menentukan catatan.
![[Pasted image 20230330212941.png]]

Lebih detail tentang [[`UPDATE` Statement]].
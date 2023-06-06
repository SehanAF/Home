A record atau Address record adalah jenis DNS record yang digunakan untuk memetakan nama domain ke alamat IPv4. A record biasanya digunakan untuk mengaitkan sebuah nama domain dengan alamat IP tertentu sehingga pengguna dapat mengakses situs web dan layanan online melalui alamat domain yang mudah diingat.

Contohnya, jika sebuah situs web memiliki alamat IP 192.168.1.1 dan nama domain "example.com", maka administrator DNS dapat membuat A record yang mengaitkan nama domain "example.com" dengan alamat IP tersebut. Ketika pengguna memasukkan "example.com" di browser, DNS akan mengecek A record untuk menemukan alamat IP yang sesuai dan mengarahkan pengguna ke situs web yang bersangkutan.

Setiap A record memiliki nilai TTL (Time-to-Live) yang menentukan berapa lama cache DNS harus menyimpan informasi tentang record tersebut sebelum memperbarui informasi dari server DNS. Semakin kecil nilai TTL, semakin cepat perubahan pada record dapat diterapkan oleh server DNS dan pengguna akhir.

A record juga dapat digunakan untuk menetapkan beberapa alamat IP untuk sebuah nama domain melalui record yang disebut dengan Multiple A records. Dalam Multiple A records, setiap alamat IP diberi nomor urut atau prioritas yang menunjukkan urutan yang harus diikuti oleh server DNS dalam mengambil alamat IP tersebut.

Berikut adalah poin penting tentang A record dalam DNS Records:

1.  A record digunakan untuk memetakan nama domain ke alamat IPv4, sehingga pengguna dapat mengakses situs web dan layanan online melalui alamat domain yang mudah diingat.
2.  A record dapat digunakan untuk menetapkan beberapa alamat IP untuk sebuah nama domain melalui Multiple A records.
3.  Setiap A record memiliki nilai TTL (Time-to-Live) yang menentukan berapa lama cache DNS harus menyimpan informasi tentang record tersebut sebelum memperbarui informasi dari server DNS.
4.  A record harus diperbarui atau diubah oleh administrator DNS jika ada perubahan pada alamat IP atau jika ingin menetapkan multiple A records untuk sebuah nama domain.
5.  A record adalah salah satu jenis DNS record yang paling umum digunakan dan sangat penting dalam menjaga ketersediaan dan keandalan jaringan internet.
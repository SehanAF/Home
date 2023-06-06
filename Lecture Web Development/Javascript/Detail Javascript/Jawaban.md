Berikut adalah kode yang diberikan:

var a = "3";
var b = "8";

Berikut adalah kode yang dapat digunakan untuk menukar nilai dari kedua variabel:

var temp = a;
a = b;
b = temp;

Kode di atas menyimpan nilai variabel a di variabel sementara 'temp', kemudian mengubah nilai a menjadi b dan nilai b menjadi 'temp' (yang sebelumnya berisi nilai a). Setelah itu, variabel a dan b telah ditukar nilainya.

Jika kode di atas dijalankan, maka output yang dihasilkan adalah:

a is 8 
b is 3

![[Pasted image 20230403085314.png]]

Penjelasan lebih detail : 

`temp` adalah variabel sementara yang digunakan untuk menyimpan nilai dari variabel `a`. Variabel `temp` dibuat untuk menyimpan nilai `a` sebelum nilainya diganti dengan nilai dari variabel `b`.

Dalam kode yang diberikan, variabel `temp` digunakan untuk menyimpan nilai awal dari variabel `a` sebelum dilakukan penukaran nilai dengan variabel `b`. Setelah nilai variabel `a` disimpan di variabel `temp`, nilai variabel `a` diganti dengan nilai variabel `b`. Kemudian, nilai dari variabel `temp` (yang sebelumnya berisi nilai variabel `a`) digunakan untuk mengganti nilai dari variabel `b`. Dengan cara ini, nilai variabel `a` dan `b` berhasil ditukar.
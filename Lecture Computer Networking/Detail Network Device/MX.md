MX Record dalam layanan DNS (Domain Name System) adalah jenis catatan yang menentukan alamat server email untuk sebuah domain. Catatan ini digunakan untuk mengarahkan email yang dikirim ke sebuah domain ke server email yang tepat. MX record terdiri dari dua bagian yaitu "Preference" dan "Mail Server".

Preference adalah angka prioritas yang menunjukkan urutan pengiriman email. Misalnya, jika sebuah domain memiliki tiga MX record dengan preference 10, 20, dan 30, maka email pertama akan dikirim ke server email dengan preference 10. Jika server tersebut tidak merespon, email akan dikirim ke server dengan preference 20 dan seterusnya.

Mail Server adalah alamat IP atau nama domain dari server email yang akan menerima email yang dikirim ke domain tersebut. Misalnya, MX record untuk domain contoh.com bisa terlihat seperti ini:

contoh.com. IN MX 10 mail.contoh.com. contoh.com. IN MX 20 backupmail.contoh.com.

Poin penting dari MX record adalah:

1.  MX record sangat penting untuk menjalankan email pada domain yang telah dibuat. Tanpa MX record yang benar, email tidak dapat diterima oleh server email yang benar.
    
2.  Jika Anda mengelola sebuah domain dan ingin menggunakan server email dari penyedia email pihak ketiga, Anda perlu menyesuaikan MX record domain Anda untuk mengarahkan email ke server email tersebut.
    
3.  Saat mengonfigurasi MX record, pastikan untuk memberikan preference yang benar agar email dapat diantarkan dengan benar. Preference yang lebih rendah berarti server email tersebut memiliki prioritas yang lebih tinggi dalam menerima email.
    
4.  Saat menggunakan layanan hosting yang berbeda dengan layanan email, pastikan untuk menggunakan MX record yang benar untuk mengarahkan email ke server email yang tepat.
    
5.  Saat mengubah MX record, perubahan ini mungkin memakan waktu hingga 48 jam untuk disebarkan di seluruh dunia. Oleh karena itu, pastikan untuk memperhitungkan waktu ini sebelum melakukan perubahan.
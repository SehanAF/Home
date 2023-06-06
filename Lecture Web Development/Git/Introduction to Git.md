# [Kuliah 1](https://cs50.harvard.edu/web/2020/notes/1/#lecture-1)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/1/#introduction)
-   [Git](https://cs50.harvard.edu/web/2020/notes/1/#git)
-   [GitHub](https://cs50.harvard.edu/web/2020/notes/1/#github)
-   [Komitmen](https://cs50.harvard.edu/web/2020/notes/1/#commits)
-   [Menggabungkan Konflik](https://cs50.harvard.edu/web/2020/notes/1/#merge-conflicts)
-   [Percabangan](https://cs50.harvard.edu/web/2020/notes/1/#branching)
    -   [Lebih Banyak Fitur GitHub](https://cs50.harvard.edu/web/2020/notes/1/#more-github-features)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/1/#introduction)

Selamat datang kembali di kuliah 1! Di kuliah 0, kami memperkenalkan HTML, CSS, dan Sass sebagai alat yang dapat kami gunakan untuk membuat beberapa halaman web dasar. Hari ini, kita akan belajar tentang penggunaan Git dan GitHub untuk membantu kita dalam mengembangkan aplikasi pemrograman web.

## [Git](https://cs50.harvard.edu/web/2020/notes/1/#git)

-   [Git](https://git-scm.com/) adalah alat baris perintah yang akan membantu kita dengan kontrol versi dalam beberapa cara berbeda:
    
    -   Mengizinkan kami melacak perubahan yang kami buat pada kode kami dengan menyimpan cuplikan kode kami pada titik waktu tertentu.
    
    ![Mengubah File](https://cs50.harvard.edu/web/2020/notes/1/images/change_file.png)
    
    -   Mengizinkan kami menyinkronkan kode dengan mudah antara orang berbeda yang mengerjakan proyek yang sama dengan memungkinkan banyak orang menarik informasi dari dan mendorong informasi ke repositori yang disimpan di web.
    
    ![Beberapa Pengguna](https://cs50.harvard.edu/web/2020/notes/1/images/mult_users.png)
    
    -   Mengizinkan kami membuat perubahan dan menguji kode pada _cabang_ yang berbeda tanpa mengubah basis kode utama kami, lalu menggabungkan keduanya.
    -   Mengizinkan kami untuk kembali ke versi sebelumnya dari kode kami jika kami menyadari bahwa kami telah melakukan kesalahan.
    -   Dalam penjelasan di atas, kami menggunakan kata **repository** , yang belum kami jelaskan. Repositori Git adalah lokasi file tempat kami akan menyimpan semua file yang terkait dengan proyek tertentu. Ini bisa berupa jarak jauh (disimpan online) atau lokal (disimpan di komputer Anda).

## [GitHub](https://cs50.harvard.edu/web/2020/notes/1/#github)

-   [GitHub](https://www.github.com/) adalah situs web yang memungkinkan kita menyimpan repositori Git dari jarak jauh di web.
-   Mari kita mulai dengan membuat repositori baru secara online
    
    1.  Pastikan Anda telah menyiapkan akun GitHub. Jika Anda belum memilikinya, Anda dapat membuatnya [di sini](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home) .
    2.  Klik tanda **+** di pojok kanan atas, lalu klik "Repositori baru"
    3.  Buat nama repositori yang menjelaskan proyek Anda
    4.  (Opsional) Berikan deskripsi untuk repositori Anda
    5.  Pilih apakah repositori harus bersifat publik (dapat dilihat oleh siapa saja di web) atau pribadi (hanya dapat dilihat oleh Anda dan orang lain yang secara khusus Anda beri akses)
    6.  (Opsional) Putuskan apakah Anda ingin menambahkan README, yang merupakan file yang menjelaskan repositori baru Anda.
    
    ![Demo repo baru](https://cs50.harvard.edu/web/2020/notes/1/images/new_repo.png)
    
-   Setelah kami memiliki repositori, kami mungkin ingin menambahkan beberapa file ke dalamnya. Untuk melakukan ini, kami akan mengambil repositori _jarak jauh_ yang baru kami buat dan membuat salinan, atau mengkloningnya, sebagai repositori _lokal_ di komputer kami.
    1.  Pastikan Anda telah menginstal git di komputer Anda dengan mengetik `git`di terminal Anda. Jika belum diinstal, Anda dapat mengunduhnya [di sini](https://git-scm.com/downloads) .
    2.  Klik tombol hijau “Clone or Download” di halaman repositori Anda, dan salin url yang muncul. Jika Anda tidak membuat README, tautan ini akan muncul di dekat bagian atas halaman di bagian “Pengaturan Cepat”.
        
        ![mengkloning dan menambahkan](https://cs50.harvard.edu/web/2020/notes/1/images/clone_and_add.png)
        
    3.  Di terminal Anda, jalankan `git clone <repository url>`. Ini akan mengunduh repositori ke komputer Anda. Jika Anda tidak membuat README, Anda akan mendapatkan peringatan: `You appear to have cloned into an empty repository.`Ini normal, dan tidak perlu khawatir.
        
        ![demo klon](https://cs50.harvard.edu/web/2020/notes/1/images/clone.png)
        
    4.  Jalankan `ls`, yang merupakan perintah yang mencantumkan semua file dan folder di direktori Anda saat ini. Anda akan melihat nama repositori yang baru saja Anda kloning.
    5.  Jalankan `cd <repository name>`untuk mengubah direktori ke folder itu.
    6.  Jalankan `touch <new file name>`untuk membuat file baru di folder itu. Anda sekarang dapat mengedit file itu. Alternatifnya, Anda dapat membuka folder di editor teks dan menambahkan file baru secara manual.
    7.  Sekarang, untuk memberi tahu Git bahwa itu harus melacak file baru yang Anda buat, Jalankan `git add <new file name>`untuk melacak file tertentu itu, atau `git add .`untuk melacak semua file di dalam direktori itu.
        
        ![-Saya waktu yang sama](https://cs50.harvard.edu/web/2020/notes/1/images/create_and_add.png)
        

## [Komitmen](https://cs50.harvard.edu/web/2020/notes/1/#commits)

-   Sekarang, kita akan mulai membahas kegunaan Git. Setelah membuat beberapa perubahan pada file, kita dapat _mengkomit_ perubahan tersebut, mengambil snapshot dari status kode kita saat ini. Untuk melakukan ini, kami menjalankan: `git commit -m "some message"`di mana pesan menjelaskan perubahan yang baru saja Anda buat.
-   Setelah perubahan ini, kita dapat menjalankan `git status`untuk melihat bagaimana kode kita dibandingkan dengan kode di repositori jarak jauh
-   Saat kami siap untuk menerbitkan komitmen lokal kami ke Github, kami dapat menjalankan `git push`. Sekarang, ketika kita pergi ke GitHub di browser web kita, perubahan kita akan tercermin.
-   Jika Anda hanya mengubah file yang sudah ada dan tidak membuat yang baru, alih-alih menggunakan `git add .`dan kemudian `git commit...`, kita dapat memadatkan ini menjadi satu perintah: `git commit -am "some message"`. Perintah ini akan melakukan semua perubahan yang Anda buat.
-   Terkadang, repositori jarak jauh di GitHub akan lebih mutakhir daripada versi lokal. Dalam hal ini, Anda ingin melakukan perubahan apa pun terlebih dahulu, lalu menjalankan `git pull`untuk menarik semua perubahan jarak jauh ke repositori Anda.

## [Menggabungkan Konflik](https://cs50.harvard.edu/web/2020/notes/1/#merge-conflicts)

-   Salah satu masalah yang dapat muncul saat bekerja dengan Git, terutama saat Anda berkolaborasi dengan orang lain, adalah yang disebut **konflik gabungan** . Konflik penggabungan terjadi saat dua orang mencoba mengubah file dengan cara yang bertentangan satu sama lain.
-   Ini biasanya akan terjadi ketika Anda salah satu `git push`atau `git pull`. Ketika ini terjadi, Git akan secara otomatis mengubah file tersebut menjadi format yang dengan jelas menguraikan apa konfliknya. Berikut adalah contoh di mana baris yang sama ditambahkan dengan dua cara berbeda:

```
a = 1
<<<<< HEAD
b = 2
=====
b = 3
>>>>> 56782736387980937883
c = 3
d = 4
e = 5
```

-   Pada contoh di atas, Anda menambahkan baris `b = 2`dan orang lain menulis `b = 3`, dan sekarang kita harus memilih salah satu baris untuk dipertahankan. Angka panjang adalah _hash_ yang mewakili komit yang bertentangan dengan suntingan Anda. Banyak editor teks juga akan memberikan penyorotan dan opsi sederhana seperti "terima saat ini" atau "terima masuk" yang menghemat waktu Anda untuk menghapus baris tambahan di atas.
-   Perintah git lain yang berpotensi berguna adalah `git log`, yang memberi Anda riwayat semua komit Anda di repositori itu.

![Catatan Git](https://cs50.harvard.edu/web/2020/notes/1/images/git_log.png)

-   Berpotensi lebih membantu, jika Anda menyadari bahwa Anda telah melakukan kesalahan, Anda dapat kembali ke komit sebelumnya menggunakan perintah `git reset`dengan salah satu dari dua cara berikut:
    -   `git reset --hard <commit>`mengembalikan kode Anda persis seperti setelah komit yang ditentukan. Untuk menentukan komit, gunakan hash komit yang terkait dengan komit yang dapat ditemukan menggunakan `git log`seperti yang ditunjukkan di atas.
    -   `git reset --hard origin/master`mengembalikan kode Anda ke versi yang saat ini disimpan secara online di Github.

## [Percabangan](https://cs50.harvard.edu/web/2020/notes/1/#branching)

Setelah Anda mengerjakan proyek selama beberapa waktu, Anda mungkin memutuskan ingin menambahkan fitur tambahan. Saat ini, kami mungkin hanya melakukan perubahan pada fitur baru ini seperti yang ditunjukkan pada grafik di bawah ini

![Tidak ada Cabang](https://cs50.harvard.edu/web/2020/notes/1/images/no_branch.png)

Tapi ini bisa menjadi masalah jika kami kemudian menemukan bug dalam kode asli kami, dan ingin kembali tanpa mengubah fitur baru. Di sinilah percabangan bisa menjadi sangat berguna.

-   Percabangan adalah metode pindah ke arah baru saat membuat fitur baru, dan hanya menggabungkan fitur baru ini dengan bagian utama kode Anda, atau cabang utama, setelah Anda selesai. Alur kerja ini akan lebih terlihat seperti grafik di bawah ini:

![Cabang](https://cs50.harvard.edu/web/2020/notes/1/images/branch.png)

-   Cabang yang sedang Anda lihat ditentukan oleh `HEAD`, yang menunjuk ke salah satu dari dua cabang. Secara default, HEAD diarahkan ke cabang master, tetapi kita juga dapat memeriksa cabang lainnya.
-   Sekarang, mari masuk ke bagaimana kita benar-benar mengimplementasikan percabangan di repositori git kita:
    
    1.  Jalankan `git branch`untuk melihat cabang mana yang sedang Anda kerjakan, yang akan memiliki tanda bintang di sebelah kiri namanya.
    
    ![Terminal cabang](https://cs50.harvard.edu/web/2020/notes/1/images/git_branch.png)
    
    1.  Untuk membuat cabang baru, kami akan menjalankan`git checkout -b <new branch name>`
    
    ![Cabang baru](https://cs50.harvard.edu/web/2020/notes/1/images/new_branch.png)
    
    1.  Beralih antar cabang menggunakan perintah `git checkout <branch name>`dan komit setiap perubahan ke setiap cabang.
    2.  Saat kita siap menggabungkan dua cabang kita bersama-sama, kita akan memeriksa cabang yang ingin kita pertahankan (hampir selalu cabang master) dan kemudian menjalankan perintah `git merge <other branch name>`. Ini akan diperlakukan mirip dengan dorongan atau tarikan, dan konflik gabungan mungkin muncul.

### [Lebih Banyak Fitur GitHub](https://cs50.harvard.edu/web/2020/notes/1/#more-github-features)

Ada beberapa fitur bermanfaat khusus untuk GitHub yang dapat membantu saat Anda mengerjakan proyek:

-   **Forking** : Sebagai pengguna GitHub, Anda memiliki kemampuan untuk _mem-fork_ setiap repositori yang dapat Anda akses, yang membuat salinan repositori yang Anda miliki. Kami melakukan ini dengan mengklik tombol "Fork" di kanan atas.
-   **Pull Requests** : Setelah Anda mem-fork repositori dan membuat beberapa perubahan pada versi Anda, Anda mungkin ingin meminta agar perubahan tersebut ditambahkan ke versi utama repositori. Misalnya, jika Anda ingin menambahkan fitur baru ke Bootstrap, Anda dapat melakukan fork pada repositori, membuat beberapa perubahan, lalu mengirimkan pull request. Permintaan penarikan ini kemudian dapat dievaluasi dan mungkin diterima oleh orang-orang yang menjalankan repositori Bootsrap. Proses orang membuat beberapa pengeditan dan kemudian meminta agar mereka digabungkan ke dalam repositori utama sangat penting untuk apa yang dikenal sebagai _perangkat lunak sumber terbuka_ , atau perangkat lunak yang dibuat oleh kontribusi dari sejumlah pengembang.
-   **Halaman GitHub** : Halaman GitHub adalah cara sederhana untuk menerbitkan situs statis ke web. (Kita akan belajar nanti tentang situs statis vs dinamis.) Untuk melakukannya:
    1.  Buat repositori GitHub baru.
    2.  Kloning repositori dan buat perubahan secara lokal, pastikan untuk menyertakan `index.html`file yang akan menjadi halaman arahan situs web Anda.
    3.  Dorong perubahan itu ke GitHub.
    4.  Arahkan ke halaman Pengaturan repositori Anda, gulir ke bawah ke Halaman GitHub, dan pilih cabang master di menu dropdown.
    5.  Gulir kembali ke bagian Halaman GitHub dari halaman pengaturan, dan setelah beberapa menit, Anda akan melihat pemberitahuan bahwa “Situs Anda dipublikasikan di: …” termasuk URL tempat Anda dapat menemukan situs Anda!

Itu saja untuk kuliah ini! Lain kali, kita akan melihat Python!
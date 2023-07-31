# ⭐️ Course Contents ⭐️

<iframe width="560" height="315" src="https://www.youtube.com/embed/vT1JzLTH4G4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Slides

![[cs231n_2017_lecture1.pdf]]

# Summary

CS231n adalah kelas visi komputer yang telah berkembang secara eksponensial dalam pendaftaran. Data visual meledak, dan algoritme diperlukan untuk memahaminya.

[00:07](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=7) CS231n adalah kursus visi komputer yang berfokus pada pemahaman data visual.
[06:03](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=363) CS231n berfokus pada jaringan saraf dan jaringan saraf konvolusional untuk tugas pengenalan visual.
[16:28](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=988) Visi komputer telah berevolusi dari struktur sederhana menjadi pengenalan berbasis fitur.
[26:54](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=1614) Masalah Pengenalan Objek Computer Vision Mendorong Kemajuan dalam AI
[36:54](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=2214) Jaringan Syaraf Konvolusional Merevolusi Klasifikasi Gambar
[41:59](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=2519) Inovasi Utama dalam Pembelajaran Mendalam: Komputasi dan Data
[47:05](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=2825) Visi komputer adalah bidang menarik yang masih memiliki jalan panjang.
[51:36](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=3096) Kursus mencakup mekanisme pembelajaran mendalam dan alat canggih
[56:00](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=3360) Prasyarat untuk kursus ini meliputi konsep Python, kalkulus, aljabar linier, dan pembelajaran mesin.

---------------------------------

Detailed Summary for [Lecture 1 | Introduction to Convolutional Neural Networks for Visual Recognition](https://www.youtube.com/watch?v=vT1JzLTH4G4) by [Merlin](https://merlin.foyer.work/)

[00:07](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=7) CS231n adalah kursus visi komputer yang berfokus pada pemahaman data visual.
- Data visual tumbuh secara eksponensial dan merupakan mayoritas data di internet.
- Visi komputer adalah bidang interdisipliner yang melibatkan fisika, biologi, dan ilmu komputer.
- 
[06:03](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=363) CS231n berfokus pada jaringan saraf dan jaringan saraf konvolusional untuk tugas pengenalan visual.
- Profesor Li Feifei biasanya mengajar kursus ini.
- Kursus ini mencakup sejarah visi komputer dan pengembangan algoritma visi komputer.

[16:28](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=988) Visi komputer telah berevolusi dari struktur sederhana menjadi pengenalan berbasis fitur.
- Pemrosesan visual awal melibatkan struktur sederhana seperti tepi dan kurva.
- Pengenalan objek dimulai dengan mengidentifikasi fitur utama dari suatu objek dan mencocokkannya dengan objek serupa.

[26:54](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=1614) Masalah Pengenalan Objek Computer Vision Mendorong Kemajuan dalam AI
- Kumpulan data tolok ukur seperti PASCAL dan ImageNet mendukung pengembangan algoritme
- Model Jaringan Syaraf Konvolusional Membuat Kemajuan Besar dalam Tantangan ImageNet 2012

[36:54](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=2214) Jaringan Syaraf Konvolusional Merevolusi Klasifikasi Gambar
- Masalah pengenalan visual berbasis CNN lainnya
- CNN telah ada sejak tahun 1990-an tetapi baru menjadi populer dalam beberapa tahun terakhir

[41:59](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=2519) Inovasi Utama dalam Pembelajaran Mendalam: Komputasi dan Data
- Hukum Moore mengarah pada komputer yang lebih cepat dan model yang lebih besar
- Ketersediaan kumpulan data berlabel besar memungkinkan pelatihan model yang lebih baik

[47:05](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=2825) Visi komputer adalah bidang menarik yang masih memiliki jalan panjang.
- Visi komputer bertujuan untuk memahami kisah gambar dengan cara yang kaya dan mendalam.
- Visi komputer memiliki aplikasi potensial dalam diagnosa medis, mobil self-driving, dan robotika.

[51:36](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=3096) Kursus mencakup mekanisme pembelajaran mendalam dan alat canggih
- Komunikasi dengan staf harus melalui Piazza
- Buku teks opsional tersedia, tetapi tidak wajib

[56:00](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=3360) Prasyarat untuk kursus ini meliputi konsep Python, kalkulus, aljabar linier, dan pembelajaran mesin.
- Python adalah bahasa utama yang digunakan untuk pekerjaan pemrograman.
- Keakraban dengan C atau C++ berguna untuk memahami paket. Beberapa latar belakang pengetahuan visi komputer juga diasumsikan.

# Computer Vision

## Penglihatan Komputer: Mempelajari Data Visual

Computer Vision (Visi Komputer) adalah ilmu yang mempelajari data visual. Dengan meningkatnya jumlah sensor di dunia, terjadi ledakan data visual, berkat ponsel pintar dan berbagai kameranya. Sekitar 80% lalu lintas internet terdiri dari data video saja. Namun, memahami data visual merupakan hal yang menantang, sering diibaratkan sebagai materi gelap dalam fisika - melimpah tetapi sulit untuk diamati secara langsung.

## Tantangan dalam Memahami Data Visual

Data visual di internet sangat besar, sehingga sangat penting untuk mengembangkan algoritme yang mampu memahami dan memanfaatkannya. Banyaknya unggahan video di platform seperti YouTube menyoroti kerumitannya. Google tidak dapat secara manual menonton dan memberi keterangan pada setiap video, sehingga membutuhkan teknologi yang secara otomatis memahami konten visual. Visi Komputer adalah bidang interdisipliner, yang menyentuh berbagai bidang ilmu pengetahuan, teknik, dan teknologi.

## Hal-hal penting yang dapat diambil:

- Visi Komputer adalah studi tentang data visual dan telah menjadi semakin penting karena lonjakan sensor dan ponsel pintar dengan banyak kamera.
- Data visual merupakan bagian penting dari lalu lintas internet, yang menekankan perlunya algoritme untuk memahami dan memanfaatkannya secara efektif.
- Mengembangkan teknologi untuk memahami data visual secara otomatis sangat penting untuk tugas-tugas seperti membuat katalog dan menyediakan konten video yang relevan.

# Interdisciplinary Fields

## Komputer Penglihatan dan Bidang Terkait

Komputer penglihatan adalah pusat dari segala sesuatu, namun ada bidang-bidang lain yang terkait dengannya. Bidang-bidang tersebut termasuk fisika, karena kita perlu memahami optik dan pembentukan gambar serta bagaimana gambar-gambar dibentuk secara fisik. Selain itu, kita juga memerlukan pemahaman tentang biologi dan psikologi untuk memahami bagaimana otak hewan melihat dan memproses informasi visual.

## Latar Belakang Instruktur

Instruktur dari kursus ini adalah mahasiswa doktoral di Laboratorium Vision Stanford yang dipimpin oleh profesor Fei-Fei Li. Laboratorium ini fokus pada pembelajaran mesin dan sisi ilmu komputer. Instruktur utama lebih fokus pada bahasa dan visi, sedangkan anggota lain dari kelompok ini lebih terlibat dalam bidang neurosains dan ilmu kognitif.

## Main Takeaways (Poin-poin Utama):

1. Komputer penglihatan adalah bidang utama yang melibatkan fisika, biologi, dan psikologi untuk memahami pengolahan informasi visual.
2. Instruktur kursus ini adalah mahasiswa doktoral dari Laboratorium Vision Stanford yang fokus pada pembelajaran mesin dan ilmu komputer.

# History of Vision

## Sejarah Penglihatan: Dari Evolusi Hewan Hingga Kamera Mekanis

### Evolusi Visi Hewan:

- 543 juta tahun lalu, kehidupan di bumi didominasi oleh air dengan beberapa spesies hewan mengapung di laut.
- Sekitar 540 juta tahun lalu, jumlah spesies hewan tiba-tiba meledak dari beberapa menjadi ratusan ribu karena munculnya visi.
- Visi memulai perlombaan evolusi, memungkinkan hewan untuk berburu dan melarikan diri, sehingga menghasilkan spesies yang lebih cepat beradaptasi.

### Pentingnya Penglihatan:

- Penglihatan adalah sistem sensorik terbesar yang memungkinkan hewan, terutama manusia, untuk bertahan hidup, bergerak, berkomunikasi, dan melakukan berbagai aktivitas.
- Pada manusia, hampir 50% neuron di korteks otak terlibat dalam pemrosesan visual.

### Sejarah Kamera Mekanis:

- Salah satu kamera awal yang dikenal berasal dari zaman Renaisans pada abad ke-17, yaitu "camera obscura," yang berdasarkan teori kamera lubang jarum.
- Kamera telah berkembang pesat dari masa itu hingga saat ini, menjadi salah satu sensor paling populer digunakan oleh orang dari ponsel pintar hingga perangkat lainnya.

### Studi Penglihatan:

- Studi tentang mekanisme penglihatan telah dilakukan, termasuk penelitian oleh Hubel dan Wiesel pada tahun 1950-an dan 1960-an.
- Penelitian tersebut mengungkapkan bahwa proses penglihatan dimulai dengan deteksi tepi yang berorientasi, dan kemudian otak membangun kompleksitas informasi visual hingga dapat mengenali dunia visual yang rumit.

## Ringkasan:

1. Evolusi visi dimulai sekitar 540 juta tahun lalu, menyebabkan ledakan jumlah spesies hewan karena kemampuan berburu dan melarikan diri yang lebih efektif.
2. Penglihatan adalah sistem sensorik terbesar yang memungkinkan hewan dan manusia untuk bertahan hidup dan beraktivitas.
3. Sejarah kamera mekanis dimulai pada abad ke-17 dengan "camera obscura," dan sejak itu kamera telah berkembang pesat dengan menjadi salah satu sensor paling populer saat ini.

# Visi Komputer: Dari Dunia Blok ke Pengenalan Dunia Nyata

## Dunia Blok: Proyek Awal dalam Visi Komputer

Dunia Blok adalah kumpulan karya oleh Larry Roberts yang dikenal sebagai tesis doktor pertama dalam visi komputer. Proyek ini bertujuan untuk menyederhanakan dunia visual menjadi bentuk-bentuk geometris sederhana dan mengembangkan sistem untuk mengenali dan merekonstruksi bentuk-bentuk tersebut. Proyek Visi Musim Panas MIT pada tahun 1966 merupakan usaha ambisius untuk membangun sebagian besar sistem visual hanya dalam satu musim panas.

## Tokoh Berpengaruh dan Proses Berpikir dalam Visi Komputer

David Marr, seorang ilmuwan visi di MIT, mengusulkan proses berpikir untuk visi komputer. Ia mengusulkan untuk memecah informasi visual menjadi "sketsa awal" dari tepi dan struktur sederhana, diikuti oleh "sketsa dua setengah dimensi" untuk menyusun permukaan dan informasi kedalaman, dan akhirnya menciptakan model 3D dari dunia visual. Pendekatan ini telah mempengaruhi bidang ini selama beberapa dekade.

## Kemajuan dalam Representasi Objek Dunia Nyata

Pada tahun 70-an, para ilmuwan komputer mencari cara untuk merepresentasikan objek dunia nyata di luar dunia blok yang sederhana. Dua gagasan berpengaruh muncul: pendekatan "tabung umum" dan "struktur gambar." Kedua metode bertujuan untuk menyederhanakan objek kompleks menjadi kumpulan bentuk-bentuk yang lebih sederhana dan konfigurasi geometrisnya.

## Tantangan dalam Pengenalan Objek

Upaya untuk merekonstruksi atau mengenali dunia visual dari struktur sederhana menghadapi tantangan. Pengenalan objek tetap sulit, dan sebagian besar upaya terbatas pada contoh-contoh mainan. Segmentasi objek, menggabungkan piksel-piksel menjadi area-area yang bermakna, menjadi fokus sebagai langkah awal sebelum pengenalan objek.

## Kemajuan dalam Deteksi Wajah

Teknik pembelajaran mesin, seperti mesin vektor dukungan, penguatan, dan jaringan saraf, mulai mendapatkan momentum pada akhir tahun 90-an dan awal tahun 2000-an. Algoritma AdaBoost memberikan kontribusi besar dalam deteksi wajah secara real-time, memungkinkan integrasi cepat ke dalam produk konsumen seperti kamera digital.

## Poin Utama:

1. Dunia Blok, proyek visi komputer awal, bertujuan menyederhanakan dunia visual menjadi bentuk-bentuk geometris untuk pengenalan.
2. Proses berpikir David Marr tentang "sketsa awal" dan "sketsa dua setengah dimensi" telah mempengaruhi visi komputer selama beberapa dekade.
3. Kemajuan dalam representasi dan segmentasi objek telah menjadi langkah penting menuju pengenalan objek dunia nyata.

# Sejarah Pengenalan Objek

## Pengenalan Objek Berbasis Fitur:

Pada akhir tahun 90-an dan awal 2000-an, pengenalan objek berbasis fitur menjadi pendekatan yang signifikan. Pendekatan ini melibatkan identifikasi fitur-fitur penting pada objek yang tetap tidak berubah terhadap perubahan sudut kamera, pencahayaan, dan sebagainya. Fitur-fitur ini kemudian dipadankan untuk mengenali objek lebih efisien daripada mencocokkan keseluruhan objek.

## Pengenalan Adegan Holistik:

Visi komputer berkembang untuk mengenali adegan secara holistik menggunakan algoritma seperti "Spatial Pyramid Matching". Fitur-fitur dari berbagai bagian gambar digabungkan dalam deskriptor fitur, yang memungkinkan pengenalan berbagai jenis adegan, seperti lanskap, dapur, atau jalan raya.

## Pengenalan Manusia: 

Teknik serupa diterapkan pada pengenalan manusia, melibatkan metode seperti "histogram of gradients" dan "deformable part models" untuk mengenali dan menyusun tubuh manusia dalam gambar.

### Poin Utama:

1. Pengenalan objek berbasis fitur melibatkan identifikasi fitur yang tidak berubah untuk mencocokkan dan mengenali objek dengan lebih efisien.
2. Pengenalan adegan holistik menggunakan fitur-fitur dari berbagai bagian gambar untuk mengklasifikasikan adegan.
3. Pengenalan manusia mengandalkan metode seperti "histogram of gradients" dan "deformable part models" untuk mengenali tubuh manusia dalam gambar.

## Lahirnya ImageNet dan Deep Learning:

Dipicu oleh keinginan untuk mengenali semua objek di dunia dan mengatasi masalah _overfitting_ dalam pembelajaran mesin, proyek ImageNet diluncurkan. Proyek ini mengumpulkan hampir 15 hingga 40 juta gambar dari ribuan kategori objek. Dataset besar ini mendorong perkembangan algoritma pengenalan objek lebih lanjut.

## Tantangan ImageNet dan Keberhasilan Deep Learning:

Tantangan ImageNet Skala Besar untuk Pengenalan Visual memberikan kumpulan data uji yang ketat untuk klasifikasi gambar. Tingkat kesalahan dalam klasifikasi gambar terus menurun dari tahun ke tahun. Pada tahun 2012, model jaringan saraf konvulsi (CNN) muncul sebagai terobosan, mengungguli algoritma lain dan mencapai tingkat kinerja manusia.

### Poin Utama:

1. Proyek ImageNet bertujuan untuk menciptakan dataset besar untuk pelatihan dan pengujian algoritma pengenalan objek.
2. Tantangan ImageNet mendorong perkembangan algoritma pengenalan objek, dan model CNN membuktikan sebagai terobosan.
3. Deep learning, terutama model CNN, menunjukkan potensi dan keberhasilannya dalam berbagai bidang, termasuk visi komputer, pemrosesan bahasa alami, dan pengenalan suara.

# Perkembangan Klasifikasi Gambar dengan Convolutional Neural Networks (CNNs)

## Pengenalan tentang Klasifikasi Gambar dan Masalah Terkait

Klasifikasi Gambar adalah algoritme yang memilih kategori tertentu dari sekumpulan kategori tetap untuk mengklasifikasikan sebuah gambar. Ini digunakan untuk mengenali makanan, karya seni, produk, dan banyak lagi.

## Masalah Klasifikasi Gambar dan Masalah Terkait

Terdapat beberapa masalah terkait, seperti deteksi objek, di mana kita menggambar kotak pembatas di sekitar objek dalam gambar, dan caption gambar, di mana sistem perlu menghasilkan kalimat bahasa alami yang menggambarkan gambar.

## Pentingnya Convolutional Neural Networks (CNNs) dalam Klasifikasi Gambar

CNNs telah menghadirkan titik terobosan dalam klasifikasi gambar sejak 2012 dan menjadi algoritme pemenang dalam kompetisi ImageNet setiap tahunnya. CNNs mengalami peningkatan dalam kompleksitas dan kedalaman dari arsitektur mereka, yang telah mempengaruhi peningkatan kinerja dalam klasifikasi gambar.

## Sejarah CNNs dan Inovasi Penting

Meskipun CNNs terkenal sejak tahun 2012, konsep ini sudah ada sejak tahun 1990-an, dan algoritme serupa telah digunakan untuk pengenalan angka. Perkembangan komputasi dan ketersediaan data berlabel memainkan peran kunci dalam meningkatkan kinerja CNNs. Ketersediaan GPU juga memungkinkan eksperimen dengan arsitektur dan model yang lebih besar.

## Tantangan dan Masa Depan

Walaupun CNNs memberikan kemajuan signifikan dalam klasifikasi gambar, bidang ini masih memiliki banyak tantangan yang harus diatasi. Beberapa di antaranya adalah segmentasi semantik, pemahaman 3D, pengenalan aktivitas, dan perkembangan augmented reality dan virtual reality.

## Inti Pesan:

- Klasifikasi Gambar adalah algoritme yang mengkategorikan gambar ke dalam kategori tertentu.
- Terdapat masalah terkait seperti deteksi objek dan caption gambar.
- CNNs adalah algoritme terobosan yang telah meningkatkan kinerja dalam klasifikasi gambar sejak 2012.

# Menyingkap Potensi dan Tantangan Visi Komputer

## Visi Komputer dan Potensinya

Dalam visi komputer, tujuan utamanya adalah memahami dan menginterpretasi gambar dengan cara yang melebihi klasifikasi sederhana. Pekerjaan lab visi fokus pada menangkap kompleksitas dunia nyata dengan mendeskripsikan gambar sebagai graf besar dengan konsep-konsep semantik yang saling terkait. Pendekatan ini mencakup identitas objek, hubungan objek, atribut objek, dan tindakan yang terjadi dalam adegan. Representasi yang lebih kaya ini memungkinkan pemahaman yang lebih mendalam tentang dunia visual, jauh melampaui apa yang dapat dicapai oleh klasifikasi gambar tradisional.

## Tantangan dalam Memahami Mendalam

Tujuan akhir visi komputer adalah mencapai pemahaman mendalam tentang gambar, mirip dengan cara manusia mempersepsikannya. Dalam sebuah studi, orang ditampilkan gambar selama setengah detik dan dapat menulis paragraf deskriptif panjang, bahkan cerita lengkap, tentang gambar tersebut. Tingkat pemahaman ini adalah aspirasi jangka panjang untuk visi komputer. Saat ini, algoritma visi komputer masih jauh dari mencapai pemahaman mendalam ini, meskipun bidang ini telah membuat kemajuan yang signifikan selama bertahun-tahun.

## Gambaran Umum dan Harapan dari Mata Kuliah

Mata kuliah visi komputer, yang diajarkan oleh Fei-Fei Li, bertujuan untuk mengeksplorasi mekanisme dari algoritma deep learning sambil memberikan paparan praktis terhadap alat perangkat lunak terbaru seperti TensorFlow dan PyTorch. Mahasiswa akan memperoleh pemahaman mendalam tentang jaringan saraf konvolusional dengan mengimplementasikannya dari awal. Mata kuliah ini juga mencakup topik-topik menarik dan artistik, seperti penjelasan gambar, DeepDream, dan transfer gaya.

## Takeaway Utama:

1. Visi komputer bertujuan untuk memahami gambar di luar klasifikasi sederhana dengan menciptakan representasi yang kaya dengan konsep-konsep semantik yang saling terkait.
2. Tujuan akhirnya adalah mencapai pemahaman mendalam tentang gambar, mirip dengan cara manusia mempersepsikannya.
3. Mata kuliah ini fokus pada pemahaman mendalam tentang algoritma deep learning dan paparan praktis terhadap alat perangkat lunak terbaru dalam visi komputer.
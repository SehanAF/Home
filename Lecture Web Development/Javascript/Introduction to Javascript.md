# [Kuliah 5](https://cs50.harvard.edu/web/2020/notes/5/#lecture-5)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/5/#introduction)
-   [JavaScript](https://cs50.harvard.edu/web/2020/notes/5/#javascript)
-   [Acara](https://cs50.harvard.edu/web/2020/notes/5/#events)
-   [Variabel](https://cs50.harvard.edu/web/2020/notes/5/#variables)
-   [`querySelector`](https://cs50.harvard.edu/web/2020/notes/5/#queryselector)
-   [Manipulasi DOM](https://cs50.harvard.edu/web/2020/notes/5/#dom-manipulation)
    -   [Konsol JavaScript](https://cs50.harvard.edu/web/2020/notes/5/#javascript-console)
    -   [Fungsi Panah](https://cs50.harvard.edu/web/2020/notes/5/#arrow-functions)
    -   [Daftar TODO](https://cs50.harvard.edu/web/2020/notes/5/#todo-list)
-   [Interval](https://cs50.harvard.edu/web/2020/notes/5/#intervals)
-   [Penyimpanan lokal](https://cs50.harvard.edu/web/2020/notes/5/#local-storage)
-   [Lebah](https://cs50.harvard.edu/web/2020/notes/5/#apis)
    -   [Objek JavaScript](https://cs50.harvard.edu/web/2020/notes/5/#javascript-objects)
    -   [Penukaran mata uang](https://cs50.harvard.edu/web/2020/notes/5/#currency-exchange)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/5/#introduction)

-   Sejauh ini, kita telah membahas cara membuat halaman web sederhana menggunakan HTML dan CSS, serta cara menggunakan Git dan GitHub untuk melacak perubahan pada kode kita dan berkolaborasi dengan orang lain. Kami juga membiasakan diri dengan bahasa pemrograman Python, mulai menggunakan Django untuk membuat aplikasi web, dan mempelajari cara menggunakan model Django untuk menyimpan informasi di situs kami.
-   Hari ini, kami akan memperkenalkan bahasa pemrograman baru: JavaScript.

## [JavaScript](https://cs50.harvard.edu/web/2020/notes/5/#javascript)

Mari kita mulai dengan meninjau kembali diagram dari beberapa kuliah yang lalu:

![Diagram Server Klien](https://cs50.harvard.edu/web/2020/notes/5/images/client_server.png)

Ingatlah bahwa di sebagian besar interaksi online, kami memiliki klien/pengguna yang mengirimkan Permintaan HTTP ke server, yang mengirimkan kembali Respons HTTP. Semua kode Python yang telah kita tulis sejauh ini menggunakan Django telah berjalan di server. JavaScript akan memungkinkan kita menjalankan kode di sisi klien, artinya tidak diperlukan interaksi dengan server saat sedang berjalan, memungkinkan situs web kita menjadi jauh lebih interaktif.

Untuk menambahkan beberapa JavaScript ke halaman kami, kami dapat menambahkan sepasang `<script>`tag di suatu tempat di halaman HTML kami. Kami menggunakan `<script>`tag untuk memberi sinyal ke browser bahwa apa pun yang kami tulis di antara kedua tag adalah kode JavaScript yang ingin kami jalankan saat pengguna mengunjungi situs kami. Program pertama kita mungkin terlihat seperti ini:

```
alert('Hello, world!');
```

Fungsi `alert`dalam JavaScript menampilkan pesan kepada pengguna yang kemudian dapat mereka abaikan. Untuk menunjukkan di mana ini akan cocok dengan dokumen HTML yang sebenarnya, berikut adalah contoh halaman sederhana dengan beberapa JavaScript:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello</title>
        <script>
            alert('Hello, world!');
        </script>
    </head>
    <body>
        <h1>Hello!</h1>
    </body>
</html>
```

![peringatan](https://cs50.harvard.edu/web/2020/notes/5/images/alert0.png)

## [Acara](https://cs50.harvard.edu/web/2020/notes/5/#events)

Salah satu fitur JavaScript yang membuatnya berguna untuk pemrograman web adalah mendukung [Pemrograman Berbasis Peristiwa](https://medium.com/@vsvaibhav2016/introduction-to-event-driven-programming-28161b79c223) .

Pemrograman Berbasis Peristiwa adalah paradigma pemrograman yang berpusat pada deteksi peristiwa, dan tindakan yang harus diambil saat peristiwa terdeteksi.

Suatu peristiwa bisa berupa apa saja termasuk tombol yang diklik, kursor yang dipindahkan, respons yang diketik, atau halaman yang dimuat. Hampir semua yang dilakukan pengguna untuk berinteraksi dengan halaman web dapat dianggap sebagai suatu peristiwa. Dalam JavaScript, kami menggunakan [Pendengar Peristiwa](https://www.w3schools.com/js/js_htmldom_eventlistener.asp) yang menunggu peristiwa tertentu terjadi, lalu mengeksekusi beberapa kode.

Mari kita mulai dengan mengubah JavaScript kita dari atas menjadi sebuah [fungsi](https://www.w3schools.com/js/js_functions.asp) bernama `hello`:

```
function hello() {
    alert('Hello, world!')
}
```

Sekarang, mari bekerja menjalankan fungsi ini setiap kali tombol diklik. Untuk melakukan ini, kami akan membuat tombol HTML di halaman kami dengan `onclick`atribut, yang memberikan instruksi browser tentang apa yang harus terjadi saat tombol diklik:

```
<button onclick="hello()">Click Here</button>
```

Perubahan ini memungkinkan kami menunggu untuk menjalankan bagian dari kode JavaScript kami hingga peristiwa tertentu terjadi.

## [Variabel](https://cs50.harvard.edu/web/2020/notes/5/#variables)

JavaScript adalah bahasa pemrograman seperti Python, C, atau bahasa lain yang pernah Anda gunakan sebelumnya, artinya JavaScript memiliki banyak fitur yang sama dengan bahasa lain termasuk variabel. Ada tiga kata kunci yang dapat kita gunakan untuk menetapkan nilai dalam JavaScript:

-   `var`: digunakan untuk mendefinisikan variabel secara global

```
var age = 20;
```

-   `let`: digunakan untuk mendefinisikan variabel yang ruang lingkupnya terbatas pada blok saat ini seperti fungsi atau loop

```
let counter = 1;
```

-   `const`: digunakan untuk menentukan nilai yang tidak akan berubah

```
const PI = 3.14;
```

Sebagai contoh bagaimana kita dapat menggunakan variabel, mari kita lihat halaman yang melacak penghitung:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Count</title>
        <script>
            let counter = 0;
            function count() {
                counter++;
                alert(counter);
            }
        </script>
    </head>
    <body>
        <h1>Hello!</h1>
        <button onclick="count()">Count</button>
    </body>
</html>
```

![perhitungan](https://cs50.harvard.edu/web/2020/notes/5/images/count.gif)

## [`querySelector`](https://cs50.harvard.edu/web/2020/notes/5/#queryselector)

Selain memungkinkan kita untuk menampilkan pesan melalui alert, JavaScript juga memungkinkan kita untuk mengubah elemen pada halaman. Untuk melakukan ini, pertama-tama kita harus memperkenalkan fungsi yang disebut `document.querySelector`. Fungsi ini mencari dan mengembalikan elemen DOM. Misalnya, kami akan menggunakan:

```
let heading = document.querySelector('h1');
```

untuk mengekstrak judul. Lalu, untuk memanipulasi elemen yang baru kita temukan, kita bisa mengubah propertinya `innerHTML`:

```
heading.innerHTML = `Goodbye!`;
```

Sama seperti di Python, kita juga bisa memanfaatkan [kondisi](https://www.w3schools.com/js/js_if_else.asp) di JavaScript. Sebagai contoh, katakanlah daripada selalu mengubah tajuk kita menjadi `Goodbye!`, kita ingin bolak-balik antara `Hello!`dan `Goodbye!`. Halaman kami kemudian mungkin terlihat seperti di bawah ini. Perhatikan bahwa dalam JavaScript, kami menggunakan `===`perbandingan yang lebih kuat antara dua item yang juga memeriksa bahwa objek memiliki tipe yang sama. Kami biasanya ingin menggunakan `===`bila memungkinkan.

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Count</title>
        <script>
            function hello() {
                const header = document.querySelector('h1');
                if (header.innerHTML === 'Hello!') {
                    header.innerHTML = 'Goodbye!';
                }
                else {
                    header.innerHTML = 'Hello!';
                }
            }
        </script>
    </head>
    <body>
        <h1>Hello!</h1>
        <button onclick="hello()">Click Here</button>
    </body>
</html>
```

![beralih](https://cs50.harvard.edu/web/2020/notes/5/images/toggle.gif)

## [Manipulasi DOM](https://cs50.harvard.edu/web/2020/notes/5/#dom-manipulation)

Mari kita gunakan ide manipulasi DOM ini untuk meningkatkan halaman penghitung kita:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Count</title>
        <script>
            let counter = 0;
            function count() {
                counter++;
                document.querySelector('h1').innerHTML = counter;
            }
        </script>
    </head>
    <body>
        <h1>0</h1>
        <button onclick="count()">Count</button>
    </body>
</html>
```

![hitungan 2](https://cs50.harvard.edu/web/2020/notes/5/images/count2.gif)

Kami dapat membuat halaman ini lebih menarik dengan menampilkan peringatan setiap kali penghitung mencapai kelipatan sepuluh. Dalam lansiran ini, kita ingin memformat string untuk menyesuaikan pesan, yang dalam JavaScript dapat kita lakukan menggunakan [template literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) . Template literal mengharuskan adanya backticks ( `` ` ``) di sekitar seluruh ekspresi dan tanda kurung kurawal $ dan kurawal di sekitar substitusi. Sebagai contoh, mari ubah fungsi hitungan kita

```
function count() {
    counter++;
    document.querySelector('h1').innerHTML = counter;
    
    if (counter % 10 === 0) {
        alert(`Count is now ${counter}`)
    }
}
```

![menghitung dengan waspada](https://cs50.harvard.edu/web/2020/notes/5/images/count3.gif)

Sekarang, mari kita lihat beberapa cara untuk meningkatkan desain halaman ini. Pertama, sama seperti kami mencoba untuk menghindari gaya sebaris dengan CSS, kami ingin menghindari JavaScript sebaris sebanyak mungkin. Kita dapat melakukannya dalam contoh penghitung kita dengan menambahkan baris skrip yang mengubah atribut `onclick`tombol pada laman, dan menghapus `onclick`atribut dari dalam `button`tag.

```
document.querySelector('button').onclick = count;
```

Satu hal yang perlu diperhatikan tentang apa yang baru saja kita lakukan adalah kita tidak memanggil fungsi `count`dengan menambahkan tanda kurung setelahnya, tetapi hanya menamai fungsinya. Ini menentukan bahwa kami hanya ingin memanggil fungsi ini saat tombol diklik. Ini berfungsi karena, seperti Python, JavaScript mendukung pemrograman fungsional, sehingga fungsi dapat diperlakukan sebagai nilai itu sendiri.

The above change alone is not enough though, as we can see by inspecting the page and looking at our browser’s console:

![konsol kesalahan](https://cs50.harvard.edu/web/2020/notes/5/images/error0.png)

This error came up because when JavaScript searched for an element using `document.querySelector('button')`, it didn’t find anything. This is because it takes a small bit of time for the page to load, and our JavaScript code ran before the button had been rendered. To account for this, we can specify that code will run only after the page has loaded using the [addEventListener](https://www.w3schools.com/jsref/met_document_addeventlistener.asp) function. This function takes in two arguments:

1.  An event to listen for (eg: `'click'`)
2.  A function to run when the event is detected (eg: `hello` from above)

We can use the function to only run the code once all content has loaded:

```
document.addEventListener('DOMContentLoaded', function() {
    // Some code here
});
```

In the example above, we’ve used an [anonymous](https://www.w3schools.com/js/js_function_definition.asp) function, which is a function that is never given a name. Putting all of this together, our JavaScript now looks like this:

```
let counter = 0;

function count() {
    counter++;
    document.querySelector('h1').innerHTML = counter;
    
    if (counter % 10 === 0) {
        alert(`Count is now ${counter}`)
    }
}

document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('button').onclick = count;
});
```

Another way that we can improve our design is by moving our JavaScript into a separate file. The way we do this is very similar to how we put our CSS in a separate file for styling:

1.  Write all of your JavaScript code in a separate file ending in `.js`, maybe `index.js`.
2.  Add a `src` attribute to the `<script>` tag that points to this new file.

For our counter page, we could have a file called `counter.html` that looks like this:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Count</title>
        <script src="counter.js"></script>
    </head>
    <body>
        <h1>0</h1>
        <button>Count</button>
    </body>
</html>
```

And a file called `counter.js` that looks like this:

```
let counter = 0;
            
function count() {
    counter++;
    document.querySelector('h1').innerHTML = counter;
    
    if (counter % 10 === 0) {
        alert(`Count is now ${counter}`)
    }
}

document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('button').onclick = count;
});
```

Having JavaScript in a separate file is useful for a number of reasons:

-   Daya tarik visual: File HTML dan JavaScript individual kami menjadi lebih mudah dibaca.
-   Akses di antara file HTML: Sekarang kita dapat memiliki banyak file HTML yang semuanya menggunakan JavaScript yang sama.
-   Kolaborasi: Sekarang kita dapat dengan mudah membuat satu orang mengerjakan JavaScript sementara yang lain mengerjakan HTML.
-   Mengimpor: Kami dapat mengimpor pustaka JavaScript yang telah ditulis orang lain. Misalnya [Bootstrap](https://getbootstrap.com/docs/4.5/getting-started/introduction/#js) memiliki pustaka JavaScript sendiri yang dapat Anda sertakan untuk membuat situs Anda lebih interaktif.

Mari kita mulai dengan contoh lain dari halaman yang bisa sedikit lebih interaktif. Di bawah ini, kami akan membuat halaman tempat pengguna dapat mengetikkan nama mereka untuk mendapatkan sapaan khusus.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Hello</title>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            document.querySelector('form').onsubmit = function() {
                const name = document.querySelector('#name').value;
                alert(`Hello, ${name}`);
            };
        });
    </script>
</head>
<body>
    <form>
        <input autofocus id="name" placeholder="Name" type="text">
        <input type="submit">
    </form>
</body>
</html>
```

![Salam Demo](https://cs50.harvard.edu/web/2020/notes/5/images/greet.gif)

Beberapa catatan tentang halaman di atas:

-   Kami menggunakan `autofocus`bidang di `name`input untuk menunjukkan bahwa kursor harus diatur di dalam input itu segera setelah halaman dimuat.
-   Kami menggunakan `#name`inside of `document.querySelector`untuk menemukan elemen dengan `id`of `name`. Kita bisa menggunakan semua penyeleksi yang sama dalam fungsi ini seperti yang bisa kita lakukan di CSS.
-   Kami menggunakan `value`atribut kolom input untuk menemukan apa yang sedang diketik.

Kita dapat melakukan lebih dari sekadar menambahkan HTML ke halaman kita menggunakan JavaScript, kita juga dapat mengubah gaya halaman! Pada halaman di bawah ini, kami menggunakan tombol untuk mengubah warna heading kami.

```
<!DOCTYPE html>
<html lang="en">
<head>
     <title>Colors</title>
     <script>
         document.addEventListener('DOMContentLoaded', function() {
            document.querySelectorAll('button').forEach(function(button) {
                button.onclick = function() {
                    document.querySelector("#hello").style.color = button.dataset.color;
                }
            });
         });
     </script>
</head>
<body>
    <h1 id="hello">Hello</h1>
    <button data-color="red">Red</button>
    <button data-color="blue">Blue</button>
    <button data-color="green">Green</button>
</body>
</html>
```

![Demo warna](https://cs50.harvard.edu/web/2020/notes/5/images/colors.gif)

Beberapa catatan pada halaman di atas:

-   Kami mengubah gaya elemen menggunakan `style.SOMETHING`atribut.
-   We use the `data-SOMETHING` attribute to assign data to an HTML element. We can later access that data in JavaScript using the element’s `dataset` property.
-   We use the `querySelectorAll` function to get an [Node List](https://www.w3schools.com/js/js_htmldom_nodelist.asp) (similar to a Python list or a JavaScript [array](https://www.w3schools.com/js/js_arrays.asp)) with all elements that match the query.
-   The [forEach](https://www.w3schools.com/jsref/jsref_foreach.asp) function in JavaScript takes in another function, and applies that function to each element in a list or array.

### [JavaScript Console](https://cs50.harvard.edu/web/2020/notes/5/#javascript-console)

The console is a useful tool for testing out small bits of code and debugging. You can write and run JavaScript code in the console, which can be found by inspecting element in your web browser and then clicking `console`. (The exact process may change frome browser to browser.) One useful tool for debugging is printing to the console, which you can do using the `console.log` function. For example, in the `colors.html` page above, I can add the following line:

```
console.log(document.querySelectorAll('button'));
```

Which gives us this in the console:

![daftar simpul](https://cs50.harvard.edu/web/2020/notes/5/images/consoleList.png)

### [Arrow Functions](https://cs50.harvard.edu/web/2020/notes/5/#arrow-functions)

Selain notasi fungsi tradisional yang telah kita lihat, JavaScript sekarang memberi kita kemampuan untuk menggunakan [Fungsi Panah](https://www.w3schools.com/js/js_arrow_function.asp) di mana kita memiliki masukan (atau tanda kurung jika tidak ada masukan) diikuti `=>`dengan beberapa kode untuk dijalankan. Misalnya, kita dapat mengubah skrip kita di atas untuk menggunakan fungsi panah anonim:

```
document.addEventListener('DOMContentLoaded', () => {
    document.querySelectorAll('button').forEach(button => {
        button.onclick = () => {
            document.querySelector("#hello").style.color = button.dataset.color;
        }
    });
});
```

Kami juga dapat menamai fungsi yang menggunakan panah, seperti dalam penulisan ulang fungsi hitungan ini:

```
count = () => {
    counter++;
    document.querySelector('h1').innerHTML = counter;
    
    if (counter % 10 === 0) {
        alert(`Count is now ${counter}`)
    }
}
```

Untuk mendapatkan ide tentang beberapa event lain yang bisa kita gunakan, mari kita lihat bagaimana kita bisa mengimplementasikan pengalih warna kita menggunakan menu dropdown daripada tiga tombol terpisah. Kami dapat mendeteksi perubahan dalam `select`elemen menggunakan `onchange`atribut. Dalam JavaScript, [ini](https://www.w3schools.com/js/js_this.asp) adalah kata kunci yang berubah berdasarkan konteks penggunaannya. Dalam kasus event handler, `this`mengacu pada objek yang memicu event.

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Colors</title>
        <script>
            document.addEventListener('DOMContentLoaded', function() {
                document.querySelector('select').onchange = function() {
                    document.querySelector('#hello').style.color = this.value;
                }
            });
        </script>
    </head>
    <body>
        <h1 id="hello">Hello</h1>
        <select>
            <option value="black">Black</option>
            <option value="red">Red</option>
            <option value="blue">Blue</option>
            <option value="green">Green</option>
        </select>

    </body>
</html>
```

![warna dengan dropdown](https://cs50.harvard.edu/web/2020/notes/5/images/colors2.gif)

Ada banyak [peristiwa](https://www.w3schools.com/js/js_events.asp) lain yang dapat kami deteksi dalam JavaScript, termasuk yang umum di bawah ini:

-   `onclick`
-   `onmouseover`
-   `onkeydown`
-   `onkeyup`
-   `onload`
-   `onblur`
-   …

### [Daftar TODO](https://cs50.harvard.edu/web/2020/notes/5/#todo-list)

Untuk menyatukan beberapa hal yang telah kita pelajari dalam kuliah ini, mari bekerja membuat daftar TODO seluruhnya dalam JavaScript. Kita akan mulai dengan menulis layout HTML halaman. Perhatikan di bawah bagaimana kami menyisakan ruang untuk daftar yang tidak diurutkan, tetapi kami belum menambahkan apa pun ke dalamnya. Perhatikan juga bahwa kami menambahkan tautan ke `tasks.js`tempat kami akan menulis JavaScript kami.

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Tasks</title>
        <script src="tasks.js"></script>
    </head>
    <body>
        <h1>Tasks</h1>
        <ul id="tasks"></ul>
        <form>
            <input id="task" placeholder = "New Task" type="text">
            <input id="submit" type="submit">
        </form>
    </body>
</html>
```

Sekarang, inilah kode kami yang dapat kami simpan `tasks.js`. Beberapa catatan tentang apa yang akan Anda lihat di bawah:

-   Kode ini sedikit berbeda dengan kode di perkuliahan. Di sini, kami hanya meminta tombol kirim dan bidang tugas input sekali di awal dan menyimpan kedua nilai tersebut dalam variabel `submit`dan `newTask`.
-   Kita dapat mengaktifkan/menonaktifkan tombol dengan menyetel atributnya `disabled`ke `false`/ `true`.
-   Dalam JavaScript, kami menggunakan `.length`untuk menemukan panjang objek seperti string dan array.
-   Di akhir skrip, kami menambahkan baris `return false`. Ini mencegah pengiriman default formulir yang melibatkan memuat ulang halaman saat ini atau mengalihkan ke yang baru.
-   Dalam JavaScript, kita dapat membuat elemen HTML menggunakan fungsi [createElement](https://www.w3schools.com/jsref/met_document_createelement.asp) . Kami kemudian dapat menambahkan elemen tersebut ke DOM menggunakan `append`fungsi.

```
// Wait for page to load
document.addEventListener('DOMContentLoaded', function() {

    // Select the submit button and input to be used later
    const submit = document.querySelector('#submit');
    const newTask = document.querySelector('#task');

    // Disable submit button by default:
    submit.disabled = true;

    // Listen for input to be typed into the input field
    newTask.onkeyup = () => {
        if (newTask.value.length > 0) {
            submit.disabled = false;
        }
        else {
            submit.disabled = true;
        }
    }

    // Listen for submission of form
    document.querySelector('form').onsubmit = () => {

        // Find the task the user just submitted
        const task = newTask.value;

        // Create a list item for the new task and add the task to it
        const li = document.createElement('li');
        li.innerHTML = task;

        // Add new element to our unordered list:
        document.querySelector('#tasks').append(li);

        // Clear out input field:
        newTask.value = '';

        // Disable the submit button again:
        submit.disabled = true;

        // Stop form from submitting
        return false;
    }
});
```

![Demo tugas](https://cs50.harvard.edu/web/2020/notes/5/images/tasks.gif)

## [Interval](https://cs50.harvard.edu/web/2020/notes/5/#intervals)

Selain menentukan bahwa fungsi berjalan saat suatu peristiwa dipicu, kita juga dapat mengatur fungsi untuk berjalan setelah waktu yang ditentukan. Sebagai contoh, mari kembali ke skrip halaman penghitung kita, dan tambahkan interval sehingga meskipun pengguna tidak mengklik apa pun, penghitung bertambah setiap detik. Untuk melakukan ini, kami menggunakan fungsi [setInterval](https://www.w3schools.com/jsref/met_win_setinterval.asp) , yang menggunakan argumen untuk menjalankan fungsi, dan waktu (dalam milidetik) antara fungsi berjalan.

```
let counter = 0;
            
function count() {
    counter++;
    document.querySelector('h1').innerHTML = counter;
}

document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('button').onclick = count;

    setInterval(count, 1000);
});
```

![menghitung otomatis](https://cs50.harvard.edu/web/2020/notes/5/images/count4.gif)

## [Penyimpanan lokal](https://cs50.harvard.edu/web/2020/notes/5/#local-storage)

Satu hal yang perlu diperhatikan tentang semua situs kami sejauh ini adalah setiap kali kami memuat ulang halaman, semua informasi kami hilang. Warna tajuk kembali menjadi hitam, penghitung kembali ke 0, dan semua tugas dihapus. Terkadang ini yang kami maksudkan, tetapi di lain waktu kami ingin dapat menyimpan informasi yang dapat kami gunakan saat pengguna kembali ke situs.

Salah satu cara yang dapat kita lakukan adalah dengan menggunakan [Penyimpanan Lokal](https://www.w3schools.com/jsref/prop_win_localstorage.asp) , atau menyimpan informasi di browser web pengguna yang dapat kita akses nanti. Informasi ini disimpan sebagai sekumpulan key-value pair, hampir seperti kamus Python. Untuk menggunakan penyimpanan lokal, kami akan menerapkan dua fungsi utama:

-   `localStorage.getItem(key)`: Fungsi ini mencari entri di penyimpanan lokal dengan kunci tertentu, dan mengembalikan nilai yang terkait dengan kunci tersebut.
-   `localStorage.setItem(key, value)`: Fungsi ini menyetel dan masuk ke penyimpanan lokal, mengaitkan kunci dengan nilai baru.

Mari kita lihat bagaimana kita dapat menggunakan fungsi baru ini untuk memperbarui penghitung kita! Pada kode di bawah ini,

```
// Check if there is already a vlaue in local storage
if (!localStorage.getItem('counter')) {

    // If not, set the counter to 0 in local storage
    localStorage.setItem('counter', 0);
}
            
function count() {
    // Retrieve counter value from local storage
    let counter = localStorage.getItem('counter');

    // update counter
    counter++;
    document.querySelector('h1').innerHTML = counter;

    // Store counter in local storage
    localStorage.setItem('counter', counter);
}

document.addEventListener('DOMContentLoaded', function() {
    // Set heading to the current value inside local storage
    document.querySelector('h1').innerHTML = localStorage.getItem('counter');
    document.querySelector('button').onclick = count;
});
```

## [Lebah](https://cs50.harvard.edu/web/2020/notes/5/#apis)

### [Objek JavaScript](https://cs50.harvard.edu/web/2020/notes/5/#javascript-objects)

Objek [JavaScript](https://www.w3schools.com/js/js_objects.asp) sangat mirip dengan kamus Python, karena memungkinkan kita untuk menyimpan pasangan nilai kunci. Misalnya, saya dapat membuat Objek JavaScript yang mewakili Harry Potter:

```
let person = {
    first: 'Harry',
    last: 'Potter'
};
```

Saya kemudian dapat mengakses atau mengubah bagian dari objek ini menggunakan notasi braket atau titik:

![Harry Potter](https://cs50.harvard.edu/web/2020/notes/5/images/console.png)

Salah satu cara Objek JavaScript sangat berguna adalah dalam mentransfer data dari satu situs ke situs lainnya, terutama saat menggunakan [API](https://www.mulesoft.com/resources/api/what-is-an-api)

API, atau Antarmuka Pemrograman Aplikasi, adalah bentuk komunikasi terstruktur antara dua aplikasi yang berbeda.

Misalnya, kami mungkin ingin aplikasi kami mendapatkan informasi dari Google Maps, Amazon, atau beberapa layanan cuaca. Kita dapat melakukannya dengan melakukan panggilan ke API layanan, yang akan mengembalikan data terstruktur kepada kita, seringkali dalam bentuk [JSON](https://www.w3schools.com/js/js_json_intro.asp) (JavaScript Object Notation). Misalnya, penerbangan dalam bentuk JSON mungkin terlihat seperti ini:

```
{
    "origin": "New York",
    "destination": "London",
    "duration": 415
}
```

Nilai-nilai dalam JSON tidak harus berupa string dan angka seperti pada contoh di atas. Kami juga dapat menyimpan daftar, atau bahkan Objek JavaScript lainnya:

```
{
    "origin": {
        "city": "New York",
        "code": "JFK"
    },
    "destination": {
        "city": "London",
        "code": "LHR"
    },
    "duration": 415
}
```

### [Penukaran mata uang](https://cs50.harvard.edu/web/2020/notes/5/#currency-exchange)

Untuk menunjukkan bagaimana kita dapat menggunakan API dalam aplikasi kita, mari bekerja membuat aplikasi di mana kita dapat menemukan nilai tukar antara dua mata uang. Sepanjang latihan, kami akan menggunakan [API Nilai Tukar Bank Sentral Eropa](https://exchangeratesapi.io/) . Dengan mengunjungi situs web mereka, Anda akan melihat dokumentasi API, yang umumnya merupakan tempat yang baik untuk memulai saat Anda ingin menggunakan API. Kita bisa menguji api ini dengan mengunjungi URL: [https://api.exchangeratesapi.io/latest?base=USD](https://api.exchangeratesapi.io/latest?base=USD) . Saat Anda mengunjungi halaman ini, Anda akan melihat nilai tukar antara Dolar AS dan banyak mata uang lainnya, yang ditulis dalam bentuk JSON. Anda juga dapat mengubah parameter GET di URL dari `USD`kode mata uang lain untuk mengubah tarif yang Anda dapatkan.

Mari kita lihat cara mengimplementasikan API ini ke dalam aplikasi dengan membuat file HTML baru bernama `currency.html`dan menautkannya ke file JavaScript tetapi biarkan badannya kosong:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Currency Exchange</title>
        <script src="currency.js"></script>
    </head>
    <body></body>
</html>
```

Sekarang, kita akan menggunakan sesuatu yang disebut [AJAX](https://www.w3schools.com/js/js_ajax_intro.asp) , atau Asynchronous JavaScript And XML, yang memungkinkan kita mengakses informasi dari halaman eksternal bahkan setelah halaman kita dimuat. Untuk melakukan ini, kami akan menggunakan fungsi [pengambilan](https://javascript.info/fetch) yang memungkinkan kami mengirim permintaan HTTP. Fungsi `fetch`mengembalikan [janji](https://web.dev/promises/) . Kami tidak akan berbicara tentang detail tentang apa itu janji di sini, tetapi kami dapat menganggapnya sebagai nilai yang akan muncul pada titik tertentu, tetapi tidak harus segera. Kami menangani janji dengan memberi mereka `.then`atribut yang menjelaskan apa yang harus dilakukan ketika kami mendapatkan `response`. Cuplikan kode di bawah ini akan mencatat tanggapan kita ke konsol.

```
document.addEventListener('DOMContentLoaded', function() {
    // Send a GET request to the URL
    fetch('https://api.exchangeratesapi.io/latest?base=USD')
    // Put response into json form
    .then(response => response.json())
    .then(data => {
        // Log data to the console
        console.log(data);
    });
});
```

![Log mata uang](https://cs50.harvard.edu/web/2020/notes/5/images/curr_log.png)

One important point about the above code is that the argument of `.then` is always a function. Although it seems we are creating the variables `response` and and `data`, those variables are just the parameters of two anonymous functions.

Rather than simply logging this data, we can use JavaScript to display a message to the screen, as in the code below:

```
document.addEventListener('DOMContentLoaded', function() {
    // Send a GET request to the URL
    fetch('https://api.exchangeratesapi.io/latest?base=USD')
    // Put response into json form
    .then(response => response.json())
    .then(data => {

        // Get rate from data
        const rate = data.rates.EUR;

        // Display message on the screen
        document.querySelector('body').innerHTML = `1 USD is equal to ${rate.toFixed(3)} EUR.`;
    });
});
```

![Mata uang](https://cs50.harvard.edu/web/2020/notes/5/images/exhange.png)

Now, let’s make the site a bit more interactive by allowing the user to choose which currency they would like to see. We’ll start by altering our HTML to allow the user to input a currency:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Currency Exchange</title>
        <script src="currency.js"></script>
    </head>
    <body>
        <form>
            <input id="currency" placeholder="Currency" type="text">
            <input type="submit" value="Convert">
        </form>
        <div id="result"></div>
    </body>
</html>
```

Now, we’ll make some changes to our JavaScript so it only changes when the form is submitted, and so it takes into account the user’s input. We’ll also add some error checking here:

```
document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('form').onsubmit = function() {

        // Send a GET request to the URL
        fetch('https://api.exchangeratesapi.io/latest?base=USD')
        // Put response into json form
        .then(response => response.json())
        .then(data => {
            // Get currency from user input and convert to upper case
            const currency = document.querySelector('#currency').value.toUpperCase();

            // Get rate from data
            const rate = data.rates[currency];

            // Check if currency is valid:
            if (rate !== undefined) {
                // Display exchange on the screen
                document.querySelector('#result').innerHTML = `1 USD is equal to ${rate.toFixed(3)} ${currency}.`;
            }
            else {
                // Display error on the screen
                document.querySelector('#result').innerHTML = 'Invalid Currency.';
            }
        })
        // Catch any errors and log them to the console
        .catch(error => {
            console.log('Error:', error);
        });
        // Prevent default submission
        return false;
    }
});
```

![Pertukaran demo](https://cs50.harvard.edu/web/2020/notes/5/images/exchange.gif)

Itu saja untuk kuliah ini! Lain kali, kita akan berupaya menggunakan JavaScript untuk membuat antarmuka pengguna yang lebih menarik!
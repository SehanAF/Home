# [Kuliah 6](https://cs50.harvard.edu/web/2020/notes/6/#lecture-6)

-   [Perkenalan](https://cs50.harvard.edu/web/2020/notes/6/#introduction)
-   [Antarmuka pengguna](https://cs50.harvard.edu/web/2020/notes/6/#user-interfaces)
-   [Aplikasi Satu Halaman](https://cs50.harvard.edu/web/2020/notes/6/#single-page-applications)
-   [Menggulir](https://cs50.harvard.edu/web/2020/notes/6/#scroll)
    -   [Gulir Tak Terbatas](https://cs50.harvard.edu/web/2020/notes/6/#infinite-scroll)
-   [Animasi](https://cs50.harvard.edu/web/2020/notes/6/#animation)
-   [Reaksi](https://cs50.harvard.edu/web/2020/notes/6/#react)
    -   [Tambahan](https://cs50.harvard.edu/web/2020/notes/6/#addition)

## [Perkenalan](https://cs50.harvard.edu/web/2020/notes/6/#introduction)

-   Sejauh ini, kita telah membahas cara membuat halaman web sederhana menggunakan HTML dan CSS, serta cara menggunakan Git dan GitHub untuk melacak perubahan pada kode kita dan berkolaborasi dengan orang lain. Kami juga membiasakan diri dengan bahasa pemrograman Python, mulai menggunakan Django untuk membuat aplikasi web, dan mempelajari cara menggunakan model Django untuk menyimpan informasi di situs kami. Kami kemudian memperkenalkan JavaScript dan mempelajari cara menggunakannya untuk membuat halaman web lebih interaktif.
-   Hari ini, kita akan membahas paradigma umum dalam desain Antarmuka Pengguna, menggunakan JavaScript dan CSS untuk membuat situs kita lebih ramah pengguna.

## [Antarmuka pengguna](https://cs50.harvard.edu/web/2020/notes/6/#user-interfaces)

Antarmuka Pengguna adalah cara pengunjung halaman web berinteraksi dengan halaman tersebut. Tujuan kami sebagai pengembang web adalah membuat interaksi ini senyaman mungkin bagi pengguna, dan ada banyak metode yang dapat kami gunakan untuk melakukannya.

## [Aplikasi Satu Halaman](https://cs50.harvard.edu/web/2020/notes/6/#single-page-applications)

Sebelumnya, jika kami menginginkan situs web dengan banyak halaman, kami akan melakukannya dengan menggunakan rute berbeda di aplikasi Django kami. Sekarang, kami memiliki kemampuan untuk memuat hanya satu halaman dan kemudian menggunakan JavaScript untuk memanipulasi DOM. Salah satu keuntungan utama melakukan ini adalah kita hanya perlu memodifikasi bagian halaman yang benar-benar berubah. Misalnya, jika kami memiliki Nav Bar yang tidak berubah berdasarkan halaman Anda saat ini, kami tidak ingin merender ulang Nav Bar itu setiap kali kami beralih ke bagian baru halaman.

Mari kita lihat contoh bagaimana kita dapat mensimulasikan peralihan halaman dalam JavaScript:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Single Page</title>
        <style>
            div {
                display: none;
            }
        </style>
        <script src="singlepage.js"></script>
    </head>
    <body>
        <button data-page="page1">Page 1</button>
        <button data-page="page2">Page 2</button>
        <button data-page="page3">Page 3</button>
        <div id="page1">
            <h1>This is page 1</h1>
        </div>
        <div id="page2">
            <h1>This is page 2</h1>
        </div>
        <div id="page3">
            <h1>This is page 3</h1>
        </div>
    </body>
</html>
```

Perhatikan pada HTML di atas bahwa kita memiliki tiga tombol dan tiga div. Saat ini, div hanya berisi sedikit teks, tetapi kami dapat membayangkan setiap div berisi konten dari satu halaman di situs kami. Sekarang, kami akan menambahkan beberapa JavaScript yang memungkinkan kami menggunakan tombol untuk beralih antar halaman.

```
// Shows one page and hides the other two
function showPage(page) {

    // Hide all of the divs:
    document.querySelectorAll('div').forEach(div => {
        div.style.display = 'none';
    });

    // Show the div provided in the argument
    document.querySelector(`#${page}`).style.display = 'block';
}

// Wait for page to loaded:
document.addEventListener('DOMContentLoaded', function() {

    // Select all buttons
    document.querySelectorAll('button').forEach(button => {

        // When a button is clicked, switch to that page
        button.onclick = function() {
            showPage(this.dataset.page);
        }
    })
});
```

![satu halaman 1](https://cs50.harvard.edu/web/2020/notes/6/images/singlepage1.gif)

Dalam banyak kasus, akan menjadi tidak efisien untuk memuat seluruh konten dari setiap halaman saat kita pertama kali mengunjungi sebuah situs, jadi kita perlu menggunakan server untuk mengakses data baru. Misalnya, saat Anda mengunjungi situs berita, akan memakan waktu terlalu lama untuk memuat situs jika harus memuat setiap artikel yang tersedia saat Anda pertama kali mengunjungi halaman tersebut. Kita dapat menghindari masalah ini dengan menggunakan strategi yang mirip dengan yang kita gunakan saat memuat nilai tukar mata uang pada kuliah sebelumnya. Kali ini, kita akan melihat penggunaan Django untuk mengirim dan menerima informasi dari aplikasi satu halaman kita. Untuk menunjukkan cara kerjanya, mari kita lihat aplikasi Django sederhana. Ini memiliki dua pola URL di `urls.py`:

```
urlpatterns = [
    path("", views.index, name="index"),
    path("sections/<int:num>", views.section, name="section")
]
```

Dan dua rute yang sesuai di `views.py`. Perhatikan bahwa `section`rute mengambil bilangan bulat, lalu mengembalikan string teks berdasarkan bilangan bulat itu sebagai Respons HTTP.

```
from django.http import Http404, HttpResponse
from django.shortcuts import render

# Create your views here.
def index(request):
    return render(request, "singlepage/index.html")

# The texts are much longer in reality, but have
# been shortened here to save space
texts = ["Text 1", "Text 2", "Text 3"]

def section(request, num):
    if 1 <= num <= 3:
        return HttpResponse(texts[num - 1])
    else:
        raise Http404("No such section")
```

Sekarang, di dalam file kita `index.html`, kita akan memanfaatkan AJAX, yang kita pelajari tentang kuliah terakhir, untuk membuat permintaan ke server untuk mendapatkan teks dari bagian tertentu dan menampilkannya di layar:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Single Page</title>
        <style>
        </style>
        <script>

            // Shows given section
            function showSection(section) {
                
                // Find section text from server
                fetch(`/sections/${section}`)
                .then(response => response.text())
                .then(text => {
                    // Log text and display on page
                    console.log(text);
                    document.querySelector('#content').innerHTML = text;
                });
            }

            document.addEventListener('DOMContentLoaded', function() {
                // Add button functionality
                document.querySelectorAll('button').forEach(button => {
                    button.onclick = function() {
                        showSection(this.dataset.section);
                    };
                });
            });
        </script>
    </head>
    <body>
        <h1>Hello!</h1>
        <button data-section="1">Section 1</button>
        <button data-section="2">Section 2</button>
        <button data-section="3">Section 3</button>
        <div id="content">
        </div>
    </body>
</html>
```

![Satu halaman 2](https://cs50.harvard.edu/web/2020/notes/6/images/singlepage2.gif)

Sekarang, kami telah membuat situs tempat kami dapat memuat data baru dari server tanpa memuat ulang seluruh halaman HTML kami!

Namun satu kelemahan dari situs kami adalah URL sekarang kurang informatif. Anda akan melihat dalam video di atas bahwa URL tetap sama meskipun kami beralih dari satu bagian ke bagian lain. Kami dapat mengatasi masalah ini menggunakan [JavaScript History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API) . API ini memungkinkan kami untuk mendorong informasi ke riwayat browser kami dan memperbarui URL secara manual. Mari kita lihat bagaimana kita bisa menggunakan API ini. Bayangkan kami memiliki proyek Django yang identik dengan yang sebelumnya, tetapi kali ini kami ingin mengubah skrip kami untuk menggunakan API sejarah:

```
// When back arrow is clicked, show previous section
window.onpopstate = function(event) {
    console.log(event.state.section);
    showSection(event.state.section);
}

function showSection(section) {
    fetch(`/sections/${section}`)
    .then(response => response.text())
    .then(text => {
        console.log(text);
        document.querySelector('#content').innerHTML = text;
    });

}

document.addEventListener('DOMContentLoaded', function() {
    document.querySelectorAll('button').forEach(button => {
        button.onclick = function() {
            const section = this.dataset.section;

            // Add the current state to the history
            history.pushState({section: section}, "", `section${section}`);
            showSection(section);
        };
    });
});
```

Pada `showSection`fungsi di atas, kita menggunakan `history.pushState`fungsi tersebut. Fungsi ini menambahkan elemen baru ke riwayat penelusuran kami berdasarkan tiga argumen:

1.  Setiap data yang terkait dengan negara bagian.
2.  Parameter judul diabaikan oleh sebagian besar browser web
3.  Apa yang harus ditampilkan di URL

Perubahan lain yang kita buat pada JavaScript di atas adalah pengaturan `onpopstate`parameter, yang menentukan apa yang harus kita lakukan saat pengguna mengklik panah kembali. Dalam hal ini, kami ingin menampilkan bagian sebelumnya saat tombol ditekan. Sekarang, situs terlihat sedikit lebih ramah pengguna:

![satu halaman dengan perubahan URL](https://cs50.harvard.edu/web/2020/notes/6/images/singlepage3.gif)

## [Menggulir](https://cs50.harvard.edu/web/2020/notes/6/#scroll)

Untuk memperbarui dan mengakses riwayat browser, kami menggunakan objek JavaScript penting yang dikenal sebagai [window](https://www.w3schools.com/js/js_window.asp) . Ada beberapa properti lain dari jendela yang dapat kita gunakan untuk membuat situs kita terlihat lebih bagus:

-   `window.innerWidth`: Lebar jendela dalam piksel
-   `window.innerHeight`: Tinggi jendela dalam piksel

![tindakan batin](https://cs50.harvard.edu/web/2020/notes/6/images/innerMeasures.png)

While the window represents what is currently visible to the user, the [document](https://www.w3schools.com/js/js_htmldom_document.asp) refers to the entire web page, which is often much larger than the window, forcing the user to scroll up and down to see the page’s contents. To work with our scrolling, we have access to other variables:

-   `window.scrollY`: How many pixels we have scrolled from the top of the page
-   `document.body.offsetHeight`: The height in pixels of the entire document.

![Menggulir langkah-langkah](https://cs50.harvard.edu/web/2020/notes/6/images/scroll.png)

We can use these measures to determine whether or not the user has scrolled to the end of a page using the comparison `window.scrollY + window.innerHeight >= document.body.offsetHeight`. The following page, for example, will change the backgroud color to green when we reach the bottom of a page:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Scroll</title>
        <script>

            // Event listener for scrolling
            window.onscroll = () => {

                // Check if we're at the bottom
                if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {

                    // Change color to green
                    document.querySelector('body').style.background = 'green';
                } else {

                    // Change color to white
                    document.querySelector('body').style.background = 'white';
                }

            };

        </script>
    </head>
    <body>
        <p>1</p>
        <p>2</p>
        <!-- More paragraphs left out to save space -->
        <p>99</p>
        <p>100</p>
    </body>
</html>
```

![gulir hijau putih](https://cs50.harvard.edu/web/2020/notes/6/images/scrollgreen.gif)

### [Infinite Scroll](https://cs50.harvard.edu/web/2020/notes/6/#infinite-scroll)

Changing the background color at the end of the page probably isn’t all that useful, but we may want to detect that we’re at the end of the page if we want to implement **infinite scroll**. For example, if you’re on a social media site, you don’t want to have to load all posts at once, you might want to load the first ten, and then when the user reaches the bottom, load the next ten. Let’s take a look at a Django application that could do this. This app has two paths in `urls.py`

```
urlpatterns = [
    path("", views.index, name="index"),
    path("posts", views.posts, name="posts")
]
```

And two corresponding views in `views.py`:

```
import time

from django.http import JsonResponse
from django.shortcuts import render

# Create your views here.
def index(request):
    return render(request, "posts/index.html")

def posts(request):

    # Get start and end points
    start = int(request.GET.get("start") or 0)
    end = int(request.GET.get("end") or (start + 9))

    # Generate list of posts
    data = []
    for i in range(start, end + 1):
        data.append(f"Post #{i}")

    # Artificially delay speed of response
    time.sleep(1)

    # Return list of posts
    return JsonResponse({
        "posts": data
    })
```

Notice that the `posts` view requires two arguments: a `start` point and an `end` point. In this view, we’ve created our own **API**, which we can test out by visiting the url `localhost:8000/posts?start=10&end=15`, which returns the following JSON:

```
{
    "posts": [
        "Post #10",
        "Post #11", 
        "Post #12", 
        "Post #13", 
        "Post #14", 
        "Post #15"
    ]
}
```

Now, in the `index.html` template that the site loads, we start out with only an empty `div` in the body and some styling. Notice that we load our static files at the beginning, and then we reference a JavaScript file within our `static` folder.

```

{% load static %}
<!DOCTYPE html>
<html>
    <head>
        <title>My Webpage</title>
        <style>
            .post {
                background-color: #77dd11;
                padding: 20px;
                margin: 10px;
            }

            body {
                padding-bottom: 50px;
            }
        </style>
        <script scr="{% static 'posts/script.js' %}"></script>
    </head>
    <body>
        <div id="posts">
        </div>
    </body>
</html>

```

Now with JavaScript, we’ll wait until a user scrolls to the end of the page and then load more posts using our API:

```
// Start with first post
let counter = 1;

// Load posts 20 at a time
const quantity = 20;

// When DOM loads, render the first 20 posts
document.addEventListener('DOMContentLoaded', load);

// If scrolled to bottom, load the next 20 posts
window.onscroll = () => {
    if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {
        load();
    }
};

// Load next set of posts
function load() {

    // Set start and end post numbers, and update counter
    const start = counter;
    const end = start + quantity - 1;
    counter = end + 1;

    // Get new posts and add posts
    fetch(`/posts?start=${start}&end=${end}`)
    .then(response => response.json())
    .then(data => {
        data.posts.forEach(add_post);
    })
};

// Add a new post with given contents to DOM
function add_post(contents) {

    // Create new post
    const post = document.createElement('div');
    post.className = 'post';
    post.innerHTML = contents;

    // Add post to DOM
    document.querySelector('#posts').append(post);
};
```

Now, we’ve created a site with infinite scroll!

![gulir tak terbatas](https://cs50.harvard.edu/web/2020/notes/6/images/infscroll.gif)

## [Animation](https://cs50.harvard.edu/web/2020/notes/6/#animation)

Another way we can make our sites a bit more interesting is by adding some animation to them. It turns out that in addition to providing styling, CSS makes it easy for us to animate HTML elements.

To create an animation in CSS, we use the format below, where the animation specifics can include starting and ending styles (`to` and `from`) or styles at different stages in the duration (anywhere from `0%` to `100%`). For example:

```
@keyframes animation_name {
    from {
        /* Some styling for the start */
    }

    to {
        /* Some styling for the end */
    }
}
```

or:

```
@keyframes animation_name {
    0% {
        /* Some styling for the start */
    }

    75% {
        /* Some styling after 3/4 of animation */
    }

    100% {
        /* Some styling for the end */
    }
}
```

Then, to apply an animation to an element, we include the `animation-name`, the `animation-duration` (in seconds), and the `animation-fill-mode` (typically `forwards`). For example, here’s a page where a title grows when we first enter the page:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Animate</title>
        <style>
            @keyframes grow {
                from {
                    font-size: 20px;
                }
                to {
                    font-size: 100px;
                }
            }

            h1 {
                animation-name: grow;
                animation-duration: 2s;
                animation-fill-mode: forwards;
            }
        </style>
    </head>
    <body>
        <h1>Welcome!</h1>
    </body>
</html>
```

![Judul berkembang](https://cs50.harvard.edu/web/2020/notes/6/images/animate0.gif)

We can do more than just manipulate size: the below example shows how we can change the position of a heading just by changing a few lines:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Animate</title>
        <style>
            @keyframes move {
                from {
                    left: 0%;
                }
                to {
                    left: 50%;
                }
            }

            h1 {
                position: relative;
                animation-name: move;
                animation-duration: 2s;
                animation-fill-mode: forwards;
            }
        </style>
    </head>
    <body>
        <h1>Welcome!</h1>
    </body>
</html>
```

![Memindahkan tajuk](https://cs50.harvard.edu/web/2020/notes/6/images/animate1.gif)

Sekarang, mari kita lihat pengaturan beberapa properti CSS menengah juga. Kita dapat menentukan gaya pada persentase berapa pun melalui animasi. Dalam contoh di bawah ini kita akan memindahkan judul dari kiri ke kanan, lalu kembali ke kiri dengan hanya mengubah animasi dari atas

```
@keyframes move {
    0% {
        left: 0%;
    }
    50% {
        left: 50%;
    }
    100% {
        left: 0%;
    }
}
```

![bolak-balik](https://cs50.harvard.edu/web/2020/notes/6/images/animate2.gif)

Jika kita ingin mengulang animasi berkali-kali, kita dapat mengubah ke `animation-iteration-count`angka yang lebih tinggi dari satu (atau bahkan `infinite`untuk animasi tanpa akhir). Ada banyak [properti animasi](https://www.w3schools.com/cssref/css3_pr_animation.asp) yang dapat kita atur untuk mengubah berbagai aspek animasi kita.

In addition to CSS, we can use JavaScript to further control our animations. Let’s use our moving header example (with infinite repetition) to show how we can create a button that starts and stops the animation. Assuming we already have an animation, button, and heading, we can add the following script to start and pause the animation:

```
document.addEventListener('DOMContentLoaded', function() {

    // Find heading
    const h1 = document.querySelector('h1');

    // Pause Animation by default
    h1.style.animationPlayState = 'paused';

    // Wait for button to be clicked
    document.querySelector('button').onclick = () => {

        // If animation is currently paused, begin playing it
        if (h1.style.animationPlayState == 'paused') {
            h1.style.animationPlayState = 'running';
        }

        // Otherwise, pause the animation
        else {
            h1.style.animationPlayState = 'paused';
        }
    }

})
```

![putar/jeda animasi](https://cs50.harvard.edu/web/2020/notes/6/images/animate4.gif)

Now, let’s look at how we can apply our new knowledge of animations to the posts page we made earlier. Specifically, let’s say we want the ability to hide posts once we’re done reading them. Let’s imagine a Django project identical to the one we just created, but with some slightly different HTML and JavaScript. The first change we’ll make is to the `add_post` function, this time also adding a button to the right side of the post:

```
// Add a new post with given contents to DOM
function add_post(contents) {

    // Create new post
    const post = document.createElement('div');
    post.className = 'post';
    post.innerHTML = `${contents} <button class="hide">Hide</button>`;

    // Add post to DOM
    document.querySelector('#posts').append(post);
};
```

Now, we’ll work on hiding a post when the `hide` button is clicked. To do this, we’ll add an event listener that is triggered whenever a user clicks anywhere on the page. We then write a function that takes in the `event` as an argument, which is useful because we can use the `event.target` attribute to access what was clicked on. We can also use the `parentElement` class to find the parent of a given element in the DOM.

```
// If hide button is clicked, delete the post
document.addEventListener('click', event => {

    // Find what was clicked on
    const element = event.target;

    // Check if the user clicked on a hide button
    if (element.className === 'hide') {
        element.parentElement.remove()
    }
    
});
```

![bersembunyi naif](https://cs50.harvard.edu/web/2020/notes/6/images/hide0.gif)

Kita sekarang dapat melihat bahwa kita telah mengimplementasikan tombol sembunyikan, tetapi tidak terlihat sebaik mungkin. Mungkin kita ingin postingannya memudar dan menyusut sebelum kita menghapusnya. Untuk melakukan ini, pertama-tama kita akan membuat animasi CSS. Animasi di bawah ini akan menghabiskan 75% waktunya untuk mengubah `opacity`dari 1 menjadi 0, yang pada dasarnya membuat postingan menghilang secara perlahan. Ini kemudian menghabiskan sisa waktu untuk memindahkan semua `height`atribut -terkaitnya ke 0, secara efektif menyusutkan pos menjadi nol.

```
@keyframes hide {
    0% {
        opacity: 1;
        height: 100%;
        line-height: 100%;
        padding: 20px;
        margin-bottom: 10px;
    }
    75% {
        opacity: 0;
        height: 100%;
        line-height: 100%;
        padding: 20px;
        margin-bottom: 10px;
    }
    100% {
        opacity: 0;
        height: 0px;
        line-height: 0px;
        padding: 0px;
        margin-bottom: 0px;
    }
}
```

Selanjutnya, kita akan menambahkan animasi ini ke CSS postingan kita. Perhatikan bahwa awalnya kita menyetel `animation-play-state`to `paused`, artinya kiriman tidak akan disembunyikan secara default.

```
.post {
    background-color: #77dd11;
    padding: 20px;
    margin-bottom: 10px;
    animation-name: hide;
    animation-duration: 2s;
    animation-fill-mode: forwards;
    animation-play-state: paused;
}
```

Terakhir, kami ingin dapat memulai animasi setelah `hide`tombol diklik, lalu menghapus kiriman. Kita dapat melakukan ini dengan mengedit JavaScript kita dari atas:

```
// If hide button is clicked, delete the post
document.addEventListener('click', event => {

    // Find what was clicked on
    const element = event.target;

    // Check if the user clicked on a hide button
    if (element.className === 'hide') {
        element.parentElement.style.animationPlayState = 'running';
        element.parentElement.addEventListener('animationend', () => {
            element.parentElement.remove();
        });
    }
    
});
```

![Tempat persembunyian yang cantik](https://cs50.harvard.edu/web/2020/notes/6/images/hide1.gif)

Seperti yang Anda lihat di atas, fungsi sembunyikan sekarang terlihat jauh lebih bagus!

## [Reaksi](https://cs50.harvard.edu/web/2020/notes/6/#react)

Pada titik ini, Anda dapat membayangkan berapa banyak kode JavaScript yang harus masuk ke situs web yang lebih rumit. Kami dapat mengurangi berapa banyak kode yang benar-benar perlu kami tulis dengan menggunakan kerangka kerja JavaScript, sama seperti kami menggunakan Bootstrap sebagai kerangka kerja CSS untuk mengurangi jumlah CSS yang sebenarnya harus kami tulis. Salah satu framework JavaScript paling populer adalah library bernama [React](https://reactjs.org/) .

So far in this course, we’ve been using **imperative programming** methods, where we give the computer a set of statements to execute. For example, to update the counter in an HTML page we might have have code that looks like this:

View:

```
<h1>0</h1>
```

Logic:

```
let num = parseInt(document.querySelector("h1").innerHTML);
num += 1;
document.querySelector("h1").innerHTML = num;
```

React allows us to use **declarative programming**, which will allow us to simply write code explaining _what_ we wish to display and not worry about _how_ we’re displaying it. In React, a counter might look a bit more like this:

View:

```
<h1>{num}</h1>
```

Logic:

```
num += 1;
```

The React framework is built around the idea of components, each of which can have an underlying state. A component would be something you can see on a web page like a post or a navigation bar, and a state is a set of variables associated with that component. The beauty of React is that when the state changes, React will automatically change the DOM accordingly.

There are a number of ways to use React, (including the popular [create-react-app](https://reactjs.org/docs/create-a-new-react-app.html) command published by Facebook) but today we’ll focus on getting started directly in an HTML file. To do this, we’ll have to import three JavaScript Packages:

-   `React`: Defines components and their behavior
-   `ReactDOM`: Takes React components and inserts them into the DOM
-   `Babel`: Menerjemahkan dari [JSX](https://reactjs.org/docs/introducing-jsx.html) , bahasa yang akan kita gunakan untuk menulis di React, ke JavaScript biasa yang dapat ditafsirkan oleh browser kita. JSX sangat mirip dengan JavaScript, tetapi dengan beberapa fitur tambahan, termasuk kemampuan untuk merepresentasikan HTML di dalam kode kita.

Mari selami dan buat aplikasi React pertama kita!

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <script src="https://unpkg.com/react@17/umd/react.production.min.js" crossorigin></script>
        <script src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js" crossorigin></script>
        <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
        <title>Hello</title>
    </head>
    <body>
        <div id="app"></div>

        <script type="text/babel">
            function App() {
                return (
                    <div>
                        Hello!
                    </div>
                );
            }

            ReactDOM.render(<App />, document.querySelector("#app"));
        </script>
    </body>
</html>
```

Karena ini adalah aplikasi React pertama kita, mari kita lihat secara mendetail apa yang dilakukan setiap bagian dari kode ini:

-   Pada tiga baris di atas judul, kita mengimpor React, ReactDOM, dan Babel versi terbaru.
-   Di dalam tubuh, kami menyertakan satu `div`dengan `id`dari `app`. Kami hampir selalu ingin membiarkannya kosong, dan mengisinya dengan kode reaksi kami di bawah ini.
-   Kami menyertakan tag skrip tempat kami menentukannya `type="text/babel"`. Ini memberi sinyal ke browser bahwa skrip berikut perlu diterjemahkan menggunakan Babel.
-   Selanjutnya, kita buat sebuah komponen bernama `App`. Komponen dalam React dapat diwakili oleh fungsi JavaScript.
-   Komponen kita mengembalikan apa yang ingin kita render ke DOM. Dalam hal ini, kami cukup mengembalikan `<div>Hello!</div>`.
-   Baris terakhir skrip kami menggunakan fungsi `ReactDOM.render`, yang membutuhkan dua argumen:
    1.  Sebuah komponen untuk merender
    2.  Sebuah elemen dalam DOM yang di dalamnya komponen tersebut harus dirender

Sekarang setelah kita memahami apa yang dilakukan kode, kita dapat melihat halaman web yang dihasilkan:

![selamat datang halo bereaksi](https://cs50.harvard.edu/web/2020/notes/6/images/react0.png)

Salah satu fitur React yang berguna adalah kemampuan merender komponen di dalam komponen lain. Untuk mendemonstrasikan ini, mari buat komponen lain bernama `Hello`:

```JSX
function Hello(props) {
    return (
        <h1>Hello</h1>
    );
}
```

Dan sekarang, mari kita render tiga `Hello`komponen di dalam `App`komponen kita:

```JSX
function App() {
    return (
        <div>
            <Hello />
            <Hello />
            <Hello />
        </div>
    );
}
```

Ini memberi kita halaman yang terlihat seperti:

![Tiga halo](https://cs50.harvard.edu/web/2020/notes/6/images/react1.png)

Sejauh ini, komponennya belum begitu menarik, karena semuanya persis sama. Kita dapat membuat komponen ini lebih fleksibel dengan menambahkan properti tambahan ( **props** dalam istilah React) ke dalamnya. Misalnya, katakanlah kita ingin menyapa tiga orang yang berbeda. Kami dapat memberikan nama orang tersebut dalam metode yang mirip dengan atribut HTML:

```JSX
function App() {
    return (
        <div>
            <Hello name="Harry" />
            <Hello name="Ron" />
            <Hello name="Hermione" />
        </div>
    );
}
```

Kami kemudian dapat mengakses alat peraga tersebut menggunakan `props.PROP_NAME`. Kami kemudian dapat memasukkan ini ke JSX kami menggunakan kurung kurawal:

```JSX
function Hello(props) {
    return (
        <h1>Hello, {props.name}!</h1>
    );
}
```

Sekarang, halaman kami menampilkan tiga nama!

![Tiga nama](https://cs50.harvard.edu/web/2020/notes/6/images/react2.png)

Sekarang, mari kita lihat bagaimana kita bisa menggunakan React untuk mengimplementasikan kembali halaman penghitung yang kita buat saat pertama kali bekerja dengan JavaScript. Keseluruhan struktur kita akan tetap sama, tetapi di dalam `App`komponen kita, kita akan menggunakan kait React `useState`untuk menambahkan status ke komponen kita. Argumen to `useState`adalah nilai awal dari status, yang akan kita atur menjadi `0`. Fungsi mengembalikan variabel yang mewakili status dan fungsi yang memungkinkan kita memperbarui status.

```JSX
const [count, setCount] = React.useState(0);
```

Sekarang, kita dapat mengerjakan fungsi apa yang akan dirender, di mana kita akan menentukan header dan tombol. Kami juga akan menambahkan pendengar acara ketika tombol diklik, yang ditangani oleh React menggunakan `onClick`atribut:

```JSX
return (
    <div>
        <h1>{count}</h1>
        <button onClick={updateCount}>Count</button>
    </div>
);
```

Terakhir, mari kita definisikan fungsinya `updateCount`. Untuk melakukan ini, kita akan menggunakan `setCount`fungsi, yang dapat mengambil nilai baru untuk status sebagai argumen.

```JSX
function updateCount() {
    setCount(count + 1);
}
```

Sekarang kami memiliki situs penghitung yang berfungsi!

![menangkal](https://cs50.harvard.edu/web/2020/notes/6/images/react3.gif)

### [Tambahan](https://cs50.harvard.edu/web/2020/notes/6/#addition)

Sekarang setelah kita merasakan kerangka kerja React, mari bekerja menggunakan apa yang telah kita pelajari untuk membangun situs mirip permainan di mana pengguna akan memecahkan masalah penjumlahan. Kita akan mulai dengan membuat file baru dengan pengaturan yang sama seperti halaman React kami yang lain. Untuk mulai membuat aplikasi ini, mari kita pikirkan tentang apa yang mungkin ingin kita lacak dalam status. Kami harus menyertakan apa pun yang menurut kami mungkin berubah saat pengguna berada di halaman kami. Negara kita mungkin termasuk:

-   `num1`: Angka pertama yang ditambahkan
-   `num2`: Angka kedua yang akan ditambahkan
-   `response`: Apa yang telah diketik pengguna
-   `score`: Berapa banyak pertanyaan yang dijawab dengan benar oleh pengguna.

Sekarang, status kita bisa menjadi objek JavaScript yang mencakup semua informasi ini:

```JSX
const [state, setState] = React.useState({
    num1: 1,
    num2: 1,
    response: "",
    score: 0
});
```

Sekarang, dengan menggunakan nilai dalam status, kita dapat merender antarmuka pengguna dasar.

```JSX
return (
    <div>
        <div>{state.num1} + {state.num2}</div>
        <input value={state.response} />
        <div>Score: {state.score}</div>
    </div>
);
```

Sekarang, tata letak dasar situs terlihat seperti ini:

![Tata letak tambahan](https://cs50.harvard.edu/web/2020/notes/6/images/add0.png)

Pada titik ini, pengguna tidak dapat mengetik apa pun di kotak input karena nilainya tetap seperti `state.response`string kosong saat ini. Untuk memperbaikinya, mari tambahkan `onChange`atribut ke elemen input, dan atur agar sama dengan fungsi yang dipanggil`updateResponse`

```JSX
onChange={updateResponse}
```

Sekarang, kita harus mendefinisikan `updateResposne`fungsi, yang mengambil kejadian yang memicu fungsi, dan menyetel `response`ke nilai input saat ini. Fungsi ini memungkinkan pengguna untuk mengetik, dan menyimpan apa pun yang telah diketik dalam file `state`.

```JSX
function updateResponse(event) {
    setState({
        ...state,
        response: event.target.value
    });
}
```

Sekarang, mari tambahkan kemampuan pengguna untuk mengirimkan masalah. Pertama-tama kita akan menambahkan event listener lain dan menautkannya ke fungsi yang akan kita tulis selanjutnya:

```JSX
onKeyPress={inputKeyPress}
```

Sekarang, kita akan mendefinisikan fungsinya `inputKeyPress`. Dalam fungsi ini, pertama-tama kita akan memeriksa apakah `Enter`tombol ditekan, lalu memeriksa apakah jawabannya benar. Ketika pengguna benar, kami ingin menambah skor dengan 1, memilih angka acak untuk masalah berikutnya, dan menghapus jawabannya. Jika jawabannya salah, kami ingin mengurangi skor sebanyak 1 dan menghapus respons.

```JSX
function inputKeyPress(event) {
    if (event.key === "Enter") {
        const answer = parseInt(state.response);
        if (answer === state.num1 + state.num2) {
            // User got question right
            setState({
                ...state,
                score: state.score + 1,
                response: "",
                num1: Math.ceil(Math.random() * 10),
                num2: Math.ceil(Math.random() * 10)
            });
        } else {
            // User got question wrong
            setState({
                ...state,
                score: state.score - 1,
                response: ""
            })
        }
    }
}
```

Untuk memberi sentuhan akhir pada aplikasi, mari tambahkan beberapa gaya ke halaman. Kami akan memusatkan semua yang ada di aplikasi, lalu memperbesar masalah dengan menambahkan dari `id`ke `problem`div yang berisi masalah, lalu menambahkan CSS berikut ke tag gaya:

```CSS
#app {
    text-align: center;
    font-family: sans-serif;
}

#problem {
    font-size: 72px;
}
```

Terakhir, mari tambahkan kemampuan untuk memenangkan permainan setelah mendapatkan 10 poin. Untuk melakukan ini, kami akan menambahkan kondisi ke `render`fungsi, mengembalikan sesuatu yang sama sekali berbeda setelah kami memiliki 10 poin:

```JSX
if (state.score === 10) {
    return (
        <div id="winner">You won!</div>
    );
}
```

Untuk membuat kemenangan lebih menarik, kami juga akan menambahkan beberapa gaya ke div alternatif:

```
#winner {
    font-size: 72px;
    color: green;
}
```

Sekarang, mari kita lihat aplikasi kita!

![selesai](https://cs50.harvard.edu/web/2020/notes/6/images/add1.gif)

Itu saja untuk kuliah hari ini! Lain kali, kita akan membicarakan beberapa praktik terbaik untuk membangun aplikasi web yang lebih besar.
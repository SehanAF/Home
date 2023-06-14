# [Kuliah 9](https://cs50.harvard.edu/college/2022/fall/notes/9/#lecture-9)

-   [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/9/#welcome)
-   [Statis ke Dinamis](https://cs50.harvard.edu/college/2022/fall/notes/9/#static-to-dynamic)
-   [Labu](https://cs50.harvard.edu/college/2022/fall/notes/9/#flask)
-   [Tata letak](https://cs50.harvard.edu/college/2022/fall/notes/9/#layout)
-   [POS](https://cs50.harvard.edu/college/2022/fall/notes/9/#post)
-   [IM baru](https://cs50.harvard.edu/college/2022/fall/notes/9/#frosh-ims)
-   [Labu dan SQL](https://cs50.harvard.edu/college/2022/fall/notes/9/#flask-and-sql)
-   [Sidang](https://cs50.harvard.edu/college/2022/fall/notes/9/#session)
-   [Toko](https://cs50.harvard.edu/college/2022/fall/notes/9/#store)
-   [API](https://cs50.harvard.edu/college/2022/fall/notes/9/#api)
-   [JSON](https://cs50.harvard.edu/college/2022/fall/notes/9/#json)
-   [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/9/#summing-up)

## [Selamat datang!](https://cs50.harvard.edu/college/2022/fall/notes/9/#welcome)

-   Pada minggu-minggu sebelumnya, Anda telah mempelajari berbagai bahasa pemrograman, teknik, dan strategi.
-   Memang, kelas ini jauh lebih sedikit dari _kelas C_ atau _kelas Python_ dan jauh lebih banyak dari _kelas pemrograman_ , sehingga Anda dapat terus mengikuti tren masa depan.
-   Dalam beberapa minggu terakhir ini, Anda telah belajar _bagaimana belajar_ tentang pemrograman.
-   Hari ini, kita akan beralih dari HTML dan CSS ke dalam menggabungkan HTML, CSS, SQL, Python, dan JavaScript sehingga Anda dapat membuat aplikasi web sendiri.

## [Statis ke Dinamis](https://cs50.harvard.edu/college/2022/fall/notes/9/#static-to-dynamic)

-   Sampai saat ini, semua HTML yang Anda lihat sudah ditulis sebelumnya dan statis.
-   Di masa lalu, saat Anda mengunjungi sebuah halaman, browser mendownload halaman HTML, dan Anda dapat melihatnya.
-   Halaman dinamis mengacu pada kemampuan Python dan bahasa serupa untuk membuat file HTML dengan cepat. Dengan demikian, Anda dapat memiliki halaman web yang dihasilkan oleh opsi yang dipilih oleh pengguna Anda.
-   Anda telah menggunakan `http-server`di masa lalu untuk melayani halaman web Anda. Hari ini, kita akan menggunakan server baru yang dapat menguraikan alamat web dan melakukan tindakan berdasarkan URL yang disediakan.

## [Labu](https://cs50.harvard.edu/college/2022/fall/notes/9/#flask)

-   _Flask_ adalah pustaka pihak ketiga yang memungkinkan Anda menghosting aplikasi web menggunakan kerangka kerja Flask di dalam Python.
-   Anda dapat menjalankan flask dengan mengeksekusi `flask run`.
-   Untuk melakukannya, Anda memerlukan file bernama `app.py`dan folder bernama `templates`.
-   Untuk memulai, buat folder bernama `templates`dan buat file bernama `index.html`dengan kode berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>hello</title>
        </head>
        <body>
            hello, {{ name }}
        </body>
    </html>
    ```
    
    Perhatikan double `{{ name }}`yang merupakan placeholder untuk sesuatu yang nantinya akan disediakan oleh server Flask kita.
    
-   Kemudian, di folder yang sama dengan `templates`folder yang muncul, buat file bernama `app.py`dan tambahkan kode berikut:
    
    ```
    # Greets user
    
    from flask import Flask, render_template, request
    
    app = Flask(__name__)
    
    
    @app.route("/")
    def index():
        return render_template("index.html", name=request.args.get("name", "world"))
    ```
    
    Perhatikan bahwa kode ini didefinisikan `app`sebagai aplikasi Flask. Kemudian, ia mendefinisikan `/`rute `app`sebagai mengembalikan konten `index.html`dengan argumen `name`. Secara default, `request.args.get`fungsi akan mencari yang `name`disediakan oleh pengguna. Jika tidak ada nama yang diberikan, maka defaultnya adalah `world`.
    
-   Terakhir, tambahkan file terakhir di folder yang sama dengan `app.py`nama `requirements.txt`yang hanya memiliki satu baris kode:
    
    ```
    Flask
    ```
    
    Pemberitahuan hanya `Flask`muncul di file ini.
    
-   Anda dapat menjalankan file ini dengan mengetik `flask run`di jendela terminal. Jika Flask tidak berjalan, pastikan sintaks Anda sudah benar di setiap file di atas. Selanjutnya, jika Flask tidak dapat dijalankan, pastikan file Anda diatur sebagai berikut:
    
    ```
    /templates
        index.html
    app.py
    requirements.txt
    ```
    
    Setelah Anda menjalankannya, Anda akan diminta untuk mengklik tautan. Setelah Anda menavigasi ke halaman web tersebut, coba tambahkan `?name=[Your Name]`ke URL dasar di bilah URL browser Anda.
    
-   Memperbaiki program kami, kami tahu bahwa sebagian besar pengguna tidak akan mengetikkan argumen ke bilah alamat. Sebaliknya, pemrogram mengandalkan pengguna untuk mengisi formulir di halaman web. Oleh karena itu, kita dapat memodifikasi index.html sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>hello</title>
        </head>
        <body>
            <form action="/greet" method="get">
                <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
                <button type="submit">Greet</button>
            </form>
        </body>
    </html>
    ```
    
    Perhatikan bahwa formulir sekarang dibuat yang mengambil nama pengguna dan meneruskannya ke rute bernama `/greet`.
    
-   Selanjutnya, kita dapat mengubah `app.py`sebagai berikut:
    
    ```
    # Adds a form, second route
    
    from flask import Flask, render_template, request
    
    app = Flask(__name__)
    
    
    @app.route("/")
    def index():
        return render_template("index.html")
    
    
    @app.route("/greet")
    def greet():
        return render_template("greet.html", name=request.args.get("name", "world"))
    ```
    
    Perhatikan bahwa jalur default akan menampilkan formulir bagi pengguna untuk memasukkan nama mereka. Rute `/greet`akan melewati `name`ke halaman web itu.
    
-   Untuk menyelesaikan implementasi ini, Anda memerlukan template lain sebagai `greet.html`berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>hello</title>
        </head>
        <body>
            hello, {{ name }}
        </body>
    </html>
    ```
    
    Perhatikan bahwa rute ini sekarang akan memberikan salam kepada pengguna, diikuti dengan nama mereka.
    

## [Tata letak](https://cs50.harvard.edu/college/2022/fall/notes/9/#layout)

-   Kedua laman web kami, `index.html`dan `greet.html`, memiliki banyak data yang sama. Bukankah menyenangkan membiarkan badan menjadi unik, tetapi menyalin tata letak yang sama dari halaman ke halaman?
-   Pertama, buat template baru bernama `layout.html`dan tulis kode sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>hello</title>
        </head>
        <body>
            {% block body %}{% endblock %}
        </body>
    </html>
    ```
    
    Perhatikan bahwa `{% block body %}{% endblock %}`memungkinkan penyisipan kode lain dari file HTML lainnya.
    
-   Kemudian, modifikasi Anda `index.html`sebagai berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
    
        <form action="/greet" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <button type="submit">Greet</button>
        </form>
    
    {% endblock %}
    ```
    
    Perhatikan bahwa baris `{% extends "layout.html" %}`memberi tahu server tempat mendapatkan tata letak halaman ini. Kemudian, `{% block body %}{% endblock %}`beri tahu kode apa yang akan dimasukkan `layout.html`.
    
-   Terakhir, ubah `greet.html`sebagai berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
        hello, {{ name }}
    {% endblock %}
    ```
    
    Perhatikan bagaimana kode ini lebih pendek dan lebih padat.
    

## [POS](https://cs50.harvard.edu/college/2022/fall/notes/9/#post)

-   Anda dapat membayangkan skenario di mana tidak aman untuk digunakan `get`, karena nama pengguna dan kata sandi akan muncul di URL.
-   Kami dapat menggunakan metode `post`untuk membantu masalah ini dengan memodifikasi `app.py`sebagai berikut:
    
    ```
    # Switches to POST
    
    from flask import Flask, render_template, request
    
    app = Flask(__name__)
    
    
    @app.route("/")
    def index():
        return render_template("index.html")
    
    
    @app.route("/greet", methods=["POST"])
    def greet():
        return render_template("greet.html", name=request.form.get("name", "world"))
    ```
    
    Perhatikan yang `POST`ditambahkan ke `/greet`rute, dan yang kita gunakan `request.form.get`daripada `request.args.get`.
    
-   Ini memberi tahu server untuk melihat _lebih dalam_ ke amplop virtual dan tidak mengungkapkan item di dalam `post`URL.
-   Namun, kode ini dapat dikembangkan lebih lanjut dengan memanfaatkan satu rute untuk keduanya `get`dan `post`. Untuk melakukannya, modifikasi `app.py`sebagai berikut:
    
    ```
    # Uses a single route
    
    from flask import Flask, render_template, request
    
    app = Flask(__name__)
    
    
    @app.route("/", methods=["GET", "POST"])
    def index():
        if request.method == "POST":
            return render_template("greet.html", name=request.form.get("name", "world"))
        return render_template("index.html")
    ```
    
    Perhatikan bahwa keduanya `get`dan `post`dilakukan dalam satu perutean. Namun, `request.method`digunakan untuk merutekan dengan benar berdasarkan jenis perutean yang diminta oleh pengguna.
    

## [IM baru](https://cs50.harvard.edu/college/2022/fall/notes/9/#frosh-ims)

-   Frosh IM atau _froshims_ adalah aplikasi web yang memungkinkan siswa untuk mendaftar olahraga intermural.
-   Buat folder dengan mengetik `mkdir froshims`di jendela terminal. Kemudian, ketik `cd froshims`untuk menelusuri folder ini. Di dalam, buat direktori bernama template dengan mengetik `mkdir templates`. Terakhir, ketik `code app.py`dan tulis kode sebagai berikut:
    
    ```
    # Implements a registration form using a select menu
    
    from flask import Flask, render_template, request
    
    app = Flask(__name__)
    
    SPORTS = [
        "Basketball",
        "Soccer",
        "Ultimate Frisbee"
    ]
    
    
    @app.route("/")
    def index():
        return render_template("index.html", sports=SPORTS)
    
    
    @app.route("/register", methods=["POST"])
    def register():
    
        # Validate submission
        if not request.form.get("name") or request.form.get("sport") not in SPORTS:
            return render_template("failure.html")
    
        # Confirm registration
        return render_template("success.html")
    ```
    
    Perhatikan bahwa `failure`opsi disediakan, sehingga pesan kegagalan akan ditampilkan kepada pengguna jika bidang `name`atau `sport`tidak diisi dengan benar.
    
-   Selanjutnya, buat file di `templates`folder bernama `index.html`dengan mengetik `code templates/index.html`dan menulis kode sebagai berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
        <h1>Register</h1>
        <form action="/register" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <select name="sport">
                <option disabled selected>Sport</option>
                {% for sport in sports %}
                    <option value="{{ sport }}">{{ sport }}</option>
                {% endfor %}
            </select>
            <button type="submit">Register</button>
        </form>
    {% endblock %}
    ```
    
-   Selanjutnya, buat file bernama `layout.html`dengan mengetik `code templates/layout.html`dan menulis kode sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>froshims</title>
        </head>
        <body>
            {% block body %}{% endblock %}
        </body>
    </html>
    ```
    
-   Keempat, buat file dalam template yang disebut `success.html`sebagai berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
        You are registered!
    {% endblock %}
    ```
    
-   Terakhir, buat file dalam template yang disebut `failure.html`sebagai berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
        You are not registered!
    {% endblock %}
    ```
    
-   Anda dapat membayangkan bagaimana kami ingin menerima pendaftaran dari banyak pendaftar yang berbeda. Kami dapat meningkatkan `app.py`sebagai berikut:
    
    ```
    # Implements a registration form, storing registrants in a dictionary, with error messages
    
    from flask import Flask, redirect, render_template, request
    
    app = Flask(__name__)
    
    REGISTRANTS = {}
    
    SPORTS = [
        "Basketball",
        "Soccer",
        "Ultimate Frisbee"
    ]
    
    
    @app.route("/")
    def index():
        return render_template("index.html", sports=SPORTS)
    
    
    @app.route("/register", methods=["POST"])
    def register():
    
        # Validate name
        name = request.form.get("name")
        if not name:
            return render_template("error.html", message="Missing name")
    
        # Validate sport
        sport = request.form.get("sport")
        if not sport:
            return render_template("error.html", message="Missing sport")
        if sport not in SPORTS:
            return render_template("error.html", message="Invalid sport")
    
        # Remember registrant
        REGISTRANTS[name] = sport
    
        # Confirm registration
        return redirect("/registrants")
    
    
    @app.route("/registrants")
    def registrants():
        return render_template("registrants.html", registrants=REGISTRANTS)
    ```
    
    Perhatikan bahwa kamus yang dipanggil `REGISTRANTS`digunakan untuk mencatat yang `sport`dipilih oleh `REGISTRANTS[name]`. Juga, perhatikan bahwa `registrants=REGISTRANTS`meneruskan kamus ke templat ini.
    
-   Selanjutnya, buat template baru bernama `registrants.html`sebagai berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
        <h1>Registrants</h1>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Sport</th>
                </tr>
            </thead>
            <tbody>
                {% for name in registrants %}
                    <tr>
                        <td>{{ name }}</td>
                        <td>{{ registrants[name] }}</td>
                    </tr>
                {% endfor %}
            </tbody>
        </table>
    {% endblock %}
    ```
    
    Perhatikan bahwa `{% for name in registrants %}...{% endfor %}`akan beralih melalui masing-masing pendaftar. Sangat kuat untuk dapat melakukan iterasi pada halaman web yang dinamis!
    
-   Menjalankan `flask run`dan memasukkan banyak nama dan olahraga, Anda dapat menelusuri `/registrants`untuk melihat data apa yang telah dicatat.
-   Anda sekarang memiliki aplikasi web! Namun, ada beberapa kelemahan keamanan! Karena semuanya adalah sisi klien, musuh dapat mengubah HTML dan _meretas_ situs web. Selanjutnya, data ini tidak akan bertahan jika server dimatikan. Mungkinkah ada cara agar data kami tetap ada bahkan ketika server dimulai ulang?

## [Labu dan SQL](https://cs50.harvard.edu/college/2022/fall/notes/9/#flask-and-sql)

-   Seperti yang telah kita lihat bagaimana Python dapat berinteraksi dengan database SQL, kita dapat menggabungkan kekuatan Flask, Python, dan SQL untuk membuat aplikasi web tempat data akan bertahan!
-   Untuk menerapkan ini, Anda perlu mengambil sejumlah langkah.
-   Pertama, ubah `requirements.txt`sebagai berikut:
    
    ```
    cs50
    Flask
    ```
    
-   Ubah `index.html`sebagai berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
        <h1>Register</h1>
        <form action="/register" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            {% for sport in sports %}
                <input name="sport" type="radio" value="{{ sport }}"> {{ sport }}
            {% endfor %}
            <button type="submit">Register</button>
        </form>
    {% endblock %}
    ```
    
-   Ubah `layout.html`sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>froshims</title>
        </head>
        <body>
            {% block body %}{% endblock %}
        </body>
    </html>
    ```
    
-   Pastikan `failure.html`muncul seperti berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
        You are not registered!
    {% endblock %}
    ```
    
-   Modifikasi `registrants.html`agar tampil seperti berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
        <h1>Registrants</h1>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Sport</th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
                {% for registrant in registrants %}
                    <tr>
                        <td>{{ registrant.name }}</td>
                        <td>{{ registrant.sport }}</td>
                        <td>
                            <form action="/deregister" method="post">
                                <input name="id" type="hidden" value="{{ registrant.id }}">
                                <button type="submit">Deregister</button>
                            </form>
                        </td>
                    </tr>
                {% endfor %}
            </tbody>
        </table>
    {% endblock %}
    ```
    
    Perhatikan bahwa nilai tersembunyi `registrant.id`disertakan sehingga memungkinkan untuk menggunakannya `id`nanti`app.py`
    
-   Terakhir, modifikasi `app.py`sebagai berikut:
    
    ```
    # Implements a registration form, storing registrants in a SQLite database, with support for deregistration
    
    from cs50 import SQL
    from flask import Flask, redirect, render_template, request
    
    app = Flask(__name__)
    
    db = SQL("sqlite:///froshims.db")
    
    SPORTS = [
        "Basketball",
        "Soccer",
        "Ultimate Frisbee"
    ]
    
    
    @app.route("/")
    def index():
        return render_template("index.html", sports=SPORTS)
    
    
    @app.route("/deregister", methods=["POST"])
    def deregister():
    
        # Forget registrant
        id = request.form.get("id")
        if id:
            db.execute("DELETE FROM registrants WHERE id = ?", id)
        return redirect("/registrants")
    
    
    @app.route("/register", methods=["POST"])
    def register():
    
        # Validate submission
        name = request.form.get("name")
        sport = request.form.get("sport")
        if not name or sport not in SPORTS:
            return render_template("failure.html")
    
        # Remember registrant
        db.execute("INSERT INTO registrants (name, sport) VALUES(?, ?)", name, sport)
    
        # Confirm registration
        return redirect("/registrants")
    
    
    @app.route("/registrants")
    def registrants():
        registrants = db.execute("SELECT * FROM registrants")
        return render_template("registrants.html", registrants=registrants)
    ```
    
    Perhatikan bahwa `cs50`perpustakaan digunakan. Rute disertakan untuk `register`untuk metode ini `post`. Rute ini akan mengambil nama dan olahraga yang diambil dari formulir pendaftaran dan menjalankan kueri SQL untuk menambahkan the `name`dan the `sport`ke `registrants`tabel. Rute `deregister`ke kueri SQL yang akan mengambil milik pengguna `id`dan menggunakan informasi tersebut untuk membatalkan pendaftaran orang ini.
    
-   Anda dapat membaca lebih lanjut di [dokumentasi Flask](https://flask.palletsprojects.com/) .

## [Sidang](https://cs50.harvard.edu/college/2022/fall/notes/9/#session)

-   Meskipun kode di atas berguna dari sudut pandang administratif, di mana administrator back-office dapat menambah dan menghapus individu dari database, dapat dibayangkan bagaimana kode ini tidak aman untuk diterapkan di server publik.
-   Pertama, aktor jahat dapat membuat keputusan atas nama pengguna lain dengan menekan tombol deregister – secara efektif menghapus rekaman jawaban mereka dari server.
-   Layanan web seperti Google menggunakan kredensial masuk untuk memastikan pengguna hanya memiliki akses ke data yang benar.
-   Kami benar-benar dapat mengimplementasikan ini sendiri menggunakan _cookie_ . Cookie adalah file kecil yang disimpan di komputer Anda, sehingga komputer Anda dapat berkomunikasi dengan server dan secara efektif mengatakan, "Saya adalah pengguna resmi yang telah masuk."
-   Dalam bentuk yang paling sederhana, kita dapat mengimplementasikannya dengan membuat sebuah folder bernama `login`dan kemudian menambahkan file-file berikut.
-   Pertama, buat file bernama `requirements.txt`yang berbunyi sebagai berikut:
    
    ```
    Flask
    Flask-Session
    ```
    
    Perhatikan bahwa selain `Flask`, kami juga menyertakan `Flask-Session`, yang diperlukan untuk mendukung sesi login.
    
-   Kedua, di `templates`folder, buat file bernama `layout.html`yang muncul sebagai berikut:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>store</title>
        </head>
        <body>
            {% block body %}{% endblock %}
        </body>
    </html>
    ```
    
    Perhatikan ini memberikan tata letak yang sangat sederhana dengan judul dan badan.
    
-   Ketiga, buat file di `templates`folder bernama `index.html`yang muncul sebagai berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
    
        {% if session["name"] %}
            You are logged in as {{ session["name"] }}. <a href="/logout">Log out</a>.
        {% else %}
            You are not logged in. <a href="/login">Log in</a>.
        {% endif %}
    
    {% endblock %}
    ```
    
    Perhatikan bahwa file ini terlihat untuk melihat apakah `session["name"]`ada. Jika ya, itu akan menampilkan pesan selamat datang. Jika tidak, ini akan merekomendasikan Anda menjelajah ke halaman untuk masuk.
    
-   Keempat, buat file bernama `login.html`dan tambahkan kode berikut:
    
    ```
    {% extends "layout.html" %}
    
    {% block body %}
    
        <form action="/login" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <button type="submit">Log In</button>
        </form>
    
    {% endblock %}
    ```
    
    Perhatikan ini adalah tata letak halaman login dasar.
    
-   Terakhir, buat file di `login`folder bernama `app.py`dan tulis kode sebagai berikut:
    
    ```
    from flask import Flask, redirect, render_template, request, session
    from flask_session import Session
    
    # Configure app
    app = Flask(__name__)
    
    # Configure session
    app.config["SESSION_PERMANENT"] = False
    app.config["SESSION_TYPE"] = "filesystem"
    Session(app)
    
    
    @app.route("/")
    def index():
        if not session.get("name"):
            return redirect("/login")
        return render_template("index.html")
    
    
    @app.route("/login", methods=["GET", "POST"])
    def login():
        if request.method == "POST":
            session["name"] = request.form.get("name")
            return redirect("/")
        return render_template("login.html")
    
    
    @app.route("/logout")
    def logout():
        session["name"] = None
        return redirect("/")
    ```
    
    Perhatikan _impor_ yang dimodifikasi di bagian atas file, termasuk `session`, yang memungkinkan Anda mendukung sesi. Yang paling penting, perhatikan bagaimana `session["name"]`digunakan dalam `login`dan `logout`rute. Rute `login`akan menetapkan nama login yang diberikan dan menetapkannya ke `session["name"]`. Namun, di `logout`rute, logout diterapkan hanya dengan mengatur `session["name"]`ke `None`.
    
-   Anda dapat membaca lebih lanjut tentang session di [dokumentasi Flask](https://flask.palletsprojects.com/en/2.2.x/api/?highlight=session#flask.session) .

## [Toko](https://cs50.harvard.edu/college/2022/fall/notes/9/#store)

-   Pindah ke contoh terakhir memanfaatkan kemampuan Flask untuk mengaktifkan sesi.
-   Kami memeriksa kode berikut untuk `store`di `app.py`. Kode berikut ditampilkan:
    
    ```
    from cs50 import SQL
    from flask import Flask, redirect, render_template, request, session
    from flask_session import Session
    
    # Configure app
    app = Flask(__name__)
    
    # Connect to database
    db = SQL("sqlite:///store.db")
    
    # Configure session
    app.config["SESSION_PERMANENT"] = False
    app.config["SESSION_TYPE"] = "filesystem"
    Session(app)
    
    
    @app.route("/")
    def index():
        books = db.execute("SELECT * FROM books")
        return render_template("books.html", books=books)
    
    
    @app.route("/cart", methods=["GET", "POST"])
    def cart():
    
        # Ensure cart exists
        if "cart" not in session:
            session["cart"] = []
    
        # POST
        if request.method == "POST":
            id = request.form.get("id")
            if id:
                session["cart"].append(id)
            return redirect("/cart")
    
        # GET
        books = db.execute("SELECT * FROM books WHERE id IN (?)", session["cart"])
        return render_template("cart.html", books=books)
    ```
    
    Perhatikan yang `cart`diimplementasikan menggunakan daftar. Item dapat ditambahkan ke daftar ini menggunakan `Add to Cart`tombol di `books.html`. Saat mengklik tombol seperti itu, `post`metode dipanggil, di mana item `id`dari item ditambahkan ke `cart`. Saat melihat keranjang, memanggil `get`metode, SQL dijalankan untuk menampilkan daftar buku di keranjang.
    

## [API](https://cs50.harvard.edu/college/2022/fall/notes/9/#api)

-   Antarmuka _program aplikasi_ atau _API_ adalah serangkaian spesifikasi yang memungkinkan Anda untuk berinteraksi dengan layanan lain. Misalnya, kita dapat menggunakan API IMDB untuk berinteraksi dengan database mereka. Kami bahkan mungkin mengintegrasikan API untuk menangani jenis data tertentu yang dapat diunduh dari server.
-   Kami melihat contoh yang disebut `shows`.
-   Melihat `app.py`, kami melihat yang berikut:
    
    ```
    # Searches for shows using Ajax
    
    from cs50 import SQL
    from flask import Flask, render_template, request
    
    app = Flask(__name__)
    
    db = SQL("sqlite:///shows.db")
    
    
    @app.route("/")
    def index():
        return render_template("index.html")
    
    
    @app.route("/search")
    def search():
        q = request.args.get("q")
        if q:
            shows = db.execute("SELECT * FROM shows WHERE title LIKE ? LIMIT 50", "%" + q + "%")
        else:
            shows = []
        return render_template("search.html", shows=shows)
    ```
    
    Perhatikan bahwa `search`rute mengeksekusi kueri SQL.
    
-   Melihat `search.html`, Anda akan melihat bahwa ini sangat sederhana:
    
    ```
    {% for show in shows %}
        <li>{{ show["title"] }}</li>
    {% endfor %}
    ```
    
    Perhatikan bahwa ini menyediakan daftar berpoin.
    
-   Terakhir, perhatikan `index.html`, perhatikan bahwa kode _AJAX_ digunakan untuk menggerakkan pencarian:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>shows</title>
        </head>
        <body>
    
            <input autocomplete="off" autofocus placeholder="Query" type="search">
    
            <ul></ul>
    
            <script>
    
                let input = document.querySelector('input');
                input.addEventListener('input', async function() {
                    let response = await fetch('/search?q=' + input.value);
                    let shows = await response.text();
                    document.querySelector('ul').innerHTML = shows;
                });
    
            </script>
    
        </body>
    </html>
    ```
    
    Perhatikan pendengar acara digunakan untuk meminta server secara dinamis untuk memberikan daftar yang cocok dengan judul yang disediakan. Ini akan menemukan `ul`tag di HTML dan memodifikasi halaman web sesuai untuk memasukkan daftar kecocokan.
    
-   Anda dapat membaca lebih lanjut di [dokumentasi AJAX](https://api.jquery.com/category/ajax/) .

## [JSON](https://cs50.harvard.edu/college/2022/fall/notes/9/#json)

-   _Notasi Objek JavaScript_ atau _JSON_ adalah file teks kamus dengan kunci dan nilai. Ini adalah cara mentah dan ramah komputer untuk mendapatkan banyak data.
-   JSON adalah cara yang sangat berguna untuk mendapatkan kembali data dari server.
-   Anda dapat melihat ini beraksi di yang `index.html`kami periksa bersama:
    
    ```
    <!DOCTYPE html>
    
    <html lang="en">
        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>shows</title>
        </head>
        <body>
    
            <input autocomplete="off" autofocus placeholder="Query" type="text">
    
            <ul></ul>
    
            <script>
    
                let input = document.querySelector('input');
                input.addEventListener('input', async function() {
                    let response = await fetch('/search?q=' + input.value);
                    let shows = await response.json();
                    let html = '';
                    for (let id in shows) {
                        let title = shows[id].title.replace('<', '&lt;').replace('&', '&amp;');
                        html += '<li>' + title + '</li>';
                    }
                    document.querySelector('ul').innerHTML = html;
                });
    
            </script>
    
        </body>
    </html>
    ```
    
    Meskipun hal di atas mungkin agak samar, ini memberikan titik awal bagi Anda untuk meneliti JSON sendiri untuk melihat bagaimana hal itu dapat diterapkan di aplikasi web Anda sendiri.
    
-   Anda dapat membaca lebih lanjut di [dokumentasi JSON](https://www.json.org/json-en.html) .

## [Menyimpulkan](https://cs50.harvard.edu/college/2022/fall/notes/9/#summing-up)

Dalam pelajaran ini, Anda belajar cara menggunakan Python, SQL, dan Flask untuk membuat aplikasi web. Secara khusus, kami membahas…

-   MENDAPATKAN
-   POS
-   Labu
-   Sidang
-   AJAX
-   JSON

Sampai jumpa di kuliah terakhir kita!
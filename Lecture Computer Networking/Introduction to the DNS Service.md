# ⭐️ Course Contents ⭐️ 

⌨️ ([0:38:03](https://www.youtube.com/watch?v=qiQR5rTSshw&list=PLUcC-GwJC7M4bq1J4_jSLOjg3jmbD7sp2&index=1&t=2283s)) Introduction to the DNS Service

## Membahas 

![[Pasted image 20230420165102.png]]

# DNS Servers

DNS (Domain Name System) adalah layanan jaringan yang memetakan nama domain ke alamat IP. DNS memudahkan pengguna internet dalam mengakses situs web dan server dengan menggunakan nama domain yang mudah diingat. Selain itu, DNS juga mempercepat proses pencarian, scalable, redundan, keamanan, dan efisien dalam manajemen jaringan. DNS sangat penting dalam menjaga keamanan dan kestabilan jaringan internet saat ini.ww

Lebih detail tentang [[DNS Servers]] (https://en.wikipedia.org/wiki/Domain_Name_System).

![[Pasted image 20230420165323.png]]

## Local DNS server

Local DNS server adalah server DNS yang digunakan oleh jaringan lokal untuk memetakan nama domain ke alamat IP lokal. Local DNS server membantu meningkatkan kecepatan akses internet, meminimalkan penggunaan bandwidth, memperkuat keamanan jaringan, dan memudahkan manajemen jaringan. Local DNS server dapat dioperasikan pada perangkat fisik atau virtual di jaringan lokal.

Lebih detail tentang [[Local DNS server]].

## Top Level Domain ( TLD ) server

Top Level Domain (TLD) server adalah server DNS yang bertanggung jawab untuk memetakan nama domain pada level TLD ke alamat IP. TLD server menyimpan informasi mengenai nama server DNS yang berwenang untuk setiap domain pada level TLD dalam database root zone file. TLD server memainkan peran penting dalam infrastruktur DNS dan memfasilitasi akses internet global dengan memastikan setiap nama domain di internet memiliki alamat IP yang tepat dan dapat diakses oleh pengguna internet.

Lebih detail tentang [[TLD]].

## Root Server 

Root server merupakan server DNS yang paling atas dalam hirarki DNS dan bertanggung jawab untuk memetakan nama domain ke alamat IP. Mereka menjaga struktur hirarki DNS, memastikan skalabilitas dan redundansi, serta mempertahankan integritas data DNS. Root server juga berperan penting dalam keamanan jaringan dengan menerapkan kebijakan keamanan seperti DNSSEC untuk mencegah serangan DNS spoofing dan penggunaan domain palsu. Sebagai bagian penting dari infrastruktur internet, Root server memainkan peran yang krusial dalam menjaga keamanan dan keandalan jaringan global.

Regenerate response

Lebih detail tentang [[Root Server]].

![[Pasted image 20230420165702.png]]

## Authoritative

Server authoritative adalah server DNS yang memiliki otoritas atas suatu domain atau subdomain tertentu. Server ini menyimpan informasi lengkap tentang nama domain dan IP address yang terkait dengan domain tersebut, dan memberikan respons yang akurat ketika permintaan DNS diterima. Server authoritative juga dapat menerapkan kebijakan keamanan dan kontrol akses untuk domain yang mereka atur, serta memainkan peran penting dalam menjaga keamanan dan keandalan jaringan internet.

Lebih detail tentang [[Authoritative]].

## Non-authoritative

Server non-authoritative dalam sistem DNS adalah server yang tidak memiliki otoritas penuh atas domain atau subdomain tertentu, namun dapat memberikan informasi DNS yang akurat tentang domain tersebut. Mereka sering digunakan sebagai proxy atau cache server untuk mengurangi waktu yang dibutuhkan untuk memperoleh informasi DNS dan mencegah overload pada server authoritative. Meskipun tidak menerapkan kebijakan keamanan, server non-authoritative berperan penting dalam memastikan ketersediaan dan keandalan jaringan internet.

Lebih detail tentang [[Non-authoritative]].

![[Pasted image 20230420170300.png]]

# DNS Records

DNS record adalah data yang disimpan dalam sistem DNS untuk memetakan nama domain ke alamat IP atau menyimpan informasi lain terkait dengan domain. DNS record memiliki beragam jenis, seperti record A, record MX, record CNAME, dan record TXT, dan dapat diubah atau diperbarui oleh administrator DNS sesuai kebutuhan. DNS record sangat penting dalam menjaga ketersediaan dan keandalan jaringan internet karena memastikan keakuratan informasi DNS dan memungkinkan pengguna untuk mengakses situs web dan layanan online dengan mudah.

Lebih detail tentang [[DNS Records]].

## A record

A record adalah jenis DNS record yang sangat penting dalam menjaga ketersediaan dan keandalan jaringan internet. Dengan memetakan nama domain ke alamat IPv4, A record memungkinkan pengguna untuk mengakses situs web dan layanan online melalui alamat domain yang mudah diingat. Selain itu, A record juga dapat digunakan untuk menetapkan beberapa alamat IP untuk sebuah nama domain melalui Multiple A records. Setiap A record memiliki nilai TTL yang menentukan berapa lama cache DNS harus menyimpan informasi tentang record tersebut sebelum memperbarui informasi dari server DNS. Jika ada perubahan pada alamat IP atau ingin menetapkan multiple A records untuk sebuah nama domain, administrator DNS harus memperbarui atau mengubah A record tersebut. Karena A record adalah salah satu jenis DNS record yang paling umum digunakan, maka pemahaman yang baik tentang A record sangat penting bagi administrator jaringan dan pengembang web.

Lebih detail tentang [[A record]].

## AAAA record

AAAA record adalah jenis DNS record yang digunakan untuk memetakan nama domain ke alamat IPv6. Poin penting dari AAAA record adalah bahwa mereka memungkinkan pengguna untuk mengakses situs web dan layanan online melalui alamat domain yang menggunakan protokol IPv6, dan dapat digunakan bersama dengan A record. Setiap AAAA record memiliki nilai TTL yang menentukan berapa lama cache DNS harus menyimpan informasi tentang record tersebut. AAAA record harus diperbarui oleh administrator DNS jika ada perubahan pada alamat IPv6. Melalui pemahaman tentang AAAA record, administrator jaringan dan pengembang web dapat memastikan bahwa situs web dan layanan online yang mereka kelola dapat diakses oleh pengguna yang menggunakan protokol IPv6.

Lebih detail tentang [[AAAA record]].

## CNAME record

CNAM record atau Canonical Name record adalah jenis DNS record yang digunakan untuk memberikan alias untuk nama domain. CNAM record memungkinkan pengguna untuk mengaitkan beberapa nama domain yang berbeda dengan satu alamat IP. Dalam penggunaannya, CNAM record dapat meningkatkan fleksibilitas dan kemudahan dalam manajemen domain dan alamat IP, memudahkan dalam pengubahan nama domain, dan juga memudahkan dalam pengelolaan subdomain. Sebagai seorang administrator DNS atau pengembang web, memahami CNAM record sangat penting untuk memastikan bahwa nama domain dapat dikelola dengan baik dan mempercepat proses pembaruan dan pengaturan domain.

Lebih detail tentang [[CNAME]].

## PTR record

PTR record dalam DNS digunakan untuk memetakan alamat IP ke nama domain. Poin penting dari PTR record adalah bahwa ia memungkinkan reverse DNS lookup, yang memungkinkan pengguna untuk mengetahui nama domain yang terkait dengan alamat IP tertentu. PTR record digunakan terutama untuk tujuan keamanan, seperti memverifikasi identitas pengirim email dan melacak aktivitas jaringan yang mencurigakan. Selain itu, PTR record juga digunakan dalam konfigurasi jaringan yang rumit dan memfasilitasi penyelarasan dua arah antara nama domain dan alamat IP.

Lebih detail tentang [[PTR]].

## MX record

MX record pada DNS adalah jenis catatan yang menunjukkan alamat server email untuk sebuah domain. Catatan ini penting untuk mengarahkan email ke server email yang benar, dan terdiri dari preference dan mail server. Penting untuk memberikan preference yang benar dan menggunakan MX record yang tepat agar email dapat diantarkan dengan benar. Perubahan MX record dapat memakan waktu hingga 48 jam untuk disebarkan di seluruh dunia.

Lebih detail tentang [[MX]]. 

![[Pasted image 20230420171705.png]]

# Dynamic DNS (DDNS)

Dynamic DNS (DDNS) adalah layanan yang menghubungkan alamat IP dinamis dengan nama domain statis agar pengguna dapat mengakses perangkat di jaringan lokal dari jarak jauh dengan mudah. Ini berguna jika pengguna memiliki perangkat yang perlu diakses dari jarak jauh seperti kamera pengawas atau server.

Lebih detail tentang [[DDNS]].

## DDNS updating

DDNS updating adalah proses untuk memperbarui alamat IP publik yang terkait dengan nama domain pengguna. Ini dilakukan dengan menggunakan perangkat lunak khusus yang terhubung ke server DDNS. DDNS updating sangat berguna untuk pengguna dengan koneksi internet yang dinamis dan memungkinkan pengguna untuk mengakses perangkat mereka melalui internet dengan menggunakan nama domain yang mudah diingat. Penting untuk dilakukan secara teratur untuk memastikan alamat IP yang terkait dengan nama domain selalu terbaru.

Lebih detail tentang [[DDNS Updating]].

![[Pasted image 20230420193231.png]]

# Summary

![[Pasted image 20230420193540.png]]
Non-authoritative server dalam sistem DNS adalah server DNS yang tidak memiliki otoritas penuh atas domain atau subdomain tertentu, namun dapat memberikan informasi DNS yang akurat tentang domain tersebut. Non-authoritative server sering kali digunakan sebagai proxy atau cache server yang dapat menyimpan informasi DNS dari server authoritative untuk domain tersebut.

Berikut adalah beberapa hal yang perlu diketahui tentang server non-authoritative:

1.  Tidak memiliki otoritas penuh atas domain Server non-authoritative tidak memiliki otoritas penuh atas domain atau subdomain tertentu. Mereka hanya memiliki salinan informasi DNS dari server authoritative dan dapat memberikan informasi DNS yang akurat tentang domain tersebut.
    
2.  Digunakan sebagai proxy atau cache server Server non-authoritative sering kali digunakan sebagai proxy atau cache server yang dapat menyimpan informasi DNS dari server authoritative untuk domain tersebut. Ini membantu mengurangi waktu yang dibutuhkan untuk memperoleh informasi DNS dan meningkatkan kinerja jaringan.
    
3.  Membantu mencegah overload pada server authoritative Dengan adanya server non-authoritative yang menyediakan informasi DNS dari cache, server authoritative tidak perlu menghasilkan respons untuk setiap permintaan DNS. Hal ini dapat membantu mencegah overload pada server authoritative dan memastikan ketersediaan informasi DNS.
    
4.  Tidak menerapkan kebijakan keamanan Karena tidak memiliki otoritas penuh atas domain, server non-authoritative tidak menerapkan kebijakan keamanan untuk domain tersebut. Namun, mereka dapat menerapkan kebijakan keamanan dan kontrol akses untuk informasi DNS yang mereka simpan di cache.
    

Dalam penggunaannya, server non-authoritative berinteraksi dengan server authoritative dan server DNS lainnya untuk memetakan nama domain ke alamat IP yang tepat. Mereka menyediakan informasi DNS dari cache dan memberikan respons DNS yang akurat dan cepat. Sebagai bagian penting dari infrastruktur DNS, server non-authoritative membantu memastikan ketersediaan dan keandalan jaringan internet.
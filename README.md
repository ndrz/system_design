# System Design 

----------------

# Daftar Isi

- **Lets Started**

  - [System Design ?](#mengapa-desain-sistem-begitu-penting)
  
- **Chapter I**

  - [IP](#ip)
  - [OSI Model](#osi-model)
  - [TCP and UDP](#tcp-and-udp)
  - [Domain Name System (DNS)](#domain-name-system-dns)
  - [Load Balancing](#load-balancing)
  - [Clustering](#clustering)
  - [Caching](#caching)
  - [Content Delivery Network (CDN)](#content-delivery-network-cdn)
  - [Proxy](#proxy)
  - [Availability](#availability)
  - [Scalability](#scalability)
  - [Storage](#storage)

- **Chapter II**

  - [Databases and DBMS](#databases-and-dbms)
  - [SQL databases](#sql-databases)
  - [NoSQL databases](#nosql-databases)
  - [SQL vs NoSQL databases](#sql-vs-nosql-databases)
  - [Database Replication](#database-replication)
  - [Indexes](#indexes)
  - [Normalization and Denormalization](#normalization-and-denormalization)
  - [ACID and BASE consistency models](#acid-and-base-consistency-models)
  - [CAP theorem](#cap-theorem)
  - [PACELC Theorem](#pacelc-theorem)
  - [Transactions](#transactions)
  - [Distributed Transactions](#distributed-transactions)
  - [Sharding](#sharding)
  - [Consistent Hashing](#consistent-hashing)
  - [Database Federation](#database-federation)

- **Chapter III**

  - [N-tier architecture](#n-tier-architecture)
  - [Message Brokers](#message-brokers)
  - [Message Queues](#message-queues)
  - [Publish-Subscribe](#publish-subscribe)
  - [Enterprise Service Bus (ESB)](#enterprise-service-bus-esb)
  - [Monoliths and Microservices](#monoliths-and-microservices)
  - [Event-Driven Architecture (EDA)](#event-driven-architecture-eda)
  - [Event Sourcing](#event-sourcing)
  - [Command and Query Responsibility Segregation (CQRS)](#command-and-query-responsibility-segregation-cqrs)
  - [API Gateway](#api-gateway)
  - [REST, GraphQL, gRPC](#rest-graphql-grpc)
  - [Long polling, WebSockets, Server-Sent Events (SSE)](#long-polling-websockets-server-sent-events-sse)

- **Chapter IV**

  - [Geohashing and Quadtrees](#geohashing-and-quadtrees)
  - [Circuit breaker](#circuit-breaker)
  - [Rate Limiting](#rate-limiting)
  - [Service Discovery](#service-discovery)
  - [SLA, SLO, SLI](#sla-slo-sli)
  - [Disaster recovery](#disaster-recovery)
  - [Virtual Machines (VMs) and Containers](#virtual-machines-vms-and-containers)
  - [OAuth 2.0 and OpenID Connect (OIDC)](#oauth-20-and-openid-connect-oidc)
  - [Single Sign-On (SSO)](#single-sign-on-sso)
  - [SSL, TLS, mTLS](#ssl-tls-mtls)

- **Chapter V**

  - [System Design Interviews](#system-design-interviews)
  - [URL Shortener](#url-shortener)
  - [WhatsApp](#whatsapp)
  - [Twitter](#twitter)
  - [Netflix](#netflix)
  - [Uber](#uber)

- **Appendix**

  - [Next Steps](#next-steps)
  - [References](#references)


# Apa itu system design?

Desain sistem adalah proses mendefinisikan arsitektur, antarmuka, dan data untuk sistem yang memenuhi persyaratan tertentu. Desain sistem memenuhi kebutuhan bisnis atau organisasi Anda melalui sistem yang koheren dan efisien. Ini membutuhkan pendekatan sistematis untuk membangun dan membangun sistem. Desain sistem yang baik mengharuskan kita memikirkan segalanya, mulai dari infrastruktur hingga data dan cara penyimpanannya.

## Mengapa Desain Sistem begitu penting?

Desain sistem membantu kami menentukan solusi yang memenuhi persyaratan bisnis. Ini adalah salah satu keputusan paling awal yang dapat kita buat saat membangun sistem. Seringkali penting untuk berpikir dari tingkat tinggi karena keputusan ini sangat sulit untuk diperbaiki nanti. Hal ini juga membuat lebih mudah untuk memikirkan dan mengelola perubahan arsitektur saat sistem berkembang.

# IP

Alamat IP adalah alamat unik yang mengidentifikasi perangkat di internet atau jaringan lokal. IP adalah singkatan dari _"Internet Protocol"_, yaitu kumpulan aturan yang mengatur format data yang dikirim melalui internet atau jaringan lokal.

Intinya, alamat IP adalah pengidentifikasi yang memungkinkan informasi terkirim antar perangkat di jaringan. Mereka berisi informasi lokasi dan membuat perangkat dapat diakses untuk komunikasi. Internet membutuhkan cara untuk membedakan antara komputer, router, dan situs web yang berbeda. Alamat IP menyediakan cara untuk melakukannya dan merupakan bagian penting dari cara kerja internet.

## Versi
Sekarang, mari belajar tentang berbagai versi alamat IP:

### IPv4
Protokol Internet asli adalah IPv4 yang menggunakan notasi dot-desimal numerik 32-bit yang hanya memungkinkan sekitar 4 miliar alamat IP. Awalnya, itu sudah lebih dari cukup, tetapi seiring pertumbuhan adopsi internet, kami membutuhkan sesuatu yang lebih baik.

_Contoh:`102.22.192.181`_

### IPv6
IPv6 adalah protokol baru yang diperkenalkan pada tahun 1998. Penyebaran dimulai pada pertengahan tahun 2000-an dan karena pengguna internet telah tumbuh secara eksponensial, itu masih berlangsung.

Protokol baru ini menggunakan notasi heksadesimal alfanumerik 128-bit. Ini berarti bahwa IPv6 dapat menyediakan sekitar ~340e+36 alamat IP. Itu lebih dari cukup untuk memenuhi permintaan yang terus meningkat di tahun-tahun mendatang.

_Contoh:`2001:0db8:85a3:0000:0000:8a2e:0370:7334`_

## Jenis

Mari kita bahas jenis-jenis alamat IP:

### Public


Alamat IP publik adalah alamat di mana satu alamat utama dikaitkan dengan seluruh jaringan Anda. Dalam jenis alamat IP ini, setiap perangkat yang terhubung memiliki alamat IP yang sama.

_Contoh: alamat IP yang diberikan ke router Anda oleh ISP._

### Private

Alamat IP pribadi adalah nomor IP unik yang ditetapkan untuk setiap perangkat yang terhubung ke jaringan internet Anda, termasuk perangkat seperti komputer, tablet, dan ponsel cerdas, yang digunakan di rumah Anda.

_Contoh: Alamat IP yang dihasilkan oleh router rumah untuk perangkat Anda._

### Static

Alamat IP statis tidak berubah dan merupakan alamat yang dibuat secara manual, bukan yang telah ditetapkan. Alamat ini biasanya lebih mahal tetapi lebih dapat diandalkan.

_Contoh: Mereka biasanya digunakan untuk hal-hal penting seperti layanan lokasi geografis yang andal, akses jarak jauh, hosting server, dll._

### Dynamic

Alamat IP dinamis berubah dari waktu ke waktu dan tidak selalu sama. Itu telah ditetapkan oleh server [Dynamic Host Configuration Protocol (DHCP)(https://en.wikipedia.org/wiki/Dynamic_Host_Configuration_Protocol)(https://id.wikipedia.org/wiki/Protokol_Konfigurasi_Hos_Dinamik). Alamat IP dinamis adalah jenis alamat protokol internet yang paling umum. Mereka lebih murah untuk digunakan dan memungkinkan kami untuk menggunakan kembali alamat IP dalam jaringan sesuai kebutuhan.

Contoh: Mereka lebih umum digunakan untuk peralatan konsumen dan penggunaan pribadi.


# OSI Model

Model OSI adalah model logis dan kontekstual yang mendefinisikan komunikasi jaringan yang digunakan oleh sistem yang terbuka untuk interkoneksi dan komunikasi dengan sistem lain. Open System Interconnection (OSI) juga mendefinisikan jaringan logistik dan secara efektif menggambarkan transfer paket komputer dengan menggunakan berbagai lapisan protokol.

Model OSI dapat dilihat sebagai bahasa universal untuk jaringan komputer. Ini didasarkan pada konsep membagi sistem komunikasi menjadi tujuh lapisan abstrak, masing-masing ditumpuk di atas yang terakhir.

## Why does the OSI model matter?

Model Open System Interconnection (OSI) telah mendefinisikan terminologi umum yang digunakan dalam diskusi dan dokumentasi jaringan. Ini memungkinkan kami untuk memisahkan proses komunikasi yang sangat kompleks dan mengevaluasi komponen-komponennya.

Meskipun model ini tidak secara langsung diimplementasikan dalam jaringan TCP/IP yang paling umum saat ini, model ini masih dapat membantu kita melakukan lebih banyak lagi, seperti:

- Mempermudah pemecahan masalah dan membantu mengindentifikasi ancaman di seluruh susunan.
- Mendorong produsen perangkat keras untuk membuat produk jaringan yang dapat berkomunikasi satu sama lain melalui jaringan.
- Penting untuk mengembangkan pola pikir yang mengutamakan keamanan.
- Memisahkan fungsi yang kompleks menjadi komponen yang lebih sederhana.

## Layers

Model OSI terbagi atas 7 lapisan. Setiap lapisan memiliki fungsi yang berbeda.
Ketujuh lapisan tersebut dapat didefinisikan sebagai berikut, dari atas ke bawah:

![osi-model](https://raw.githubusercontent.com/ndrz/system_design/main/files/osi-model.png)

### Application Layer

Application layer merupakan lapisan yang langsung berinteraksi dengan data dari pengguna. Aplikasi perangkat lunak seperti web browser  dan email klien bergantung pada lapisan aplikasi untuk memulai komunikasi. Tetapi harus diperjelas bahwa aplikasi perangkat lunak klien bukan bagian dari application layer, melainkan application layer bertanggung jawab atas protokol dan penanganan data yang diandalkan oleh perangkat lunak untuk menyajikan data yang bermakna bagi pengguna. Protokol yang berada pada layer ini adalah HTTP, FTP, SMTP, dan NFS.

### Presentation Layer

Presentation layer juga disebut Translation layer. Data dari Application layer diekstraksi di sini dan dimanipulasi sesuai format yang diperlukan untuk dikirim melalui jaringan. Fungsi lapisan penyajian adalah : 
- **Translasi/Terjemahan**: Misalnya, ASCII ke EBCDIC.
- **Enkripsi/Dekripsi**: Enkripsi data menerjemahkan data ke dalam bentuk atau kode lain. Data terenkripsi dikenal sebagai ciphertext dan data yang didekripsi dikenal sebagai teks biasa. Nilai kunci digunakan untuk mengenkripsi serta mendekripsi data.
- **Kompresi**: Mengurangi jumlah bit yang perlu ditransmisikan pada jaringan.

### Session Layer

Session Layer adalah lapisan yang bertanggung jawab untuk membuka dan menutup komunikasi antara kedua perangkat. Waktu antara saat komunikasi dibuka dan ditutup dikenal sebagai sesi. Lapisan sesi memastikan bahwa sesi tetap terbuka cukup lama untuk mentransfer semua data yang dipertukarkan, dan kemudian segera menutup sesi untuk menghindari pemborosan sumber daya. Lapisan sesi juga menyinkronkan transfer data dengan pos pemeriksaan.


### Transport Layer

Transport layer menyediakan layanan ke Application layer dan mengambil layanan dari Network Layer. Data di lapisan transport disebut sebagai **segmen** .

Lapisan ini bertanggung jawab atas pengiriman pesan secara end to end. Lapisan transport juga memberikan pengakuan atas transmisi data yang berhasil dan mentransmisikan ulang data jika ditemukan kesalahan.

Di sisi pengirim, lapisan transport menerima data yang diformat dari lapisan atas, melakukan segmentasi, dan juga menerapkan kontrol aliran dan kesalahan untuk memastikan transmisi data yang tepat. Selain itu juga lapisan transport menambahkan nomor port sumber dan tujuan di headernya dan meneruskan data yang tersegmentasi ke Network layer.

Umumnya, nomor port tujuan ini dikonfigurasi, baik secara default ataupun manual. Misalnya, ketika aplikasi web membuat permintaan ke server web, biasanya menggunakan nomor port 80, karena ini adalah port default yang ditetapkan untuk aplikasi web. Banyak aplikasi memiliki port default yang ditetapkan.

Di sisi penerima, lapisan transport atau Transport Layer membaca nomor port dari headernya dan meneruskan data yang telah diterimanya ke aplikasi masing-masing. Lapisan ini juga melakukan pengurutan dan pemasangan kembali data yang tersegmentasi.

Fungsi dari Transport layer adalah sebagai berikut:

- **Segmentasi dan Reassembly** : Lapisan ini menerima pesan dari lapisan (sesi), dan memecah pesan menjadi unit-unit yang lebih kecil. Setiap segmen yang dihasilkan memiliki header yang terkait dengannya. Lapisan transport di stasiun tujuan menyusun kembali pesan.
- **Service Point Addressing** : Untuk mengirimkan pesan ke proses yang benar, header lapisan transport menyertakan jenis alamat yang disebut Service Point Addressing atau alamat port. Jadi dengan menentukan alamat ini, lapisan transport memastikan bahwa pesan dikirim ke proses yang benar.

### Network Layer.

Network layer bertanggung jawab untuk memfasilitasi transfer data antara dua jaringan yang berbeda. Network layer memecah segmen dari Transport layer menjadi unit-unit yang lebih kecil, yang disebut paket, pada perangkat pengirim, dan menyusun kembali paket-paket ini pada perangkat penerima. Network layer juga menemukan jalur fisik terbaik untuk data mencapai tujuannya, ini dikenal sebagai perutean. Jika kedua perangkat yang berkomunikasi berada di jaringan yang sama, maka Network layer tidak diperlukan.


### Data Link Layer

Data Link Layer sangat mirip dengan network layer, kecuali data link layer memfasilitasi transfer data antara dua perangkat di jaringan yang sama. Data Link Layer mengambil paket dari network layer dan memecahnya menjadi potongan-potongan kecil yang disebut frame.


### Physical Layer

Physical Layer ini mencakup peralatan fisik yang terlibat dalam transfer data, seperti kabel dan switches. Physical Layer juga merupakan layer di mana data dikonversi menjadi bit, yang merupakan string 1 dan 0. Physical Layer antara kedua perangkat juga harus menyetujui konvensi sinyal sehingga angka 1 dapat dibedakan dari angka 0 pada kedua perangkat.


# TCP and UDP

## TCP

Transmission Control Protocol (TCP) berorientasi pada koneksi, artinya setelah koneksi dibuat, data dapat ditransmisikan ke kedua arah. TCP memiliki sistem bawaan untuk memeriksa kesalahan dan untuk menjamin data akan dikirim sesuai urutan pengirimannya, menjadikannya protokol yang sempurna untuk mentransfer informasi seperti diam gambar, data file, dan halaman web.

![tcp](https://raw.githubusercontent.com/ndrz/system_design/main/files/tcp.png)

Tetapi sementara TCP secara ditangkapah dapat dipertahankan, mekanisme umpan baliknya juga menghasilkan overhead yang lebih besar, yang berarti penggunaan bandwidth yang tersedia di jaringan lebih besar.

## UDP

User Datagram Protocol (UDP) adalah protokol internet tanpa koneksi yang lebih sederhana di mana layanan pengecekan kesalahan dan pemulihan tidak diperlukan. Dengan UDP, tidak ada overhead untuk membuka koneksi, memelihara koneksi, atau mengakhiri koneksi. Data terus dikirim ke penerima, apakah mereka menerimanya atau tidak.

![udp](https://raw.githubusercontent.com/ndrz/system_design/main/files/udp.png)

Ini lebih disukai untuk komunikasi waktu nyata seperti siaran atau jaringan transmisi multicast. Kita harus menggunakan UDP melalui TCP saat kita membutuhkan latensi terendah dan data terlambat lebih buruk daripada hilangnya data.

## TCP vs UDP

TCP adalah protokol yang berorientasi pada koneksi, sedangkan UDP adalah protokol tanpa koneksi. Perbedaan utama antara TCP dan UDP adalah kecepatan, karena TCP relatif lebih lambat daripada UDP. Secara keseluruhan, UDP adalah protokol yang jauh lebih cepat, lebih sederhana, dan lebih efisien, namun pengiriman ulang paket data yang hilang hanya dimungkinkan dengan TCP.

TCP menyediakan pengiriman data yang dipesan dari pengguna ke server (dan sebaliknya), sedangkan UDP tidak didedikasikan untuk komunikasi end-to-end, juga tidak memeriksa kesiapan penerima.

| Feature             | TCP                                         | UDP                                |
| ------------------- | ------------------------------------------- | ---------------------------------- |
| Connection          | Requires an established connection          | Connectionless protocol            |
| Guaranteed delivery | Can guarantee delivery of data              | Cannot guarantee delivery of data  |
| Re-transmission     | Re-transmission of lost packets is possible | No re-transmission of lost packets |
| Speed               | Slower than UDP                             | Faster than TCP                    |
| Broadcasting        | Does not support broadcasting               | Supports broadcasting              |
| Use cases           | HTTPS, HTTP, SMTP, POP, FTP, etc            | Video streaming, DNS, VoIP, etc    |


# Domain Name System (DNS)

Sebelumnya kita telah mempelajari alamat IP yang memungkinkan setiap mesin terhubung dengan mesin lainnya. Tapi seperti yang kita tahu manusia lebih nyaman dengan nama daripada angka. Lebih mudah mengingat nama seperti google.comdaripada sesuatu seperti 122.250.192.232.

Ini membawa kita ke Sistem Nama Domain (DNS) yang merupakan sistem penaamaan hirarki dan terdesentralisasi yang digunakan untuk menerjemahkan nama domain yang dapat dibaca manusia ke alamat IP.

## How DNS works

![dns](https://raw.githubusercontent.com/ndrz/system_design/main/files/how-dns-works.png)

Pencarian DNS melibatkan delapan langkah berikut:

Klien mengetikkan example.com ke dalam web browser, kueri dikirim ke internet dan diterima oleh penyelesai DNS.
Penyelesaian kemudian secara rekursif menanyakan nama server root DNS.
Server root merespons penyelesaikan dengan alamat Top-Level Domain (TLD).
Resolver kemudian membuat permintaan ke .comTLD.
Server TLD kemudian merespons dengan alamat IP dari server nama domain, example.com .
Terakhir, penyelesaikan rekursif mengirimkan kueri ke server nama domain.
Alamat IP untuk example.com kemudian dikembalikan ke penyelesai dari nama server.
Penyelesaian DNS kemudian merespons ke browser web dengan alamat IP dari domain yang diminta pada awalnya.
Setelah alamat IP diselesaikan, klien harus dapat meminta konten dari alamat IP yang diselesaikan. Misalnya, IP yang diselesaikan dapat mengembalikan halaman web untuk dirender di browser.

## Server types

Sekarang, mari kita lihat empat kelompok server utama yang menyusun infrastruktur DNS.

### DNS Resolver

Penyelesaian DNS (juga dikenal sebagai penyelesai rekursif DNS) adalah perhentian pertama dalam kueri DNS. Penyelesaian rekursif bertindak sebagai perantara antara klien dan server nama DNS. Setelah menerima kueri DNS dari klien web, penyelesaikan rekursif akan merespon dengan data yang di-cache, atau mengirimkan permintaan ke server nama root, diikuti dengan permintaan lain ke server nama TLD, lalu satu permintaan terakhir ke server nama resmi. Setelah menerima respon dari server nama otoritatif yang berisi alamat IP yang diminta, penyelesaikan rekursif kemudian mengirimkan respon ke klien.

### DNS root server

Server root menerima kueri penyelesai rekursif yang menyertakan nama domain, dan server nama root merespons dengan mengarahkan penyelesaikan rekursif ke server nama TLD, berdasarkan ekstensi domain tersebut ( , , , dll .com. .net) .org. Root nameserver diawasi oleh organisasi nirlaba bernama Internet Corporation for Assigned Names and Numbers (ICANN) .

Ada 13 nama server akar DNS yang diketahui oleh setiap penyelesai rekursif. Perhatikan bahwa meskipun ada 13 root nameserver, bukan berarti hanya ada 13 mesin di sistem root nameserver. Ada 13 jenis root nameserver, tetapi ada beberapa pertarungan dari masing-masing di seluruh dunia, yang menggunakan perutean Anycast untuk memberikan respons cepat.


### TLD nameserver

Server nama TLD menyimpan informasi untuk semua nama domain yang berbagi ekstensi domain umum, seperti .com, .net, atau apa pun yang muncul setelah titik terakhir di URL.

Pengelolaan server nama TLD ditangani oleh Internet Assigned Numbers Authority (IANA) , yang merupakan cabang dari ICANN . IANA memecah server TLD menjadi dua kelompok utama:

Domain tingkat atas umum : Ini adalah domain seperti .com, .org, .net, .edu, dan .gov.
Domain tingkat atas kode negara : Ini termasuk semua domain yang khusus untuk suatu negara atau negara bagian. Contohnya adalah .uk, .us, .ru, dan .jp.

### Authoritative DNS server

Server nama otoritatif biasanya merupakan langkah terakhir penyelesain dalam perjalanan untuk mendapatkan alamat IP. Server nama otoritatif berisi informasi khusus untuk nama domain yang dilayaninya (misalnya google.com ) dan dapat memberikan penyelesaikan rekursif dengan alamat IP server yang ditemukan di catatan DNS A, atau jika domain memiliki catatan CNAME (alias) itu akan memberikan penyelesaikan rekursif dengan domain alias , di mana penyelesai rekursif harus melakukan pencarian DNS yang sama sekali baru untuk mendapatkan catatan dari server nama otoritatif (seringkali catatan A yang berisi alamat IP). Jika tidak dapat menemukan domain, kembalikan pesan NXDOMAIN.

## Query Types

Ada tiga jenis kueri dalam sistem DNS:
### Recursive

Dalam kueri rekursif, klien DNS memerlukan server DNS (biasanya penyelesai rekursif DNS) akan merespons klien dengan catatan sumber daya yang diminta atau pesan kesalahan jika penyelesain tidak dapat menemukan catatan.

### Iterative

Dalam kueri iteratif, klien DNS memberikan nama host, dan Penyelesaian mengembalikan DNS jawaban terbaik yang dapat diberikan. Jika penyelesai DNS memiliki catatan DNS yang relevan di cache-nya, itu akan mengembalikannya. Jika tidak, ini merujuk klien DNS ke Server Root atau Server Nama Resmi lainnya yang terdekat dengan zona DNS yang diperlukan. Klien DNS kemudian harus mengulang kueri secara langsung terhadap server DNS yang dibatalkan.

### Non-recursive

Kueri non-rekursif adalah kueri di mana Penyelesaian DNS sudah mengetahui jawabannya. Itu baik segera mengembalikan catatan DNS karena sudah menyimpan di cache lokal, atau menanyakan Server Nama DNS yang memegang untuk catatan, artinya pasti memegang IP yang benar untuk nama host itu. Dalam kedua kasus tersebut, putaran kueri tambahan tidak diperlukan (seperti dalam kueri rekursif atau iteratif). Sebaliknya, respon segera dikembalikan ke klien.

## Record Types


## Subdomains


## DNS Zones


## DNS Caching


## Reverse DNS


## Examples


# Load Balancing


## But why?


## Workload distribution
## Layers


### Network layer


### Application layer


## Types


### Software


### Hardware


## Routing Algorithms

Now, let's discuss commonly used routing algorithms:


## Advantages


## Redundant load balancers


## Features


### Active-Active



### Active-Passive


## Advantages


## Load balancing vs Clustering


## Challenges



## Examples


# Caching


## Caching and Memory


## Cache hit and Cache miss

### Cache hit


### Cache miss


## Cache Invalidation


### Write-through cache


### Write-around cache


### Write-back cache


## Eviction policies

Following are some of the most common cache eviction policies:


## Distributed Cache


## Global Cache



## Use cases


**When not to use caching?**


## Advantages


## Examples



# Content Delivery Network (CDN)

## How does a CDN work?


## Types


### Push CDNs


### Pull CDNs


## Disadvantages



## Examples


# Proxy

## Types


### Forward Proxy


### Reverse Proxy



## Load balancer vs Reverse Proxy


## Examples


# Availability

## Availability in Sequence vs Parallel

### Sequence




  
  


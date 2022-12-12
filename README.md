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

![osi-model](https://raw.githubusercontent.com/ndrz/system_design/main/files/osi-model/osi-model.png)

### Application Layer

Application layer merupakan lapisan yang langsung berinteraksi dengan data dari pengguna. Aplikasi perangkat lunak seperti web browser  dan email klien bergantung pada lapisan aplikasi untuk memulai komunikasi. Tetapi harus diperjelas bahwa aplikasi perangkat lunak klien bukan bagian dari application layer, melainkan application layer bertanggung jawab atas protokol dan penanganan data yang diandalkan oleh perangkat lunak untuk menyajikan data yang bermakna bagi pengguna. Protokol yang berada pada layer ini adalah HTTP, FTP, SMTP, dan NFS.

### Presentation Layer

Presentation layer juga disebut Translation layer. Data dari Application layer diekstraksi di sini dan dimanipulasi sesuai format yang diperlukan untuk dikirim melalui jaringan. Fungsi lapisan penyajian adalah : 
- **Translasi/Terjemahan**: Misalnya, ASCII ke EBCDIC.
- **Enkripsi/Dekripsi**: Enkripsi data menerjemahkan data ke dalam bentuk atau kode lain. Data terenkripsi dikenal sebagai ciphertext dan data yang didekripsi dikenal sebagai teks biasa. Nilai kunci digunakan untuk mengenkripsi serta mendekripsi data.
- **Kompresi**: Mengurangi jumlah bit yang perlu ditransmisikan pada jaringan.

### Session


### Transport


### Network


### Data Link


### Physical



# TCP and UDP

## TCP




## UDP


## TCP vs UDP


# Domain Name System (DNS)


## How DNS works


## Server types

Now, let's look at the four key groups of servers that make up the DNS infrastructure.

### DNS Resolver


### DNS root server



### TLD nameserver



### Authoritative DNS server


## Query Types


### Recursive


### Iterative


### Non-recursive


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




  
  


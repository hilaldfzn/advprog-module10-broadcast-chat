# **Rust Tutorial & Exercise**
**Muhammad Hilal Darul Fauzan**<br/>
**2206830542**<br/>
**Pemrograman Lanjut C**<br/>

## **Tutorial Modul 10: Asynchronous Programming**

### 2.1. Original code of broadcast chat.

![3 Client](images/image.jpg)
![with 1 Server](images/image2.jpg)

Berdasarkan gambar di atas, terlihat bahwa ada tiga client yang masing-masing mengirimkan pesan. Gambar tersebut juga menunjukkan bahwa server menerima pesan dari tiap client dan kemudian mengirimkannya kembali ke semua client. Untuk menjalankan program tersebut, langkah pertama yang saya lakukan adalah membuka empat terminal. Lalu, jalankan perintah `cargo run --bin server` untuk mengatur server. Kemudian diikuti dengan menjalankan perintah `cargo run --bin client` di tiga terminal sisanya untuk mengaktifkan tiga client. Setelah itu, di terminal yang berfungsi sebagai client, pesan dapat diketik dan dikirimkan ke server. Selanjutnya, server akan mengirimkannya ke semua client yang terkoneksi dengannya.

### 2.2. Modifying the websocket port

Untuk mengubah port dari 2000 menjadi 8080, ubah potongan kode berikut pada `src/server.rs` dan `src/client.rs`.
```rust
// src/server.rs
let listener = TcpListener::bind("127.0.0.1:2000").await?; // before
let listener = TcpListener::bind("127.0.0.1:8080").await?; // after

// src/client.rs
ClientBuilder::from_uri(Uri::from_static("ws://127.0.0.1:2000")) // before
ClientBuilder::from_uri(Uri::from_static("ws://127.0.0.1:8080")) // after
```

Berdasarkan kode pada `src/bin/server.rs` dan `src/bin/client.rs`, kedua program tersebut menggunakan protokol WebSocket yang sama yang dikelola oleh library `tokio_websockets`. Hal ini memastikan bahwa komunikasi antara client dan server berjalan menggunakan protokol yang konsisten dan terdefinisi dengan baik.

Dari gambar di bawah ini, terlihat juga bahwa program masih beroperasi dengan baik meskipun terdapat perubahan pada port yang digunakan. Hal ini menunjukkan fleksibilitas dalam konfigurasi konektivitas antara client dan server. <br>
![Re-run Client](images/image3.jpg)
![Re-run Server](images/image4.jpg)
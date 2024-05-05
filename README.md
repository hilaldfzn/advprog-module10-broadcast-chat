# **Rust Tutorial & Exercise**
**Muhammad Hilal Darul Fauzan**<br/>
**2206830542**<br/>
**Pemrograman Lanjut C**<br/>

## **Tutorial Modul 10: Asynchronous Programming**

## 2.1. Original code of broadcast chat.

![3 Client](images/image.jpg)
![with 1 Server](images/image2.jpg)

Berdasarkan gambar di atas, terlihat bahwa ada tiga client yang masing-masing mengirimkan pesan. Gambar tersebut juga menunjukkan bahwa server menerima pesan dari tiap client dan kemudian mengirimkannya kembali ke semua client. Untuk menjalankan program tersebut, langkah pertama yang saya lakukan adalah membuka empat terminal. Lalu, jalankan perintah `cargo run --bin server` untuk mengatur server. Kemudian diikuti dengan menjalankan perintah `cargo run --bin client` di tiga terminal sisanya untuk mengaktifkan tiga client. Setelah itu, di terminal yang berfungsi sebagai client, pesan dapat diketik dan dikirimkan ke server. Selanjutnya, server akan mengirimkannya ke semua client yang terkoneksi dengannya.
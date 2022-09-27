# Writing and Presentation Test Week 1

## Unix Command Line



### Shell
- Mungkin Anda sudah pernah menggunakan CLI sebelumnya, contoh contoh dari CLI adalah sebagai berikut: sh, bash, zsh, CMD.exe. beberapa contoh CLI yang pernah kita gunakan tersebut merupakan salah satu jenis dari Shell. 
- Shell merupakan sebuah program komputer atau environment yang dapat menampilkan layanan operating system kepada user sehingga user dapat berkomunikasi atau memberikan perintah kepada sistem

### Command Line Interface
- Command Line Interface (CLI) adalah salah satu jenis Shell yang berbasis teks untuk memasukan perintah dalam menjalankan fungsi dari sistem operasi
- Metode yang paling umum digunakan untuk mengakses CLI menggunakan terminal adalah menggunakan CMD, tetapi untuk tingkat lebih lanjut biasanya juga digunakan sh, zsh ataupun menggunakan bash milik Git. 

### File System Stucture
- Direktori yang berisi file dan folder kita di dalam sebuah PC biasa di susun dalam bentuk pohon (tree). Itulah yang disebut filesystem, gunanya untuk memanajemen penyimpanan data yang kita miliki ke dalam sebuah sistem penyimpanan. Sedangkan, pada akhirnya terdapat sebuah direktori dengan hirarki paling atas yaitu root directory (juga disebut dengan hirarki pertama).

### Perintah dasar Unix Command Line
- Ketika kita mengakses sebuah terminal menggunakan CLI, terdapat banyak sekali perintah-perintah yang dapat digunakan untuk mengaksses file system struktur yang kita miliki. Perintah-perintah tersebut dikelompokkan sebagai berikut: 
  - Navigasi
  - Memanipulasi file
  - Memanipulasi folder
  - Teks
  - Menginstal suatu hal
 
 -  Untuk melihat curent working directory sendiri dapat menggunakan perintah **pwd** (Print working directory)
    
    ![gambar](https://user-images.githubusercontent.com/83742894/192573340-af45ad20-fe6c-4268-b324-ebc9619a33cf.png)

 -  Command untuk melihat isi dari sebuah directory yaitu **ls** (list)
    
    ![gambar](https://user-images.githubusercontent.com/83742894/192573693-f190eb62-8a77-4310-870e-9439cd67d3c8.png)

 -  Command untuk berpindah directory yaitu CD (change directory), cara penggunaannya adalah menuliskan cd lalu setelahnya kita menuliskan direktori yang menjadi target kita seperti ini: CD <direktori>
    
    ![gambar](https://user-images.githubusercontent.com/83742894/192577732-d3b82295-9824-4b45-bd8f-d62c622d9a47.png)

 -  Command untuk melihat isi files adalah cat, cara penggunaannya adalah dengan menulis cat beserta tanda “>” beserta nama file dan tipe filenya. Contoh: cat > error.log
    
    ![gambar](https://user-images.githubusercontent.com/83742894/192577804-2f410d4c-dd40-4dfd-87fb-612b508c67da.png)  

 -  Command untuk membuat file yaitu touch, sedangkan untuk membuat direktori kita bisa menggunakan command mkdir. Contoh penggunaannya adalah sebagai berikut: 
  
    ![gambar](https://user-images.githubusercontent.com/83742894/192578037-e3595fc2-3eb1-4f68-a152-d0aa379e6e7b.png)

 -  Command untuk menyalin file adalah cp, sedangkan untuk menyalin direktori kita harus menuliskan command cp -R. contoh penggunaannya adalah sebagai berikut: 
   
    ![gambar](https://user-images.githubusercontent.com/83742894/192578072-f4514084-b288-4b21-bd72-3e2e6709b0ee.png)
    
    Setelah perintah cp, kita bisa menuliskan nama dari file yang kita copy. Jika di dalam folder tidak ada file dengan nama serupa, maka file akan di copy ke dalam folder saat ini. Tetapi, bisa juga menuliskan direktori tujuan untuk copy file ke folder tersebut. Hal ini juga dapat diterapkan ketika melakukan copy pada sebuah folder/direktori. Berikut penerapannya kepada sebuah folder/direktori: 
    
    ![gambar](https://user-images.githubusercontent.com/83742894/192578365-17bb7192-5b72-4720-8995-4ed0a80e2b4a.png)
    
    ![gambar](https://user-images.githubusercontent.com/83742894/192578391-48bdca64-e232-4f89-84a9-f25590cfb941.png)

  -  Comand untuk me-rename sebuah file yaitu mv. Selain berfungsi untuk memindah lokasi file, mv juga dapat digunakan untuk me-rename sebuah file/direktori. Cara penggunaannya adalah mv (nama file) (nama file baru) / mv (nama direktori) (nama direktori baru). Penggunaannya adalah sebagai berikut: 
     
        ![gambar](https://user-images.githubusercontent.com/83742894/192578879-288b4cc9-25a7-44e1-a23f-6819bad14ac5.png)

  -  Untuk menghapus file dapat menggunakan command rm, sedangkan untuk menghapus direktori menggunakan command rm -r. Contoh penggunaannya adalah sebagai berikut: 
   
        ![gambar](https://user-images.githubusercontent.com/83742894/192578978-0ab72e10-9cf1-42cf-9891-9a73c0842a90.png)



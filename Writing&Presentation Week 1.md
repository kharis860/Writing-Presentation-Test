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

 -  Command untuk berpindah directory yaitu CD (change directory), cara penggunaannya adalah menuliskan cd lalu setelahnya kita menuliskan direktori yang menjadi target kita seperti ini: 
 
    ![gambar](https://user-images.githubusercontent.com/83742894/192577732-d3b82295-9824-4b45-bd8f-d62c622d9a47.png)

 -  Command untuk melihat isi files adalah **cat**, cara penggunaannya adalah dengan menulis cat beserta tanda “>” beserta nama file dan tipe filenya. Contoh: cat > error.log
   
    ![gambar](https://user-images.githubusercontent.com/83742894/192577804-2f410d4c-dd40-4dfd-87fb-612b508c67da.png)  

 -  Command untuk membuat file yaitu **touch**, sedangkan untuk membuat direktori kita bisa menggunakan command mkdir. Contoh penggunaannya adalah sebagai berikut: 
  
    ![gambar](https://user-images.githubusercontent.com/83742894/192578037-e3595fc2-3eb1-4f68-a152-d0aa379e6e7b.png)

 -  Command untuk menyalin file adalah **cp**, sedangkan untuk menyalin direktori kita harus menuliskan command cp -R. contoh penggunaannya adalah sebagai berikut: 
   
    ![gambar](https://user-images.githubusercontent.com/83742894/192578072-f4514084-b288-4b21-bd72-3e2e6709b0ee.png)
    
    Setelah perintah cp, kita bisa menuliskan nama dari file yang kita copy. Jika di dalam folder tidak ada file dengan nama serupa, maka file akan di copy ke dalam folder saat ini. Tetapi, bisa juga menuliskan direktori tujuan untuk copy file ke folder tersebut. Hal ini juga dapat diterapkan ketika melakukan copy pada sebuah folder/direktori. Berikut penerapannya kepada sebuah folder/direktori: 
    
    ![gambar](https://user-images.githubusercontent.com/83742894/192578365-17bb7192-5b72-4720-8995-4ed0a80e2b4a.png)
    
    ![gambar](https://user-images.githubusercontent.com/83742894/192578391-48bdca64-e232-4f89-84a9-f25590cfb941.png)

  -  Comand untuk me-rename sebuah file yaitu **mv**. Selain berfungsi untuk memindah lokasi file, mv juga dapat digunakan untuk me-rename sebuah file/direktori. Cara penggunaannya adalah mv (nama file) (nama file baru) / mv (nama direktori) (nama direktori baru). Penggunaannya adalah sebagai berikut: 
     
        ![gambar](https://user-images.githubusercontent.com/83742894/192578879-288b4cc9-25a7-44e1-a23f-6819bad14ac5.png)

  -  Untuk menghapus file dapat menggunakan command **rm**, sedangkan untuk menghapus direktori menggunakan command rm -r. Contoh penggunaannya adalah sebagai berikut: 
   
        ![gambar](https://user-images.githubusercontent.com/83742894/192578978-0ab72e10-9cf1-42cf-9891-9a73c0842a90.png)


## Git & GitHub Dasar


### Alasan Git & GitHub Merupakan Tools Wajib untuk Digunakan
- Git merupakan sebuah Version Control System yang berguna untuk mencatat setiap perubahan pada file project yang kita miliki baik itu dikerjakan hanya oleh individu maupun dikerjakan oleh tim. Git biasa digunakan karena dengan kelebihannya di atas seseorang dapat menyimpan file dengan lebih efektif. Sedangkan GitHub adalah tempat berbasis cloud yang dapat kita gunakan untuk menyimpan project kita secara cloud. 
- Jadi, tujuan utamanya adalah agar kita dapat berkolaborasi dengan orang lain pada project yang sama tanpa harus repot-repot untuk copy paste folder project dengan perubahan terbaru ataupun harus saling tunggu ketika akan melanjutkan penulisan kode pada sebuah project.

### Perbedaan Git dan GitHub
- Berdasarkan paparan yang telah disampaikan diatas maka perbedaan Git dan GitHub adalah sebagai berikut: 
  -  Git berperan sebagai tools yang menyimpan setiap perubahan pada project yang kita miliki beserta siapa saja yang melakukan perubahan pada project tersebut
  -  Sedangkan, GitHub merupakan sebuah tools yang berguna untuk upload project yang telah disimpan oleh Git ke dalah suatu wadah berbasis cloud agar kita bisa mengerjakannya secara kolaborasi dengan orang lain. Kedua tools ini jika dipakai secara bersamaan dapat meningkatkan fungsionalitas dari masing-masing tools menjadi lebih luas

### Alur Kerja Git dan GitHub
#### Alur kerja Git: 
1. Ketika pertama kali menggunakan Git, user harus mengkonfigurasi Git yang mereka miliki agar identitasnya dapat ditampilkan dengan baik
2. User melakukan pengecekan status untuk mengetahui rincian dari aksi yang telah diberlakukan ke dalam suatu project
3. User melakukan perintah Git add agar sebuah project berubah status menjadi staged dan siap untuk melakukan commit (dalam tahap ini project belum tersimpan di version control)
4. User melakukan commit, sehingga file sudah tersimpan di dalam version control beserta informasi siapa saja yang melakukan perubahan ke dalam file tersebut

#### Alur Kerja GitHub
1. User membuat akun GitHub jika belum pernah menggunakan GitHub sebelumnya
2. User membuat sebuah repository, biasanya kita harus memasukan nama repository beserta deskripsi untuk menjelaskan isi dari repository tersebut. Atur juga repository Anda ingin bersifat public atau private
3. Nantinya repository ini akan digunakan sebagai tempat untuk menampung segala hal yang telah kita simpan menggunakan Git sebelumnya
4. Agar alur nomor 3 dapat berlaku, kita harus menyambungkan Git & GitHub kita menggunakan command Git remote
5. Setelah kita berhasil menyambungkan keduanya, maka kita bisa melakukan upload project kita ke GitHub menggunakan command push

### Membuat Repository Git

1.  Ketika kita ingin menggunakan GitHub, kita harus membuat repository terlebih dahulu. Repository merupakan sebuah wadah atau tempat yang nantinya digunakan untuk menyimpan project yang telah kita buat. Cara membuat repository adalah sebagai berikut:
![gambar](https://user-images.githubusercontent.com/83742894/192589341-740d7af1-3e0f-4db3-949f-328b671910d0.png)

2. Pilih New repository pada dropdown + pada pojok kanan atas tampilan GitHub
![gambar](https://user-images.githubusercontent.com/83742894/192589443-d150b595-4561-4b73-814c-e0393089c2be.png)

3. Isi nama repository dan tambahkan juga deskripsi repository dan informasi-informasi lainnya yang anda perlukan

### Commit pada Git 

Menggulas sedikit materi yang telah saya paparkan di atas. Commit berfungsi untuk merupah status dari project yang telah kita simpan menjadi staged sehingga siap untuk melakukan commit dan nantinya bisa melakukan push ke GitHub. Cara melakukan Commit adalah sebagai berikut: 
1. Lakukan inisialisasi terlebih dahulu untuk membuat repository pada file lokal yang nantinya akan ada file .git. kita hanya perlu melakukan inisialisasi menggunakan command git init sekali dalam 1 project. 
![gambar](https://user-images.githubusercontent.com/83742894/192590056-03959349-7de7-4958-ba75-732d3706fc53.png)

2. Masukkan perintah “git add .” untuk menambahkan semua file yang kita miliki ke dalam sebuah repository yang telah kita pilih sebelumnya.

    ![gambar](https://user-images.githubusercontent.com/83742894/192590077-cc7682a6-24f3-4e5e-bbc8-51398db4c61f.png)

3. untuk melakukan commit, masukkan perintah git commit -m “”. Fungsinya adalah untuk melakukan commit terhadap project yang kita miliki beserta menambahkan pesan di dalamnya.

    ![gambar](https://user-images.githubusercontent.com/83742894/192590127-f15dd5a6-aab1-4d2d-9bc3-21038919a8a3.png)


### Publish Aplikasi ke GitHub
Untuk melakukan publish project aplikasi kita ke GitHub, kita harus melakukan git remote dan push. Langkahnya adalah sebagai berikut: 
1. Copy terlebih alamat repository kita yang berupa HTTPS, SSH atau GitHub CLI

    ![gambar](https://user-images.githubusercontent.com/83742894/192591160-abf786c0-50e7-4f93-b33a-0e89bf40ee42.png)

2. Berikan perintah git remote beserta alamat dari repository kita untuk menghubungkan repository lokal ke GitHub
![gambar](https://user-images.githubusercontent.com/83742894/192591484-d1184983-157c-4e6b-aa4e-88eb528e4673.png)

3. Setelah itu berikan perintah git push beserta alamat dari repository kita. Selanjutnya, cek pada akun GitHub anda untuk memastikan sekali lagi bahwa project anda telah terupload 
![gambar](https://user-images.githubusercontent.com/83742894/192591498-cb25254f-2810-4ce4-b30b-57fca70eae34.png)
5. Setelah itu berikan perintah git push beserta alamat dari repository kita. Selanjutnya, cek pada akun GitHub anda untuk memastikan sekali lagi bahwa project anda telah terupload 
![gambar](https://user-images.githubusercontent.com/83742894/192591509-241c8308-7db9-4f85-b0cf-4cc64c998b86.png)


### Cloning GitHub ke Local PC

Mungkin kita agak asing dengan istilah cloning ini. Inti dari aksi cloning ini adalah “mendownload” project yang ada di GitHub ke dalam penyimpanan lokal komputer kita. Cara melakukan clone menggunakan Git Bash adalah sebagai berikut: 
1.  buka Git Bash menuju direktori yang nantinya akan kita gunakan untuk melakukan clone
![gambar](https://user-images.githubusercontent.com/83742894/192592313-12aa9a80-ccc4-4e15-8cd7-42bda1ea1e52.png)

2.  Copy alamat repository GitHub yang nantinya akan kita clone
![gambar](https://user-images.githubusercontent.com/83742894/192592350-1d461b35-6994-4302-8d00-b32204195492.png)

3.  Lalu masukkan command git clone beserta alamat tujuan dari repository github kita
![gambar](https://user-images.githubusercontent.com/83742894/192592389-3e1a3c85-f308-48a5-87e4-be914a640228.png)

4.  Selanjutnya, kita bisa melakukan pull untuk mengambil file project dari GitHub ke penyimpanan lokal kita.
![gambar](https://user-images.githubusercontent.com/83742894/192592435-b14fe477-91b3-4b65-9084-595e9b579ea7.png)

## HTML
## CSS
## Algoritma & Struktur Data
## JavaScript Dasar


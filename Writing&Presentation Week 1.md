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



### Peran HTML pada Web Development

- HTML merupakan singkatan dari Hypertext Markup Language (bukan merupakan bahasa pemrograman), HTML memiliki peran untuk menampilkan konten pada browser berupa kerangka statis dari sebuah aplikasi seperti: teks, gambar, video, link dan masih banyak lagi. 
### Tools Pendukung dalam menggunakan HTML

Ketika kita akan menggunakan HTML, pastinya kita memerlukan tools/software tambahan untuk menjalankannya. Tools yang harus kita siapkan untuk menjalankan HTML adalah browser dan code editor. 
- Browser yang biasanya saya pakai adalah mozila firefox
![gambar](https://user-images.githubusercontent.com/83742894/192594834-de11bde7-1811-4b4b-97c6-466a1ff75100.png)

- Sedangkan code editor yang biasa saya gunakan adalah Visual Studio Code
![gambar](https://user-images.githubusercontent.com/83742894/192594865-e40c9712-3ad2-4aef-be95-11537e4afeeb.png)

### Membuat HTML Sederhana
Kita bisa membuat HTML sederhana dengan mudah, langkah-langkah untuk membuat HTML sederhana adalah sebagai berikut: 

1. Buka VS Code lalu buat file baru dengan nama apapun dengan tipe file .html. tapi untuk best practicenya kita namai file kita dengan nama index.html

    ![gambar](https://user-images.githubusercontent.com/83742894/192595317-a1d31b41-958c-4038-9dcc-bba0acf379b7.png)

2. Ketik tanda “!” sebagai shortcut untuk membuat template HTML awal yang nantinya menghasilkan baris kode sebagai berikut:
![gambar](https://user-images.githubusercontent.com/83742894/192595360-a99c5363-1120-4329-9228-7c87a4c87c07.png)

3. program sederhana kita sudah berhasil dibuat
![gambar](https://user-images.githubusercontent.com/83742894/192595386-985e1994-91db-4a12-9929-488fcf9d0ca4.png)
![gambar](https://user-images.githubusercontent.com/83742894/192595403-68985cfe-8436-4456-9aa5-218fe781a5b9.png)

### Menjalankan HTML Secara Manual dan Menggunakan Live Server dari VS Code

#### Menjalankan HTML Secara Manual
1. Untuk menjalankan file HTML secara manual, kita bisa melakukan klik kanan pada file, lalu klik open in default/other browser. Tetapi, kekurangan jika menggunakan metode ini kita harus merefresh browser tiap kita melakukan perubahan pada kode yang kita miliki
![gambar](https://user-images.githubusercontent.com/83742894/192596050-48e720ba-efa2-4be0-ba34-11cd5e6e47f4.png)

Cara agar kita tidak perlu merefresh browser ketika terjadi perubahan adalah dengan menggunakan fitur Go live. Cara menggunakan Go live adalah sebagai berikut: 
#### Menjalankan HTML Menggunakan Live Server
1. Klik pada tombol Go Live

    ![gambar](https://user-images.githubusercontent.com/83742894/192596301-f92230d5-4034-4a2c-a023-b443edb96e20.png)

2. Maka akan muncul notifikasi seperti ini
![gambar](https://user-images.githubusercontent.com/83742894/192596322-c35e299c-cb86-4581-aae5-12ae283cb470.png)

3. File HTML sudah berhasil di jalankan
![gambar](https://user-images.githubusercontent.com/83742894/192596349-f72387d6-dfb5-40f0-876d-59eb3ac5d76f.png)


### Tag HTML Populer
Beberapa tag HTML yang populer adalah tag img, h1, a dan br. Contoh implementasi sederhananya adalah sebagai berikut: 

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Catatan</title>
  </head>
  <body>
    <h1>Hallo teman-teman ini adalah HTML saya</h1>
    <h2>kita bisa menuju ke google</h2>
    <img src="https://tinyurl.com/ycxmkwjp" alt="" />
    <br />
    <a href="https://www.google.com">Klik untuk menuju ke google</a>
  </body>
</html>

```
Kemudian hasilnya adalah sebagai berikut: 
![gambar](https://user-images.githubusercontent.com/83742894/192597051-04a52dca-6431-4f7e-b475-7caacaa6a941.png)
### Pengimplementasian Semantic HTML
Menggunakan Semantic HTML artinya menggunakan elemen HTML sesuai dengan kebutuhan konten yang nantinya akan kita tampilkan di dalam project yang kita buat. Kegunaan dari penggunaan semantic HTML sendiri antara lain: 
1. Meningkatkan accessiblity
2. Meningkatkan SEO
3. Lebih mudah dimaintain

#### Berikut beberapa tag yang mengikuti semantic HTML: 
![gambar](https://user-images.githubusercontent.com/83742894/192597389-3d6e26b1-a68d-4bfe-8cb6-d1051aa10b1d.png)

Sedangkan untuk implementasi sederhana dari semantic HTML adalah sebagai berikut: 
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <title>Latihan CSS</title>
  </head>
  <body>
    <nav>
      <a href="#" class="logo">Kharis</a>
      <ul class="nav-menu">
        <li><a href="">Home</a></li>
        <li><a href="">About</a></li>
        <li><a href="">Contacts</a></li>
      </ul>
    </nav>
    <section>
      <div class="deskripsi">
        <h1 class="teks">hai.. I'm Kharis</h1>
        <a href="#">Hire Me</a>
      </div>
      <div>
        <img src="kharis.jpg" alt="" width="200px" />
      </div>
    </section>
  </body>
</html>

```

Kode tersebut akan menghasilkan tampilan sederhana seperti ini: 
![gambar](https://user-images.githubusercontent.com/83742894/192598077-187a952e-290c-4d71-9e9e-7e32942ca3fa.png)


### Mempublish Website sampai ke Tahap Deployment
Setelah kita berhasil membuat program sederhana pertama kita, kita bisa melakukan deploy terhadap project tersebut. Deploy merupakan sebuah proses menyebarkan aplikasi yang sudah kita kerjakan agar dapat diakses orang lain secara online. Cara melakukannya adalah sebagai berikut:
1. buka netlify.com
![gambar](https://user-images.githubusercontent.com/83742894/192598203-8a7df959-8590-4f5e-b976-514882967029.png)

2. cukup upload project anda, maka project tersebut sudah terdeploy dengan baik. Anda dapat membuka web sederhana pada link berikut:  https://tangerine-macaron-6d9e3a.netlify.app
![gambar](https://user-images.githubusercontent.com/83742894/192598224-4c298d41-71be-43dd-9b25-1aad247f404c.png)


## CSS



### Peran CSS pada Web Development
- CSS merupakan kepanjangan dari Cascading Style Sheets
- Peran yang dimiliki oleh CSS dalam web development yaitu sebagai sebuah bahasa style sheet yang berfungsi untuk memberikan styling atau hiasan kepada elemen HTML yang telah kita tulis agar nampak lebih indah dan mempunyai sebuah layout tertentu. 
- Mengubah warna, font, mengatur tata letak dan lain sebagainya

### Menyisipkan CSS ke dalam File HTML
CSS digunakan untuk memberi styling kepada element HTML yang kita miliki, berarti kita harus menyisipkannya di dalam file HTML yang kita miliki. Untuk melakukannya terdapat 3 cara yang dapat kita lakukan antara lain: 
1. Inline Styles yaitu menambahkan CSS langsung pada atribut HTML
Contoh penggunaannya adalah sebagai berikut: 
    ```
    <img style="width: 150px; border: 1px solid red src="https://tinyurl.com/ycxmkwjp" alt="" />
    ```
2. Internal CSS yaitu menyisipkan css di dalam file HTML
Contoh penggunaannya adalah sebagai berikut: 
    ```
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Catatan</title>
        <style>
          img {
            width: 150px;
            border: 1px solid red;
          }
        </style>
      </head>
      <body>
        <img src="https://tinyurl.com/ycxmkwjp" alt="" />
      </body>
    </html>

    ```
3. Eksternal CSS yaitu manaruh CSS pada file terpisah kemudian nantinya memakai tag penghubung di dalam file HTML. Contoh penggunaannya adalah sebagai berikut:
    ![gambar](https://user-images.githubusercontent.com/83742894/192601601-0c605fd8-cd24-46f1-88fb-d50c1fab7989.png)

    ```
    img {
      width: 150px;
      border: 1px solid red;
      }
    ```
### Sintaks Dasar CSS
Sintaks dasar dari css biasa ditulis dengan 4 selektor sebagai berikut: 
1. (*) (Global), selektor ini berpengaruh terhadap semua elemen yang ada di dalam file HTML. Contoh penggunaannya adalah sebagai berikut:
    ```
    * {
      margin: 0;
      padding: 0;
      text-decoration: none;
      list-style: none;
    }
    ```
2. Tag selektor ini hanya memilik elemen sesuai tag yang dipilih. Contoh penggunaannya adalah sebagai berikut:
    ```
    section {
      display: flex;
      justify-content: center;
      }

    ```
3. Class selektor ini dapat memberikan style pada elemen mana saja yang diberikan classname tertentu. 1 classname dapat digunakan ke lebih dari 1 elemen html. Contoh penggunaannya adalah sebagai berikut:
    ```
    .teks {
      font-size: 34px;
      font-weight: 600;
      }

    ```
4. Id selektor ini memberikan style pada elemen html namun lebih spesifik daripada class. Dimana id hanya dapat digunakan pada 1 elemen html tertentu saja. Contoh penggunaannya adalah sebagai berikut:
    ```
    #deskripsi a {
      padding: 20px 40px;
      font-size: 24px;
      border-radius: 40px;
      align-items: center;
      display: inline-block;
      }

    ```
### Styling CSS pada sebuah Halaman HTML
Berikut adalah contoh penerapan styling pada sebuah landing page sederhana: 
- HTML
    ```
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <link rel="stylesheet" href="style.css" />
        <title>Latihan CSS</title>
      </head>
      <body>
        <nav>
          <a href="#" class="logo">Kharis</a>
          <ul class="nav-menu">
            <li><a href="">Home</a></li>
            <li><a href="">About</a></li>
            <li><a href="">Contacts</a></li>
          </ul>
        </nav>
        <section>
          <div class="deskripsi">
            <h1 class="teks">hai.. I'm Kharis</h1>
            <a href="#">Hire Me</a>
          </div>
          <div>
            <img src="kharis.jpg" alt="" width="200px" />
          </div>
        </section>
      </body>
    </html>
    ```
- CSS
    ```
    * {
      margin: 0;
      padding: 0;
      text-decoration: none;
      list-style: none;
      font-family: "poppins", sans-serif;
      color: rgb(60, 96, 164);
    }
    nav {
      display: flex;
      justify-content: space-between;
      padding: 10px 50px;
    }
    .logo {
      font-weight: 600;
      font-size: 36px;
    }
    ul {
      display: flex;
    }
    ul li {
      margin: 0 20px;
      padding: 5px 10px;
      font-weight: 600;
      font-size: 16px;
    }
    ul li a:hover {
      background-color: rgb(60, 96, 164);
      color: #fff;
      border-radius: 10px;
      animation-delay: 2ms;
      transition: 0.5s;
      padding: 3px 3px;
    }
    section {
      position: relative;
      display: flex;
      justify-content: center;
      top: 100px;
    }
    .deskripsi {
      margin-right: 400px;
    }
    .deskripsi h1 {
      font-size: 60px;
    }
    .deskripsi a {
      padding: 10px 20px;
      font-size: 22px;
      border-radius: 40px;
      align-items: center;
      display: inline-block;
      color: #fff;
      background-color: rgb(60, 96, 164);
    }
    .deskripsi a:hover {
      padding: 10px 20px;
      font-size: 22px;
      border-radius: 40px;
      align-items: center;
      display: inline-block;
      border: 2px solid rgb(60, 96, 164);
      color: rgb(60, 96, 164);
      background-color: #fff;
      transition: 0.5s;
      animation: ease-in;
    }
    .teks {
      font-size: 34px;
      font-weight: 600;
    }
    ```
Dari kode HTML dan CSS diatas menghasilkan tapilan sebagai berikut: 
![gambar](https://user-images.githubusercontent.com/83742894/192604141-1f2a319c-ce16-4abe-b190-9055f2d9ea26.png)

### Flexbox
Flexbox merupakan sebuah mode layout yang digunakan untuk mengatur tata letak elemen yang ada di dalam suatu halaman web. Flexbox juga disebut sebagai cara untuk mengatur layout dari sebuah tampilan web. Contoh flexbox adalah sebagai berikut: 

- HTML
    ```
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <link rel="stylesheet" href="style.css" />
        <title>Catatan</title>
      </head>
      <body>
        <div class="container">
          <div class="item">kotak</div>
          <div class="item">kotak</div>
          <div class="item">kotak</div>
          <div class="item">kotak</div>
          <div class="item">kotak</div>
          <div class="item">kotak</div>
          <div class="item">kotak</div>
          <div class="item">kotak</div>
          <div class="item">kotak</div>
          <div class="item">kotak</div>
        </div>
      </body>
    </html>

    ```
- CSS
    ```
    .container {
      display: flex;
      border: 3px solid blue;
      justify-content: space-between;
      }
    .item {
      border: 1px solid black;
      width: 100px;
      height: 100px;
      background-color: yellow;
      }
    ```
Dari kode HTML dan CSS di atas menghasilkan tampilan sebagai berikut: 
![gambar](https://user-images.githubusercontent.com/83742894/192604840-d31c8e93-d740-4c52-b95b-c924e92b4208.png)


## Algoritma & Struktur Data



### Perbedaan Algoritma dan Struktur Data
- Algoritma adalah sebuah deretan langkah-langkah yang disusun untuk menyelesaikan suatu masalah
- Sedangkan struktur data merupakan penyusunan data di dalam sebuah media penyimpanan komputer sehingga data tersebut dapat digunakan dengan efisien 

### Manfaat Algoritma dan Struktur Data
- Manfaat dari penggunaan algoritma adalah kita dapat memahami bagaimana alur dari sebuah bahasa pemrograman bekerja. Sehingga, jika kita memahami sebuah algoritma daari suatu permasalahan kita isa menterjemahkannya ke dalam bahasa pemrograman apa saja dan mengimplementasikannya
- Manfaat dari penggunaan struktur data adalah memudahkan kita dalam mengorganisir sebuah data yang kita memiliki sehingga memiliki tampilan yang rapi. Sehingga, kita bisa dengan mudah mengolah data tersebut menjadi informasi dengan cepat dan mudah

### Membuat algoritma sederhana
Contoh algoritma sederhana: 
```
Start
Declare variable “nama”
Declare variable “informasi”
Declare variable “gabungkan”
Fill “nama” variable with string “Nama saya Kharis”
Fill “informasi” variable with string “, Saya mengikuti Studi Independen Skilvul”
Fill “gabungkan” variable with “nama”.concat(“informasi”)
Display “gabungkan” variable
stop

```

### Menerapkan algoritma ke dalam bahasa pemrograman
Hasil dari penerapan algoritma diatas ke bahasa pemrograman javascript adalah sebagai berikut: 
```
let nama = “Nama saya Kharis”
let informasi = ', Saya mengikuti Studi Independen Skilvul'
let gabungkan = nama.concat(informasi);
console.log(gabungkan)

```
### Pendekatan menyelesaikan suatu masalah untuk diselesaikan melalui program 
Kita coba buat sebuah program sederhana
Kharis ingin menampilkan angka ganjil yang terdapat di antara 1-30. Maka penyelesaiannya adalah sebagai berikut: 
```
for (let i= 1; i<31; i++){
    if (i%2== 1){
        console.log(i)
    }
}

```
Dan hasilnya adalah yang ada pada gambar berikut: 
![gambar](https://user-images.githubusercontent.com/83742894/192605976-96294b40-d183-4235-a588-3a1d660b9449.png)

### menerapkan salah satu algoritma dengan JavaScript 
Latihan untuk menerapkan Algoritma ke Javascript
Kita buat terlebih dahulu algoritma yang mengubah satuan waktu 2 jam menjadi satuan detik yang diharapkan menghasilkan 7200 detik
```
Declare “jam” variable
Fill “jam” variable with number 2
Declare “satuanDetik” variable
Fill “satuanDetik” variable with “jam” variable X 3600 number
Display "2 jam jika di convert ke detik, maka akan ada sebanyak "+satuanDetik+" Detik"
```

Maka kode javascriptnya akan menjadi seperti berikut ini: 
```
console.log("====Convert satuan jam ke detik====")
let jam= 2
let satuanDetik= jam*3600
console.log("2 jam jika di convert ke detik, maka akan ada sebanyak "+satuanDetik+" Detik")

```
hasilnya seperti ini: 
![gambar](https://user-images.githubusercontent.com/83742894/192606369-56d283e8-b42d-4144-bfe1-a046625e8345.png)

## JavaScript Dasar


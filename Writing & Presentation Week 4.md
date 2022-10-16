# Writing & Presentation Test Week 4

## Asyncronous Fetch dan Async Await

### Server
- Server merupakan sebuah sistem komputer yang memiliki layanan khusus terkait penyimpanan data. Server bertugas untuk mengambil sebuah data dari database ketika ada suatu permintaan data dari web application
### API
- API (Application Programming Interface) merupakan sebuah interface yang dapat menghubungkan sebuah aplikasi dengan aplikasi lainnya, seperti menghubungkan data dari web application ke server dan database
- Data yang biasanya kita terima maupun kirimkan ke dalam sebuah API adalah berupa data dalam bentuk JSON
- Untuk menjalankan promises kita bisa menggunakan 2 cara yaitu promise then-catch yang telah kita bahas pada minggu lalu dan async await. Berikut penjelasannya
### Fetch
- Fetch merupakan object promise yang telah disediakan oleh JavaScript
- Untuk menggunakan fetch kita harus menggunakan link sumber yang telah disediakan oleh pengembang API untuk mengambil data-data yang sudah tersedia untuk nantinya kita tampilkan pada web application kita. Sama seperti promise, kita juga bisa mengambil data dari fetch menggunalan then-catch maupun async await.
- Contoh penggunaan fetch menggunakan then-catch:
    ```
    fetch("link")
      .then((variable) => {
        console.log(variable);
      })
      .catch((variable_error) => {
        console.log(variable_error);
      });
    ```
- Contoh fetch menggunakan async await:
    ```
     async function namaFunction() {
      let var1 = await fetch("link");
      let var2 = await var1.json();
      let varN = await var2;

      console.log(varN);
    }
    ```
### Async Await
- Async merupakan sebuah function yang digunakan untuk memanggil promises, untuk mendeklarasikannya kita harus menambahkan keyword async di depan sebuah function.
- Await merupakan sebuah keyword yang hanya bisa diberlakukan di dalam sebuah function async dan module. Await berfungsi untuk membuat sebuah promise menunggu untuk mendapatkan nilai pemenuhannya. Contoh penggunaan: 
    ```
    //promise
    let namaPromise = (kondisi) => {
      return new Promise((resolve, reject) =>   {
        if (kondisi == "ok") {
          resolve("benar");
        }
        reject("salah");
      });
    };

    // async await
    
    async function namaFunction() {
      try {
        let hasil = await namaPromise("ok");
      } catch (error) {
        console.log(error);
      }
    }
    
    namaFunction();
    ```
## Memanggil data menggunakan DOM
- Kita bisa menampilkan data yang telah kita fetch menggunakan DOM agar data tersebut tampil pada aplikasi yang sedang kita buat.
### Memanggil data biasa menggunakan DOM
- Memanggil data biasa menggunakan DOM, contoh penggunaan: 
    ```
    let gambar = "pict.png";
    let judul = "title";
    let skor = "rating";
    let tanggal = "20 Juni 2021";

    let element = document.getElementById("row");
    element.innerHTML += `<div class="col-md-4 pb-4">
              <div class="card">
                <img src="${gambar}" alt="" width="100%" />
                <div class="card-body">
                  <div class="rating">
                    <h5 class="card-title">${judul}</h5>
                    <h5 class="ratingItem">${skor}</h5>
                  </div>
                  <p class="dateItem card-text">${tanggal}</p>
                </div>
              </div>
            </div>`;
    ```
### Memanggil data hasil pengolahan fetch menggunakan DOM
- Memanggil data hasil pengolahan fetch menggunakan DOM, contoh penggunaan: 
    ```
    async function getData() {
      let data = await fetch("https://api.themoviedb.org/3/discover/movie?api_key=e69fcdc178dedb2c9d8eef09ceba5795&sort_by=popularity.desc");
      let hasilData = await data.json();
      let finalData = await hasilData.results;
      // perulangan untuk mengambil data yang ada di masing-masing objek
      finalData.forEach((item) => {
        let element = document.getElementById("row");
        element.innerHTML += `<div class="col-md-4 pb-4">
              <div class="card">
                <img src="${base + item.backdrop_path}" alt="" width="100%" />
                <div class="card-body">
                  <div class="rating">
                    <h5 class="card-title">${item.title}</h5>
                    <h5 class="ratingItem">${item.vote_average}</h5>
                  </div>
                  <p class="dateItem card-text">${item.release_date}</p>
                </div>
              </div>
            </div>`;
      });
    }
    // run async tampilan awal web
    getData();
    ```


## Git & GitHub Lanjutan
### Kolaborasi GitHub
- GitHub mempunyai fasilitas dimana masing-masing individu yang terhubung melalui GitHub dapat saling berkolaborasi ketika sedang mengerjakan sebuah project pemrograman, biasanya colaboration dilakukan di dalam sebuah organization yang berisi ketua tim dan colaborator. Tujuan dari dilakukannya kolaborasi adalah agar kita dapat menggabungkan progress yang dilakukan oleh masing-masing colaborator sehingga pekerjaan dapat dikerjakan bersama-sama dan dapat selesai lebih cepat
- Ketika kita sedang berkolaborasi di dalam 1 organization kita tidak boleh langsung melakukan development fitur kita hanya pada 1 branch karena dapat menyebabkan banyak kebingungan dan mungkin dapat menyebabkan terjadinya conflict. Maka dari itu ketika mulai dari proses pengembangan fitur per individu, development hingga deploy harus dipecah menjadi beberapa branch yang berbeda. Beberapa branch yang harus dibuat adalah sebagai berikut: 
    - Branch main biasa digunakan untuk menampung sebuah project yang sudah matang dan siap untuk di deploy
    - Branch development, biasa digunakan untuk menampung sebuah project yang masih pada proses development. Biasanya merge pull request dari progress masing-masing colaborator akan dilakukan pada branch ini
    - Branch mandiri merupakan cabang terluar sebuah branch yang digunakan oleh masing-masing colaborator untuk mengerjakan fitur mereka masing-masing sebelum nantinya akan di merge pada branch development
### Organization
- Organization merupakan sebuah repositori GitHub yang memungkinkan beberapa individu untuk melakukan kolaborasi, umumnya di dalam 1 organization terdapat 1 ketua tim dan beberapa colaborator. Di dalam proses development sebaiknya branch ini di set menjadi public
### Pull request
- Pull request merupakan permintaan untuk menggabungkan (merge) kode yang telah dikerjakan pada branch mandiri ke dalam branch development. Ketika akan melakukan merge masing-masing colaborator harus meminta pull request kepada ketua tim sebelum nantinya disetujui dan project disatukan di dalam branch development
### Hal yang harus dilakukan oleh colaborator
- Ketika akan melakukan kolaborasi masing-masing colaborator harus melakukan clone pada repository yang telah dibuat menggunakan perintah **git clone**. Proses ini cukup dilakukan 1 kali saja
- Setelah melakukan git clone, sebelum mulai berkolaborasi kita harus berpindah terlebih dahulu ke branch development menggunakan perintah **git switch dev** untuk melakukan pull agar kita mendapatkan informasi kode terupdate menggunakan perintah **git pull**
- Setelah mendapatkan progres kode terupdate kita harus berpindah ke dalam branch mandiri untuk mengerjakan tugas kita di sana. Untuk berpindah kita bisa menggunakan **git switch [nama branch kita]**
- Selanjutnya, ketika kita sudah selesai mengerjakan 1 fitur dan ingin melakukan push ada hal yang harus dilakukan terlebih dahulu. Yang pertama kita harus melakukan pull di dalam branch development untuk mendapatkan progress kode terupdate sebelum akhirnya kita melakukan push pada branch mandiri kita
- Setelah kode kita terupdate menjadi progress terbaru kita bisa melakukan push progress kita ke branch mandiri lalu meminta pull request kepada ketua tim dengan menekan tombol pull request
- Setelah melakukan push kita bisa melakukan merge semua progres ke dalam branch development, untuk menyatukannya kita harus melakukan pull request dan nantinya ketua tim harus melakukan acc terhadap merge request dengan menekan tombol merge pull request lalu Anda bisa melakukan progress selanjutnya
### Handle Conflict
- Conflict merupakan keadaan dimana terdapat pertentangan ketika proses merge dari 2 file milik colaborator yang berbeda.   
- Ketika terjadi sebuah conflict ketika melakukan merge antar branch yang harus dilakukan adalah dengan mengambil progres terbaru dari branch development, kemudian kita merge dengan progres yang ada para branch mandiri kita. 
- Setelah didapatkan letak conflict yang terjadi, kita bisa memilih beberapa solusi yaitu, menerima perubahan baru dari branch mandiri, tetap menggunakan perubahan yang sebelumnya sudah ada pada branch development, menerima perubahan lama dan perubahan baru dan membandingkan kedua perubahan tersebut

## Responsive Web Design
- Cara menerapkan responsive ke dalam sebuah web dapat dibilang tidak ada aturan patennya. Jadi terdapat seni di dalam menerapkan responsive ke dalam sebuah aplikasi web. Cara menerapkan responsive adalah sebagai berikut: 
    - Tag viewport, merupakan sebuah method pada HTML yang berfungsi agar web designer bisa mengontrol area halaman web agar tampilan tetap bagus jika dibuka menggunakan device apa saja. Viewport biasanya di tuliskan menggunakan tag <meta>. Tag view port berfungsi untuk menyesuaikan tampilan dari aplikasi web kita sesuai dengan device yang digunakan user untuk membuka aplikasi web. Bisa dibilang viewport juga merupakan cara untuk membuat aplikasi kita menjadi responsive tetapi belum sempurna, contoh penggunaan:
        ```
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        ```

    - Max-width css, merupakan property css yang berfungsi untuk mengatur width maksimum dari sebuah elemen, dengan menggunakan property ini elemen (contohnya element img) yang kita miliki bisa menjadi responsive. Contoh penggunaan: 
        ```
        img {
        max-width: 100px;
        }
        ```
    - Css relative units, satuan ukur/panjang pada css yang bersifat relative (css units w3school) seperti rem, em, vw, vh dan %.
        - Rem merupakan satuan ukuran font yang relative terhadap root element. Contoh penggunaan: 
            ```
            h1 {
              font-size: 20rem;
            }
            ```
        - Em merupakan satuan ukuran font yang relative terhadap parent element. Contoh penggunaan: 
            ```
            h1 {
              font-size: 20em;
            }
            ```
        - Vw merupakan satuan ukuran yang relatif dan bernilai 1% dari lebar viewport. Contoh penggunaan: 
            ```
            h1 {
              font-size: 20vw;
            }
            ```
        - Vh merupakan satuan ukuran yang relatif dan bernilai 1% dari tinggi viewport. Contoh penggunaan: 
            ```
            h1 {
              font-size: 20vh;
            }
            ```
        - % Merupakan satuan ukuran yang relatif terhadap parent element. Contoh penggunaan:
            ```
            h1 {
              font-size: 20%;
            }
            ```
    - Media query digunakan untuk membuat styling berdasarkan ukuran device tertentu. Contoh penggunaan: 
        ```
        @media (max-width: 767px) {
      .head {
        display: block;
        padding-top: 50px;
      }
        ```
## Bootstrap 5
### Grid System Bootstrap dan Container Bootstrap
- Di dalam bootstrap kita juga sudah disediakan block bawaan bootstrap yang berguna untuk mengatur layout dari website kita agar tampilannya menjadi responsive. Berikut contoh block bootstrap yang berfungsi untuk mengatur responsive: 
    - Grid system merupakan sebuah flexbox grid yang berfungsi untuk membangun layout dengan bentuk dan ukuran yang berorientasi pada ukuran 12 kolom dan 6 jenis ukuran responsive. Untuk menggunakan grid system kita harus menggunakan container bootstrap yang akan kita ulas pada point pembahasan selanjutnya. Berikut adalah jenis ukuran pada bootstrap: 
        - Xxl merupakan grid sistem yang dapat beradaptasi pada breakpoint dengan ukuran >=1400px. Untuk menggunakan ukuran ini kita bisa menggunakan prefix .col-xxl-
        - Xl merupakan grid sistem yang dapat beradaptasi pada breakpoint dengan ukuran >=1200px. Untuk menggunakan ukuran ini kita bisa menggunakan prefix .col-xl-
        - Lg merupakan grid sistem yang dapat beradaptasi pada breakpoint dengan ukuran >= 992px. Untuk menggunakan ukuran ini kita bisa menggunakan prefix .col-lg-
        - Md merupakan grid sistem yang dapat beradaptasi pada breakpoint dengan ukuran >=768px. Untuk menggunakan ukuran ini kita bisa menggunakan prefix .col-md-
        - Sm merupakan grid sistem yang dapat beradaptasi pada breakpoint dengan ukuran >=576px. Untuk menggunakan ukuran ini kita bisa menggunakan prefix .col-sm-
        - Xs merupakan grid sistem yang dapat beradaptasi pada breakpoint dengan ukuran <576px. Untuk menggunakan ukuran ini kita bisa menggunakan prefix .col-xs-
    - Container merupakan block bawaan bootstrap yang digunakan untuk mengatur pad dan align content sesuai dengan viewport sebuah device. Container merupakan element layout dasar pada bootstrap yang harus dicantumkan ketika sedang menggunakan bootstrap grid system. Sama seperti col, container juga memiliki 6 jenis ukuran yang dapat kita lihat pada gambar: 
    ![gambar](https://user-images.githubusercontent.com/83742894/196022131-038394a0-2119-4fe5-8e3b-34d36833aa36.png)

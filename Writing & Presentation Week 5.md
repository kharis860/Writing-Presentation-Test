# Writing & Presentation Test Week 5

## Intro to React JS

### Kekurangan pada DOM JS
- Sebelumnya ketika kita menggunakan JS DOM pasti kita merasakan suatu kesulitan dalam melakukan pemrograman di dalamnya kaerna adanya kekurangan yang dimiliki oleh JS DOM. Maka hadirlah React JS yang menanggulangi kekurangan-kekurangan tersebut. 
- Hari ini kita akan bersama menginstal React JS. Untuk menggunakan React JS, kita harus Node JS terlebih dahulu dan usahakan versi terbaru. Boleh menggunakan versi agak lama tapi jangan yang terlalu usang
### Node JS
- Fungsi dari Node JS ini adalah agar kita dapat menjalankan JavaScript di luar browser setelah sebelumnya kita hanya melakukan pemrograman JavaScript di dalam Browser. Di dalam sebuah browser terdapat mesin javascript (Google Chrome menggunakan mesin V8), sehingga kita dapat menjalankan javascript di web browser
- Teknologi yang memungkinkan javascript untuk dapat berjalan diluar ranah browser adalah dengan menggunakan Node JS yang di dalamnya juga terdapat mesin yang dapat menjalankan javascript. Node JS nantinya juga digunakan untuk mendownload package package dan library yang disediakan oleh react
### React JS
- React merupakan sebuah framework view library JS yang dikembangkan oleh tim yang juga mengerjakan facecook karena mereka merasa kesulitan ketika menggunakan DOM biasa ketika mengembangkan facebook. Dengan menggunakan react kita dapat menggunakan DOM JS dengan lebih mudah. Selain angular dan vue, terdapat alternative serupa seperti svelte
### Konsep React JS
- React JS memiliki konsep declarative, componen based dan learn once, write anywhere. 
- declarative di sini maksudnya react js mudah di deklarasikan, di debug dan penggunaannya simpel.
- Kemudian componen based, dimana kita bisa membuat componen di dalam react JS yang dapat kita panggil dimanapun. 
- learn once, write anywhere karena setelah kita mengetahui penggunaan react kita juga bisa mengimplementasikannya pada tampilan mobile (React Native)
### Menginstall dan Membuat Project React JS
- Sebelum install react harus install node js terlebih dahulu. Setelah menginstall Node JS, kita bisa menginstall React JS di laptop kita dengan perintah berikut di dalam folder yang kita inginkan dan sekaligus membuat project React baru di sana:
    ```
    npx create-react-app nama-Aplikasi
    ```
- Berikut adalah proses instalasi yang saya lakukan:

    ![gambar](https://user-images.githubusercontent.com/83742894/197824795-d9398e91-6b2d-435f-9e4c-18e5ae22a774.png)
    ![gambar](https://user-images.githubusercontent.com/83742894/197824812-6748badb-7699-425c-9b44-76228e0b30f4.png)

- Jika tampilan sudah seperti ini dan terdapat notifikasi Happy hacking berarti project kita sudah selesai dibuat dan kita bisa mulai mengerjakan project kita. 
- Ketika kita mengerjakan project tersebut, kita harus mengaktifkan live server milik react untuk melihat progress dari aplikasi kita dengan perintah:
    ```
    cd nama-Aplikasi
    npm start
    ```
  ![gambar](https://user-images.githubusercontent.com/83742894/197824934-543a7348-9b40-4318-a20e-cafeb04bf553.png)

- Kurang lebih seperti ini isi dari susunan file yang terdapat di dalam project yang telah kita buat: 
 ![gambar](https://user-images.githubusercontent.com/83742894/197825172-75b53772-e07d-4ba8-bb12-14daac63ff87.png)

### Single Page Application
![gambar](https://user-images.githubusercontent.com/83742894/197825337-63f91d5e-ff92-45d4-b204-cefbdf86324b.png)

- React menggunakan teknologi SPA (Single Page Aplication), dimana tidak akan refresh ketika kita melakukan request untuk berpindah page karena pada dasarnya kita hanya mengganti kontent pada template SPA

### Virtual dan Real DOM
- Pada react ketika kita menggunakan DOM nantinya akan diolah oleh React JS Virtual DOM (replikas dari sebuah DOM yang asli), yaitu sebagai perantara antara web pake dengan real DOM
- Performance issue yang ada di dalam REAL DOM adalah dimana setiap ada perubahan DOM akan merender seluruh kode secara keseluruhan sehingga sebuah web menjadi terasa berat. 
- Sedangkan pada virtual DOM, ketika ada perubahan akan dilakukan render hanya pada bagian kode yang telah dilakukan sebuah perubahan
### JSX
- Ketika membuat penulisan kode di dalam app.js di dalam react kita menggunakan JSX. JSX merupakan kependekan dari JavaScript Syntax Extension atau biasa dikenal dengan JavaScript XML yang memungkinkan kita untuk menulis program yang seolah tampil dalam bentuk HTML di dalam file JavaScript
### Export dan Import antar File
- Karena di dalam React kita menggunakan konsep componen-based maka kita akan banyak melakukan export dan import file di dalamnya. Export dan import ini digunakan untuk berbagai fungsi seperti menggunakan komponen di suatu halaman, ataupun menghubungkan program kita dengan file lain seperti CSS ataupun Bootstrap
- Pada masing-masing halaman atau componen yang kita hubungkan dengan file utama (index.html) kita harus membuatnya dalam file JavaScript yang terpisah-pisah. Di dalam tersebut kita membuat tampilan berupa fungtion yang nantinya akan kita panggil pada file utama. 
- Function pada JSX bersifat hanya bisa menampung satu parent element saja (mulai dari tag pembuka sampai tag penutup). Contoh penggunaannya adalah seperti ini:
    ```
    import logo from "./logo.svg";
    import "./App.css";
    import Info from "./components/Info.js";
    function App() {
      return (
        <div className="App">
          <h1 className="profil-header">haloo</h1>
        </div>
      );
    }
    
    export default App;
    ```
- jika kita tidak ingin menggunakan div dalam menginputkan beberapa element kita juga dapat menambahkannya dengan React fragment (<></>) seperti berikut: 
    ```
    import logo from "./logo.svg";
    import "./App.css";
    import Info from "./components/Info.js";
    function App() {
      return (
        <>
          <h1 className="profil-header">haloo</h1>
        </>
      );
    }
    
    export default App;
    ```
- setelah kita sudah selesai membuat komponen seperti file App.js di atas, kita bisa melakukan import dengan sintaks:
    ```
    export default nama-function
    ```
- kemudian untuk dapat memakai komponen yang telah dibuat kita bisa menggunakan perintah import seperti berikut: 
    ```
    import nama-fungtion from “route file”
    ```

# Writing & Presentation Test Week 6

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
## React JS Component
### Penggunaan Component
- Component pada React JS merupakan sebuah potongan kode yang berdiri sendiri dan dapat dipakai ulang di dalam project React. Kita membuat komponen agar kita dapat memecah tampilan halaman menjadi bagian bagian kecil, dengan tujuan nantinya komponen tersebut dapat dipakai di halaman lainnya tanpa membuat kembali
- Component dapat dipakai ketika kita membutuhkan suatu tampilan UI yang harus di tampilkan di beberapa halaman/section yang berbeda, namun memiliki tampilan yang sama hanya saja memiliki isi data yang berbeda
### Penggunaan Props dan State
- Props merupakan argumen yang ada di dalam component yang berfunsgi untuk menangkap data yang penggunaannya seperti attribute pada HTML, props digunakan untuk melakukan pengiriman dan penerimaan data antar component di dalam project React. Penggunaan props adalah sebagai berikut: 
    ```
    function Card(props) {
      return (
        <div>
          <h2>{props.nama}</h2>
          <p>{props.umur}</p>
        </div>
      );
    }
    
    export default Card;
    ```
- di dalam memanggil data yang ditangkap menggunakan props. Selain menggunakan cara diatas, kita juga dapat menggunakan destrukturisasi dalam pengambilan datanya seperti berikut: 
    ```
    function Card({ nama, umur }) {
      return (
        <div>
          <h2>{nama}</h2>
          <p>{umur}</p>
        </div>
      );
    }
    
    export default Card;
    ```
- State merupakan data lokal yang terdapat pada sebuah component. Sebuah componen yang memiliki state dapat disebut dengan stateful component. Sedangkan component yang tidak memiliki state disebut dengan stateless dan hanya memiliki props saja. Ini adalah contoh dari stateless component: 
    ```
    function Card({nama}) {
      return (
        <div>
          <h2>{nama}</h2>
        </div>
      );
    }
    
    export default Card;
    ```
### React JS Bootstrap
- Kita dapat menyisipkan framework bootstrap ke dalam project react kita. Dalam menyisipkannya kita dapat memilih beberapa cara yang sudah disediakan oleh React dan Bootstrap. Kita dapat menginstall bootstrap terhadap project kita menggunakan perintah di dalam terminal:
    ```
    npm install react-bootstrap bootstrap
    ```
- bisa menggunakan link CDN menggunakan link reel pada file index.html, begitu juga jika ingin menambahkan css secara manual tanpa menggunakan import export. Jika menyisipkan bootstrap menggunakan link CDN kita harus memasukkan URL berikut ke dalam file index.html.
- URL CSS
    ```
    https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css
    ```
- URL JS
    ```
    https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js
    ```
- Kita juga bisa menyisipkan bootstrap menggunakan import pada file index.html, perintah untuk import bootstrap adalah sebagai berikut:
    ```
    import 'bootstrap/dist/css/bootstrap.css'
    ```
- Yang menjadi catatan ketika akan menggunakan bootstrap kita harus memilih salah satu agar tidak terjadi conflict

## Handle Event
- Pembahasan selanjutnya adalah handle event. Handle event merupakan bagaimana kita membuat program yang dapat menangani keadaan dari adanya input yang dimasukkan oleh user ke dalam website yang kita miliki. Penggunaan yang paling umum adalah berada di dalam sebuah button
### Bagaimana meng-handle event React JS
- Ketika kita membuat variable biasa di dalam react maka akan bersifat emmutable, maksud dari emmutable ini adalah data tersebut tidak dapat berubah dengan begitu saja ketika kita olah dengan metode biasa lalu kita tampilkan ke dalam tampilan HTML kita. 
- maka dari itu ketika membuat sebuah variable data kita harus membuatnya menggunakan state dan useState yang bisa kita panggil ke dalam sebuah function yang nantinya akan berjalan pada button yang kita beri perintah onClick. Sebelum menggunakan useState kita harus melakukan import terlebih dahulu dengan cara sebagai berikut: 
    ```
    import { useState } from "react";
    ```
## Handle Event
- Pembahasan selanjutnya adalah handle event. Handle event merupakan bagaimana kita membuat program yang dapat menangani keadaan dari adanya input yang dimasukkan oleh user ke dalam website yang kita miliki. Penggunaan yang paling umum adalah berada di dalam sebuah button
### Bagaimana meng-handle event React JS
- Ketika kita membuat variable biasa di dalam react maka akan bersifat emmutable, maksud dari emmutable ini adalah data tersebut tidak dapat berubah dengan begitu saja ketika kita olah dengan metode biasa lalu kita tampilkan ke dalam tampilan HTML kita. 
- maka dari itu ketika membuat sebuah variable data kita harus membuatnya menggunakan state dan useState yang bisa kita panggil ke dalam sebuah function yang nantinya akan berjalan pada button yang kita beri perintah onClick. Sebelum menggunakan useState kita harus melakukan import terlebih dahulu dengan cara sebagai berikut: 
    ```
    import { useState } from "react";
    ```
- Contoh pendeklarasian useState:
    ```
    function NamaFunction() {
      let [variable,setVariable]= usestate("nilai awal")
    }
    ```
- Sedangkan, untuk penggunaan handle event pada button adalah menggunakan properties onClick untuk memanggil function yang berisi useState yang telah kita buat:
    ```
    <button onClick={nambah}>+</button>
    ```
- Data yang ada di dalam state tidak mungkin tidak berubah di dalam pengolahan data, maka kita bisa mengubah data yang ada di dalam useState menggunakan variable set yang biasanya dideklarasikan dengan “setVariable” untuk mengubah nilai awal dari sebuah useState. Contoh penggunaan setVariable:
    ```
    function nambah() {
        setVariable(variable + 1);
      }
    ```
### Render dan Conditional Render
- Setiap code yang kita tuliskan di dalam project React sebelum ditampilkan ke dalam sebuah website pasti melewati proses render terlebih dahulu. Namun, kita dapat mengatur kondisional dari code mana saja yang ingin kita tampilkan di dalam tampilan website kita di dalam keadaan tertentu. Conditional render salah satunya bisa dilakukan menggunakan operator ternary
- Ternary merupakan sebuah operator yang ada di dalam bahasa pemrograman JavaScript yang dapat digunakan di dalam pengkondisian di dalam project React yang kita miliki. Operand dari operator ternary akan menjalankan kondisi sebelum colon (:) dan akan menjalankan kondisi yang terdapat setelah colon (:) jika bernilai false. Contoh penggunaan ternary di dalam melakukan conditional render adalah sebagai berikut: 
    ```
    import "./App.css";
    import User from "./components/User";
    import { useState } from "react";
    function App() {
      let [isLogin, setIsLogin] = useState(false);
      return (
        <div>
          <h1 className="profil-header">haloo</h1>
          <button onClick={() => setIsLogin(true)}>login</button>
          {isLogin ? <User /> : <span>Anda belum login</span>}
        </div>
      );
    }
    
    export default App;
    ```
- karena state isLogin pada code di atas masih bernilai false, maka operator ternary akan menampilkan opsi kedua yaitu berupa teks “Anda belum login”. Nantinya ketika tombol sudah ditekan dan mengubah state isLogin menjadi true, barulah dirender opsi pertama di dalam operator ternary

## Component Lifecycle
### Component Lifecyle dan Penggunaannya
- Component ketika tampil di dalam sebuah project React. Ia memiliki sebuah siklus hidup mulai dari ia tampil, mengalami update, hingga menghilang dikarenakan sebuah kondisional tertentu. Di dalam component life cycle, hal ini biasa disebut dengan fase mount, update dan unmout. 
- terdapat 2 cara pembuatan component:
    1. Function Component
    2. Class Component
- Yang menjadi perbedaan antara function component dan class component adalah dibagian cara pendeklarasiannya dan tahap lifecyclenya yang agak berbeda. Perbedaan life cycle yang terdapat pada class component adalah dimana terdapat istilah lifecycle seperti componentDidMount, ComponentDidUpdate dan componentWillUnmount.
- Terdapat 3 lifecyle yang dialami oleh component di dalam React yaitu:
    1. Mount: munculnya sebuah komponen ke dalam sebuah tampilan website
    2. Update: perubahan data yang ada di dalam component tersebut
    3. Unmount: menghilangnya sebuah komponen dari sebuah tampilan website
- Penjelasan diatas adalah terkait pengertian dari masing-masing lifecycle. Sedangkan, untuk contoh dari penggunaan masing-masing life cycle pada project react adalah:
    1. Mount: mengambil data dari API
    2. Update: munculnya komponen lain di sebuah halaman
### Side Effect
- Tiap komponen yang telah kita buat dapat kita beri sebuah side effect di dalamnya. Side effect merupakan code yang berada component yang dijalankan setelah function utama di jalankan. Side effect juga dapat digunakan untuk memberikan suatu effect setelah user berinteraksi pada sebuah tampilan website. Untuk memakai side effect kita harus memanggil function useEffect ke dalam file component yang kita miliki. Contoh penggunaan side effect adalah sebagai berikut:
    ```
    import { useEffect } from "react";
    
    function namaComponent() {
      useEffect(() => {
        <h1>ini adalah side effect</h1>;
      });
      return (
        <>
          <h1>isi</h1>
        </>
      );
    }
    ```
- Urutan React JS dalam merender sebuah component yang terdapat sebuah side effect di dalamnya yaitu dimulai dengan merender isi function, setelah itu merender isi dari return. Setelah semuanya dirender barulah giliran side effect untuk dirender. Jadi, biasanya side effect ini dirender terakhir kali di dalam sebuah component. Untuk visualisasnya agar dapat lebih mudah dipahami, bisa kita lihat pada tampilan console di bawah ini: 

    ![gambar](https://user-images.githubusercontent.com/83742894/198953300-d5200052-122b-4284-af93-cfe26a2ab193.png)

- Use effect merupakan function yang kita panggil dari react, jadi harus kita deklarasikan terlebih dahulu di atas menggunakan perintah:
    ```
    import { useState } from "react";
    ```
- ketika kita menggunakan side effect hanya untuk mounting saja (hanya tampil sekali di awal rendering), maka kita harus menambahkan dependensi berupa array kosong setelah penulisan callback. Dapat kita lihat pada contoh berikut:
    ```
    useEffect(() => {
        console.log("ini adalah side effect");
      }, []); //ini adalah dependensi yang ditulis setelah callback
    ```
- Jika kita tidak menambahkan dependensi tersebut, maka side effect akan terus dirender dan bisa digunakan pada life cycle mount dan update.
### Fetch menggunakan Axios
- Di dalam React JS kita juga dapat melakukan fetch data dari sumber eksternal sama seperti saat kita menggunakan vanilla JS. Tetapi React JS sudah menyediakan sebuah library khusus yang lebih simpel untuk digunakan daripada menggunakan fungsi fetch yaitu menggunakan axios. Untuk menggunakannya kita harus menginstall axios pada project kita terlebih dahulu dengan perintah: 
    ```
    npm install axios
    ```
- Sedangkan contoh penggunaan axios untuk mengambil/fetch data dari sumber eksternal adalah sebagai berikut:
    ```
    axios("https://digimon-api.vercel.app/api/digimon").then((res) => {
          setDigimons(res.data);
        });
    ```
- Merupakan tambahan fitur yang ada mulai React 16.8. kita bisa memakai sebuah state dan fitur react lainnya tanpa menuliskan sebuah class. biasanya use ditandai dengan adanya penulisan “use”. ini merupakan fitur yang disediakan untuk fungsional component

## Form Handle React JS
- React JS sudah memaparkan di dalam dokumentasi mereka bagaimana caranya membuat sebuah form di dalam project React. Dimana kita bisa menghandle form dengan lebih simpel di dalam project react jika dibandingkan dengan vanilla JS. Alasannya adalah karena kita tidak perlu melakukan getElement ke dalam code HTML, melainkan kita bisa langsung melakukan logic di dalam code HTML tersebut menggunakan properties onChange dan onSubmit pada form
- Tetapi, di dalam penulisan properties label di dalam form terdapat beberapa perbedaan. Seperti properties name pada input, jika pada HTML biasa kita menggunakan name maka di React kita menggunakan properties HTMLfor
    ```
    <label htmlFor="nama">Nama</label>
    ```
- Kita juga harus menambahkan properties tambahan di dalam tag unput berupa value{}, yang nantinya variable di dalamnya dideklarasikan menggunakan useState
    ```
    import { useState } from "react";
    function Form() {
      const [nama, setNama] = useState("");
      return (
        <>
          <h1>Form identitas</h1>
          <form action="">
            <label htmlFor="nama">Nama</label>
            <input type="text" value={nama} />
          </form>
        </>
      );
    }
    
    export default Form;
    ```
- kemudian, karena form yang kita miliki masih satu arah. Kita harus menambahkan properties onChange yang nantinya diberi sebuah callback yang memanggil setter dari useState agar kita dapat menyimpan data yang telah diinputkan user ke dalam state yang telah kita buat sebelumnya.
    ```
    <input type="text" value={nama} onChange={(e) => setNama(e.target.value)} />
    ```
- Agar kita dapat menampilkan sebuah event ke dalam tampilan web kita, maka kita harus memberikan sebuah function yang isinya sebuah event yang dipanggil melalui properties onSubmit pada tag form
    ```
      function handleEvent(e) {
        e.preventDefault();
      }
      return (
        <>
          <h1>Form identitas</h1>
          <form action="" onSubmit={handleEvent}>
    ```
- Sedangkan, jika kemarin kita pada vanilla JS kita menggunakan function reset kepada element form yang sudah di getElement. Di project react kita bisa mengatur setter dari setiap form menjadi sebuah form yang bernilai string kosong pada function yang menghandle form
    ```
    function handleEvent(e) {
        e.preventDefault();
        alert(`nama ${nama} alamat ${alamat}`);
        setNama("");
        setAlamat("");
      }
    ```
- Lalu, untuk menangkap inputan tersebut kita harus membuat state baru yang di dalamnya berbentuk objek.
    ```
      const [data, setData] = useState({});
      console.log(nama, alamat);
      function handleEvent(e) {
        e.preventDefault();
        alert(`nama ${nama} alamat ${alamat}`);
        setData({ nama: nama, alamat: alamat });
        setNama("");
        setAlamat("");
      }
    ```
- Jika sudah seperti ini kita bisa menampilkan data yang telah diinput dalam form menggunakan format pemanggilan objek, seperti berikut:
    ```
          <h1>nama</h1>
          <h1>{data.nama}</h1>
          <h1>alamat</h1>
          <h1>{data.alamat}</h1>
    ```
- Yang perlu menjadi catatan adalah terdapat penulisan yang agak berbeda jika kita menggunakan dropdown. Kita harus memberikan setiap value pada optionnya dan  value tersebut nantinya akan ditangkap oleh state yang berada pada tag select
    ```
    <select value={program} onChange={(e) => setProgram(e.target.value)}>
              <option value="">Pilih program</option>
              <option value="studi independen">studi independen</option>
              <option value="magang">magang</option>
            </select>
    
    ```

# Writing & Presentation Test Week 8

## React Context

### Instalasi React Context
- Context pada React JS merupakan sebuah fasilitas yang disediakan oleh React agar kita dapat memanajemen state secara global sehingga state tersebut dapat diakses oleh semua components yang kita miliki sehingga dapat menghindari adanya props drilling ketika akan mengakses sebuah data. Namun, walaupun begitu context tidak dapat disebut sebagai sebuah state management. Penggunaan context di dalam project react kita sangat efektif jika kita hanya memiliki sedikit data yang ingin kira sebar untuk diakses oleh semua components
- Berbeda dengan redux, ketika ingin menggunakan context kita tidak perlu menginstall dependencies apapun karena sudah di sediakan dari bawaan project React.Untuk menggunakan context, pertama tama kita harus membuat context terlebih dahulu menggunakan perintah berikut:  
    ```
    export const namaContext = createContext();
    ```
### Pemanggilan React Context
- Setelah membuat context, kita bisa menanggil context tersebut ke dalam functional component yang kita miliki sebagai sebuah open dan close tag yang berfungsi sebagai provider yang menyediakan data ke komponent yang nantinya akan kita ambil datanya melalui props: 
    ```
    return (
    <namaContext.Provider value={}>
      
    </namaContext.Provider>
    )

    ```
- Kemudian, value yang ada di dalam close and open tag tersebut adalah state yang akan menyimpan data yang akan kita sediakan secara global. Pada langkah ini kita harus membuat state tersebut lalu nantinya getter dan setter dari useState ini akan dijadikan sebagai value dari tag context yang ada di dalam return
    ```
    const [getter, setrer] = useState(0);
      return (
        <namaContext.Provider value={(getter, setter)}>
          {children}
        </namaContext.Provider>
        )
    ```
- Setelah memanggil context, kita menuju ke index.js lalu melakukan import context ke dalamnya:
    ```
    import KeranjangCountProvider from "./components/KeranjangCountProvider";
    ```
- Function provider ini nantinya akan menerima sebuah props berupa keseluruhan dari app yang kita miliki. kita bisa memanggilnya ke dalam return sebagai tag pembuka dan penutup pada file utama index.js kita sebagai sebagai mengirimkan data props ke file component kita yang berisi context.
    ```
    const root = ReactDOM.createRoot(document.getElementById("root"));
    root.render(
      // <React.StrictMode>
      <namaProvider>
        <App />
      </namaProvider>
      // </React.StrictMode>
    );
    ```
- Karena app.js sudah kita provide kepada sebuah element, kita bisa memanggil app.js sebagai sebuah props yang bisa kita panggil pada file yang berisi context kita sebelumnya lalu kita panggil ke dalam context:
    ```
    function namaProvider({ children }) {
      const [getter, setter] = useState(0);
      return (
        <namaContext.Provider value={(getter, setter)}>
          {children}
        </namaContext.Provider>
        )
      }
    ```
### Penggunaan React Context
- Kemudian untuk menggunakan context di dalam sebuah component maka kita harus menggunakan useContext yang harus kita import terlebih dahulu lalu kita pakai untuk memanggil context yang telah kita buat sebelumnya:
    ```
    function Keranjang() {
      const namaVariable = useContext(namatContext);
      return (
        <div>
          <h1>Keranjang: {namaVariable.getter}</h1>
          <h2></h2>
        </div>
      );
    }
    ```
- Cara diatas ini juga berlaku di dalam file lainnya jika kita ingin mengakses dan menampilkan data berasal dari context
- Kita sudah mengetahui cara bagaimana kita menampilkan data dari context, selanjutnya kita akan membahas mengenai bagaimana kita merubah data state yang ada di dalam context tersebut. 
- Cara untuk kita merubah data state yang ada di dalam context yaitu kita harus memanggil context yang telah kita membuat di dalam component yang ingin kita ubah datanya menggunakan useContext:
    ```
    import { namaContext } from "../components/KeranjangCountProvider";
    ```
    ```
    function namaFunction() {
      const { getter, setter } = useContext(namaContext);
       );
    ```
- Selanjutnya kira buat function yang nantinya akan dipanggil di dalam button, sehingga ketika kita menekan button tersebut berjalanlah function tersebut untuk merubah data di dalam context
    ```
    import { useState } from "react";
    import { KeranjangCountContext } from "../components/KeranjangCountProvider";
    import { useContext } from "react";
    
    function Counter() {
      const { getter, setter } = useContext(namaContext);
      const [count, setCount] = useState(0);
    
      function incrementF() {
        setter(getter + 1);
        setCount(count + 1);
      }
      function decrementF() {
        setter(getter - 1);
        setCount(count - 1);
      }
      return (
        <div>
          <button onClick={  decrementF}>-</button>
          <span>{count}</span>
          <button onClick={incrementF}>+</button>
        </div>
      );
    }
    ```
- Dengan melakukan proses ini nantinya kita bisa mengakses dan menampilkan data pada fungtional component yang kita buat dari context yang telah dibuat sebelumnya
### Cara Menggunakan 2 Context Bersamaan
- Lalu bagaimana jika terdapat 2 context di dalam project kita?. Jika hal demikian terjadi di dalam project kita maka kemungkinan besar akan terjadi sebuah context hell. 
- Pertama kita harus membuat context tersebut seperti langkah” sebelumnya hingga memanggill context ke dalam index.js. seperti berikut: 
    ```
    import { createContext } from "react";
    import { useState } from "react";
    
    const namaContext2= createContext()
    function namaProvider2({children}) {
              const [getter2, setter2]=useState({
                        name1: value1, 
                        name2: value2
              })
              return ( 
                        <namaContext2 value={{getter2, setter2 } }>
                                  {children}
                        </namaContext2>
               );
    }
    
    export default namaProvider2;
    ```
- Sebelum kita menambahkan context kedua ke dalam file utama index.js, kita harus mengimportnya terlebih dahulu seperti biasa
- Context kita pada file utama index.js yang lama kita bungkus dengan context yang baru sehingga membentuk context hell. Tetapi yang perlu menjadi catatan adalah bahwa urutan penempatan pemanggilan context pada tahap ini harus benar-benar diperhatikan karena sangat berhubungan dengan proses pengambilan data dari parent ke child. Jika kita salah mengatur urutannya maka akses dan pengambilan data kita kedepannya akan mengalami error
    ```
    const root = ReactDOM.createRoot(document.getElementById("root"));
    root.render(
      // <React.StrictMode>
      <UserProvider>
        <KeranjangCountProvider>
          <App />
        </KeranjangCountProvider>
      </UserProvider>
      // </React.StrictMode>
    );
    ```
- Setelah terpanggil seperti ini, kita bisa melakukan pemanggilan data seperti proses yang telah kita lakukan sebelumnya

## Kombinasi Context dan useReducer
### Alasan kita mengkombiansikan Context dan useReducer 
- UserReducer biasa digunakan ketika kita memiliki sebuah state yang membutuhkan banyak cara perubahan atau membutuhkan proses perubahan yang kompleks
- Untuk mengkombinasikan keduanya, pertama kita harus membuat beberapa component utama penggunaan context seperti pada pertemuan kemarin. Seperti component biasa dan komponen provider untuk membuat context
- Kombinasi antara context dan use reducer berfungsi agar kita dapat memanage sebuah data dengan terorganisir dengan baik. Bisa saja kita melakukan manage data hanya menggunakan context biasa. Namun, kita harus mengolah datanya di dalam code jsx kita. Sehingga kita tidak bisa melakukan reusable manage data dan lebih sulit untuk di-maintenance. Hadirnya kombinasi context dan useReducer hadir memberi solusi dari kekurangan tersebut.
### Set-up Awal Penggunaan Kombinasi Context dan Reducer
- Jika kita ingin menggunakan reducer maka pertama-tama kita harus melakukan import useReducer ke dalam file context provider agar kita dapat menggunakan useReducer: 
    ```
    import { createContext, useState, useReducer } from "react";
    ```
- Setelah berhasil di import maka kita bisa membuat reducer beserta initial state di dalam file tersebut seperti sebagai berikut:
    ```
    const initialState = {
      name: value,
    };
    
    function reducer(state, action) {
      switch (action.type) {
        default:
          return state;
      }
    }
    ```
- Buat terlebih dahulu constant variable agar kedepannya kita dapat lebih mudah memanggilnya di dalam action maupun reducer
    ```
    const INCREMENT = "INCREMENT";
    const DECREMENT = "DECREMENT";
    ```
- Setelah itu kita buat lagi state beserta deklarasi action type yang nantinya akan dipanggil pada reducer dan memanggil function reducer dan initialState sebagai parameter di dalam useReducer
    ```
    function namaProvider({ children }) {
      const [state, dispatch] = useReducer(reducer, initialState);
      return (
        <namaContext.Provider value={{  }}>
          <div>{children}</div>
        </namaContext.Provider>
      );
    }
    ```
- Lalu tambahkan function yang berisi action di dalam function provider tersebut sesuai yang Anda butuhkan, tak lupa function action ini memiliki return berupa type dari suatu hal yang nantinya dilakukan oleh reducer
    ```
    function namaProvider({ children }) {
      const [state, dispatch] = useReducer(reducer, initialState);
      const namaFunction = () => {
        dispatch({ type: VALUE });
      };
    ```
- Setelah membuat value, maka kita bisa menambahkan dan mengatur case yang ingin kita jalankan di dalam reducer, berikut adalah contoh pengolahan data pada counter:
    ```
    function reducer(state, action) {
      switch (action.type) {
        case INCREMENT:
          return { count: state.count + 1 };
        case DECREMENT:
          return { count: state.count - 1 };
        default:
          return state;
      }
    }
    ```
- Setelah itu, kita harus memanggil state dan action yang telah kita buat ke dalam value yang dimiliki oleh provider:
    ```
    return (
        <namaContext.Provider value={{ state, namaAction }}>
          <div>{children}</div>
        </namaContext.Provider>
      );
    ```
### Penggunaan Kombinasi Context dan useReducer
- Cara kita menghandle data menggunakan context biasa dengan menggunakan kombinasi context dan useReducer agak berbeda. Jika awalnya kita menggunakan context biasa dan ingin berpindah ke kombinasi context dan useReducer maka akan ada beberapa hal yang perlu kita sesuaikan seperti berikut: 
- Pertama kita harus memanggil value milik provider yang kita butuhkan ke dalam functional component yang ingin kita pakai: 
    ```
    function namaComponent() {
      const { state, namaAction } = useContext(namaContext);
     
      return ()
    ```
- Lalu selanjutnya yang harus kita lakukan adalah memanggil masing-masing action dan state tersebut ke dalam component yang kita miliki. Cara pengimplementasikannya pun agak berbeda dengan menggunakan context biasa berikut perbandingan kombinasi context biasa dan kombinasi context dan reducer: 
- Kombinasi context dan reducer: 
    ```
      return (
        <div>
          <button onClick={decrement}>-</button>
          <span>{state.count}</span>
          <button onClick={increment}>+</button>
        </div>
      );
    ```
- Menggunakan context biasa: 
    ```
    return (
        <div>
          <button onClick={() => state.setCount(state.count - 1)}>-</button>
          <span>{state.count}</span>
          <button onClick={() => state.setCount(state.count + 1)}>+</button>
          <button onClick={decrement}>-</button>
          <span>{state.count}</span>
          <button onClick={increment}>+</button>
        </div>
      );
    ```
- Perbedaannya terletak di dalam pengolahan datanya, jika menggunakan context biasa maka kita harus memberlakukan pengolahan datanya secara inline di dalam element jsx. Sedangkan, jika kita menggunakan kombinasi context dan reducer maka semua pengolahan diletakkan di dalam reducer dan tinggal memanggil functionnya saha di dalam method onClick 
## React Testing
### Definisi React Testing
- Testing merupakan sebuah kegiatan memberlakukan sebuah pengecekan terhadap program yang kita miliki guna mencari tahu apakah program yang kita miliki sudah sesuai dengan ekspektasi yang kita miliki atau tidak. 
- Tanpa sadar selama ini kita sudah melakukan testing pada saat kita melakukan tugas-tugas TPA maupun groub project. Karena pasti di dalamnya kita melakukan uji coba terhadap aplikasi tersebut apakah sudah berjalan sesuai dengan yang kita inginkan. 

### Jenis-Jenis Testing
- Testing terbagi menjadi 2 jenis yaitu manual testing dan automation testing. Contoh dari manual testing adalah testing yang sudah pernah kita lakukan pada project yang kita miliki sebelumnya. sedangkan contoh dari automation testing adalah memberlakukan sebuah test kepada sebuah project code menggunakan sebuah code testing. Secara umum, automation testing dibagi menjadi 3 jenis test yaitu: 
    1. Unit test
        Pada jenis ini kita melakukan pengujian terhadap unit kecil yang ada di dalam code program di dalam project kita. Contoh dari unit tes adalah dimana developer melakukan cek terhadap hasil dari function yang telah kita buat. Testing jenis ini memerlukan cost yang rendah dengan waktu pengerjaan yang tergolong cepat
    2. Intergration
        Integration merupakan pemberlakuah testing terhadap code program project yang terhubung dengan sistem lainnya. Test jenis ini biasanya dilakukan oleh perusahaan besar yang memiliki kapabilitas mengeluarkan biaya testing karena memerlukan budget menengah dan pengerjaan yang cukup lambat
    3. End to end
        Pengecekan cari sisi user, contohnya adalah kita melakukan suatu skenario bagaimana seorang user sedang mengakses sebuah aplikasi. Jenis tes ini memerlukan waktu yang lambat dan cost yang besar. Test ini biasa dilakukan oleh seorang Quality Assurance engineer yang di hire oleh sebuah perusahaan, mereka umumnya melakukan test tersebut menggunakan software seperti katalon 
        Pada dasarnya developer memiliki ranahnya masing-masing. Untuk developer di perusahaan besar biasanya testing yang dilakukan yaitu mencakup ketiga jenis diatas. Sedangkan, developer di dalam ranah startup lebih berfokus pada validasi sebuah aplikasi terhadap minat market atau customer
- Cara penulisan test ada 2:
    1. Membuat fitur terlebih dahulu lalu melakukan testing kemudian
    
        Biasanya dilakukan oleh developer di dalam sebuah startup untuk mengejar tenggat waktu diluncurkannya sebuah aplikasi.  Fokus pemberlakuan test ini adalah agar developer dapat memenuhi kebutuhan customer di dalam sebuah fitur
    2. Membuat testing terlebih dahulu lali melakukan pembuatan fitur kemudian (TDD)
    
        Metode ini dilakukan dengan 3 tahap yaitu red, green dan blue zone. Dimana, awalnya dilakukan sebuah penuangan ide dan ekspektasi terhadap kode, jika kode tersebut sudah memenuhi ekspektasi maka akan di finalisasi dan dilakukan refactor untuk melakukan efisiensi terhadap kode tersebut
- Tujuan utama dari dilakukan sebuah testing adalah untuk melihat apakah ada suatu error pada saat dimana 2 atau lebih fitur berjalan secara bersamaan di dalam aplikasi. Yang perlu menjadi catatan dala melakukan testing membutuhkan waktu yang cukup lama

### Penggunaan Testing
- Contoh penggunaan manual testing
    ```
    // contoh skenario sebuah testing
    // lakukan penjumlahan function menggunakan 2 parameter
    
    // buat ekspektasinya terlebih dahulu
    console.log(sum(0, 8)); //8
    console.log(sum(3, 4)); //7
    console.log(sum(9, 2)); //11
    console.log(sum(4, 5)); //9
    
    
    // jalankan function sesuai soal
    
    function sum(x, y) {
      return x + y;
    }
    ```
- Untuk melakukan manual testing yang hal pertama yang dilakukan yaitu kita buat dulu proses penghitungannya beserta ekspektasi yang kita harapkan
    ```
    asus@LAPTOP-SSPEPM0V MINGW64 /e/Latihan Frontend/React/Day 13/Testing 
    $ node app.js
    8
    7
    11
    9
    ```
- Jika sudah, jalankan perintah node “nama aplikasi” pada terminal untuk menjalankan proses penghitungan. Jika sudah berjalan, nantin akan terlihat apakah hasil yang muncul sudah tertera dengan ekspektasi kita atau tidak
- Contoh penggunaan automation testing
- Kemudian jangan lupa tambahkan object JSON berikut di dalam file package.json agar kita dapat melakukan testing: 
    ```
    "scripts": {
    "test": "jest"
  }
    ```
- Untuk menggunakan automation testing kita harus menginstall dependensinya terlebih dahulu menggunakan perintah:
    ```
    npm install -D jest
    ```
- Buat sebuah fungtion berisi penghitungan di file utama lalu export agar nantinya bisa kita import pada file testing: 
    ```
    function sum(x, y) {
      return x + y;
    }
    
    module.exports = sum;
    ```
- Selanjutnya kita harus membuat file baru dengan ekstensi .test.js yang nantinya berisi ekspektasi dari hasil code yang ingin di jalankan dan juga harus melakukan import file utama yang ingin dilakukan sebuah testing seperti ini:
    ```
    const sum = require("./app");
    
    test("sum 1, 2-> 3", () => {
      expect(sum(0, 0)).toBe(0);
      expect(sum(0, 1)).toBe(1);
      expect(sum(2, 5)).toBe(7);
    });
    ```
- Selanjutnya jalankan testnya menggunakan perintah: 
    ```
    Npm run test
    ```
- Jika pengujiannya sesuai dengan ekspektasi maka akan memunculkan hasil sebagai berikut:
    ```
    asus@LAPTOP-SSPEPM0V MINGW64 /e/Latihan Frontend/React/Day 13/Testing
    $ npm run test
    
    > test
    > jest
    
     PASS  ./app.test.js
      √ sum 1, 2-> 3 (2 ms)
    
    Test Suites: 1 passed, 1 total
    Tests:       1 passed, 1 total
    Snapshots:   0 total
    Time:        0.465 s, estimated 1 s
    Ran all test suites.
    ```
- Dan jika tidak sesuai dengan ekspektasi maka hasilnya akan menjadi seperti ini:
    ```
    asus@LAPTOP-SSPEPM0V MINGW64 /e/Latihan Frontend/React/Day 13/Testing
    $ npm run test
        Received: 0
    
          3 | test("sum 1, 2-> 3", () => {
          4 |   expect(sum(0, 0)).toBe(0);
        > 5 |   expect(sum(0, 1)).toBe(1);
            |                     ^
          6 |   expect(sum(2, 5)).toBe(7);
          7 | });
          8 | // test("cek ganjil/genap", () => {
    
          at Object.toBe (app.test.js:5:21)
    
    Test Suites: 1 failed, 1 total
    Tests:       1 failed, 1 total
    Snapshots:   0 total
    Time:        0.679 s, estimated 1 s
    Ran all test suites.
    ```
- Selain testing simpel di atas, jest juga menyediakan banyak matchers yang bisa digunakan untuk melakukan lebih banyak testing terhadap jenis data yang dapat dilihat pada dikumentasi berikut: 
    > https://jestjs.io/docs/using-matchers
- berikut adalah contoh penggunaan matcher:
    ```
    test("check thruty", () => {
      expect(isEven(4)).toBeTruthy();
      expect(isEven(3)).toBeTruthy();
    });
    ```
- Untuk menghasilkan pengujian lebih jauh kita bisa menambahkan dependensi coverage di dalam dependencies seperti berikut:
    ```
    {
      "scripts": {
        "test": "jest --coverage"
      },
      "devDependencies": {
        "jest": "^29.3.1"
      }
    }
    ```
- Dengan menambahkan coverage, maka hasil yang akan di tampilkan di dalam pengujian kita akan ditampilkan secara lebih lengkap seperti berikut: 
    ```
    asus@LAPTOP-SSPEPM0V MINGW64 /e/Latihan Frontend/React/Day 13/Testing
    $ npm run test
    
    > test
    > jest --coverage
    
     PASS  ./app.test.js                                                                                                                                            
      √ check thruty (1 ms)
                                                                                                                                                                    
    ----------|---------|----------|---------|---------|-------------------                                                                                         
    File      | % Stmts | % Branch | % Funcs | % Lines | Uncovered Line #s                                                                                          
    ----------|---------|----------|---------|---------|-------------------
    All files |     100 |       50 |     100 |     100 | 
     app.js   |     100 |       50 |     100 |     100 | 29
    ----------|---------|----------|---------|---------|-------------------
    Test Suites: 1 passed, 1 total
    Tests:       1 passed, 1 total
    Snapshots:   0 total
    Time:        0.584 s, estimated 1 s
    Ran all test suites.
    ```
### React Testing Library
- React Testing Library merupakan sebuah fungsi untuk melakukan testing terhadap component-components yang ada di dalam project React. Yang melakukan tes berdasarkan user centric, atau melakukan testing dari sudut pandang user
- Di dalam project react kurang lebih fil testingnya juga sama yaitu terdapat ekspektasi hasil yang diinginkan developer di dalamnya seperti berikut: 
    ```
    test('renders learn react link', () => {
      render(<App />);
      const linkElement = screen.getByText(/learn react/i);
      expect(linkElement).toBeInTheDocument();
    });
    ```
- Sintaks screen biasa dikkombinasikan dengan method yang telah disediakan oleh React lalu di dalam file testing ini digunakan untuk mengakses dan mengambil sebuah element. Contoh method yang telah disediakan seperti getBy, findBy, queryBy, getAllBy, findAlBy, queryAllBy. Untuk mengambil element, kita harus memperhatikan aksesibilitasnya karena tidak semua element dapat diakses begitu saja
- Untuk urutan penulisan di dalam file testingnya dimulai dari merender component, mencari element, berinteraksi dengan element dan yang terakhir assert hasil dari element tersebut apakah sudah sesuai dengan ekspektasi yang diinginkan atau belum
- Jika kita membuat sebuah project react baru menggunakan npx, maka di dalamnya sudah tersedia sebuah file testing yang secara default melakukan testing terhadap tahap render component react dalam format regex, tetapi selain menggunakan regex kita juga bisa menuliskannya menggunakan format string
- Untuk hasil pengetesannya pun hampir sama, namun membutuhkan waktu yang lebih lama: 
    ```
    PASS  src/App.test.js
    
    Test Suites: 1 failed, 1 passed, 2 total
    Tests:       1 passed, 1 total
    Snapshots:   0 total
    Time:        6.84 s
    Ran all test suites related to changed files.
    
    Watch Usage: Press w to show more.
    ```































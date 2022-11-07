# Writing & Presentation Test Week 7

## PropTypes

### Pengertian instalasi PropTypes
- Proptypes merupakan sebuah validator typechecking yang ada di dalam React JS yang digunakan untuk memastikan bahwa data yang akan kita terima dari hasil pemrosesan sudah valid. Untuk menggunakan propTypes kita harus menginstallnya terlebih dahulu. Kita dapat menginstallnya menggunakan perintah: 
    ```
    npm install prop-types
    ```
- Kita juga harus meng-importnya terlebih dahulu ke dalam sebuah komponen yang ingin kita beri validasi di dalamnya menggunakan perintah:
    ```
    import PropTypes from "prop-types";
    ```
### Penggunaan PropTypes
- Cara penggunaan proptypes adalah dengan memanggil function yang ingin kita beri validator, lalu kenakan properties proptype ke dalamnya. Setelah itu buat objek yang berisi inputan yang ingin diberi validasi beserta tipe data validatornya, kita juga bisa menambahkan validatornya berupa any untuk memperbolehkan data apa saja masuk menjadi sebuah input seperti berikut: 
    ```
    import PropTypes from "prop-types";
    
    function StudentInfo({ nama, umur }) {
      return (
        <>
          <h2>{nama}</h2>
          <h2>{umur + 5}</h2>
        </>
      );
    }
    StudentInfo.propTypes = {
      nama: PropTypes.string,
      umur: PropTypes.number.isRequired,
    };
    
    export default StudentInfo;
    ```
- Kita juga bisa memberlakukan properties isRequired untuk memvalidasi bahwa sebuah inputan harus memiliki data di dalamnya. Contoh penggunaan: 
```
StudentInfo.propTypes = {
  nama: PropTypes.string,
  umur: PropTypes.number.isRequired,
};
```
- Di dalam proptypes selain memberikan 1 opsi tipe data untuk sebuah inputan, kita juga bisa memberikan opsi tersebut lebih dari satu, yaitu menggunakan method oneOfType(). Cara penggunaannya adalah sebagai berikut: 
    ```
    StudentInfo.propTypes = {
      nama: PropTypes.string,
      umur: PropTypes.oneOfType([PropTypes.string, PropTypes.number]),
    };
    ```
- Kita juga bisa melakukan set isi data dari sebuah array menggunakan perintah arrayOf seperti ini: 
    ```
    umur: PropTypes.arrayOf(PropTypes.number)
    ```
    ```
    umur: PropTypes.arrayOf(PropTypes.oneOfType([PropTypes.string, PropTypes.number]))
    ```
- Jika data yang diinputkan tidak sesuai dengan kriteria yang telah di set pada proptypes, maka code akan tetap berjalan tetapi tampil sebuah peringatan/error pada console browser
- Selain melakukan cek validasi tipe data yang ada di dalam sebuah array, kita juga bisa menambahkan validasi untuk tipe data yang berada di dalam object. Kita bisa melakukan cek menggunakan method shape(), contohnya adalah sebagai berikut:
    ```
    info: PropTypes.shape({
        kelas: PropTypes.number,
        hobi: PropTypes.string,
      })
    ```
- Sedangkan, untuk menambahkan validasi berupa inputan apa saja yang harus ditambahkan kita bisa menggunakan method PropTypes.exact(). Jika kita memberikan input yang tidak sesuai dengan yang telah di set di dalam exaxt maka akan terjadi peringatan error pada console. Penulisan PropTypes.exact() sama dengan penggunaan PropType.shape()
## React Router
### Instalasi Router
- Kalau kita kemarin sempat membuat kode di dalam app.js, mulai pertemuan kali ini kita tidak akan melakukannya lagi karena pada dasarnya app.js hanya berisi code terkati routing dan tidak diisi dengan code logic sehingga file app.js akan terlihat bersih
- Untuk menggunakan React router, kita harus menginstall react router terlebih dahulu menggunakan perintah: 
    ```
    npm install react-router-dom@6
    ```
- Lakukan import pada file index.js menggunakan perintah
    ```
    import { BrowserRouter } from "react-router-dom";
    ```
- pakai routes pada halaman app.js
    ```
    import logo from "./logo.svg";
    import "./App.css";
    import { Routes, Route, Link } from "react-router-dom";
    
    function App() {
      return (
        <>
          <Routes></Routes>
        </>
      );
    }
    
    export default App;
    ```
### Penggunaan React Routes
- nanti di dalam tag routes kita bisa menambahkan tag route yang nanti kita bisa mengaturnya untuk berpindah halaman
    ```
    function App() {
      return (
        <>
          <Routes>
            <Route path="/" element={<HomePage />} />
          </Routes>
        </>
      );
    }
    ```
- Path “/” biasa digunakan sebagai halaman default yang muncul pertama kali ketika user membuka aplikasi kita
- Sedangkan, untuk berpindah dari satu halaman ke halaman lainnya kita bisa menggunakan tag link yang bisa kita atur setelah kita mengatur sebuah routes
    ```
    <>
      {/* kita bisa menaruh navbar di sini dengan catatan navbar tersebut akan ditampilkan di semua halaman */}
      <nav>
        <Link to={"/"}>Home</Link>
        <Link to={"/About"}>About</Link>
      </nav>
    ```
- Di dalam melakukan routing, kita juga bisa menggunakan parameter dalam penggunaannya. Untuk melakukannya kita bisa menggunakan params. Menggunakan params kita bisa mengirimkan beberapa data yang berbeda karena di dalamnya kita menggunakan parameter id untuk menampilkan masing-masing datanya
## React Redux
### Alasan Penggunaan Redux
- Props drilling merupakan sebuah proses oper data props dari parent ke banyak turunannya
- Permasalahan awal mengapa kita membutuhkan redux adalah bagaimana memberikan data yang sama terhadap semua child yang terhubung pada 1 parent. Solusi dari permasalahan ini adalah dengan menaruh sebuah data di dalam state yang terpusat (bukan di dalam app lagi) tetapi diluar semua bagian baik itu parent maupun child. 
- Keuntungan menggunakan cara ini adalah baik parent maupun child dapat mengaksesnya secara mandiri tanpa harus mengambil data melalui konsep parent child terlebih dahulu. Hal ini disebut dengan state management. Ada beberapa state management seperti redux dan context
### Instalasi Redux
- Untuk menggunakan reduct kita harus install package nya terlebih dahulu menggunakan perintah: 
    ```
    Npm install redux 
    ```
### Dasar Penggunaan Redux
- Tahap pembuatan redux adalah menyediakan store (tempat penyimpanan data) terlebih dahulu menggunakan createStore() yang nantinya berisi sebuah function berupa reducer seperti berikut:  
    ```
    import { createStore } from "redux";
    const store = createStore(() => {});
    
    export default store;
    ```
- Selanjutnya kita harus membuat sebuah reducer di dalam store. Reducer bisa diibaratkan menjadi rak yang menyimpan barang-barang. Reducer ini nantinya akan menerima initial state di dalamnya berupa nilai awal yang di deklarasikan seperti berikut: 
    ```
    const initialState = {
      keranjang: 1,
    };
    
    function keranjangReducer(state = initialState, action) {
      switch (action.type) {
        default:
          return state;
          break;
      }
    }
    
    export default keranjangReducer;
    ```
- Langkah selanjutnya kita harus membuat provider yang menyatakan bahwa store yang telah kita buat tersedia atau siap diakses oleh component yang ada di dalam project react kita. Untuk membuat provider kita bisa menginstallnya terlebih dahulu menggunakan install react redux menggunakan perintah: 
    ```
    npm install react-redux
    ```
- Setelah itu import provider dan store yang telah kita buat sebelumnya pada file index.js pada folder store agar kita dapat memberikan provider dan memanggil store ke dalam app yang ada di dalam index.js. berikut adalah perintah import dan contoh pemberian provider
    ```
    Import {Provider} from “react-redux”
    Import store from “./redux/store”
    ```
    ```
    import { Provider } from "react-redux";
    import store from "./components/redux/store";
    
    const root = ReactDOM.createRoot(document.getElementById("root"));
    root.render(
      // <React.StrictMode>
      <Provider store={store}>
        <App />
      </Provider>
      // </React.StrictMode>
    );
    ```
### Menampilkan Data dari Redux
- Tahap selanjutnya kita harus mengambil data dari store untuk ditampilkan pada component. Untuk melakukannya kita bisa menggunakan useSelector() yang berisi parameter yang mengarah ke dalam store untuk akses data ke dalam store
    ```
    function Keranjang() {
      const { keranjang } = useSelector((state) => state);
    
      return (
        <div>
          <h1>Keranjang</h1>
          <h2>{keranjang}</h2>
        </div>
      );
    }
    ```
### Interaksi data Redux
- Setelah bisa menampilkan data yang telah diambil dari store, selanjutnya kita harus bisa membuat interaksi terdapat data yang ada di dalamnya. Untuk melakukannya kita dapat membuat action yang nantinya menentukan apa yang nantinya akan kita berlakukan pada data yang kita simpan di dalam store. Namun, action nantinya hanya akan berisi type dari action yang akan di jalankan saya. Sedangkan untuk pemrosesan datanya akan dilakukan di dalam switch yang ada di dalam reducer. Berikut adalah pembuatan actionnya:
    ```
    export const INCREMENT = "INCREMENT";
    export const DECREMENT = "DECREMENT";
    
    function increment() {
      return {
        type: INCREMENT,
      };
    }
    function decrement() {
      return {
        type: DECREMENT,
      };
    }
    ```
- Sedangkan untuk pemrosesan yang nantinya diberlakukan kepada data di dalam store di simpan di dalam reducer seperti berikut:
    ```
    import { INCREMENT, DECREMENT } from "../action/keranjangAction";
    
    const initialState = {
      keranjang: 1,
    };
    
    function keranjangReducer(state = initialState, action) {
      switch (action.type) {
        case INCREMENT:
          state = {
            keranjang: state.keranjang + 1,
          };
          return state;
        case DECREMENT:
          state = {
            keranjang: state.keranjang - 1,
          };
          return state;
        default:
          return state;
                break;
      }
    }
    ```
### Memberi Perubahan dan Memasukkan Data ke dalam Reducer
- Langkah selanjutnya adalah mengubah data yang ada pada store. Ketika mengubah data, kita harus mengakses reducer melalui perantara dispatch() yang di dalamnya berisi action. Sebelum menggunakan dispatch kita harus melakukan import useDispatch dan import function action yang telah kita buat sebelumnya. import tersebut dapat kita lakukan seperti berikut:
    ```
    import { useDispatch } from "react-redux";
    import { increment, decrement } from "../components/action/KeranjangAction";
    ```
- Setelah melakukan import, kita harus memasukkan method useDispatch ke dalam sebuah variable agar nantinya kita dipermudah dalam menggunakannya seperti berikut: 
    ```
     const dispatch = useDispatch();
    ```
- Kita dapat memanggil dispatch di dalam function yang nantinya dipanggil menggunakan method onClick pada button
    ```
    function Counter() {
      const dispatch = useDispatch();
      const [count, setCount] = useState(0);
    
      function increment() {
        dispatch(increment());
        setCount(count + 1);
      }
      function decrement() {
        dispatch(decrement());
        setCount(count - 1);
      }
      return (
        <div>
          <button onClick={decrement}>-</button>
          <span>{count}</span>
          <button onClick={increment}>+</button>
        </div>
      );
    }
    ```

## Mengulas React Redux lebih Jauh
### Penggunaan Combine Reducer
- Membuat component to do list menggunakan redux
- Untuk membuat to do list kita bisa membuat form terlebih dahulu beserta handlenya untuk user memasukkan apa yang akan mereka kerjakan. Kemudian data yang telah diinputkan nantinya disimpan di dalam redux. Tetapi sebelumnya kita harus menyiapkan sebuah reducer untuk menyimpan data to do list seperti berikut: 
    ```
    const initialTodo = {
      data: ["tidur", "makan"],
    };
    
    function todoReducer(state = initialTodo, action) {
      switch (action.type) {
        default:
          return state;
          break;
      }
    }
    
    export default rodoReducer;
    ```
- Simpan reducer yang telah dibuat ke dalam store. Karena di dalam store sudah menyimpan reducer sebelumnya, jadi kita harus menggunakan function combine reducer agar kita dapat menyimpan lebih dari 1 reducer
    ```
    import { combineReducers, createStore } from "redux";
    import counterReducer from "../reducer/counterReducer";
    
    const allReducers = combineReducer({
      counter: counterReducer,
      todo: todoReducer,
    });
    const store = createStore(allReducers);
    
    export default store;
    ```
- Sebagai catatan, pengambilan data sebuah reducer biasa dan combine reducer berbeda. Data hasil dari combine reducer ditampilkan dalam bentuk object, sehingga ketika kita mengaksesnya harus dengan cara pengaksesan sebuah object JS. Contoh pengambilan datanya: 
    ```
    const { data } = useSelector((state) => state.todo);
    ```
- Setelah bisa mengambil datanya, kita bisa menampilkannya di dalam component
```
<ul>
        {data.map((item, index) => (
          <li key={index}>{item}</li>
        ))}
</ul>
```
### Penggunaan Payload
- Setelah berhasil menampilkan data, kita bisa memasukkan data dari form to do ke dalam redux dan ikut di tampilkan ke dalam list. Untuk melakukannya kita harus menambahkan dan membuat action terlebih dahulu, sebelum nantinya kita harus membuat payload ke dalam reducer untuk menghandle datanya ke dalam redux. 
- Membuat action
    ```
    export const ADD_TODO = "ADD_TODO";
    
    export function addTodo(todo) {
      
      return {
        type: ADD_TODO,
      };
    }
    ```
- Lalu atur reducer
    ```
    import { ADD_TODO } from "../action/todoAction";
    
    const initialTodo = {
      data: ["tidur", "makan"],
    };
    
    function todoReducer(state = initialTodo, action) {
      switch (action.type) {
        default:
          return state;
      }
    }
    
    export default todoReducer;
    ```
- Atur juga dispatchnya terlebih dahulu
    ```
      function handleSubmit(event) {
        dispatch(addTodo(todo));
        event.preventDefault();
        setTodo("");
      }
    ```
- Sebelum payload kita membutuhkan parameter di dalam actionnya, lalu setelah itu kita bisa menambahkan payload ke dalam action
    ```
    export const ADD_TODO = "ADD_TODO";
    
    export function addTodo(todo) {
      console.log(todo, "dari action");
      return {
        type: ADD_TODO,
        payload: todo,
      };
    }
    ```
- Setelah itu kita harus mengatur return di dalam reducer berupa object baru yang isinya property data ditambah dengan data baru dari payload
    ```
    import { ADD_TODO } from "../action/todoAction";
    
    const initialTodo = {
      data: ["tidur", "makan"],
    };
    
    function todoReducer(state = initialTodo, action) {
      switch (action.type) {
        case ADD_TODO:
          return {
            data: [...state.data, action.payload],
          };
        default:
          return state;
      }
    }
    
    export default todoReducer;
    ```

## React Thunk
- Secara default proses memasukkan data ke dalam reducer malalui dispatch hanya bisa menggunakan proses syncronous (tidak ada delay). Namun, ada kalanya kita harus menggunakan proses asyncronous seperti axios dan fetch sehingga menyebabkan masalah di program kita. Solusi yang dapat digunakan adalah menggunakan thunk agar program kita dapat berjalan dengan normal. 
### Install dan Import React Thunk
- Thunk merupakan sebuah function di dalam React JS Redux yang digunakan untuk membawa atau menjalankan asyncronous logic ke dalam reducer. Untuk menggunakan thunk, pertama kita harus menginstall thunk terlebih dahulu menggunakan perintah: 
    ```
    Npm install redux-thunk
    ```
- Jika sebelumnya kita menjalankan fetch data dari API menggunakan axios di dalam useEffect langsung di dalam component, jika menggunakan thunk maka kita harus melakukan fetch data menggunakan axios di dalam action. Kemudian action ini nantinya dibawa oleh dispatch ke dalam reducer 
- Setelah melakukan install thunk, sebelum menggunakannya kita harus melakukan import middleware terlebih dahulu menggunakan perintah:
    ```
    import { createStore, combineReducers, applyMiddleware } from "redux";
    ```
### Menggunakan Thunk ke dalam Project React
- Setelah itu, kita dapat memasukkan thunk yang kita miliki ke dalam middleware yang sebelumnya sudah kita import ke dalam project React. Middleware ini nantinya akan membawa thunk ke dalam store bersama combine reducer seperti berikut:
    ```
    const allReducer = combineReducers({
      todo: todoReducer,
    });
    
    const store = createStore(allReducer, applyMiddleware(thunk));
    ```
- Selanjutnya kita membuat action yang memiliki proses asyncronous terlebih dahulu. Kita membuat sebuah action yang memiliki return berupa sebuah function dengan parameter sebuah dispatch yang nantinya akan membawa function berisi action type.
### Alasan Penggunaan Thunk pada Project React
- Alasan penggunaan thunk menggunakan applyMiddleware pada store yaitu dikarenakan kita akan menggunakan proses asyncronous yang nantinya di jalankan pada file action: 
    ```
    import { createStore, combineReducers, applyMiddleware } from "redux";
    import thunk from "thunk";
    import todoReducer from "../reducer/todoReducer";
    
    const allReducer = combineReducers({
      todo: todoReducer,
    });
    
    const store = createStore(allReducer, applyMiddleware(thunk));
    ```
- dengan begitu, kita bisa melakukan proses asyncronous di dalam action yang terhubung ke reducer sebagai file yang berisi pengolahan data:
    ```
    import axios from "axios";
    
    export const GET_TODO = "GET_TODO";
    export const FETCH_START = "FETCH_START";
    export const SUCCES = "SUCCES";
    
    function fetchStart() {
      return {
        type: FETCH_START,
      };
    }
    
    function succes() {
      return {
        type: SUCCES,
        payload: data,
      };
    }
    export const getTodo = () => {
      return async (dispatch) => {
        dispatch(fetchStart());
    
        const hasil = await axios.get("URL Link");
        dispatch(succes(result.data));
      };
    };
    
    ```
- Return yang bembawa asynconous juga membawa dispatch yang berfungsi untuk mengirimkan data hasil fetch ke dalam store sebelum nantinya bisa diakses oleh masing-masing component untuk ditampilkan datanya






























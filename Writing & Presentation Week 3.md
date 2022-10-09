# Writing & Presentation Test Week 3

## Array dan Multi-Dimensional Array
### Array
- Array merupakan sebuah struktur data yang digunakan untuk menyimpan sekumpulan data dengan berbagai tipe data dalam suatu variabel. Contoh array: 
    ```
    let hewan = ["kucing", "Anjing", "Kelinci"];
    ```
- untuk menampilkan isi array kita bisa menggunakan perintah soncole.log(namaArray[index])
    ```
    let hewan = ["kucing", "Anjing", "Kelinci"];

    console.log(hewan[0]); //output: kucing
    ```
- Pada tipe data array JavaScript sudah menyediakan property bawaan length. Property length berfungsi untuk mengembalikan jumlah element yang ada pada suatu tipe data array. Contoh penggunaan: 
    ```
    let hewan = ["kucing", "Anjing", "Kelinci"];

    console.log(hewan.length);
    // output: 3
    ```
- Selain propery, JavaScript juga menyediakan beberapa method bawaan seperti: push(), unshift(), pop(), splice(), slice(). Penjelasan dari method-method tersebut adalah sebagai berikut: 
    - Push() merupakan method yang berfungsi untuk menambahkan item baru pada akhir sebuah array sehingga menambah panjang array dan array akan memiliki return length baru. Contoh penggunaan: 
        ```
        let hewan = ["kucing", "Anjing", "Kelinci"];

        hewan.push("sapi");
        // isi array menjadi ["kucing", "Anjing", "Kelinci", "sapi"]
        ```
    - Unshift() merupakan method yang berfungsi untuk menambahkan 1 atau lebih element pada permulaan array sehingga mengembalikan return berupa length baru pada array. Contoh penggunaan: 
        ```
        let hewan = ["kucing", "Anjing", "Kelinci"];

        hewan.push("sapi");
        // isi array menjadi ["kucing", "Anjing", "Kelinci", "sapi"]
        hewan.unshift("biawak", "kanguru");
        // isi array menjadi ["biawak", "kanguru","kucing", "Anjing", "Kelinci", "sapi"]
        ```
    - Pop() merupakan method yang berfungsi untuk menghapus element terakhir pada sebuah array sehingga mengubah isi array dan mengembalikan return element yang telah dihapus. Contoh penggunaan: 
        ```
        let hewan = ["kucing", "Anjing", "Kelinci"];

        hewan.push("sapi");
        // isi array menjadi ["kucing", "Anjing", "Kelinci", "sapi"]
        hewan.unshift("biawak", "kanguru");
        // isi array menjadi ["biawak", "kanguru","kucing", "Anjing", "Kelinci", "sapi"]
        hewan.pop();
        console.log(hewan.pop());
        //output: "kelinci"
        ```
    - Splice() merupakan method yang digunakan untuk menambah dan/atau menghapus element pada sebuah array sehingga merubah isi dari tipe data array. Cara penggunaannya adalah array.splice(index, banyak data, item 1, …, item n). Contoh penggunaan: 
        ```
        let hewan = ["kucing", "Anjing", "Kelinci"];

        hewan.splice(1, 1, "siput", "ular");
        // output: [ "kucing", "siput", "ular", "Kelinci"]
        ```
    - Slice() merupakan method yang mengembalikan suatu element yang dipilih pada sebuah array menjadi array baru. Ketika menggunakan slice() kita memasukkan argumen berupa permulaan dan akhiran (opsional) element yang dipilih. Contoh penggunaan:
        ```
         let hewan = ["kucing", "Anjing", "Kelinci"];

        console.log(hewan.slice(1, 3));
        //output: array[ "Anjing", "Kelinci" ]
        ```
- **Menampilkan isi data array menggunakan looping** 
- Ketika kita menampilkan isi data dari sebuah array kita harus menuliskan perintah console.log(array[index]). Jika hanya mengeluarkan 1 isi data mungkin masih oke, tetapi, ketika kita harus menampilkan banyak isi data sebuah array maka perintah yang dituliskan menjadi sangat banyak dan tidak efisien. Solusi untuk hal tersebut adalah menampilkan isi data array menggunakan looping agar kita tidak perlu menuliskan perintah berulang-ulang. Perulangan atau method yang digunakan untuk menampilkan isi dari sebuah array adalah sebagai berikut: 
    - Loop normal biasa digunakan untuk mengakses array. contoh penggunaan: 
        ```
        let hewan = ["kucing", "Anjing", "Kelinci"];

        for (let i = 0; i < hewan.length; i++) {
          console.log(hewan[i]);
        }
        ```
    - Variable of variables. Contoh penggunaan:
        ```
        let hewans = ["kucing", "Anjing", "Kelinci"];

        for (let hewan of hewans) {
          console.log(hewan);
        }
        ```
    - forEach merupakan sebuah method yang mengembalikan callback berupa function yang berisi setiap element yang dimiliki oleh sebuah array. Contoh penggunaan:
        ```
        let hewan = ["kucing", "Anjing", "Kelinci"];

        hewan.forEach((item) => {
          console.log(item);
        });
        ```
    - map merupakan sebuah method yang berguna untuk membuat array baru dengan menjalankan function untuk tiap element dari sebuah array tanpa mengubah array aslinya. Method ini tidak akan berjalan jika sebuah array element tidak memiliki value. Contoh penggunaan:
        ```
        let hewans = ["kucing", "Anjing", "Kelinci"];

        let hewan = hewans.map((item) => {
          return "aku memiliki" + item;
        });
        console.log(hewan);
        ```
        Contoh implementasi dari method map() dan forEach() dalam sebuah kasus adalah sebagai berikut: 
    - map()
        ```
        let mToCm = [1.2, 3.8, 6.2, 8.7];

        let hasilCm = mToCm.map((x) => {
          return x * 100 + " cm";
        });

        console.log(hasilCm);
        ```
    - forEach()
        ```
        let mToCm = [1.2, 3.8, 6.2, 8.7];
        let hasilCm = [];

        mToCm.forEach((x) => {
          hasilCm.push(x * 100 + " cm");
        });

        console.log(hasilCm);
        ```
### Multi-Dimensional Array
- Multi-dimensional array merupakan tipe data dimana sebuah array memiliki isi data berupa kumpulan dari 1 atau lebih array. Contoh penggunaan: 
    ```
    let multi = [
      ["nim", 4612420002],
      ["jurusan", "ilmu komputer"],
      ["prodi", "sistem informasi"],
      ["organisasi", "HIMA"],
    ];

    console.log(multi[0][1]); //output: 4612420002
    ```
## Mengenal Object Lebih Lanjut
- object merupakan sebuah variabel yang menyimpan nilai (properti) dan sebuah fungsi (method). Contoh deklarasi:
    ```
    let namaObject={
      properties1: value1,
      properties2: value2,
      ...,
      propertiesN: valueN
    };
    ```
- Mari kita membahas lebih jauh mengenai object
    - Membuat object, contoh penggunaan:
        ```
        let gajah = {
          nama: "boni",
          belalai: 1,
          telinga: 2,
          kaki: 4,
        };
        ```
        Sedangkan, untuk mengakses isi objek dibagi menjadi 2 cara: 
        - Dot notation yaitu cara mengakses object dengan menuliskan titik pada penulisan nama object dan propertynya. Contoh penggunaan: 
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };

            console.log(gajah.nama); // output: Boni
            ```
        - Bracket yaitu cara mengakses object dengan cara menuliskan properties yang ingin kita akses ke dalam sebuah bracket. Contoh penggunaan: 
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };

            console.log(gajah["nama"]); // output: Boni
            ```
        - Kita juga bisa memanggil nama objek menggunakan variable, kita bisa melakukannya dengan mendeklarasikan sebuah properties ke dalam sebuah variable terlebih dahulu sebelum akhirnya digunakan untuk mengakses object. Contoh penggunaan: 
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            let name = "nama";
            console.log(gajah[name]); // output: Boni
            ```
    - Menambahkan key/properties pada object
    Menambahkan key/properties pada object dapat dilakukan dengan 2 cara yaitu sebagai berikut: 
        - Dot notation cara menambahkan key/properties object dengan menuliskan titik pada penulisan nama object dan property barunya. Contoh penggunaan: 
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            
            gajah.ekor = 1;
            console.log(gajah);
            // // output:let gajah = {
            //   nama: "Boni",
            //   belalai: 1,
            //   telinga: 2,
            //   kaki: 4,
            //   ekor: 1
            // };
            ```
        - Bracket cara menambahkan key/properties object dengan cara menuliskan properties baru beserta value yang ingin kita tambahkan ke dalam sebuah bracket. Contoh penggunaan: 
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            
            gajah["ekor"] = 1;
            console.log(gajah);
            // // output:let gajah = {
            //   nama: "Boni",
            //   belalai: 1,
            //   telinga: 2,
            //   kaki: 4,
            //   ekor: 1
            // };
            ```
    - Mengganti properties dari sebuah object, kita juga bisa menggunakan 2 cara : 
        - Dot notation
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            
            gajah.nama = "Dona";
            console.log(gajah);
            //output: 
            // gajah = {
            //   nama: "Dona",
            //   belalai: 1,
            //   telinga: 2,
            //   kaki: 4,
            // };
            ```
        - Bracket
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            
            gajah["nama"] = "Dona";
            console.log(gajah);
            //output:
            // gajah = {
            //   nama: "Dona",
            //   belalai: 1,
            //   telinga: 2,
            //   kaki: 4,
            // };
            ```
    - Mengganti properties dari sebuah object, kita juga bisa menggunakan 2 cara : 
        - Dot notation
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            
            gajah.nama = "Dona";
            console.log(gajah);
            //output: 
            // gajah = {
            //   nama: "Dona",
            //   belalai: 1,
            //   telinga: 2,
            //   kaki: 4,
            // };
            ```
        - Bracket
            ```
            let gajah = {
              nama: "Boni",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            
            gajah["nama"] = "Dona";
            console.log(gajah);
            //output:
            // gajah = {
            //   nama: "Dona",
            //   belalai: 1,
            //   telinga: 2,
            //   kaki: 4,
            // };
            ```
    - Object yang memiliki method, method yang dimaksud di sini adalah ketika kita menambahkan property berupa function ke dalam sebuah object. Contoh penggunaan:
        ```
        let salam = {
          datang: function () {
            return "assalamu'alaikum";
          },
          jawab: function () {
            return "waalaikumsalam";
          },
        };
        console.log(salam.datang());
        // output: "assalamu'alaikum"
        ```
        Selain menambahkan method, JavaScript juga sudah menyediakan beberapa method bawaan. Contohnya object.keys() dan object.values(). 
        - object.keys()
            ```
              nama: "Dona",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            
            console.log(Object.keys(gajah));
            //output: ["nama","belalai","telinga","kaki"]
            ```
        - object.values()
            ```
            gajah = {
              nama: "Dona",
              belalai: 1,
              telinga: 2,
              kaki: 4,
            };
            
            console.log(Object.values(gajah));
            //output: ["Dona", 1, 2, 4]
            ```
    - Object bersarang atau yang kerap disebut dengan nested object adalah sebuah object yang memiliki property berupa object dan bisa juga memiliki property selain object. Contoh penggunaan: 
        ```
        let namaObject1 = {
          property1: "value 1",
          property2: "value 2",
          namaObject2: {
            property1_1: "value 1.1",
            property1_2: "value 1.2",
          },
        };
        
        console.log(namaObject1.namaObject2.property1_1);
        // output: "value1.1"
        ```
    - Implementasi perulangan pada object digunakan untuk mengakses isi dari sebuah object agar kita tidak perlu menuliskan perintah yang sama secara berulang-ulang. Contoh penggunaan: 
        ```
        let namaObject1 = {
          property1: "value 1",
          property2: "value 2",
          property3: "value 3",
          property4: "value 4",
        };
        
        for (let x in namaObject1) {
          console.log(namaObject1[x]);
        }
        // output: "value 1"
        // output: "value 2"
        // output: "value 3"
        // output: "value 4"
        ```
    - Array berisi object merupakan sebuah array yang isi datanya berupa deret object
        ```
        let array = [
          {
            property1_1: "value 1.1",
            property1_2: "value 1.2",
            property1_3: "value 1.3",
            property1_4: "value 1.4",
          },
        
          {
            property2_1: "value 2.1",
            property2_2: "value 2.2",
            property2_3: "value 2.3",
            property2_4: "value 2.4",
          },
          {
            property3_1: "value 3.1",
            property3_2: "value 3.2",
            property3_3: "value 3.3",
            property3_4: "value 3.4",
          },
        ];
        
        let x = array.map((element) => {
          return element;
        });
        
        console.log(x[0].property1_1);
        // output: "value 1.1"
        ```

## Module JavaScript dan Rekursif
### Module JavaScript
- Module merupakan cara yang disediakan oleh JavaScript agar kita dapat menaruh kode-kode yang kita miliki dalam file yang berbeda sehingga kita bisa lebih mudah untuk memaintainnya. Untuk menggunakan module kita menggunakan statement import dan export kemudian nantinya file-file yang di export dihubungkan ke file utama. 
- Import merupakan statement yang berfungsi untuk memasukkan data dari luar ke dalam sebuah file. Dalam JavaScript module kita bisa melakukan import dengan 2 cara yaitu import named export dan import default export. Saat melakukan import kita juga bisa melakukan alias untuk mengganti nama variablenya. Berikut contoh penggunaannya: 
    - Import merupakan metode memasukkan data named export yang sifatnya sekunder. Contoh penggunaan: 
        ```
        import {variable} from "./namaFile.js";
        ```
    - Import default export merupakan metode memasukkan data default export yang sifatnya primer. Contoh penggunaan:
        ```
        import variable from "./namaFile.js";
        ```
- Export merupakan statement yang berfungsi untuk mengeluarkan data dari dalam ke luar sebuah file. Dalam JavaScript module kita bisa melakukan export dengan 2 cara yaitu export dan default export.  Kita bisa melakukan export pada variable function, object dan lain-lain. Saat melakukan import kita juga bisa melakukan alias untuk mengganti nama variablenya. Berikut contoh penggunaannya: 
    - Named export merupakan metode mengeluarkan data named export yang sifatnya sekunder. Cara mendeklarasikannya terdapat 2 cara yaitu In-line individually dan All at once at the bottom seperti berikut:  
        - In-line individually
            ```
            export let variable = [“array”];
            export let variable1 = [“array”];
            ```
        - All at once at the bottom
            ```
            let variable = [“array”];
            let variable1 = [“array”]";

            export { variable, variable1 };
            ```
    - Default export merupakan metode mengeluarkan data default yang sifatnya primer. Kita hanya bisa memiliki 1 default export dalam 1 file. Cara penggunaan: 
        ```
        let variable = ["array"];

        export default variable;
        ```
        
### Rekursif
- Rekursif merupakan sebuah function yang memanggil dirinya sendiri hingga kondisi tertentu. Rekursif digunakan untuk menyelesaikan sebuah permasalahan dengan memecahnya hingga permasalahan yang paling kecil. Rekursif menerima 2 input yaitu base case dan recursive case. 
- Base case merupakan titik terkecil yang menjadi penanda berhentinya sebuah rekursif
- Recursive case merupakan perulangan function memanggil dirinya sendiri hingga kondisi tertentu
- Contoh penggunaan rekursif adalah sebagai berikut:
    ```
    function namaFungsi(x) {
          //base case
          if (x == 1) {
            console.log("base case");
          } else {
            //recursive case
            namaFungsi(x - 1);
            console.log("recursive case");
          }
        }
        // cara memanggil rekursif
        namaFungsi(x)
    ```
- Contoh perbandingan jika menggunakan perulangan for
    ```
    function namaFunction(x) {
          let variable = 1;
          for (let i = n; i >= 1; i--) {
            variable = variable * i;
            console.log(i);
          }
          return variable;
        }
        console.log(namaFunction(x));
    ```

## Asyncronous dan Promises Callback
### Asyncronous
- JavaScript merupakan sebuah bahasa pemrograman yang single-thread, non-blocking, dan asyncronous. Mari kita bahas karakteristik dari bahasa pemrograman JavaScript: 
    - Single-thread
    Bahasa pemrograman JavaScript merupakan bahasa pemrograman yang hanya mempunyai 1 jalur antrian di dalam pemrosesan datanya
    - Non-blocking
    Bahasa pemrograman JavaScript tidak melakukan block atau tindakan pencegahan terhadap suatu proses yang hanya memerlukan sedikit waktu pemrosesan. Jika ada suatu proses yang hanya membutuhkan sedikit pemrosesan maka akan dipersilahkan untuk diproses terlebih dahulu dibandingkan dengan suatu proses yang membutuhkan waktu yang lama
    - asyncronous
    Bahasa pemrograman JavaScript bisa memanggil urutan perintah secara acak, hal ini berlaku karena konsep asyncronous adalah memanggil sebuah proses yang belum selesai untuk diproses terlebih dahulu.
    Di dalam konsep asyncronous kita juga mengenal callback. Callback merupakan sebuah function yang dijadikan sebagai sebuah argumen.

### Promises Callback
- Promises merupakan sebuah object yang berisi producing code yang pemanggilan dari kode yang telah dibuat itu sendiri. Contoh pengunaan: 
    ```
    let promises = new Promise((resolve, reject) => {
      resolve("kondisi sukses");
      //or //reject("kondisi gagal");
    });
    
    promises
      .then((result) => {
        console.log(result);
      })
      .catch((err) => {
        console.log(err);
      });

    ```
- Selain membuat promises seperti cara di atas. Kita juga bisa membuat promises di dalam sebuah function sehingga nanti semua eksekusi proses berada di dalam function tersebut. Contoh penggunaan: 
    ```
    let namaFunction = (kondisi) => {
      return new Promise((resolve, reject) => {
        if (kondisi == "benar") {
          resolve("kondisi sukses");
        }
        reject("kondisi gagal");
      });
    };
    
    namaFunction("benar")
      .then((result) => {
        console.log(result);
      })
      .catch((err) => {
        console.log(err);
      });
    ```
## Web Storage
- Web storage merupakan salah satu web API yang dapat menyimpan data pengguna secara lokal pada sisi client. Data yang nantinya di simpan oleh Web Storage akan bertahan lebih lama karena data tersebut di simpan pada storage yang ada pada browser. Dengan menggunakan Web Storage kita bisa menyimpan data sebesar 5MB di tiap pagenya. Di dalam Web Storage terdapat 2 jenis storage yaitu: 
    - Local Storage 
        - Local Storage merupakan tempat pada browser yang digunakan untuk menyimpan data sebesar 5MB. Data yang kita simpan pada local storage tidak terpaut pada tanggal kadaluarsa dan juga tidak akan terhapus jika browser ditutup, data tersebut akan selamanya tersedia jika tidak dihapus. Sebagai catatan local storage hanya dapat menyimpan data string. Untuk menyimpan data kita bisa menggunakan method setItem() dan harus memasukkan 2 parameter berupa key dan value. Contoh penggunaan: 
            ```
            localStorage.setItem("key", value);
            ```
        - setelah menyimpan data, kita bisa mengambil data yang kita punya dengan method getItem() dengan argumen berupa key yang telah kita masukkan sebelumnya. contoh penggunaan: 
            ```
            localStorage.getItem("key");
            ```
        - Sedangkan untuk menghapus key di dalam Local Storage kita bisa menggunakan method removeItem() untuk menghapus item tertentu dan method clear() untuk menghapus semua key. Contoh penggunaan: 
            ```
            localStorage.removeItem("key")
            ```
            
            ```
            localStorage.clear()
            ```
    - Session Storage
        - Session storage merupakan tempat pada browser yang digunakan untuk menyimpan data sebesar 5MB. Data yang kita simpan pada session storage akan hilang ketika session dari sebuah page browser berakhir(ketika menutup tab/window). Jika kita membuka banyak tab dengan URL yang sama maka akan ada session storage yang berbeda pada masing-masing tab/window. Data yang kita simpan menggunakan Session Storage juga harus berbentuk string. 
        - Pada Session storage kita juga bisa melakukan penyimpanan, pengambilan, dan menghapus data. Perintah yang digunakan sama seperti yang digunakan pada Local Storage bedanya kita harus memanggil perintah Session Storage terlebih dahulu. Contoh penggunaan: 
        - Untuk menyimpan data kita bisa menggunakan method setItem() dan harus memasukkan 2 parameter berupa key dan value. Contoh penggunaan: 
            ```
            sessionStorage.setItem("key", value);
            ```
        - Setelah menyimpan data, kita bisa mengambil data yang kita punya dengan method getItem() dengan argumen berupa key yang telah kita masukkan sebelumnya. contoh penggunaan: 
            ```
            sessionStorage.getItem("key");
            ```
        - sedangkan untuk menghapus key di dalam Session Storage kita bisa menggunakan method removeItem() untuk menghapus item tertentu dan method clear() untuk menghapus semua key. Contoh penggunaan: 
            ```
            sessionStorage.removeItem("key")
            ```
            
            ```
            sessionStorage.clear()
            ```

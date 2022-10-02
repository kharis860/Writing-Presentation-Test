# Writing & Presentation Test Week 2



## Function and Scope JavaScript

### Function
- Function merupakan sekumpulan blok kode dalam sebuah group untuk menyelesaikan suatu tugas tertentu. Function bisa dibuat menggunakan 3 cara yaitu:

  - Function classic/literal
    ```
    // function classic/literal
    function namaFunction(parameter) {
    return "ini function classic";
    }
    ```
  - Function variable
    ```
    // function variable
    let namaFunction = function (parameter) {
    return "ini function variabel";
    };
    ```
  - Arrow function
    ```
    // arrow function
    let namaFunction = (parameter) => {
    return "ini menggunakan arrow function";
    };
    ```
- Function dapat dideklarasikan menggunakan return maupun tidak. Tetapi untuk best practicenya biasa digunakan return untuk mengembalikan isi dari sebuah function
    ```
    // contoh function menggunakan return
    function waktu(time = "malam") {
      console.log("Selamat makan" + time);
    }
    
    // contoh function tidak menggunakan return
    function waktu(time) {
      return "Selamat makan" + time;
    }
    
    console.log(waktu(" malam")); //memanggil function
    ```
- Contoh implementasi function dalam sebuah program sederhana
    ```
    // function yang melakukan cek pada sebuah angka
    // jika angka lebih besar dari 50 maka return true
    // jika lebih kecil maka return sebaliknya
    
    function check(number) {
    if (number > 50) {
        return true;
      } else if (number < 50) {
        return false;
      }
    }

    console.log(check(51)); //true
    ```

### Scope 

>berbicara soal function, ada 2 scope yang harus dibahas

- Scope dapat dikatakan sebagai sebuah konsep flow data variable yang dapat menentukan suatu variable bisa diakses pada scope tertentu atau tidak
- scope merupakan konsep pembatas yang ada di dalam JavaScript untuk membatasi pengaksesan suatu variabel. Sejauh ini, scope yang perlu kita bahas ada 2:
    - Global scope variable yaitu variabel yang di deklarasikan di luar block sehingga dapat diakses secara menyeluruh atau dapat diakses dimanapun dalam suatu file. Agar menjadi sebuah Global Scope Variable maka variablenya harus di deklarasikan di luar block
        ```
        // contoh global scope
        let hargaPokok = 5000;
        let hargaJual = 7000;
        let bersih;
        
        //function untuk menghitung keuntungan
        function untung() {
          bersih = hargaJual - hargaPokok;
          return "keuntungan yang di dapat adalah " + bersih;
        }

        console.log(untung());
        ```
    - Local scope variable yaitu variabel yang di deklarasika di dalam sebuah block seperti function, conditional dan looping  sehingga variable tersebut hanya dapat diakses di dalam sebuah blok tersebut saja.
        ```
        // contoh local scope
        function untung() {
          let hargaPokok = 5000;
          let hargaJual = 7000;
          let bersih;
          bersih = hargaJual - hargaPokok;
          return "keuntungan yang di dapat adalah " + bersih;
        }

        console.log(untung());
        console.log(hargaPokok);
        ```
- Block adalah kode yang terletak di dalam sebuah curly braces {} atau kurung kurawal

## Data Type Built-in and Method JavaScript

### JavaScript adalah Bahasa Pemrograman Dynamic dan Weak Typing
- Bahasa pemrograman JavaScript merupakan bahasa pemrograman yang dynamic dan mempunyai kesulitak penulisan yang rendah. Disebut dynamic typing karena di dalam ia memiliki cara penulisan sintaks yang cukup dinamis dibandingkan dengan bahasa pemrograman lainnya. Sebagai contoh ketika sedang mendeklarasikan sebuah variabel dan fungsi tidak memerlukan tipe data, sehingga isi dari variable tersebut otomatis menyesuaikan tipe data yang tepat tanpa harus dituliskan terlebih dahulu.
### Properties dan Method JavaScript
#### properties
- Di dalam javascript kita mengenal properties dan method
- Properties merupakan sebuah nilai yang berkaitan dengan objek pada JavaScript
- Javascript memiliki 1 properties bawaan untuk tipe data string yaitu String.length. properties ini biasanya digunakan untuk mengembalikan nilai panjang karakter dari sebuah string. Contoh penggunaannya adalah sebagai berikut:
    ```
    let nama = "Kharis";
    console.log(nama.length); //6
    ```
#### Method
- Method adalah tindakan yang dapat diberlakukan pada sebuah objek. Pada javascript sudah terdapat beberapa method bawaan yang dapat digunakan kepada masing-masing tipe data. Selain method bawaan, di dalam JavaScript kita juga bisa menambahkan method kita sendiri dengan adanya prototype. Berikut adalah beberapa method bawaan yang telah disediakan oleh JavaScript. Kita mulai dari method yang disediakan untuk string terlebih dahulu:
    - toUpperCase()
    Method ini berfungsi untuk mengubah semua string asal menjadi huruf kapital. Contoh penggunaannya adalah sebagai berikut: 
        ```
        let dummy = "hari ini adalah hari sabtu";
        console.log(dummy.toUpperCase());
        // output: HARI INI ADALAH HARI SABTU
        ```
    - toLowerCase()
    Method ini berfungsi untuk mengubah semua huruf pada string asal menjadi huruf kecil/non-kapital. Contoh penggunaan:
        ```
        let dummy = "DARI MANA DUITNYA???";
        console.log(dummy.toLowerCase());
        // output: dari mana duitnya???
        ```
    - charAt()
    Method ini digunakan untuk mendapatkan nilai index pada charackter di sebuah kalimat yang terdapat pada variabel JavaScript. Contoh penggunaan:
        ```
        let dummy = "hari ini adalah hari sabtu";
        console.log(dummy.charAt(0));
        // output: h
        ```
    - includes()
    Method ini digunakan untuk mencari apakah terdapat suatu substring di dalam sebuah variabel string, method ini nantinya akan mengembalikan return boolean. Yang perlu jadi catatan adalah method ini bersifat case sensitive, jadi masukkan Contoh penggunaan: 
        ```
        let dummy = "hari ini adalah hari sabtu";
        console.log(dummy.includes("z"));
        // output: false
        // case sensitive
        console.log(dummy.includes("H"));
        ```
    - split()
    Method ini dugunakan untuk memisahkan huruf-huruf/string yang ada di dalam sebuah variabel menjadi sebuah array. Method ini memerlukan 2 argumen, yaitu pembatas tiam string dan jumlah array yang diinginkan (opsional). Contoh penggunaan:
        ```
        let buah = "apel, jeruk, durian, mangga";
        console.log(buah.split(",", 2));
        // output: Array [ "apel", " jeruk" ]
        ```
- Contoh Properties JavaScript yang disediakan untuk tipe data number adalah NaN. Properties NaN berfungsi untuk memeriksa apakah sebuah data berupa number. Properties ini mempunyai return berupa boolean. Contoh penggunaan:
    ```
    let dummy = "tes";
    console.log(isNaN(dummy));
    // output: true
    ```
- Setelah string, kita menuju ke method bawaan yang disediakan JavaScript untuk tipe data number. Beberapa methodnya adalah sebagai berikut: 
    - toString()
    Method ini berfungsi untuk mengubah suatu data menjadi sebuah string yang merepresentasikan sebuah objek. Contoh penggunaan: 
        ```
        let mobil = {
          roda: 4,
          jendela: 5,
        };
        console.log(mobil.roda.toString());
        // output: 4
        ```
    - toFixed()
    Method ini digunakan untuk mengubah data tipe number (desimal) menjadi string dan membulatkannya sesuai jumlah desimal yang diinginkan pada argumen yang diinputkan. Contoh penggunaan:
        ```
        let desimal = 4.564765;
        console.log(desimal.toFixed(2));
        // output: 4.56
        ```
- JavaScript juga menyediakan properties dan method untuk math terkait fungsi-fungsi yang biasanya digunakan di dalam kehidupan sehari-hari. Beberapa properties dan method tersebut adalah sebagai berikut:
    ##### Properties
    - Math.PI
    - Math.SQRT2
    - Math.LOG10E

    ##### Method
    - Math.sin()
    - Math.cos()
    - Math.tan()
    - Math.max()
    - Math.min()
    - Math.pow()
    - Math.random()

## DOM Intro & Traversing
### DOM Intro
- DOM merupakan jembatan supaya bahasa pemrograman dapat berinteraksi dengan dokumen HTML baik itu dari segi struktur, tampilan dan kontennya. Sebagai contoh dengan DOM bahasa pemrograman JavaScript dapat memanipulasi HTML. di dalam HTML terdapat element dan node, berikut perbedaannya:
    - Elemen HTML merupakan sebuah komponen yang menyusun dokumen HTML
    - Node merupakan bagian terkecil atau bisa juga diartikan isi dari sebuah elemen HTML. Contohnya isi dari H1 ataupun sebuah attribute dari tag HTML

### Traversing
- Traversing yaitu proses pencarian sebuah element HTML berdasarkan hubungan yang miliki oleh seuah elemen dengan elemen lainnya. Traversing secara garis besar dibedakan menjadi 3 kategori sebagai berikut: 
    - Ke bawah
        - getElementByID
        Method ini digunakan untuk mengembalikan value dari sebuah elemen dengan ID tertentu. Jika elemen tidak ada maka akan mengembalikan nilai null. Contoh penggunaan: 
            ```
            document.getElementById("namaId")
            ```
        - getElementsByClassName
        Method ini digunakan untuk mengembalikan value dari sebuah elemen dengan nama class tertentu. Method ini mempunyai return sebuah HTMLCollection. Contoh penggunaan: 
            ```
            document.getElementsByClassName("namaClass")
            ```
        - getElementsByTagName
        Method ini digunakan untuk mengembalikan value dari sebuah elemen dengan tag tertentu. Method ini mempunyai return sebuah HTMLCollection. Contoh penggunaan:
            ```
            document.getElementsByTagName(h1);
            ```
        - querySelector
        Method ini digunakan untuk mengembalikan element pertama di dalam dokumen yang cocok dengan selector yang dipanggil atau di dalam sekelompok selector. Jika tidak ada element yang cocok maka method ini akan mengembalikan value null. Contoh penggunaan: 
            ```
            document.querySelector("namaSelector")
            ```
        - querySelectorAll
        Method ini digunakan untuk mengembalikan semua element yang cocok dengan selector yang diinputkan. Method ini memiliki return berupaModelist. Jika selector invalid maka akan menampilkan SYNTAX_ERR. Contoh penggunaan: 
            ```
            document.querySelectorAll(p);
            ```
        - Children
        Method ini digunakan untuk mengembalikan sebuah collection dari elemnt child dari sebuah element. Return yang nantinya ditampilkan method ini adalah HTMLCollection object. Contoh penggunaan: 
            ```
            document.getElementById("namaId").children;
            ```
    - Ke atas
        - parentElement
        Properties ini digunakan untuk mengambil return berupa parent dari sebuah element yang diinputkan. Jika parent element yang dimaksud tidak tersedia maka akan mengembalikan return berupa null. Contoh penggunaan: 
            ```
            document.getElementById("namaId").parentElement;
            ```
        - closest()
        method ini digunakan untuk mencari element terdekat menurut susunan DOM tree yang sesuai dengan selector yang diinputkan. Pencarian dimulai dari element yang dipilih lalu menuju ke parent, grandparent dan seterusnya sampai hasilnya cocok. Jika tidak ada element terdekat method ini akan memiliki return null(). Contoh penggunan: 
            ```
            let element= document.getElementById("namaId")

            console.log(element.closest("targetSelector"))
            ```
    - Ke samping
        - nextElementSibling
        Property ini digunakan untuk mengembalikan element selanjutnya pada level DOM tree yang sama. Contoh penggunaan: 
            ```
            let next = document.getElementById("div1").nextElementSibling;

            console.log(next);
            // targetnya adalah div2
            ```
        - previousElementSibling
        Property ini digunakan untuk mengembalikan element sebelumnya pada level DOM tree yang sama. Contoh penggunaan: 
            ```
            let previous = document.getElementById("div2").previousElementSibling;

            console.log(next);
            // targetnya adalah div1
            ```




## DOM Manipulation
- Setelah kita dapat mengakses element HTML melalui DOM, selanjutnya kita bisa memanipulasi atau memberi perubahan pada elemen HTML yang kita miliki. Beberapa hal dasar yang dapat dilakukan dengan DOM manipulation antara lain: 
    - Memberikan konten.
    Pada DOM manipulation kita bisa memberikan konten ke dalam HTML menggunakan property innerText. Properti ini berfungsi untuk menambahkan konten berupa teks pada sebuah elemen HTML. Contoh penggunaan: 
        ```
        let source = document.getElementById("namaId");

        source.innerText = "Teks yang ingin dimasukkan";
        ```
    - Membuat element
    Pada DOM manipulation kita bisa menyisipkan sebuah element HTML baru ke dalam dokumen HTML menggunakan property innetHTML. Property ini digunakan untuk menambahkan element HTML (inner HTML) ke dalam sebuah document HTML. Contoh penggunaan: 
        ```
        let source = document.getElementById("namaId");

        source.innerHTML = "element HTML yang ingin dimasukkan";
        // contoh 
        source.innerHTML= "<h1>Saya ingin menambahkan elemen H1</h1>"
        ```
    - Menghapus element
    Menggunakan DOM manipulation kita juga dapat menghapus sebuah element HTML. Kita bisa menggunakan method remove() yang dapat berfungsi untuk menghapus element HTML. Contoh penggunaan: 
        ```
        let source = document.getElementById("namaId");

        source.remove();
        ```
    - Memambahkan attribute
    Untuk menambahkan attribute kita dapat menggunakan method setAttribute(). Method ini berfungsi untuk menambahkan sebuah value baru ke dalam sebuah attribute. 
        ```
        let input = document.getElementById("classInput");

        input.setAttribute("name", "pekerjaan");
        ```
    - Menambahkan dan menghapus style
    Kita bisa menambahkan style pada element HTML menggunakan perintah style. Contoh penggunaan: 
        ```
        let image= document.getElementById("idImage")

        image.style.width= "200px"
        ```
    - sedangkan untuk menghapus sebuah style property, kita bisa menggunakan method removeProperty. Method ini berfungsi untuk menghapus sebuah property dari sebuah css style yang telah di deklarasikan. Contoh penggunaan:
        ```
        let btn = document.getElementById("btn1");

        btn.style.removeProperty("background-color");
        ```
    - Menambahkan dan menghapus class
    kita bisa menambahkan sebuah class pada sebuah element HTML menggunakan property classlist. Property tersebut berfungsi untuk mengembalikan DOMTokenList collection pada class attribute sebuah element pada HTML, jadi dengan property tersebut kita bisa memanipulasi sebuah class. Contoh penggunaan:
        ```
        let dummy = document.getElementsByTagName(h1);

        dummy.clastlist.add("paragraf");
        ```
    - sedangkan, untuk menghapus class, kita bisa menggunakan classlist.remove(). Contoh penggunaan: 
        ```
        let dummy = document.getElementsByTagName(h1);

        dummy.classlist.add("paragraf");
        //penggunaan classlist.remove
        dummy.classList.remove("paragraf");
        ```

## DOM Event
- Agar event dapat terjadi, kita harus menambahkannya ke dalam HTML. Di dalam JavaScript terdapat 3 cara untuk menambahkan event yaitu: 
    - HTML attribute
        ```
        <button onclick="alert('kalkulasi Anda berhasil')">calculate</button>
        ```
    - Event property
        ```
        let btn = document.getElementById("btn1");
        btn.onclick = function () {
          alert("input berhasil");
        };

        ```
    - addEventListener()
        ```
        let btn = document.getElementById("btn1");

        btn.addEventListener("click", evt);

        function evt() {
          alert("input berhasil");
        }
        ```
- DOM event merupakan kejadian/kegiatan/interaksi yang terjadi pada website yang bisa terjadi karena aksi yang dilakukan oleh user di dalam sebuah browser. Beberapa event yang sering digunakan pada DOM event antara lain: 
    - Click merupakan event dalam JavaScript yang terjadi jika sebuah tombol atau element pada HTML ditekan/diklik. Contoh penggunaan
        ```
        let btn = document.getElementById("btn1");

        btn.addEventListener("click", evt);
        function evt() {
          alert("input berhasil");
        }
        ```
    - Submit merupakan event dalam JavaScript yang biasa digunakan untuk button yang terdapat pada sebuah form. Contoh penggunaan:
        ```
        let btn = document.getElementById("btnSubmit");

        btn.addEventListener("submit", kirim);

        function submit() {
          alert("submit telah berhasil");
        }

        ```    
    - Focus merupakan event pada javascript yang memberikan kesan aktif pada sebuah halaman website, event ini biasanya digunakan pada input, select atau link. Contoh penggunaan:
        ```
        let uname = document.getElementById("uname");

        uname.addEventListener("focus", fokus);

        function fokus() {
          uname.style.background = "red";
        }

        ```
    - Blur merupakan event pada JavaScript yang memberikan kesan tidak aktif (hilang fokus) pada element di sebuah dokumen HTML. Event ini biasa digunakan pada form, event ini aktif setelah user meninggalkan form tersebut. Contoh penggunaan: 
        ```
        let pass = document.getElementById("pass");

        pass.addEventListener("blur", blurr);

        function blurr() {
          pass.style.background = "";
        }
        ```
    - Mouseover merupakan event pada JavaScript yang terjadi ketika pointer mouse bergerak pada sebuah element HTML atau ke salah satu children sebuah element HTML. Contoh penggunaan: 
        ```
        let link = document.getElementById("switchLink");

        link.addEventListener("mouseover", turnRed());

        function turnRed() {
          pass.style.background = "red";
        }
        ```
    - Change merupakan event yang terjadi ketika user memasukkan pilihan dalam opsi yang ada pada select element sehingga tampil pilihan yang mereka pilih. Event ini juga berlaku pada radiobutton dan sceckbox, event akan terjadi ketika user telah memasukkan input mereka. Contoh penggunaan: 
        ```
        let pilih = document.getElementById("mobil").value;
        pilih.addEventListener("change", berubah());

        function berubah() {
        document.getElementById("messageBox").innerText = "anda telah memilih" + pilih;
        }
        ```
    - Scroll merupakan event yang terjadi ketika user melakukan scroll pada sebuah div di dalam sebuah HTML. Contoh penggunaan:
        ```
        let pilih = document.getElementById("mobil").value;
        pilih.addEventListener("change", berubah());

        function berubah() {
          document.getElementById("messageBox").innerText = "anda telah memilih" + pilih;
        }

        ```

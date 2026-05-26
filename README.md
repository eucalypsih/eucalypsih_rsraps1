* [Rust By Practice - Rust By Practice](https://practice.course.rs/)
* [Tour of Rust - Let's go on an adventure!](https://tourofrust.com/)
* [Rust Playground | Interactive Rust Learning Environment | LabEx](https://labex.io/tutorials/rust-online-rust-playground-372918)


Kuasai Konsep Dasar (Java Dasar)
Pahami sintaks fundamental Java sebelum masuk ke tingkat yang lebih rumit:
* **Struktur Kode**: Pahami fungsi kode utama `public static void main(String[] args)` sebagai pintu masuk jalannya program Java.
* **Tipe Data & Variabel**: Pelajari cara menyimpan informasi menggunakan tipe data primitif seperti `int`, `double`, `boolean`, dan tipe data objek seperti `String`.
* **Operator**: Kuasai operator aritmatika, perbandingan, dan logika untuk mengolah data.
* **Percabangan (Control Flow)**: Gunakan fungsi `if`, `else if`, `else`, dan `switch` untuk menentukan arah jalannya program berdasarkan kondisi tertentu.
* **Perulangan (Looping)**: Pelajari struktur `for`, `while`, dan `do-while` untuk mengeksekusi kode berulang kali.

Java merupakan bahasa pemrograman yang berbasis objek (Object-Oriented Programming). Kuasai empat pilar utama OOP berikut
* Enkapsulasi (Encapsulation): Teknik menyembunyikan data sensitif menggunakan akses modifier `private` dan menyediakannya lewat fungsi `getter` dan `setter`.
* Pewarisan (Inheritance): Mewariskan atribut dan metode dari sebuah kelas induk (`parent class`) ke kelas anak (`child class`).
* Polimorfisme (Polymorphism): Kemampuan satu objek untuk memiliki banyak bentuk, yang diimplementasikan melalui metode Runtime Polymorphism (overriding) atau Compile-time Polymorphism (overloading).
* Abstraksi (Abstraction): Menyembunyikan detail implementasi kerangka kode dan hanya menampilkan fungsi penting menggunakan `abstract class` atau `interface`.

Struktur Data dan Fungsi Lanjutan
Setelah memahami OOP, tingkatkan keahlian Anda ke materi tingkat menengah:
* **Java Collections**: Pelajari cara mengelola kumpulan data dinamis menggunakan `List` (seperti `ArrayList`), `Set` (`HashSet`), dan `Map` (`HashMap`).
* **Exception Handling**: Gunakan blok `try-catch` untuk menangani error agar aplikasi Anda tidak langsung *crash* saat menghadapi galat.


Polimorfisme berasal dari bahasa Yunani (Poly = banyak, Morph = bentuk). Dalam pemrograman Java, polimorfisme terjadi ketika beberapa kelas yang berbeda terhubung satu sama lain melalui hubungan pewarisan (Inheritance), tetapi memiliki metode dengan nama yang sama namun perilakunya berbeda.

Method Overloading (Polimorfisme Statis)
Overloading terjadi ketika sebuah kelas memiliki beberapa metode dengan nama yang sama, tetapi parameter (input) yang berbeda. Jenis parameter bisa berbeda jumlahnya atau berbeda tipe datanya. Java menentukan metode mana yang dijalankan saat kode dikompilasi (compile-time).

Contoh Kode Overloading:
```java
class Kalkulator {
    // Metode 1: Menerima dua angka integer
    int tambah(int a, int b) {
        return a + b;
    }

    // Metode 2: Nama sama, tapi menerima tiga angka integer
    int tambah(int a, int b, int c) {
        return a + b + c;
    }

    // Metode 3: Nama sama, tapi tipe datanya double
    double tambah(double a, double b) {
        return a + b;
    }
}

```
> Cara Kerja: Saat Anda memanggil tambah(5, 10), Java otomatis menjalankan Metode 1. Jika Anda memanggil tambah(2.5, 3.5), Java otomatis menjalankan Metode 3.

Method Overriding (Polimorfisme Dinamis)
Overriding terjadi ketika kelas anak (subclass) menulis ulang metode yang sudah ada di kelas induk (superclass). Nama metode, parameter, dan tipe kembaliannya harus sama persis, tetapi isi (perilaku) kodenya diubah sesuai kebutuhan kelas anak. Java menentukan metode mana yang dijalankan saat program berjalan (runtime).

Contoh Kode Overriding:
```java
// Kelas Induk (Superclass)
class Hewan {
    void bersuara() {
        System.out.println("Hewan membuat suara...");
    }
}

// Kelas Anak (Subclass)
class Anjing extends Hewan {
    @Override // Penanda bahwa metode ini menulis ulang metode kelas induk
    void bersuara() {
        System.out.println("Anjing menggonggong: Guk Guk!");
    }
}

class Kucing extends Hewan {
    @Override
    void bersuara() {
        System.out.println("Kucing mengeong: Meong~");
    }
}
```


qa: Mengapa Polimorfisme Sangat Penting?

Polimorfisme memungkinkan Anda membuat kode yang sangat fleksibel. Anda bisa membuat satu variabel atau array dengan tipe kelas induk, tetapi mengisinya dengan berbagai macam objek kelas anak.

Contoh Implementasi Fleksibilitas Polimorfisme:
```java
public class Main {
    public static void main(String[] args) {
        // Membuat objek berwujud Anjing dan Kucing, tetapi bertipe Hewan
        Hewan peliharaan1 = new Anjing();
        Hewan peliharaan2 = new Kucing();

        // Memanggil metode yang sama, menghasilkan output berbeda (Polimorfisme)
        peliharaan1.bersuara(); // Output: Anjing menggonggong: Guk Guk!
        peliharaan2.bersuara(); // Output: Kucing mengeong: Meong~
    }
}
```

Dengan teknik ini, jika di masa depan Anda menambah kelas `class Burung extends Hewan`, Anda tidak perlu merombak total struktur kode utama Anda. Cukup panggil fungsi `.bersuara()` dan perilakunya akan menyesuaikan secara otomatis.




Pewarisan (Inheritance) adalah konsep dalam Java di mana sebuah kelas baru (kelas anak/subclass) dapat mengadopsi atau mengambil semua atribut (variabel) dan metode (fungsi) yang bersifat publik atau dilindungi dari kelas yang sudah ada (kelas induk/superclass).

Dalam bahasa Java, pewarisan ini dihubungkan dengan menggunakan kata kunci `extends`.

qa: Mengapa Kita Butuh Pewarisan?

* Reusabilitas Kode (Code Reusability): Anda tidak perlu menulis ulang kode yang sama pada kelas-kelas yang mirip. Cukup tulis sekali di kelas induk.

* Efisiensi Struktur: Mempermudah pengaturan logika program karena hubungan antar objek menjadi lebih terstruktur dan logis.



Contoh Kasus Nyata: Sistem Karyawan Perusahaan
Bayangkan Anda sedang membuat sistem untuk mendata karyawan di perusahaan. Ada dua jenis posisi: `Manager` dan `Programmer`. Kedua posisi ini sama-sama memiliki `nama` dan `gaji`, tetapi memiliki tugas tambahan yang berbeda.

Tanpa pewarisan, Anda harus mengetik variabel `nama` dan `gaji` berulang kali di kelas `Manager` dan kelas `Programmer`. Dengan pewarisan, kita buat satu kelas induk bernama Karyawan.



1. Membuat Kelas Induk (Superclass)
```java
class Karyawan {
    String nama;
    double gaji;

    void tampilkanInformasi() {
        System.out.println("Nama: " + nama);
        System.out.println("Gaji: Rp" + gaji);
    }
}
```

2. Membuat Kelas Anak (Subclass) Menggunakan `extends`
Sekarang, kelas `Manager` dan `Programmer` cukup mewarisi kelas Karyawan dan hanya perlu menambahkan atribut khusus mereka sendiri.
```java
// Manager adalah anak dari Karyawan
class Manager extends Karyawan {
    String departemen; // Atribut khusus Manager

    void pimpinRapat() { // Metode khusus Manager
        System.out.println(nama + " sedang memimpin rapat departemen " + departemen);
    }
}

// Programmer adalah anak dari Karyawan
class Programmer extends Karyawan {
    String bahasaPemrograman; // Atribut khusus Programmer

    void tulisKode() { // Metode khusus Programmer
        System.out.println(nama + " sedang menulis kode " + bahasaPemrograman);
    }
}
```


3. Cara Menjalankannya di Kelas Utama (Main)
Perhatikan bahwa objek `Manager` dan `Programmer` bisa langsung mengakses variabel nama, gaji, dan metode `tampilkanInformasi()` meskipun kode tersebut tidak tertulis di dalam kelas mereka secara langsung.
```java
public class Main {
    public static void main(String[] args) {
        // Membuat objek Manager
        Manager bos = new Manager();
        bos.nama = "Budi";         // Warisan dari Karyawan
        bos.gaji = 15000000;       // Warisan dari Karyawan
        bos.departemen = "IT";     // Milik Manager sendiri

        // Membuat objek Programmer
        Programmer dev = new Programmer();
        dev.nama = "Andi";                 // Warisan dari Karyawan
        dev.gaji = 8000000;                // Warisan dari Karyawan
        dev.bahasaPemrograman = "Java";    // Milik Programmer sendiri

        // Memanggil metode eksekusi
        bos.tampilkanInformasi(); // Output: Nama dan Gaji Budi
        bos.pimpinRapat();        // Output: Budi sedang memimpin rapat...

        System.out.println("-----------------------");

        dev.tampilkanInformasi(); // Output: Nama dan Gaji Andi
        dev.tulisKode();          // Output: Andi sedang menulis kode...
    }
}

```

Aturan Penting Pewarisan di Java
* Single Inheritance: Di Java, sebuah kelas anak hanya boleh memiliki satu kelas induk langsung. Anda tidak bisa melakukan `class Manager extends Karyawan, Pemimpin`.
* Kata Kunci `super`: Jika kelas anak ingin mengakses metode atau konstruktor asli milik kelas induk yang kebetulan namanya sama, Anda bisa menggunakan kata kunci `super` (misalnya: `super.tampilkanInformasi())`.



Kata kunci `super` di dalam Java adalah variabel referensi khusus yang digunakan untuk merujuk langsung ke objek dari kelas induk (superclass) terdekat.

Ada tiga fungsi utama dari kata kunci super yang sering digunakan dalam pemrograman: untuk mengakses *metode* induk, mengakses *atribut* induk, dan memanggil *konstruktor* induk.


1. Mengakses Metode Induk (Method Overriding)
Ketika kelas anak menulis ulang (override) metode milik kelas induk, metode asli di kelas induk akan "tertutup". Jika Anda ingin tetap menjalankan kode asli milik kelas induk di dalam metode kelas anak, gunakan `super.namaMetode()`.

Contoh Kasus:
```java
class Kendaraan {
    void hidupkanMesin() {
        System.out.println("Mesin kendaraan dinyalakan.");
    }
}

class Mobil extends Kendaraan {
    @Override
    void hidupkanMesin() {
        super.hidupkanMesin(); // Memanggil fungsi asli dari kelas Kendaraan
        System.out.println("Mobil siap melaju kencang!"); // Modifikasi tambahan di kelas anak
    }
}

```

Jika Anda memanggil `mobil.hidupkanMesin()`, outputnya akan memunculkan kedua baris teks di atas secara berurutan.


2. Mengakses Atribut Induk (Name Collision)
`super` juga digunakan jika kelas anak membuat variabel baru dengan nama yang sama persis dengan variabel di kelas induk. `super` akan memastikan Java mengambil nilai dari kelas induk, bukan kelas anak.

Contoh Kasus:
```java
class Orang {
    String warnaRambut = "Hitam";
}

class Anak extends Orang {
    String warnaRambut = "Pirang"; // Menutupi variabel kelas induk

    void cetakWarna() {
        System.out.println("Warna rambut saya: " + warnaRambut);        // Mengambil milik anak (Pirang)
        System.out.println("Warna rambut orang tua: " + super.warnaRambut); // Mengambil milik induk (Hitam)
    }
}

```

3. Memanggil Konstruktor Induk (`super()`)

Konstruktor adalah metode khusus yang otomatis berjalan saat objek pertama kali dibuat (`new`). Jika kelas induk memiliki konstruktor yang membutuhkan parameter (input data), kelas anak wajib memanggil konstruktor induk tersebut di baris paling pertama menggunakan fungsi `super()`

Contoh Kasus:
```java
class Hewan {
    String jenis;

    // Konstruktor kelas induk
    Hewan(String jenis) {
        this.jenis = jenis;
    }
}

class Kucing extends Hewan {
    String nama;

    // Konstruktor kelas anak
    Kucing(String jenis, String nama) {
        super(jenis); // WAJIB ditulis di baris pertama untuk mengisi data ke kelas Hewan
        this.nama = nama;
    }

    void info() {
        System.out.println(nama + " adalah seekor " + jenis);
    }
}

```

Cara Penggunaan di Main:
```java
Kucing k = new Kucing("Mamalia", "Milo");
k.info(); // Output: Milo adalah seekor Mamalia

```




Ringkasan Aturan `super`
* `super` selalu merujuk pada satu tingkat kelas di atasnya (induk langsung).
* Penggunaan `super()` untuk **konstruktor harus diletakkan di baris paling pertama** di dalam konstruktor kelas anak. Jika tidak, Java akan menampilkan pesan eror saat kompilasi.















<br>


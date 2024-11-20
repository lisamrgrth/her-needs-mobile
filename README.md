# TUGAS 7: Elemen Dasar Flutter
### Lisa Margaretha Esron Tobing (2306245541) - PBP B

---

## 1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.

**Stateless Widget** adalah jenis widget yang **tidak memiliki state**. Tampilan yang dihasilkan oleh stateless widget **tidak akan berubah** karena aksi internal. Stateless widget hanya akan berubah jika terdapat perubahan dari parent widget atau melalui **aksi/event eksternal**.
Beberapa contoh dari stateless widget adalah: **Text** dan **Icon**

Di sisi lain, **Stateful Widget** adalah widget yang memiliki **state yang dapat berubah-ubah** selama siklus hidupnya. Widget ini memungkinkan **pembaruan tampilan** berdasarkan interaksi pengguna atau perubahan data.
Contoh dari stateful widget adalah: **Kotak Centang (Checkbox)**: Status kotak centang (tercentang atau tidak) dapat berubah berdasarkan interaksi pengguna.

### Perbedaan Utama

| Stateless Widget                          | Stateful Widget                          |
|-------------------------------------------|------------------------------------------|
| Tidak memiliki state internal yang berubah | Memiliki state internal yang dapat berubah|
| Digunakan untuk elemen statis             | Digunakan untuk elemen dinamis           |
| Tidak berubah tanpa event dari parent     | Berubah sesuai interaksi atau data baru  |


## 2. Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.

1. **MyApp**: 
   - Stateless Widget yang berfungsi sebagai titik masuk aplikasi. Widget ini mengatur MaterialApp yang menjadi dasar aplikasi dan menentukan tema serta widget home (MyHomePage).

2. **MaterialApp**: 
   - Widget ini adalah akar dari aplikasi Flutter, berfungsi untuk menyediakan tema, judul aplikasi, serta pengelolaan rute.

3. **Scaffold**: 
   - Widget ini memberikan struktur dasar untuk halaman aplikasi, mencakup AppBar, body, drawer, dan floating action button, serta menyusun layout aplikasi secara standar.

4. **AppBar**: 
   - Widget ini menampilkan bar atas dengan judul aplikasi "herNeeds".

5. **Padding**: 
   - Widget ini memberikan ruang di sekitar child widget. Dalam proyek ini, digunakan untuk memberi jarak di sekeliling konten dalam body Scaffold.

6. **Column**: 
   - Widget ini menyusun child widget secara vertikal. Dalam proyek ini, digunakan untuk mengatur layout informasi pengguna dan widget lainnya.

7. **Row**: 
   - Widget ini menyusun widget anak secara horizontal. Dalam proyek ini, digunakan untuk menampilkan InfoCard secara berdampingan.

8. **SizedBox**: 
   - Widget ini memberikan ruang kosong di antara widget. Dalam proyek ini, digunakan untuk memberi jarak vertikal antara Row dan elemen lainnya.

9. **Center**: 
   - Widget ini menempatkan child widget di tengah parent. Dalam proyek ini, digunakan untuk menempatkan teks sambutan dan GridView di tengah halaman.

10. **GridView**: 
    - Widget ini menampilkan widget dalam bentuk grid. Dalam proyek ini, digunakan untuk menampilkan ItemCard dalam 3 kolom.

11. **Card**: 
    - Widget ini menampilkan konten dalam bentuk kartu dengan shadow. Dalam proyek ini, digunakan dalam InfoCard untuk memberikan tampilan yang menarik.

12. **Container**: 
    - Merupakan model kotak yang dapat digunakan untuk mengatur ukuran, padding, margin, dan dekorasi. Dalam proyek ini, digunakan dalam InfoCard dan ItemCard.

13. **Text**: 
    - Widget ini menampilkan teks dalam aplikasi. Beberapa widget Text digunakan untuk menampilkan nama, NPM, kelas, dan pesan dalam Snackbar.

14. **Icon**: 
    - Widget ini menampilkan ikon dari paket Material Icons. Dalam proyek ini, digunakan dalam ItemCard untuk menampilkan ikon sesuai dengan atribut item.

15. **InkWell**: 
    - Widget ini memberikan efek sentuhan pada child widget. Dalam proyek ini, digunakan dalam ItemCard untuk menangani interaksi saat kartu ditekan.

16. **SnackBar**: 
    - Widget ini menampilkan pesan sementara di bagian bawah layar. Dalam proyek ini, ditampilkan ketika pengguna menekan ItemCard.

17. **MyHomePage**: 
    - Widget Stateless yang berfungsi sebagai halaman utama aplikasi, menampilkan informasi pengguna dan daftar tombol.

18. **InfoCard**: 
    - Widget Stateless yang menampilkan informasi dalam bentuk kartu dengan judul dan konten. Dalam proyek ini, digunakan untuk menampilkan NPM, nama, dan kelas pengguna.

19. **ItemHomepage**: 
    - Class yang menyimpan atribut untuk tombol, yaitu nama, ikon, dan warna. Digunakan untuk mendefinisikan item yang ditampilkan dalam ItemCard.

20. **ItemCard**: 
    - Widget Stateless yang menampilkan kartu dengan ikon dan nama. Menangani interaksi pengguna dan menampilkan SnackBar saat ditekan.


## 3. Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.

`setState()` dalam `Stateful Widget` berfungsi untuk memberi tahu Flutter bahwa ada perubahan pada *state* yang memerlukan *rebuild* dari UI. Flutter akan menjalankan ulang metode `build` pada widget tersebut dan akan men-update tampilan agar sesuai dengan nilai *state* yang baru.

Variabel yang di-define di kelas *state*, biasanya dengan `this` atau variabel yang sudah didaftarkan di dalam kelas *state* tersebut, adalah variabel-variabel yang terdampak oleh `setState()`. Variabel ini biasanya mencakup variabel interaktif, variabel yang menampung data tampilan, dan status UI lainnya.

Jadi, hanya variabel-variabel yang didefinisikan di dalam kelas *state* yang akan terpengaruh oleh `setState()`. Variabel di luar kelas *state* tidak akan di-update atau tidak berpengaruh langsung terhadap pembaruan tampilan widget yang bersangkutan.


## 4. Jelaskan perbedaan antara const dengan final.

`const` maupun `final` berguna untuk men-declare nilai-nilai yang tidak bisa diubah setelah didefinisikan. Akan tetapi, keduanya memiliki perbedaan:

1. **`final`**: Mendeklarasikan variabel yang hanya dapat diinisialisasi satu kali dan tidak dapat diubah setelah inisialisasi.
   - Nilai dari variabel `final` bisa ditentukan saat *runtime* (tidak harus diketahui saat kompilasi).
   - Cocok digunakan untuk variabel yang tidak berubah setelah diberikan nilai pertama kali, tetapi nilainya mungkin baru diketahui saat aplikasi dijalankan.
   - Contoh: 
     ```dart
     final currentTime = DateTime.now(); // Nilai ditentukan saat runtime
     ```

2. **`const`**: Mendeklarasikan nilai yang bersifat konstan atau tetap, yang harus ditentukan pada saat *kompilasi*.
   - Variabel `const` benar-benar bersifat *compile-time constant*, artinya nilainya harus sudah diketahui sebelum aplikasi dijalankan.
   - Biasanya digunakan untuk nilai konstan yang tidak berubah selamanya dan bisa dihitung di awal, seperti nilai numerik, string tetap, atau daftar yang sudah pasti.
   - Contoh:
     ```dart
     const pi = 3.14159; // Nilai diketahui saat kompilasi
     ```


## 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.

### Membuat sebuah program Flutter baru dengan tema E-Commerce yang sesuai dengan tugas-tugas sebelumnya.

Pertama, saya masuk ke direktori yang digunakan untuk menyimpan proyek Flutter. Lalu, generate proyek Flutter baru melalui terminal dengan nama `her_needs`. Setelah itu, saya melakukan inisialisasi Git di folder root proyek dengan perintah `git init`, kemudian add-commit-push proyek ke repositori baru di GitHub dengan nama `her-needs-mobile`.


### Membuat tiga tombol sederhana dengan ikon dan teks 

Pertama, saya membuat sebuah kelas bernama `ItemHomepage` yang berisi atribut `name` dan `icon` di file `menu.dart`. Selanjutnya, buat list `ItemHomepage` yang berisi tiga tombol yang akan ditambahkan pada kelas `MyHomePage`. Kemudian, saya membuat kelas `ItemCard` untuk menampilkan tombol-tombol tersebut. Tombol yang ditekan nantinya skan menampilkan snackbar dengan pesan "Kamu telah menekan tombol [nama tombol]".

### Mengimplementasikan warna-warna yang berbeda untuk setiap tombol (Lihat Daftar Produk, Tambah Produk, dan Logout).

Pertama-tama, saya menambahkan atribut `color` di class `ItemHomePage` agar setiap tombol memiliki warna berbeda
```dart
class ItemHomepage {
    final String name;
    final IconData icon;
    final Color color;

    ItemHomepage(this.name, this.icon, this.color);
}
```

Lalu, di file `menu.dart`, saya menambahkan 3 instance `ItemHomepage` di dalam list dengan 3 warna berbeda:

```dart
final List<ItemHomepage> items = [
    ItemHomepage("Lihat Daftar Produk", Icons.shopping_cart, const Color(0xFFC7A4FF)),
    ItemHomepage("Tambah Produk", Icons.add, const Color(0xFFA994C8)),
    ItemHomepage("Logout", Icons.logout, const Color(0xFF8E6FBF)),
  ];
```

Lalu, pada class `ItemCard`, saya ubah properti `color` dalam `Material` menjadi `item.color`,hal ini memastikan setiap tombol memiliki warna background sesuai atribut `color` yang sudah didefinisikan di `ItemHomepage`.

```dart
@override
Widget build(BuildContext context) {
  return Material(
    color: item.color,  // Mengatur warna background tombol sesuai dengan warna item
    // Kode lainnya...
  );
}
```

### Menampilkan Snackbar dengan Pesan

Di dalam kelas `ItemCard`, saya menambahkan kode berikut:

```dart
child: InkWell(
  // Aksi ketika kartu ditekan.
  onTap: () {
    // Menampilkan pesan SnackBar saat kartu ditekan.
    ScaffoldMessenger.of(context)
      ..hideCurrentSnackBar()
      ..showSnackBar(
        SnackBar(content: Text("Kamu telah menekan tombol ${item.name}!"))
      );
  },
);
```
Hal ini akan menampilkan pesan Snackbar setiap kali kartu ditekan

# TUGAS 8: Flutter Navigation, Layouts, Forms, and Input Elements

---

## 1. Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?

`const` di Flutter digunakan untuk menandai nilai atau objek sebagai konstan selama runtime, yang berarti nilai atau widget tersebut hanya dibuat sekali dan tidak akan berubah sepanjang eksekusi aplikasi. 

## Keuntungan Menggunakan `const` dalam Flutter

- **Penggunaan Memori yang Lebih Efisien**: Mengurangi overhead memori karena objek yang sama tidak perlu dibuat berulang kali.
- **Peningkatan Performa**: Karena objek tidak dibuat ulang setiap kali UI dirender, proses rendering menjadi lebih cepat.
- **Konsistensi**: `const` memastikan nilai tetap stabil dan tidak dapat diubah, sehingga menghindari perubahan yang tidak diinginkan.

## Waktu Penggunaan `const` 

- **Digunakan untuk Elemen UI atau Data yang Bersifat Tetap**: 
  Misalnya, `Text("Welcome")` atau `Icon(Icons.home)`. Elemen ini tidak akan berubah selama runtime, sehingga penggunaan `const` mengoptimalkan performa dan efisiensi memori.

- **Tidak Digunakan untuk Widget atau Nilai yang Bersifat Dinamis**: 
  Hindari penggunaan `const` pada widget atau nilai yang berubah-ubah atau membutuhkan interaksi, seperti animasi, data pengguna, atau widget yang bergantung pada perubahan state.


## 2. Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!

1. **Column**: Digunakan untuk menyusun child widget secara vertikal, dari atas ke bawah. Biasanya digunakan ketika ingin menyusun elemen dalam bentuk daftar atau list.
   
2. **Row**: Digunakan untuk menyusun child widget secara horizontal, dari kiri ke kanan. Biasanya digunakan ketika ingin menyusun elemen dalam barisan.

## Perbandingan `Column` dan `Row` dalam Flutter

| **Aspek**            | **Column**                           | **Row**                              |
|----------------------|--------------------------------------|--------------------------------------|
| **Sumbu utama**      | Vertikal (dari atas ke bawah)        | Horizontal (dari kiri ke kanan)      |
| **Sumbu silang**     | Horizontal (sepanjang layar)         | Vertikal (sepanjang layar)           |
| **Cocok untuk**      | Menyusun elemen secara vertikal      | Menyusun elemen secara horizontal    |
| **Misal Penggunaan** | Form input, daftar vertikal          | Navbar, tombol-tombol sejajar        |

## Contoh Implementasi

### 1. **menu.dart**
- **Row** digunakan untuk menampilkan tiga `InfoCard` (NPM, Name, dan Class) dalam satu baris di halaman utama (`MyHomePage`).
- Di bagian **body**, **Column** digunakan untuk menata beberapa widget (seperti `Row`, `Text`, dan `GridView`).
- Di dalam widget `InfoCard`, **Column** digunakan untuk menampilkan `title` dan `content` secara vertikal.

### 2. **productentry_form.dart**
- **Column** digunakan untuk menyusun semua form fields (seperti `TextFormField` untuk input nama, harga, deskripsi, dll.) secara vertikal.
- Tombol "Save" disusun dalam **Column** agar posisinya tetap berada di bawah input fields.

### 3. **left_drawer.dart**
- Pada bagian `DrawerHeader`, saya menggunakan **Column** untuk menyusun dua teks secara vertikal, yaitu judul "herNeeds" dan deskripsi "Your one-stop shop for all things chic and stylish".

### 4. **product_card.dart**
- Di dalam widget `ItemCard`, **Column** digunakan untuk menampilkan `Icon` dan `Text` secara vertikal di tengah kartu.


## 3. Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!

## Elemen Input yang Digunakan

1. **TextFormField**: Digunakan untuk menginput data berupa teks. Dalam tugas ini, **TextFormField** digunakan untuk memasukkan informasi produk, seperti:
   - Nama produk (name)
   - Harga (price)
   - Deskripsi (description)
   - Jumlah (amount)
   - Ukuran (size)

Setiap **TextFormField** ini memiliki properti `decoration` untuk menampilkan label dan hint. Selain itu, dilakukan validasi untuk memastikan bahwa data yang diinput memenuhi ketentuan (misalnya, harga harus berupa angka positif, nama produk tidak boleh kosong, dan lain-lain).

2. **ElevatedButton**: Digunakan untuk tombol "Save" yang akan menyimpan data yang diinput oleh pengguna.

## Elemen Input Flutter Lain yang Tidak Digunakan pada Tugas Ini

1. **DatePicker**: Digunakan untuk memilih tanggal.
2. **DropdownButton / DropdownMenu**: Digunakan untuk memilih dari daftar pilihan yang sudah disediakan dalam bentuk dropdown.
3. **Switch**: Digunakan untuk memilih antara dua keadaan (on/off).
4. **Radio / RadioListTile**: Digunakan untuk memilih satu pilihan dari beberapa opsi yang ada.
5. **Checkbox / CheckboxListTile**: Digunakan untuk memilih satu atau lebih pilihan dalam bentuk kotak centang.


## 4. Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?

Ya, saya menerapkan tema dalam aplikasi yang saya buat untuk memastikan konsistensi visual di seluruh aplikasi. Penerapan tema ini juga memudahkan perubahan desain secara global tanpa perlu mengubah warna atau gaya di setiap widget secara manual.

## Cara Mengatur Tema dalam Aplikasi Flutter agar Aplikasi Konsisten

Cara mengatur tema dalam aplikasi Flutter agar aplikasi yang dibuat konsisten:

1. **Menentukan Tema di main.dart**: 
   Pada aplikasi, saya menggunakan `ThemeData` di dalam `MaterialApp` untuk mengatur warna dan gaya tema yang akan digunakan di seluruh aplikasi.
   
2. **Menggunakan Tema di Widget**: 
   Setelah tema didefinisikan, saya menggunakan `Theme.of(context)` untuk mengakses nilai tema yang sudah ditentukan sebelumnya, dan mengaplikasikannya pada widget. 
   
   ```dart
   backgroundColor: Theme.of(context).colorScheme.primary,
   ```


## 5. Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?

Untuk menangani navigasi antar halaman dalam aplikasi dengan banyak halaman, saya menggunakan `Navigator` dan `MaterialPageRoute`. Berikut penjelasannya:

1. **Navigator**:
   `Navigator` adalah widget yang menyediakan cara yang sederhana untuk menambahkan, mengganti, atau menghapus halaman di atas navigation stack.

2. **MaterialPageRoute**:
   `MaterialPageRoute` digunakan untuk membuat transisi halaman dengan gaya material design, yang memberikan pengalaman pengguna yang lebih konsisten.

## Fungsi Navigasi di Flutter

1. **Navigator.push**:  
   Menambahkan (mendorong) halaman baru ke atas tumpukan.

2. **Navigator.pop**:  
   Menghapus (menarik) halaman dari tumpukan untuk kembali ke halaman sebelumnya.

3. **Navigator.pushReplacement**:  
   Mengganti halaman teratas dalam tumpukan dengan halaman baru, tanpa menyimpan halaman sebelumnya.

## Contoh Implementasi Navigasi

1. **Menambah halaman baru di atas halaman saat ini**  
   - Ketika pengguna mengklik tombol "Tambah Produk" pada `LeftDrawer` atau `product_card`, `Navigator.push` akan membawa pengguna ke halaman `ProductEntryFormPage`.

2. **Mengganti halaman saat ini dengan halaman baru**  
   - `Navigator.pushReplacement` digunakan di halaman `LeftDrawer` saat mengarahkan pengguna ke halaman `MyHomePage`.

3. **Kembali ke halaman sebelumnya**  
   - Di halaman `productentry_form.dart`, kita bisa kembali ke halaman sebelumnya menggunakan `Navigator.pop` setelah melakukan suatu aksi atau ketika ingin keluar dari halaman tanpa menyimpan perubahan.


# TUGAS 9: Integrasi Layanan Web Django dengan Aplikasi Flutter

---

## 1. Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?

Kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON karena beberapa alasan berikut:

### 1. Struktur Data yang Terorganisir:
- Model mendefinisikan struktur data yang jelas dan konsisten
- Memudahkan konversi antara JSON dan objek Dart melalui metode fromJson() dan toJson()
- Memastikan format data sesuai dengan yang diharapkan

### 2. Type Safety:
- Memberikan keamanan tipe data saat compiling
- Mendeteksi error yang berpotensial terjadi sebelum aplikasi dijalankan
- Mencegah kesalahan akses properti yang tidak ada
- IDE dapat memberikan peringatan jika ada ketidaksesuaian tipe data

### 3. Kemudahan Akses dan Maintainability:
- Akses data melalui properti yang terdefinisi dengan jelas (seperti product.name daripada jsonData['name'])
- Autocomplete dari IDE membantu development
- Kode lebih mudah dibaca dan dipelihara
- Memudahkan dokumentasi dan kolaborasi tim

Jika kita tidak membuat model terlebih dahulu sebenarnya tidak selalu error, tetapi ada beberapa masalah yang mungkin timbul:

- Runtime errors karena kesalahan tipe data atau properti yang tidak ada
- Kode menjadi lebih sulit dibaca dan dipelihara
- Kehilangan bantuan IDE untuk autocomplete dan type checking
- Data validation harus dilakukan manual dan lebih rawan kesalahan
- Debugging menjadi lebih sulit karena struktur data tidak terdefinisi dengan jelas

Meskipun aplikasi bisa berjalan tanpa model, penggunaan model sangat direkomendasikan untuk memastikan kualitas kode, kemudahan maintenance, dan stabilitas aplikasi dalam jangka panjang.


## 2. Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas ini

Library **`http`** pada Flutter berfungsi sebagai alat utama untuk melakukan komunikasi berbasis protokol HTTP antara aplikasi dan server web. Dengan menggunakan library ini, aplikasi Flutter bisa:  
1. **Mengambil Data dari Server**  
   Library ini memungkinkan pengambilan data dari server, seperti data API, menggunakan permintaan HTTP dengan metode seperti `GET`. Contohnya:  
   ```dart
   final response = await request.get('http://127.0.0.1:8000/json/');
   ```  
   Pada tugas ini, permintaan tersebut digunakan untuk mengambil data produk dari server Django dalam format JSON.  

2. **Mengirim Data ke Server**  
   Library ini juga mendukung pengiriman data ke server menggunakan metode seperti `POST`. Contoh implementasi:  
   ```dart
   final response = await request.postJson(
       "http://127.0.0.1:8000/auth/register/",
       jsonEncode({
         "username": username,
         "password1": password1,
         "password2": password2,
       }));
   ```  
   Dalam tugas ini, permintaan `POST` digunakan untuk mengirim data registrasi pengguna ke server Django, seperti informasi username dan password yang telah di-encode dalam format JSON.

Secara keseluruhan, library **`http`** menjadi jembatan penting dalam tugas ini untuk menghubungkan aplikasi Flutter dengan server Django, mendukung pengelolaan data secara real-time.


## 3. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

### **Fungsi CookieRequest**

**CookieRequest** adalah class khusus yang dirancang untuk mengelola autentikasi dan cookie dalam aplikasi Flutter. Fungsi utamanya meliputi:  

1. **Mengelola Session dan Cookies**  
   Memastikan session pengguna tetap konsisten di seluruh aplikasi dengan menyimpan dan menggunakan cookie yang diterima dari server. Hal ini penting untuk autentikasi pengguna pada backend Django.

2. **Melakukan HTTP Request**  
   CookieRequest mempermudah pengiriman permintaan HTTP (seperti `GET` dan `POST`) ke web service Django dengan menyertakan cookie secara otomatis dalam setiap request yang memerlukannya. 

3. **Menyimpan Informasi Login Pengguna**  
   Menyimpan data login pengguna (seperti status login dan token autentikasi) agar dapat digunakan kembali di seluruh aplikasi tanpa perlu login ulang.

4. **Mengatur State Autentikasi Secara Global**  
   CookieRequest membantu menjaga state autentikasi (misalnya, apakah pengguna sudah login atau belum) agar dapat diakses oleh berbagai komponen aplikasi.  

### **Mengapa Instance CookieRequest Perlu Dibagikan ke Semua Komponen di Aplikasi Flutter**

Instance **CookieRequest** perlu dibagikan ke seluruh komponen dalam aplikasi Flutter karena:  

1. **Konsistensi Data**  
   Membagikan instance yang sama memastikan semua komponen menggunakan data autentikasi dan cookies yang sama, sehingga tidak terjadi inkonsistensi.

2. **Efisiensi Pengelolaan Resource**  
   Dengan menggunakan satu instance untuk seluruh aplikasi, pembuatan instance baru yang berlebihan dapat dihindari, sehingga aplikasi menjadi lebih efisien dalam penggunaan memori.

3. **State Management Terpusat**  
   State autentikasi dapat dikelola secara global. Jika ada perubahan pada state (misalnya, pengguna logout), perubahan tersebut akan langsung tercermin di seluruh komponen yang menggunakan instance tersebut.

4. **Konsistensi Session**  
   Cookies yang dikelola oleh instance **CookieRequest** memastikan bahwa setiap request HTTP yang membutuhkan autentikasi tetap terhubung dengan session pengguna yang aktif.

Pembagian instance ini dilakukan menggunakan Provider, sehingga setiap komponen dapat mengakses instance yang sama dan mempertahankan konsistensi data autentikasi di seluruh aplikasi.


## 4. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.

1. **Input Data di Flutter**  
   - Pengguna memasukkan data melalui form atau input field di aplikasi Flutter. Lalu, Data yang diinputkan kemudian dikirim melalui request HTTP, biasanya menggunakan metode **POST** atau **PUT**, tergantung operasinya.

2. **Pengolahan Data di Backend (Django)**  
   - Data yang dikirim oleh Flutter diterima di backend Django melalui endpoint tertentu. Setelah itu, Django memproses data, misalnya dengan menyimpannya ke database menggunakan model yang telah didefinisikan. Django kemudian dapat mengirimkan respons berupa status operasi atau data yang diperbarui dalam format JSON.  

3. **Mengambil Data di Flutter**  
   - Flutter menggunakan metode **GET** untuk mengambil data dari endpoint Django.  
   - Data JSON yang diterima kemudian di-decode dan dipetakan ke dalam model Dart agar mudah diolah di aplikasi.  

4. **Menampilkan Data di Flutter**  
   - Data yang telah dipetakan ditampilkan di UI menggunakan widget seperti **ListView**, **FutureBuilder**, atau **GridView**.  

### Alur Sederhana  
Input data → Data dikirim ke backend (POST/PUT) → Data disimpan di database → Data diambil kembali oleh Flutter (GET) → Data ditampilkan di aplikasi.  


## 5. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.

#### **1. Register (Pendaftaran Akun)**  
1. **Input Data di Flutter**:  
   - Pengguna memasukkan data seperti username, password, dan konfirmasi password di form registrasi.  
   - Data ini dikirimkan ke endpoint Django, misalnya `/auth/register/`, menggunakan request **POST**.  

2. **Proses di Backend (Django)**:  
   - Django menerima data dan memvalidasi input, seperti memastikan password dan konfirmasi password sesuai.  
   - Jika valid, Django membuat akun baru menggunakan model `User` dan menyimpan data ke database.  
   - Django merespons dengan JSON yang berisi status registrasi, seperti "Success" atau "Error".  

3. **Respons di Flutter**:  
   - Jika pendaftaran berhasil, Flutter menampilkan pesan konfirmasi atau mengarahkan pengguna ke halaman login.  

#### **2. Login**  
1. **Input Data di Flutter**:  
   - Pengguna memasukkan username dan password pada form login.  
   - Data dikirimkan ke endpoint Django, misalnya `/auth/login/`, menggunakan request **POST** melalui `CookieRequest`.  

2. **Proses di Backend (Django)**:  
   - Django memvalidasi kredensial pengguna dengan mencocokkannya di database.  
   - Jika berhasil, Django membuat sesi login dengan menyimpan informasi pengguna di server menggunakan middleware autentikasi.  
   - Django mengirimkan cookie sesi kepada Flutter melalui respons HTTP.  

3. **Respons di Flutter**:  
   - Flutter menyimpan cookie sesi yang diterima menggunakan `CookieRequest`.  
   - Jika login berhasil, aplikasi mengarahkan pengguna ke halaman utama atau dashboard.

#### **3. Logout**  
1. **Input Data di Flutter**:  
   - Pengguna menekan tombol logout. Flutter mengirimkan request **POST** ke endpoint Django, misalnya `/auth/logout/`.  

2. **Proses di Backend (Django)**:  
   - Django menerima request logout dan menghapus sesi login pengguna dari server.  
   - Django merespons dengan status logout berhasil.  

3. **Respons di Flutter**:  
   - Flutter menghapus cookie sesi pengguna dan mengarahkan kembali ke halaman login.  

### **Tampilan Menu Setelah Autentikasi**  
- **Setelah Login Berhasil**:  
   Flutter mengecek apakah pengguna telah login dengan memeriksa status sesi di `CookieRequest`.  
   Jika pengguna login, halaman utama atau dashboard akan ditampilkan. Menu atau fitur yang membutuhkan autentikasi akan aktif.  

- **Jika Tidak Login**:  
   Flutter mengarahkan pengguna ke halaman login untuk memastikan hanya pengguna yang terautentikasi dapat mengakses fitur tertentu.  


## 6. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step!

- Mengimplementasikan fitur registrasi akun pada proyek tugas Flutter.

### **1. Membuat Aplikasi Baru di Django**  
   - Saya buat aplikasi baru bernama **`authentication`** untuk menangani proses registrasi, login, dan logout:  
     ```bash
     python manage.py startapp authentication
     ```  
   - Tambahkan **`authentication`** ke dalam daftar `INSTALLED_APPS` di file **`settings.py`**:
     ```python
     INSTALLED_APPS = [
         ...
         'authentication',
     ]
     ```

### **2. Menambahkan Cross-Origin Resource Sharing (CORS)**  
   - Instal library **django-cors-headers** untuk memungkinkan komunikasi antara backend Django dan aplikasi Flutter:
     ```bash
     pip install django-cors-headers
     ```
   - Tambahkan **`corsheaders`** ke `INSTALLED_APPS` di file **`settings.py`**:
     ```python
     INSTALLED_APPS = [
         ...
         'corsheaders',
     ]
     ```
   - Tambahkan middleware `CorsMiddleware` di `MIDDLEWARE`:

### **3. Mengatur URL Routing**  
   - Tambahkan path baru di file **`urls.py`** proyek untuk mengarahkan ke aplikasi **`authentication`**:
   - Saya buat file **`urls.py`** di dalam aplikasi **`authentication`** untuk mengatur routing URL yang diperlukan

### **4. Membuat Fungsi View untuk Registrasi, Login, dan Logout**  
   - Di dalam file **`views.py`** aplikasi **`authentication`**, saya buat fungsi untuk menangani registrasi
     
   - Saya juga membuat fungsi untuk login dan logout

### **5. Menghubungkan Backend dengan Aplikasi Flutter**  
   - Di aplikasi Flutter, saya menggunakan library **`http`** untuk mengirimkan permintaan registrasi ke endpoint Django.  

- Membuat halaman login pada proyek tugas Flutter.

1. **Menginstal Package Diperlukan**  
   - Install package **`provider`** dan **`pbp_django_auth`** untuk mendukung manajemen state dan autentikasi:  
     ```bash
     flutter pub add provider
     flutter pub add pbp_django_auth
     ```

2. **Menambahkan CookieRequest dengan Provider**  
   - Saya ubah file **`main.dart`** agar root widget menyediakan instance **CookieRequest** untuk semua widget dalam aplikasi menggunakan **Provider**
   - Perubahan ini memungkinkan instance **CookieRequest** digunakan secara global untuk mengelola autentikasi dan cookie.

3. **Membuat Halaman Login dan Registrasi**  
   - Tambahkan dua file baru di direktori **`lib/screens`**:  
     - **`login.dart`** untuk halaman login.  
     - **`register.dart`** untuk halaman registrasi.  

4. **Menyesuaikan Root Widget**  
   - Ubah **`home`** di **`main.dart`** menjadi **`LoginPage`** agar pengguna diarahkan ke halaman login terlebih dahulu:  
     ```dart
     home: const LoginPage(),
     ```
   - Dengan ini, pengguna hanya dapat mengakses halaman lain setelah berhasil login.

5. **Membuat Form Login**  
   - Di file **`login.dart`**, buat form login dengan input **username** dan **password**, serta tombol untuk mengirimkan data ke server 

6. **Menghubungkan dengan Backend Django**  
   - Pastikan endpoint login di Django tersedia dan menangani request dengan benar.

Penjelasan di atas telah menjelaskan mengenai integrasi sistem autentikasi Django dengan proyek tugas Flutter **herNeeds**.

- Membuat model kustom sesuai dengan proyek aplikasi Django.  

1. **Mengambil Endpoint JSON dari Backend Django**  
   - Saya memulai dengan menjalankan backend Django herNeeds untuk memastikan endpoint JSON yang diperlukan dapat diakses. 
   - Endpoint ini menyediakan data dalam format JSON yang akan digunakan sebagai referensi untuk membuat model di Flutter.

2. **Menggunakan QuickType untuk Membuat Model Dart**  
   - Saya membuka situs **QuickType** untuk mempermudah pembuatan model Dart.  
   - Pertama, saya salin respons JSON dari endpoint Django lalu saya tempelkan JSON tersebut pada **textbox input** di QuickType. Setelah itu, saya atur **source type** menjadi **JSON** dan **language** menjadi **Dart**. Terakhir, saya ubah nama modelnya menjadi **ProductEntry**.

3. **Menyalin Kode Model yang Dihasilkan**  
   - Setelah model **Dart** berhasil dibuat oleh QuickType, saya menyalin kode yang dihasilkan.

4. **Menyimpan Model dalam Proyek Flutter**  
   - Saya membuat file baru bernama **`product_entry.dart`** di direktori **`lib/models`** pada proyek Flutter.  
   - Saya menempelkan kode model Dart yang telah disalin ke dalam file tersebut.

- Membuat halaman yang berisi daftar semua item yang terdapat pada endpoint JSON di Django yang telah kamu deploy.
   - Tampilkan name, price, dan description dari masing-masing item pada halaman ini.

1. **Menambahkan Package HTTP**  
   - Saya tambahkan package **HTTP** untuk mengakses data dari API dengan menjalankan perintah berikut di terminal:  
     ```bash
     flutter pub add http
     ```

2. **Mengatur Izin Akses Internet**  
   - Selanjutnya, saya menambahkan izin akses internet ke aplikasi dengan menyertakan baris berikut di file **AndroidManifest.xml**:  
     ```xml
     <uses-permission android:name="android.permission.INTERNET" />
     ```  

3. **Membuat File Halaman Daftar Produk**  
   - Saya membuat file baru bernama **`list_productentry.dart`** di direktori **`lib/screens`**. Jangan lupa untuk mengimport library yang diperlukan.

4. **Mengambil Data dari Endpoint Django**  
   - Saya menambahkan fungsi **`fetchProduct()`** untuk mengambil data JSON dari endpoint Django dan memetakan datanya ke model `ProductEntry`:  

5. **Menampilkan Data**  
   - Halaman daftar item menampilkan **name**, **price**, dan **description** dari produk dengan cara:  
      1. **FutureBuilder**: Digunakan untuk mengambil data dari server dan menunggu hingga data tersedia. 

      2. **ListView.builder**: Menampilkan daftar produk dalam bentuk scrollable list. Setiap item produk diambil dari data yang diterima dan dibuat sebagai elemen daftar.  

      Setiap produk menampilkan:  
         - **Nama produk** menggunakan widget teks standar.  
         - **Harga** dengan format angka dan label "Price".  
         - **Deskripsi** dengan batas maksimal dua baris, menggunakan ellipsis jika teks terlalu panjang.  

6. **Menambahkan Navigasi ke Halaman Daftar Produk**  
   - Saya memperbarui file **`left_drawer.dart`** untuk menambahkan navigasi ke halaman daftar produk:  

- Membuat halaman detail untuk setiap item yang terdapat pada halaman daftar Item.
   - Halaman ini dapat diakses dengan menekan salah satu item pada halaman daftar Item.
   - Tampilkan seluruh atribut pada model item kamu pada halaman ini.
   - Tambahkan tombol untuk kembali ke halaman daftar item.

Saya mengimplementasikan halaman detail produk dengan beberapa cara:

1. **Navigasi ke Halaman Detail**:
   - Saya menggunakan `InkWell` untuk membuat seluruh card item dapat ditekan yang nanti setelah ditekan akan terarah ke halaman detail produk. Saya gunakan `Navigator.push()` untuk navigasi ke halaman detail
   - Data produk dikirim melalui constructor `ProductDetailPage`

2. **Tampilan Detail Produk**:
   - Membuat class `ProductDetailPage` sebagai StatelessWidget
   - Menggunakan `SingleChildScrollView` untuk memungkinkan scroll jika konten panjang
   - Menampilkan data dalam `Card` dengan padding yang rapi
   - Menampilkan seluruh atribut produk:
     * Nama produk (dengan style bold dan ukuran 24.0)
     * Harga produk
     * Deskripsi produk
     * Stok produk
     * Ukuran produk

3. **Tombol Kembali**:
   - Menambahkan `leading` button di AppBar dengan icon `Icons.arrow_back`
   - Mengimplementasikan `Navigator.pop(context)` untuk kembali ke halaman sebelumnya

Implementasi ini memberikan navigasi yang intuitif dan tampilan detail yang informatif untuk setiap produk.

- Melakukan filter pada halaman daftar item dengan hanya menampilkan item yang terasosiasi dengan pengguna yang login.

Data yang ditampilkan di **ListView** telah terfilter secara otomatis, karena endpoint proyek ini hanya mengembalikan produk milik pengguna yang sedang login. 
   - Fungsi `show_json` pada `views.py` difilter untuk hanya mengembalikan produk yang dimiliki oleh pengguna yang login:  
   ```python
   def show_json(request):
       data = Product.objects.filter(user=request.user)
       return HttpResponse(serializers.serialize("json", data), content_type="application/json")
   ```  
   - Request ke endpoint dilakukan dengan menyertakan session user menggunakan **`CookieRequest`**, sehingga hanya data produk milik user terkait yang diterima.  
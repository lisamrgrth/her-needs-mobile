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
    ItemHomepage("Lihat Daftar Produk", Icons.mood, const Color(0xFFC7A4FF)),
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
   
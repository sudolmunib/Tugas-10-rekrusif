# <h1 align="center">Laporan Praktikum Modul 10 Rekursif</h1>

<p align="center">Nama: Abdul munib</p>
<p align="center">NIM: 2311110004</p>
<p align="center">Kelas: SISD-04A</p>

## Dasar Teori

Pengertian Algoritma rekursif
Rekursif dapat diartikan bahwa suatu proses yang bisa memanggil dirinya sendiri. sedikit menyimpang dari pengertian ada sedikit pendapat tentang Rekursif salah satunya adalah Menurut definisi dalam Microsoft Bookshelf, Rekursif adalah kemampuan suatu rutin untuk memanggil dirinya sendiri. Dalam Rekursif sebenarnya terkandung pengertian prosedur dan fungsi. Perbedaannya adalah bahwa rekursif bisa memanggil ke dirinya sendiri, tetapi prosedur dan fungsi harus dipanggil lewat pemanggil prosedur dan fungsi. Rekursif merupakan teknik pemrograman yang penting dan beberapa bahasa pemrograman mendukung keberadaan proses rekursif ini. Dalam prosedur dan fungsi, pemanggilan ke dirinya sendiri bisa berarti proses berulang yang tidak bisa diketahui kapan akan berakhir.

Algoritma rekursif
- Teknik Rekursif merupakan salah satu cara pembuatan algoritma dengan pemanggilan procedure atau function yang sama

- Ada variabel lokal baru

- Program menjadi lebih sederhana

- Menggunakan perulangan if else

Kelebihan perulangan rekursif:
• Sangat mudah untuk melakukan perulangan dengan batasan yang luas dalam artian melakukan perulangan dalam skala yang besar.
• Dapat melakukan perulangan dengan batasan fungsi.
2. Fungsi Algoritma Rekursif

Fungsi tersebut memanggil dirinya sendiri secara rekursif terhadap versi input yang lebih kecil (n-1) dan mengkalikan hasil dari pemanggilan rekursif dengan n, sampai pada kasus dasar, sama analoginya dengan definisi matematika dari faktorial.

Rekursi dalam pemrograman komputer dicontohkan saat sebuah fungsi didefinisikan dalam bentuk sederhana, bahkan versi terkecil dari dirinya. Solusi dari permasalahan kemudian dirancang dengan menggabungkan solusi-solusi yang didapat dari versi sederhana dari permasalahan. Salah satu contoh aplikasi rekursi yaitu dalam parsing untuk bahasa pemrograman. Keuntungan utama dari rekursi adalah suatu himpunan tak-terbatas dari kalimat yang memungkinkan, perancangan atau data lainnya dapat didefinisikan, diurai atau dihasilkan dengan suatu program komputer yang terbatas.

Relasi perulangan adalah persamaan-persamaan untuk menentukan satu atau lebih urutan-urutan secara rekursif. Beberapa relasi perulangan tertentu dapat “diselesaikan” untuk mendapatkan definisi bukan-rekursif.

Penggunaan rekursi dalam suatu algoritma memiliki kelebihan dan kekurangan. Kelebihan utamanya adalah biasanya kesederhanaan. Kekurangan utamanya adalah terkadang algoritma tersebut membutuhkan memori yang sangat banyak jika kedalaman rekursi sangat besar.

3. Contoh Algoritma Rekursif

Contoh paling sederhana dari proses rekursi adalah menghitung nilai faktorial dari bilangan bulat. Nilai faktorial, secara rekursif dapat ditulis sebagai :

0! = 1

N! = N x (N-1)!, Untuk N > 0

yang secara notasi pemrograman bisa ditulis sebagai:

FAKTORIAL (0) = 1 1)

FAKTORIAL (N) = N * FAKTORIAL (N-1)


### Guided 1

#### Kode Program
```C++
#include <iostream>

using namespace std;

void countdown(int n) {
    if (n == 0) {
        return;
    }

    cout << n << " ";
    countdown(n - 1);
}

int main( ) {
    cout << " Rekursif Langsung: ";
    countdown(5);
    cout << endl;
    return 0;
}
```
#### Output 

![Screenshot 2024-05-27 165043](https://github.com/sudolmunib/tugas-struktur-data/assets/162574378/11a801ce-d7a8-4f8c-8b66-94a01a33a458)
#### Interpretasi

#include <iostream>
using namespace std;
Baris pertama adalah preprocessor directive yang menyertakan pustaka input/output standard (iostream). using namespace std digunakan agar kita dapat menggunakan elemen-elemen dalam namespace std tanpa harus menuliskan std:: di depan setiap elemen.

Fungsi Rekursif countdown:

void countdown(int n) {
    if (n == 0) {
        return;
    }
    cout << n << " ";
    countdown(n - 1);
}

Fungsi countdown menerima satu parameter bertipe int yang dinamakan n. Fungsi ini digunakan untuk menampilkan angka n dan kemudian memanggil dirinya sendiri dengan parameter n-1, sampai n mencapai 0.

Basis kasus: Jika n sama dengan 0, fungsi akan berhenti (mengembalikan kontrol ke pemanggilnya) dengan perintah return.
Proses rekursif: Jika n tidak sama dengan 0, fungsi akan mencetak nilai n diikuti dengan sebuah spasi, kemudian memanggil dirinya sendiri dengan nilai n-1.
Fungsi main:

int main() {
    cout << " Rekursif Langsung: ";
    countdown(5);
    cout << endl;
    return 0;
}

Fungsi main adalah titik awal eksekusi program. Dalam fungsi ini:

Pesan "Rekursif Langsung: " dicetak ke layar.
Fungsi countdown dipanggil dengan argumen 5, yang memulai proses hitungan mundur.
Setelah fungsi countdown selesai, karakter endl dicetak untuk memindahkan kursor ke baris baru.
Program mengembalikan 0 untuk menunjukkan bahwa program telah selesai dijalankan tanpa kesalahan.
Cara Kerja Program
- Program mencetak pesan "Rekursif Langsung: ".
- Program memanggil fungsi countdown dengan nilai awal 5.
- Fungsi countdown akan mencetak angka 5 dan memanggil dirinya sendiri dengan nilai 4.
- Proses ini berlanjut sampai n mencapai 0, di mana fungsi akan berhenti memanggil dirinya sendiri.
- Setelah semua pemanggilan rekursif selesai, program mencetak karakter endl dan selesai.

### Guided 2

#### Kode Program
```C++
// Guided 2 Rekursif Tidak Langsung

#include <iostream>

using namespace std;

void functionB(int n);

void functionA(int n) {
    if (n > 0) {
        cout << n << " ";
        functionB(n-1);
    }
}

void functionB(int n) {
    if (n > 0) {
        cout << n<< " ";
        functionB(n/2);
    }
}

int main( ) {
    int num= 5;
    cout << "Rekursif Tidak Langsung:";
    functionA(num);
    return 0;
}
```

#### Output 

![Screenshot 2024-05-27 165220](https://github.com/sudolmunib/tugas-struktur-data/assets/162574378/ec6771ad-9d80-4612-a827-0717e8c569f6)

Interpretasi:

Header dan Namespace

#include <iostream>: Mengikutsertakan pustaka standar untuk input dan output pada C++.

using namespace std: Memungkinkan penggunaan fitur standar C++ seperti cout tanpa perlu mendahuluinya dengan std::.
Deklarasi Fungsi

Mendeklarasikan functionB agar dapat digunakan di dalam functionA.
Definisi Fungsi functionA

if (n > 0): Memeriksa apakah n lebih besar dari 0.
cout << n << " ";: Mencetak nilai n diikuti dengan spasi.
functionB(n-1): Memanggil functionB dengan parameter n-1.
Definisi Fungsi functionB

if (n > 0): Memeriksa apakah n lebih besar dari 0.
cout << n << " ";: Mencetak nilai n diikuti dengan spasi.
functionA(n/2): Memanggil functionA dengan parameter n dibagi 2.
Fungsi main

int num = 5;: Mendeklarasikan dan menginisialisasi variabel num dengan nilai 5.

cout << "Rekursif Tidak Langsung:";: Mencetak teks "Rekursif Tidak Langsung:".

functionA(num);: Memanggil functionA dengan argumen num (nilai 5).
Alur Eksekusi Program

Program dimulai dari fungsi main dan mencetak "Rekursif Tidak Langsung:".

functionA dipanggil dengan parameter n = 5.
Dalam functionA:

Karena n > 0, nilai 5 dicetak diikuti spasi.
Memanggil functionB dengan nilai n - 1 = 4.
Dalam functionB:

Karena n > 0, nilai 4 dicetak diikuti spasi.
Memanggil functionA dengan nilai n / 2 = 2.
Dalam functionA:

Karena n > 0, nilai 2 dicetak diikuti spasi.
Memanggil functionB dengan nilai n - 1 = 1.
Dalam functionB:

Karena n > 0, nilai 1 dicetak diikuti spasi.
Memanggil functionA dengan nilai n / 2 = 0.
Dalam functionA:

Karena n tidak lebih besar dari 0, fungsi berhenti dan tidak melakukan apa-apa.

Rekursi selesai dan kembali ke main, program berakhir.
Dalam program ini, ada dua fungsi, functionA dan functionB, yang saling memanggil secara bergantian. Fungsi functionA menerima satu parameter integer n dan mencetak nilai n jika lebih besar dari 0, lalu memanggil functionB dengan parameter n-1. Sementara itu, fungsi functionB juga menerima satu parameter integer n, mencetak nilai n jika lebih besar dari 0, lalu memanggil functionA dengan parameter n/2.

Program dimulai dengan fungsi main yang menginisialisasi variabel num dengan nilai 5 dan mencetak teks "Rekursif Tidak Langsung:". Kemudian, functionA dipanggil dengan nilai num (5). Di dalam functionA, karena n lebih besar dari 0, nilai 5 dicetak dan functionB dipanggil dengan nilai 4. Di dalam functionB, nilai 4 dicetak dan functionA dipanggil dengan nilai 2. Proses ini berlanjut dengan functionA mencetak 2 dan memanggil functionB dengan nilai 1, kemudian functionB mencetak 1 dan memanggil functionA dengan nilai 0. Karena n tidak lebih besar dari 0, pemanggilan rekursif berhenti.

Output dari program ini adalah "Rekursif Tidak Langsung: 5 4 2 1", di mana angka-angka tersebut dicetak secara bergantian oleh functionA dan functionB sesuai dengan logika rekursi tidak langsung yang telah dijelaskan.

## Tugas Praktikum 

### Unguided 1

### Soal 
[1]
Buatlah sebuah program Rekursif Langsung (Direct Recursion) yang menghitung nilai faktorial dari sebuah inputan bilangan bulat positif!

Masukkan bilangan bulat positif: 5

Faktorial dari 5 adalah: 120

```C++
#include <iostream>

using namespace std;

// Fungsi rekursif untuk menghitung faktorial
int faktorial(int n) {
    if (n == 0 || n == 1) {
        return 1;
    } else {
        return n * faktorial(n - 1);
    }
}

int main() {
    int num;
    
    // Meminta pengguna untuk memasukkan bilangan bulat positif
    cout << "Masukkan bilangan bulat positif: ";
    cin >> num;
    
    // Mengecek apakah input adalah bilangan bulat positif
    if (num < 0) {
        cout << "Input tidak valid. Silakan masukkan bilangan bulat positif." << endl;
    } else {
        // Menghitung dan mencetak hasil faktorial
        int hasil = faktorial(num);
        cout << "Faktorial dari " << num << " adalah: " << hasil << endl;
    }

    return 0;
}
```

#### Output 

![Screenshot 2024-05-27 165333](https://github.com/sudolmunib/tugas-struktur-data/assets/162574378/c011e3b7-992d-41e7-9a5c-0a310b0c13ab)

Interpretasi

Fungsi faktorial adalah fungsi rekursif yang menghitung faktorial dari bilangan n. Jika n adalah 0 atau 1, fungsi mengembalikan 1 (karena faktorial dari 0 dan 1 adalah 1). Jika n lebih besar dari 1, fungsi mengembalikan hasil dari n * faktorial(n - 1), yang berarti memanggil dirinya sendiri dengan nilai n yang dikurangi 1.


Variabel num dideklarasikan untuk menyimpan bilangan bulat yang akan dimasukkan oleh pengguna.

cout digunakan untuk meminta pengguna memasukkan bilangan bulat positif.

cin digunakan untuk membaca input dari pengguna dan menyimpannya ke variabel num.

Program kemudian memeriksa apakah num kurang dari 0. Jika ya, program menampilkan pesan bahwa input tidak valid dan


Program memanggil fungsi faktorial dengan n = 5.
Fungsi faktorial bekerja sebagai berikut:
faktorial(5) memanggil faktorial(4).
faktorial(4) memanggil faktorial(3).
faktorial(3) memanggil faktorial(2).
faktorial(2) memanggil faktorial(1).
faktorial(1) mengembalikan 1 (basis kasus).
faktorial(2) mengembalikan 2 * 1 = 2.
faktorial(3) mengembalikan 3 * 2 = 6.
faktorial(4) mengembalikan 4 * 6 = 24.
faktorial(5) mengembalikan 5 * 24 = 120.
Hasil faktorial disimpan dalam variabel hasil.
Output Hasil:
Program menampilkan hasil: "Faktorial dari 5 adalah: 120".
Misalkan pengguna memasukkan nilai -3:

### Unguided 2

#### Soal

2. Buatlah versi program Rekursif Tidak Langsung (Indirect Recursion) dari soal nomor 1 diatas!

#### Kode Program
```C++
#include <iostream>

using namespace std;

// Deklarasi fungsi
int functionA(int n);
int functionB(int n);

int main() {
    int num;
    
    // Meminta pengguna untuk memasukkan bilangan bulat positif
    cout << "Masukkan bilangan bulat positif: ";
    cin >> num;
    
    // Mengecek apakah input adalah bilangan bulat positif
    if (num < 0) {
        cout << "Input tidak valid. Silakan masukkan bilangan bulat positif." << endl;
    } else {
        // Menghitung dan mencetak hasil faktorial menggunakan rekursi tidak langsung
        int hasil = functionA(num);
        cout << "Faktorial dari " << num << " adalah: " << hasil << endl;
    }

    return 0;
}

// Fungsi A untuk rekursi tidak langsung
int functionA(int n) {
    if (n == 0 || n == 1) {
        return 1;
    } else {
        return n * functionB(n - 1);
    }
}

// Fungsi B untuk rekursi tidak langsung
int functionB(int n) {
    if (n == 0 || n == 1) {
        return 1;
    } else {
        return n * functionA(n - 1);
    }
}
```

#### Output 

![Screenshot 2024-05-27 165535](https://github.com/sudolmunib/tugas-struktur-data/assets/162574378/05679b69-5f50-4843-bfce-c1fa37c5cd32)
Interpretasi

Program ini menggunakan rekursi tidak langsung antara functionA dan functionB untuk menghitung faktorial dari bilangan bulat positif yang dimasukkan oleh pengguna.

Fungsi functionA dan functionB memiliki logika yang serupa. Ketika dipanggil dengan sebuah bilangan bulat n, mereka memeriksa apakah n adalah 0 atau 1. Jika ya, mereka mengembalikan 1 sebagai nilai faktorial. Jika n lebih besar dari 1, keduanya akan memanggil fungsi yang lain dengan n - 1. functionA memanggil functionB(n - 1), sementara functionB memanggil functionA(n - 1).

Di dalam fungsi main, program meminta pengguna memasukkan bilangan bulat positif. Setelah memeriksa validitas input, program memanggil functionA untuk menghitung faktorialnya. Hasilnya kemudian ditampilkan ke layar.

Penjelasan Output:

Output dari program terjadi karena rekursi tidak langsung antara functionA dan functionB. Ketika pengguna memasukkan bilangan bulat positif, program memanggil functionA dengan nilai tersebut. Berikut adalah alur proses yang menghasilkan output:

Ketika functionA dipanggil dengan n, ada dua kemungkinan:

Jika n sama dengan 0 atau 1, fungsi mengembalikan 1 sebagai hasil faktorial.
Jika n lebih besar dari 1, fungsi memanggil functionB(n - 1), mengalikan n dengan hasilnya, dan mengembalikan hasil tersebut.
Ketika functionB dipanggil dengan n, proses yang sama terjadi seperti pada functionA, namun fungsi functionB memanggil functionA(n - 1).

Kedua fungsi ini saling memanggil secara bergantian, membentuk rekursi tidak langsung. Setiap kali salah satu fungsi dipanggil dengan nilai n, nilai tersebut dikalikan dengan hasil rekursi dari fungsi yang lain.

Misalnya, jika pengguna memasukkan nilai 5:

Pertama, functionA(5) memanggil functionB(4).
Kemudian, functionB(4) memanggil functionA(3).
Proses ini berlanjut hingga mencapai kondisi dasar ketika n adalah 0 atau 1.
Hasil dari seluruh proses rekursi ini menghasilkan faktorial dari bilangan yang dimasukkan.
Sehingga outputnya adalah "Faktorial dari 5 adalah: 120", yang merupakan faktorial dari bilangan yang dimasukkan pengguna.

## Daftar Pustaka

[1] 
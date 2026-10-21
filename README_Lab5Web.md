# Lab5Web – Pengenalan JavaScript

## Identitas Praktikum
- **Mata Kuliah:** Pemrograman Web
- **Praktikum:** Lab 5 – Pengenalan JavaScript
- **Nama:** ................................................
- **NIM:** .................................................
- **Kelas:** ................................................

## 1. Tujuan Praktikum
Praktikum ini bertujuan untuk memahami dasar penggunaan JavaScript pada halaman web, meliputi:
1. Mengubah teks pada elemen HTML menggunakan `textContent`.
2. Menggunakan `console.log()`, `alert()`, dan `prompt()`.
3. Memahami variabel `let` dan `const`.
4. Menggunakan percabangan `if–else` dan `switch`.
5. Melakukan operasi aritmetika melalui function dengan parameter.
6. Memeriksa bilangan ganjil atau genap.
7. Mengubah warna latar halaman melalui tombol.
8. Menghitung total harga menu yang dipilih.
9. Menghitung nilai akhir, menentukan predikat, dan memeriksa status kelulusan.

## 2. Alat dan Bahan
- Visual Studio Code atau editor kode sejenis.
- Browser seperti Google Chrome atau Microsoft Edge.
- File HTML dan JavaScript.
- Repository GitHub bernama `Lab5Web`.

## 3. Struktur Folder
Susunan file yang disarankan:

```text
Lab5Web/
├── index.html
├── script.js
├── README.md
└── screenshots/
    ├── latihan-1.png
    ├── latihan-2.png
    ├── latihan-3.png
    └── latihan-4.png
```

Simpan seluruh screenshot di folder `screenshots`. Nama file gambar di bawah harus disesuaikan dengan nama file yang benar-benar digunakan pada repository.

## 4. Langkah Kerja
1. Membuat repository baru di GitHub dengan nama `Lab5Web`.
2. Membuat file `index.html` untuk struktur halaman.
3. Membuat file `script.js` untuk kode JavaScript.
4. Menghubungkan file JavaScript ke HTML menggunakan:
   ```html
   <script src="script.js"></script>
   ```
5. Menjalankan `index.html` melalui browser.
6. Menguji setiap fitur dan mencatat hasilnya.
7. Mengambil screenshot hasil latihan dan menyimpannya ke folder `screenshots`.
8. Menambahkan seluruh file ke repository, kemudian melakukan commit dan push.
9. Mengirim URL repository melalui e-learning/ecampus sesuai instruksi dosen.

## 5. Penjelasan Latihan dan Hasil

### Latihan 1 – Menampilkan dan mengubah konten
Elemen `<p id="pesan">Konten Awal.</p>` digunakan sebagai tempat menampilkan teks. JavaScript memilih elemen tersebut dengan `document.getElementById("pesan")`, kemudian mengubah teksnya menggunakan `textContent`.

Contoh:
```javascript
document.getElementById("pesan").textContent = "Hello World";
console.log("Hello World");
```

**Hasil yang diharapkan:** teks pada halaman berubah dan pesan juga dapat dilihat pada Console browser.

![Latihan 1 – Konten halaman](screenshots/latihan-1.png)

### Latihan 2 – Menggunakan prompt dan alert
Program meminta nama pengguna melalui `prompt()`. Jika nama diisi, program menampilkan sapaan melalui `alert()` dan memperbarui teks halaman. Jika nama kosong atau hanya berisi spasi, program menampilkan pesan bahwa nama belum diisi.

Contoh:
```javascript
const namaPengguna = prompt("Masukkan nama Anda:", "");

if (namaPengguna && namaPengguna.trim() !== "") {
  alert("Halo, " + namaPengguna + "!");
  document.getElementById("pesan").textContent =
    "Selamat datang, " + namaPengguna + ".";
} else {
  alert("Nama belum diisi.");
}
```

**Hasil yang diharapkan:** nama yang dimasukkan muncul pada pesan sapaan. Jika input dibatalkan atau kosong, muncul pesan peringatan.

![Latihan 2 – Dialog sapaan](screenshots/latihan-2.png)

### Latihan 3 – Operasi aritmetika dengan function
Function `operasiDasar(a, b)` menerima dua parameter dan menampilkan hasil penjumlahan, pengurangan, perkalian, pembagian, dan modulus ke Console. Pembagian dengan nol diperiksa agar program tidak menampilkan hasil pembagian yang tidak sesuai.

Contoh pemanggilan:
```javascript
operasiDasar(9, 4);
```

**Hasil yang diharapkan:** hasil operasi ditampilkan pada Console browser. Buka Developer Tools dengan menekan `F12`, kemudian pilih tab **Console**.

![Latihan 3 – Operasi dasar](screenshots/latihan-3.png)

### Latihan 4 – Validasi nilai dan percabangan if–else
Program meminta nilai melalui `prompt()`, mengubah input menjadi angka, lalu memeriksa apakah input kosong, bukan angka, kurang dari 0, atau lebih dari 100. Jika nilai valid dan minimal 60, program menampilkan “Lulus”; jika kurang dari 60, program menampilkan “Belum lulus”.

**Hasil yang diharapkan:** input di luar rentang 0–100 ditolak. Nilai 60–100 dinyatakan lulus, sedangkan nilai 0–59 dinyatakan belum lulus.

![Latihan 4 – Validasi nilai](screenshots/latihan-4.png)

### Latihan 5 – Percabangan switch
Program meminta pengguna memasukkan angka 1–5. Pernyataan `switch` memilih pesan yang sesuai untuk setiap angka. `break` digunakan untuk menghentikan eksekusi pada case yang cocok, sedangkan `default` dijalankan jika pilihan tidak tersedia.

**Hasil yang diharapkan:** angka 1 menampilkan “Bilangan satu”, angka 2 menampilkan “Bilangan dua”, dan seterusnya sampai angka 5. Input lain menampilkan “Pilihan tidak tersedia”.

### Latihan 6 – Memeriksa bilangan ganjil atau genap
Function `cekBilangan()` membaca input dari elemen dengan ID `bilangan`. Nilai dikonversi menjadi angka, lalu diperiksa menggunakan operator modulus (`%`). Jika sisa pembagian dengan 2 adalah 0, bilangan dinyatakan genap; selain itu, bilangan dinyatakan ganjil. Input kosong dan bukan bilangan bulat ditolak.

**Hasil yang diharapkan:** input `4` menampilkan “Bilangan genap”, sedangkan input `5` menampilkan “Bilangan ganjil”.

### Latihan 7 – Mengubah warna latar halaman
Function `ubahWarnaLatar(warna)` mengubah properti `document.body.style.backgroundColor`. Tombol pada halaman memanggil function dengan warna `lightgreen`, `white`, atau `lightyellow`.

**Hasil yang diharapkan:** warna latar berubah sesuai tombol yang ditekan.

### Latihan 8 – Menghitung total menu makanan
Setiap checkbox menu memiliki class `menu` dan atribut `value` yang berisi harga. Ketika pilihan berubah, event `change` memanggil function `hitungTotal()`. Function tersebut menjumlahkan harga dari checkbox yang dicentang dan menampilkan total pada elemen dengan ID `total`.

**Hasil yang diharapkan:** total berubah secara otomatis ketika checkbox dipilih atau dilepas. Jika total tetap Rp0 saat ada pilihan yang dicentang, pastikan variabel `daftarMenu` sudah dibuat dengan benar dan berisi semua elemen `.menu`, serta function `hitungTotal()` dipanggil saat halaman dimuat.

Contoh bagian JavaScript yang diperlukan:
```javascript
const daftarMenu = document.querySelectorAll(".menu");

daftarMenu.forEach((item) => {
  item.addEventListener("change", hitungTotal);
});

function hitungTotal() {
  let total = 0;

  daftarMenu.forEach((item) => {
    if (item.checked) {
      total += Number(item.value);
    }
  });

  document.getElementById("total").textContent =
    total.toLocaleString("id-ID");
}

hitungTotal();
```

### Latihan 9 – Menghitung nilai akhir dan predikat
Function `hitungNilaiAkhir(tugas, uts, uas)` menghitung nilai akhir dengan bobot tugas 30%, UTS 30%, dan UAS 40%. Function `tentukanPredikat(nilai)` menentukan predikat berdasarkan nilai akhir. Program juga menampilkan status lulus jika nilai akhir minimal 60.

Rumus:
```text
Nilai Akhir = (Tugas × 0,30) + (UTS × 0,30) + (UAS × 0,40)
```

Contoh nilai:
- Tugas = 85
- UTS = 78
- UAS = 88

**Hasil perhitungan:** nilai akhir = 84,10. Berdasarkan aturan predikat pada program, nilai tersebut mendapat predikat B karena belum mencapai 85. Statusnya adalah “Lulus”.

## 6. File HTML dan JavaScript
Pada `index.html`, pastikan seluruh elemen yang dipakai JavaScript berada di dalam `<body>`, sebelum tag penutup `</body>`. Jangan meletakkan elemen seperti `<label>`, `<input>`, atau `<button>` setelah `</html>` karena elemen tersebut berada di luar struktur dokumen HTML.

Pastikan `script.js` dipanggil setelah elemen HTML tersedia, misalnya tepat sebelum `</body>`:
```html
<script src="script.js"></script>
</body>
</html>
```

## 7. Cara Menjalankan Program
1. Buka folder `Lab5Web` di Visual Studio Code.
2. Pastikan `index.html` dan `script.js` berada di folder yang sama jika menggunakan struktur di atas.
3. Buka `index.html` pada browser.
4. Ikuti dialog dan uji setiap tombol.
5. Untuk melihat keluaran `console.log()`, tekan `F12` lalu buka tab **Console**.
6. Coba beberapa masukan berbeda untuk memastikan program berjalan sesuai kondisi yang ditentukan.

## 8. Screenshot
Simpan screenshot yang benar-benar diambil dari browser atau Console pada folder `screenshots`. Gunakan format Markdown berikut dan samakan nama file dengan file gambar di repository:

```markdown
![Latihan 1](screenshots/latihan-1.png)
![Latihan 2](screenshots/latihan-2.png)
![Latihan 3](screenshots/latihan-3.png)
![Latihan 4](screenshots/latihan-4.png)
```

Tambahkan gambar lain untuk latihan berikutnya bila tersedia. Pastikan file gambar sudah diunggah ke GitHub agar gambar tampil pada halaman README.

## 9. Perintah Git untuk Mengumpulkan
Jalankan perintah berikut pada terminal di dalam folder proyek:

```bash
git add .
git commit -m "Menyelesaikan praktikum Lab5Web"
git branch -M main
git push -u origin main
```

Jika repository lokal belum terhubung ke GitHub, tambahkan remote terlebih dahulu. Ganti `USERNAME` dengan username GitHub sendiri:

```bash
git remote add origin https://github.com/USERNAME/Lab5Web.git
```

Jika remote sudah tersedia, jangan menambahkannya lagi. Periksa dengan `git remote -v`.

## 10. Kesimpulan
Praktikum Lab5Web memperkenalkan penggunaan JavaScript untuk memanipulasi halaman HTML dan membuat interaksi dengan pengguna. Materi yang dipraktikkan mencakup dialog input dan pesan, operasi aritmetika, percabangan `if–else` dan `switch`, pemeriksaan bilangan, perubahan warna latar, penghitungan harga menu, serta penghitungan nilai akhir dan predikat. Pengujian perlu dilakukan dengan beberapa input dan hasilnya didokumentasikan melalui screenshot. Semua file praktikum dan dokumentasi kemudian disimpan dalam repository GitHub untuk dikumpulkan melalui e-learning/ecampus.

## 11. Pengumpulan
- [ ] Repository bernama `Lab5Web` sudah dibuat.
- [ ] File HTML dan JavaScript sudah diunggah.
- [ ] README.md sudah dilengkapi.
- [ ] Screenshot sudah dimasukkan dan tampil di README.
- [ ] Perubahan sudah di-commit dan di-push.
- [ ] URL repository sudah dikirim melalui e-learning/ecampus.

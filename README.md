# Basis Data Part 9: Praktik Data Cleansing Menggunakan OpenRefine (Studi Kasus Nyata)

## Pendahuluan

Dalam dunia basis data dan analisis data, kualitas data menentukan kualitas hasil analisis. Data yang terlihat sederhana sering kali menyimpan banyak permasalahan tersembunyi seperti duplikasi, perbedaan penulisan, spasi berlebih, dan format yang tidak konsisten. Masalah-masalah ini dikenal sebagai *messy data*.

Pada **Basis Data Part 9**, pembelajaran difokuskan pada praktik **data cleansing** menggunakan **OpenRefine**, sebuah tools open-source yang banyak digunakan oleh data analyst dan data engineer untuk membersihkan dan menstandarkan data sebelum diproses lebih lanjut.

---

## Mengapa Data Cleansing Sangat Penting?

Tanpa proses data cleansing, analisis data dapat menghasilkan:

* Data duplikat dalam laporan
* Perhitungan statistik yang tidak akurat
* Kesalahan pengambilan keputusan

Oleh karena itu, data cleansing merupakan tahap krusial sebelum data dimasukkan ke dalam database atau digunakan dalam analisis lanjutan.

---

## Pengenalan OpenRefine

**OpenRefine** adalah aplikasi berbasis web lokal yang dirancang untuk bekerja dengan data tidak terstruktur atau tidak konsisten. Beberapa keunggulan OpenRefine antara lain:

* Visualisasi data secara langsung
* Transformasi data tanpa menulis kode
* Fitur clustering untuk mendeteksi duplikasi
* Riwayat perubahan yang aman

OpenRefine bekerja dalam bentuk *project*, sehingga data asli tetap aman dan tidak berubah.

---

## Studi Kasus Dataset

Dataset yang digunakan pada Part 9 berisi data dengan kolom utama:

* Timestamp
* Name of person presenting
* Name of project/news package

Dari hasil observasi awal, ditemukan banyak variasi penulisan nama untuk orang yang sama, seperti:

* Tim
* Timmy Campbell
* Tim Campbell
* Timothy Campbell
* Campbell

Masalah ini menjadi fokus utama dalam proses data cleansing.

---

## Tahap 1: Loading File dan Create Project

Langkah awal adalah mengimpor file CSV ke OpenRefine dengan tahapan:

1. Membuka OpenRefine melalui browser
2. Memilih file CSV
3. Mengecek parsing options (separator, header, encoding)
4. Membuat project baru

Tahap ini memastikan struktur data terbaca dengan benar sebelum dilakukan pembersihan.

---

## Tahap 2: Examining Data Menggunakan Text Facet

Setelah project dibuat, proses evaluasi data dilakukan menggunakan fitur **Text Facet**.

Text Facet memungkinkan pengguna untuk:

* Melihat seluruh nilai unik dalam satu kolom
* Mengidentifikasi data yang tidak konsisten
* Menghitung frekuensi kemunculan data

Melalui fitur ini, variasi nama yang merujuk pada orang yang sama dapat terdeteksi dengan jelas.

---

## Tahap 3: Removing Whitespace

Whitespace atau spasi di awal dan akhir teks sering kali tidak terlihat tetapi berdampak besar.

OpenRefine menyediakan transformasi:

* Trim leading and trailing whitespace

Transformasi ini menghapus spasi tersembunyi sehingga data yang tampak sama benar-benar dianggap sama oleh sistem.

---

## Tahap 4: Menyeragamkan Format Teks (Case Formatting)

Perbedaan huruf kapital dan huruf kecil juga menyebabkan inkonsistensi data.

Dengan fitur **To Titlecase**, seluruh data nama dapat diseragamkan sehingga:

* Tampilan data lebih rapi
* Mudah dibaca
* Konsisten antar entri

---

## Tahap 5: Data Cleansing dengan Cluster and Edit

Fitur **Cluster and Edit** merupakan inti dari OpenRefine.

Pada tahap ini:

1. OpenRefine mengelompokkan data berdasarkan kemiripan
2. Pengguna memilih nama standar
3. Data digabung menjadi satu nilai konsisten

Sebagai contoh, seluruh variasi nama:

* Tim
* Timmy Campbell
* Tim Campbell
* Timothy Campbell

Digabung menjadi satu nama standar:
**Timothy Campbell**

---

## Tahap 6: Algorithm Settings dan Akurasi Clustering

OpenRefine menyediakan beberapa algoritma clustering seperti:

* Fingerprint
* Key Collision

Pengaturan algoritma ini mempengaruhi tingkat sensitivitas clustering. Penggunaan algoritma yang tepat membantu mendeteksi duplikasi tanpa menggabungkan data yang seharusnya berbeda.

---

## Tahap 7: Cleaning Individual Entries

Tidak semua data dapat dibersihkan secara otomatis. Untuk kasus tertentu, pengeditan manual tetap diperlukan.

Melalui Text Facet, pengguna dapat mengedit nilai tertentu secara langsung sehingga seluruh data benar-benar bersih.

---

## Tahap 8: Exporting Cleaned Data

Setelah seluruh proses data cleansing selesai, dataset dapat diekspor kembali dalam format CSV.

Data hasil cleansing ini siap untuk:

* Dimasukkan ke database
* Digunakan untuk analisis data
* Digunakan dalam laporan atau visualisasi

---

## Evaluasi Hasil Data Cleansing

Setelah proses pembersihan:

* Jumlah nilai unik berkurang
* Data menjadi konsisten
* Risiko kesalahan analisis menurun

Hal ini menunjukkan bahwa proses data cleansing berhasil dilakukan.

---

## Kesimpulan

Basis Data Part 9 memberikan pemahaman praktis mengenai pentingnya data cleansing dalam pengolahan data. Dengan OpenRefine, proses pembersihan data dapat dilakukan secara cepat, visual, dan minim kesalahan.

Materi ini menjadi jembatan antara konsep basis data dan praktik nyata di dunia profesional, khususnya dalam bidang data analytics dan data engineering.

---

**Referensi:**

* Modul Basis Data Part 9 – Using OpenRefine

**Alan Dodi Amdani - Capston 3**

# **Saudi Arabia Used Car Regression**
<hr>

Pengetahuan domain dan literasi didapat berdasarkan sumber-sumber berikut:

- [expertarrivals.com](https://www.expertarrivals.com)
- [kenresearch.com](https://www.kenresearch.com/blog/2020/09/future-of-saudi-arabia-used-car-market-growth-rate-ken-research/)
- [kaggledatasets Saudi Arabia Used Cars](https://www.kaggle.com/datasets/turkibintalib/saudi-arabia-used-cars-dataset?select=UsedCarsSA_Clean_EN.csv)
- [syarah.com](https://syarah.com/)
-[Parameters of your Random Forest](https://www.analyticsvidhya.com/blog/2015/06/tuning-random-forest-model/)
- [Random Forest Regressor](https://levelup.gitconnected.com/random-forest-regression-209c0f354c84)
- [Random Forest Regressor 2](https://www.sciencedirect.com/science/article/pii/S0140988320303662)

# **1. Business Problem Understanding**
<hr>

Transportasi merupakan alat penting yang mendukung kehidupan manusia. Mobil adalah salah satu jenis transportasi yang paling populer di Arab Saudi dan menjadi tingkat kebutuhan utama dibandingkan dengan sepeda motor. Suhu panas di Arab membuat sepeda motor tidak menjadi pilihan dan membuat mobil lebih diminati. Selain itu, dengan diterapkannya aturan yang memperbolehkan perempuan bekerja dan mengemudi pada tahun 2019, permintaan akan mobil semakin meningkat. Artikel yang membahas peluang pasar mobil bekas di Arab Saudi menyatakan bahwa rasio membeli mobil bekas dibandingkan dengan mobil baru adalah 2:1 dan masih bisa meningkat seiring dengan pertumbuhan ekonomi yang baik di Arab Saudi.

Karena permintaan mobil bekas yang tinggi, ada beberapa platform situs web seperti syarah.com yang berniat untuk menjadi media untuk membeli dan menjual mobil bekas. syarah.com, yang didirikan pada tahun 2015, adalah salah satu platform membeli dan menjual mobil bekas terbesar di Arab Saudi. Di syarah.com, pelanggan dapat memilih mobil sesuai keinginan mereka dengan mengombinasikan spesifikasi dan harga yang diinginkan. Banyak fitur juga ditampilkan di situs web untuk memberikan spesifikasi mobil yang lebih lengkap. Semakin baik spesifikasi mobil, semakin tinggi harganya. Dalam hal harga, menentukan harga mobil bekas cukup rumit karena sulit untuk menentukan harga pasar dan mempertimbangkan begitu banyak spesifikasi. Belum lagi adanya fitur baru pada mobil terbaru yang membuat harga mobil bekas turun. Oleh karena itu, kita membutuhkan alat bantu seperti machine learning untuk membuat harga mobil bekas lebih akurat.

Data transaksi mobil bekas yang sebelumnya dapat dipelajari oleh machine learning sehingga bisa menghasilkan model yang dapat digunakan oleh perusahaan seperti syarah.com. Hal ini diharapkan dapat membuat harga mobil bekas lebih kompetitif di pasar. Karena tidak semua penjual potensial memahami spesifikasi mobil mereka, machine learning diperlukan untuk memastikan harga yang akurat dan kompetitif. Ini akan memberikan manfaat bagi semua pihak, baik perusahaan seperti syarah.com, calon pembeli, dan penjual potensial.

## **Problem Statement**

Satu dari beberapa tantangan utama bagi perusahaan yang menjual mobil bekas adalah menemukan solusi untuk menciptakan model bisnis yang menguntungkan dari segi finansial bagi pemilik/penjual mobil dan memberikan pengalaman yang baik bagi pembeli. Harga yang terlalu tinggi dapat membuat pembeli enggan membeli dan memilih platform lain, sementara harga yang terlalu rendah dapat mengakibatkan pemilik merugi dan tidak memperoleh keuntungan yang memadai ataupun maksimal.

Bagi penjual potensial, model bisnis yang dihasilkan oleh perusahaan akan mengurangi waktu yang dihabiskan dalam mencari harga mobil bekas. Jangan lupa bahwa harga jual merupakan faktor yang membuat mobil bekas tersebut kompetitif, sehingga keuntungan yang diambil dapat dimaksimalkan.

Bagi calon pembeli, waktu yang mereka habiskan dalam membandingkan harga juga akan dikurangi. Ini karena jika model bisnis perusahaan dapat dihasilkan, maka semua harga di platform adalah harga kompetitif sehingga mereka tidak perlu khawatir dengan harga yang terlalu mahal atau terlalu murah.

Perusahaan yang menjual mobil bekas harus memiliki model bisnis yang baik untuk menentukan harga yang sesuai dan akurat, karena spesifikasi dan kondisi mobil bekas yang beragam. Model bisnis yang baik dalam menentukan harga akan membuat calon pembeli atau pelanggan semakin tertarik pada perusahaan, dan memberikan kenyamanan bagi mereka dalam menentukan spesifikasi dan harga yang diinginkan. Keakuratan harga dan kenyamanan ini dapat meningkatkan minat pelanggan untuk berbelanja di perusahaan, dan tentu saja akan memperkuat posisi finansial perusahaan.

## **Goals**

Untuk mengatasi masalah yang ada, perusahaan Syarah.com membutuhkan alat yang dapat membantu calon pembeli menentukan mobil yang mereka inginkan dengan melihat spesifikasi dan harga yang akurat. Variabel spesifikasi seperti merek mobil, tahun pembuatan, jarak tempuh dan lain-lain harus diperhitungkan untuk menentukan harga yang akurat. Dengan begitu, harga mobil dapat bersaing di pasaran dan perusahaan dapat memperoleh keuntungan yang maksimal.


####**Setelah memperoleh model optimal untuk dataset ini, dapat disimpulkan bahwa:**

1. Model optimal yang dipilih adalah Random Forest Regressor (sebelum hyper parameter tunning) dimana dari model ini menghasilkan score:
- **RSME: 18544.323207**
- **MAE:	11601.684861**
-**MAPE;	0.216333**
- **R-Square = 0.779479**

2. Hasil model Random Forest Regression ketika tunning meruubah parameter default menjadi:
* **model__min_samples_leaf : 2**
* **max_depth : 8**
* **n_estimators : 200**

*Namun yang dipilih adalah model default dikarenakan model menurun performanya setelah dilakukan hyperparameter tuning.*

3. Variabel target "Price" yang memiliki nilai 0 tidak digunakan dalam pemodelan karena bersifat nego karena dalam Machine Learning kita membutuhkan angka yang pasti.
Berdasarkan Evaluasi Matriks, model ini memiliki kesalahan sekitar 11601 SAR (dari MAE) atau 21% (dari MAPE) prediksi akan menyimpang.

####**Batasan atau limitasi model model, yaitu:**

- Semakin sedikit merek mobil yang dijual, model akan semakin sulit untuk memprediksi harga.
- Untuk mobil yang ingin dijual di bawah 10k SAR atau mobil dengan harga diatas 183125 SAR, model ini tidak cocok untuk digunakan.
- Model diatas tidak cocok untuk mobil keluaran tahun 2005 kebawah.
- Model ini dapat diimporvisasi agar menghasilkan prediksi yang lebih baik lagi, namun kita dapat melakukan A/B testing terhadap model yang sudah dibuat ini untuk mengetahui tingkat efektivitas penggunaan model terhadap peningkatan jumlah penjualan mobil bekas ini. Nantinya, dari hasil A/B testing kita akan mendapatkan insight lain terkait hal apa saja yang dapat diperbaiki pada model.

### **Untuk memperbaiki hasil prediksi, beberapa hal yang dapat dilakukan adalah:**

1. Menilai dan membagi error yang muncul ke dalam dua kategori, overestimasi dan underestimasi. Selanjutnya, memeriksa bagaimana error tersebut terkait dengan setiap variabel bebas. Ini akan membantu mengungkap aspek dan faktor-faktor yang menyebabkan tingginya error dan memberikan peluang untuk melakukan ulang modeling dengan menggunakan teknik perbaikan fitur yang berbeda.
2. Menambahkan sumber data agar model memiliki lebih banyak informasi untuk dipelajari, yaitu dengan menambahkan data teraktual tentang mobil bekas di Arab Saudi.
3. Menambahkan fitur yang memiliki korelasi dengan harga mobil, seperti kondisi mobil, garansi resmi, dan lain-lain.
4. Menentukan perbedaan antara mobil yang dikategorikan sebagai klasik dan mobil biasa yang digunakan untuk keperluan sehari-hari, karena hal ini akan mempengaruhi kaitan antara price dan mileage. Contohnya, sebuah mobil tahun 1980 akan memiliki harga yang lebih tinggi dibandingkan dengan mobil tahun 2007, tetapi membutuhkan pengetahuan domain untuk mengkategorikan mobil sebagai klasik.
5. Menyatakan opsi untuk membuat model tersendiri bagi mobil mewah atau fokus pada penjualan mobil biasa untuk kebutuhan sehari-hari, karena kehadiran data mobil mewah dapat memberikan dampak signifikan terhadap model.
6. Penambahan jumlah data perlu diberikan perhatian pada merek mobil yang sedikit jumlahnya dan harganya mahal. Sedikitnya jumlah data sangat mempengaruhi hasil model akhir yang diperoleh untuk sedikitnya merek mobil.
7. Pada masa depan, model ini perlu dibantu oleh model klasifikasi yang memiliki variabel target adalah penjualan yang "menguntungkan atau tidak" berdasarkan nilai harga mobil yang telah terjual.



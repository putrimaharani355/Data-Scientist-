# Company Coach **Cleaning Data**

### Sumber data
Data yang digunakan adalah data invoice perusahaan. Data ini terdiri dari 1712 dan terdiri dari kolom **id_order, id_produk, nama_produk, kategori_produk, tanggal_pembelian, kuantitas, total_harga, PPN, bayar_cash, metode_bayar**

### Study Case 
Proyek ini berfokus pada **proses pembersihan data** dari data invoice untuk memastikan data yang digunakan dalam analisis dan pengembangan model prediksi berada dalam kondisi **bersih, konsisten, dan siap digunakan**.


### Tahap
1. Import dan Load Dataset <br>
Dataset dibaca dari file Dataset dengan menggunakan pandas.
2. Explorasi Awal <br>
Menggunakan df.head(), df.info(), dan df.describe() untuk melihat struktur dan ringkasan data.
3. Pembersihan Nilai Hilang <br> 
Mengisi missing values pada kolom kuantitas dan total_harga dengan nilai median (edian tidak terpengaruh outlier). Kolom PPN diisi dengan nilai tetap 0.1, kemungkinan karena itu adalah nilai pajak default.
4. Menghapus kolom tidak dibutuhkan <br>
Kolom bayar_cash dihapus dikarenakan tidak relebvan
5. Tipe Data diubah sesuai kebutuhan<br>
tanggal_pembelian: diubah ke tipe datetime agar bisa digunakan dalam sort, group by hari, dsb.<br>
kategori_produk: diubah menjadi kategori (baik untuk efisiensi dan pemodelan).<br>
kuantitas dan total_harga: diubah ke integer 64-bit.<br><br>
# Company Coach **Regresi** 

### Sumber data 
Dataset berisi data penjualan beberapa produk selama 1 bulan terakhir serta total penjualan harian. Berisi 32 data yang terdiri dari **Day, Diabetasol Coklat 1 kg, Fitbar Multigrain raisin 22 gram, Hydro Coco Original 500 ml, Slim & Fit Milk 312 gr, Daily Sales**

### Study Case 
Tim bisnis berencana membuat **promo diskon** untuk salah satu produk, namun khawatir akan terjadi **penurunan penjualan** pada hari berikutnya.
Untuk mendukung pengambilan keputusan, dilakukan **pengembangan model prediksi** yang dapat memperkirakan **penjualan produk untuk hari berikutnya**, sehingga hasil prediksi ini dapat digunakan tim bisnis dalam merancang strategi promosi yang lebih tepat.

### Tahap 
1. Load Data dan Library <br>
   Mengimpor library penting (pandas, numpy, matplotlib, seaborn, sklearn) dan membaca dataset 
2. Visualisasi Awal<br>
   Membuat scatterplot antara variabel Diabetasol Coklat 1 kg dengan Daily Sales untuk melihat pola hubungan antar variabel.
3. Pembersihan Data<br>
   Menghapus data kosong (NaN) pada kolom Diabetasol Coklat 1 kg menggunakan metode dropna() untuk memastikan kualitas data.
4. Penentuan Fitur dan Target<br>
   Menetapkan Diabetasol Coklat 1 kg sebagai fitur (X) dan Daily Sales sebagai target (y) untuk model prediksi.
5. Split Data<br>
   Membagi data menjadi 70% training set dan 30% testing set, serta melakukan reshaping agar sesuai dengan format input model.
6. Pembuatan Model <br>
  Melatih model Linear Regression menggunakan training set untuk mempelajari hubungan antara fitur dan target.
7. Prediksi dan Visualisasi Hasil <br>
  Melakukan prediksi terhadap testing set dan memvisualisasikan perbandingan antara data aktual dan data prediksi menggunakan grafik garis.
8. Evaluasi Model <br>
  Menghitung Mean Squared Error (MSE) untuk mengukur akurasi model, serta menampilkan intercept dan coefficient dari model regresi.

### Hasil 
1. Scatter Plot antara penjualan diebetasol coklat dengan total penjualan harian
![Image](https://github.com/user-attachments/assets/5a3fce56-7347-4e8a-8408-aca4082514c1)
Plot tersebut menunjukkan **penjualan diabetasol coklat memiliki korelasi positif dengan penjualan harian. Yang dapat disimpulkan semakin tinggi penjualan produk tersebut maka semakin tinggi pula total penjualan harian. berdasarkan plot ini Produk Diabetasol Coklat memliki pengaruh besar terhadap total penjualan harian, sehingga jika promo difokuskan pada produk ini dapat berdampak signifikan pada peningkatan penjualan.**
2. Perbandingan antara data aktual dan data prediksi
![Image](https://github.com/user-attachments/assets/4d35063d-d4a6-44eb-b04c-05476f72e47b)
Grafik tersebut menunjukkan **Model prediksi telah memprediksi data dengan benar.**
3. Mean Squared Error (MSE), Intercept, Coefficient
Mean Squared Error: 5646943705294.958 <br>
Intercept of the model: 6728389.623898853 <br>
Coefficient of the line: [1.0712553] <br> 
   

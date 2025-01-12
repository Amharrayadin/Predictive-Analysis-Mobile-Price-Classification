# Laporan Proyek Machine Learning - Muhamad Amhar Rayadin

## Domain Proyek
Dalam dunia teknologi yang terus berkembang, produsen perangkat mobile menghadapi tantangan besar dalam menentukan segmen harga yang sesuai untuk produk mereka. Kesalahan dalam penetapan harga dapat menyebabkan hilangnya daya saing di pasar yang semakin kompetitif. Di sisi lain, konsumen sering kali kesulitan memilih perangkat yang sesuai dengan kebutuhan dan anggaran mereka, mengingat banyaknya variasi spesifikasi dan harga yang tersedia. Masalah ini menciptakan kebutuhan akan solusi berbasis data yang mampu memberikan panduan yang lebih objektif dan efisien.

Sebagai respons terhadap kebutuhan ini, proyek ini berfokus pada pengembangan model prediktif yang memanfaatkan dataset Mobile Price Classification dari Kaggle. Dengan model ini, diharapkan kategori harga perangkat mobile dapat diklasifikasikan secara akurat berdasarkan spesifikasi teknisnya. Hasil dari model ini dapat memberikan manfaat besar, baik bagi produsen untuk menetapkan strategi pemasaran yang lebih efektif maupun bagi konsumen untuk membuat keputusan pembelian yang lebih tepat.

Persaingan yang semakin ketat membuat solusi berbasis data seperti machine learning menjadi penting. Teknologi ini memungkinkan klasifikasi harga perangkat dilakukan secara efisien dan akurat. Dengan demikian, model ini tidak hanya berperan dalam meningkatkan efisiensi pengambilan keputusan, tetapi juga memberikan produsen keunggulan kompetitif yang signifikan di pasar.

## Business Understanding
Implementasi model ini dapat memberikan manfaat besar dalam mendukung pengambilan keputusan strategis. Produsen dapat menentukan spesifikasi yang optimal untuk segmen pasar yang ditargetkan, sedangkan konsumen dapat memilih perangkat yang paling sesuai dengan preferensi mereka. Selain itu, model ini dapat digunakan untuk merumuskan strategi pemasaran dan produksi yang lebih efisien.

Model ini dirancang untuk memenuhi kebutuhan berbagai pemangku kepentingan, termasuk tim pemasaran yang dapat memanfaatkan wawasan dari model untuk merancang kampanye yang lebih terarah, manajemen produk yang memerlukan panduan dalam perencanaan produk baru, serta tim riset yang menggunakan hasil analisis untuk mengeksplorasi pasar secara lebih mendalam.

Dalam penerapan nyata, model ini dapat diintegrasikan ke dalam sistem rekomendasi atau digunakan sebagai alat analisis bagi produsen. Contohnya, saat merencanakan peluncuran produk baru, produsen dapat memprediksi kategori harga yang sesuai berdasarkan spesifikasi produk yang direncanakan. Konsumen juga dapat menggunakan model ini dalam aplikasi e-commerce untuk mendapatkan rekomendasi perangkat sesuai kebutuhan.

Data spesifikasi perangkat meliputi berbagai atribut teknis seperti kapasitas baterai (`battery_power`), kecepatan prosesor (`clock_speed`), RAM (`ram`), dan resolusi layar (`px_height` dan `px_width`). Target utama dari proyek ini adalah mengklasifikasikan perangkat ke dalam salah satu dari empat kategori harga: 0 (Low), 1 (Medium), 2 (High), dan 3 (Very High). Dengan demikian, cakupan proyek ini mencakup analisis mendalam terhadap hubungan antara spesifikasi teknis perangkat dengan kategori harga yang diharapkan.

### Problem Statements

1. Bagaimana memanfaatkan data spesifikasi perangkat yang meliputi berbagai atribut teknis seperti kapasitas baterai (`battery_power`), kecepatan prosesor (`clock_speed`), RAM (`ram`), dan resolusi layar (`px_height` dan `px_width`) untuk memprediksi kategori harga dengan akurasi tinggi?
2. Algoritma mana yang memberikan hasil terbaik dalam klasifikasi harga perangkat mobile?

### Goals

1. Membangun model prediktif untuk mengklasifikasikan perangkat ke dalam empat kategori harga: 0 (Low), 1 (Medium), 2 (High), dan 3 (Very High).
2. Mengidentifikasi algoritma terbaik berdasarkan evaluation matrix utamanya akurasi tiap alogoritma.

### Solution Statements

1. Menerapkan algoritma Logistic Regression, Decision Tree dan Random Forest.
2. Mengevaluasi model dengan classification report kemudian membandingkan akurasi tiap model.

## Data Understanding

Dataset yang digunakan adalah [Mobile Price Classification](https://www.kaggle.com/iabhishekofficial/mobile-price-classification) dari Kaggle.

### Ringkasan Dataset

-   **Jumlah data:** 2000 baris dengan 21 kolom.
    
-   **Informasi utama:** Dataset berisi fitur-fitur seperti kapasitas baterai, kecepatan prosesor, jumlah RAM, resolusi layar, dan kategori harga.
    
### Atribut Dataset

Berikut adalah tabel yang menjelaskan atribut pada dataset beserta deskripsinya:

| Nama Atribut     | Tipe Data  | Deskripsi                                                                 |
|------------------|------------|---------------------------------------------------------------------------|
| `battery_power`  | Numerikal  | Kapasitas baterai perangkat dalam mAh                                     |
| `blue`           | Kategorikal| Apakah perangkat mendukung Bluetooth (0: Tidak, 1: Ya)                   |
| `clock_speed`    | Numerikal  | Kecepatan prosesor dalam GHz                                             |
| `dual_sim`       | Kategorikal| Apakah perangkat mendukung dual SIM (0: Tidak, 1: Ya)                    |
| `fc`             | Numerikal  | Resolusi kamera depan dalam megapiksel                                   |
| `four_g`         | Kategorikal| Apakah perangkat mendukung 4G (0: Tidak, 1: Ya)                          |
| `int_memory`     | Numerikal  | Kapasitas memori internal dalam GB                                       |
| `m_dep`          | Numerikal  | Ketebalan perangkat dalam cm                                            |
| `mobile_wt`      | Numerikal  | Berat perangkat dalam gram                                              |
| `n_cores`        | Numerikal  | Jumlah inti prosesor                                                    |
| `pc`             | Numerikal  | Resolusi kamera belakang dalam megapiksel                               |
| `px_height`      | Numerikal  | Tinggi resolusi layar dalam piksel                                      |
| `px_width`       | Numerikal  | Lebar resolusi layar dalam piksel                                       |
| `ram`            | Numerikal  | Kapasitas RAM dalam MB                                                  |
| `sc_h`           | Numerikal  | Tinggi layar dalam cm                                                   |
| `sc_w`           | Numerikal  | Lebar layar dalam cm                                                    |
| `talk_time`      | Numerikal  | Durasi maksimal waktu bicara dalam jam                                  |
| `three_g`        | Kategorikal| Apakah perangkat mendukung 3G (0: Tidak, 1: Ya)                          |
| `touch_screen`   | Kategorikal| Apakah perangkat memiliki layar sentuh (0: Tidak, 1: Ya)                 |
| `wifi`           | Kategorikal| Apakah perangkat mendukung WiFi (0: Tidak, 1: Ya)                        |
| `price_range`    | Kategorikal| Kategori harga perangkat (0: Low, 1: Medium, 2: High, 3: Very High)      |

### Analisis EDA

1. **Persebaran Data Atribut Target dengan Value Counts**
   ![Persebaran Data Target](https://i.ibb.co.com/rsrsjpr/proce.png)
   Dari gambar di atas, terlihat bahwa output target memiliki persebaran data yang seimbang di setiap labelnya.

2. **Distribusi Fitur Numerikal Menggunakan Boxplot**
   ![Distribusi Boxplot Fitur Numerikal](https://i.ibb.co.com/f4LBLks/Desain-tanpa-judul-16.png)
   Dari hasil visualisasi pada boxplot, dapat dilihat bahwa fitur numerikal seperti `battery_power`, `int_memory`, dan `ram` memiliki distribusi yang baik.

3. **Distribusi Fitur Kategorikal dengan Histogram**
   ![Distribusi Histogram Fitur Kategorikal](https://i.ibb.co.com/YPBrQDT/Desain-tanpa-judul-17.png)
   Dari hasil visualisasi pada histogram, terlihat bahwa fitur kategorikal seperti `blue`, `four_g`, dan `n_cores` memiliki distribusi yang relatif seimbang.

4. **Korelasi antara Fitur dan Target Divisualisasikan dengan Heatmap**
   ![Heatmap Korelasi](https://i.ibb.co.com/JK7TVjp/corrr.png)
   Dari correlation matrix, terlihat bahwa sebagian besar atribut memiliki korelasi yang sangat rendah terhadap target, kecuali atribut `ram` yang memiliki korelasi sebesar 0.92.

## Data Preparation

Tahapan yang dilakukan:

1.  **Split Data** Tahap ini bertujuan untuk membagi dataset menjadi dua bagian, yaitu data latih (training set) dan data uji (testing set). Data latih digunakan untuk melatih model machine learning, sementara data uji digunakan untuk mengevaluasi performa model. Pada proyek ini, dataset dibagi dengan rasio 80% untuk data latih dan 20% untuk data uji.
    
2.  **Membuat Pipeline untuk Normalisasi Data** Pada tahap ini, pipeline dibuat untuk melakukan normalisasi fitur numerikal dan encoding fitur kategorikal secara otomatis. Normalisasi dilakukan menggunakan Standard Scaler, yang berfungsi untuk mengubah distribusi data numerikal sehingga memiliki rata-rata 0 dan standar deviasi 1. Teknik ini membantu meningkatkan performa model berbasis gradien. Untuk fitur kategorikal, digunakan One-Hot Encoding yang mengubah kategori menjadi vektor biner sehingga dapat digunakan oleh algoritma machine learning.
    Proses normalisasi dan encoding dilakukan menggunakan library scikit-learn untuk memastikan efisiensi dan konsistensi dalam pengolahan data. Pipeline ini mempermudah implementasi preprocessing secara terintegrasi dengan proses pelatihan model. - Dataset dibagi menjadi training set (80%) dan testing set (20%).

## Modeling

### Algoritma yang Digunakan

1. **Logistic Regression**  
   Logistic Regression adalah algoritma machine learning yang digunakan untuk memprediksi probabilitas kejadian dalam sebuah data yang bersifat kategorikal. Model ini bekerja dengan memodelkan hubungan antara satu atau lebih fitur independen dan variabel dependen melalui fungsi logistik (sigmoid). Logistic Regression sangat cocok digunakan sebagai baseline karena kesederhanaannya dan kemampuannya untuk memberikan hasil yang cukup baik pada data yang memiliki distribusi linier.

2. **Decision Tree**  
   Decision Tree adalah algoritma berbasis pohon keputusan yang membagi data menjadi subset berdasarkan fitur tertentu. Setiap percabangan pada pohon merepresentasikan kondisi pada fitur, dan setiap daun merepresentasikan hasil prediksi. Algoritma ini mampu menangkap hubungan non-linear dalam data, namun rentan terhadap overfitting jika pohonnya terlalu dalam.

3. **Random Forest**  
   Random Forest adalah algoritma ensemble yang menggabungkan prediksi dari banyak pohon keputusan untuk meningkatkan akurasi dan mengurangi overfitting. Algoritma ini bekerja dengan membangun beberapa pohon keputusan secara acak dan menggabungkan prediksinya melalui proses voting. Teknik ini sangat efektif untuk menangani data dengan banyak fitur dan hubungan non-linear.

### Proses dan Tahapan

- Setiap model dilatih menggunakan data latih (training set) yang telah diproses.
- Model diuji menggunakan data uji (testing set) untuk mengevaluasi performanya.
- Metrik seperti precision, recall, F1-score, dan akurasi digunakan untuk mengevaluasi kinerja masing-masing model.


## Evaluation

### Hasil Metrik Evaluasi

Hasil evaluasi untuk setiap algoritma yang digunakan dalam proyek ini adalah sebagai berikut:

| Model                | Accuracy | Macro Precision | Macro Recall | Macro F1-Score |
|----------------------|----------|-----------------|--------------|----------------|
| Logistic Regression  | 0.97     | 0.97            | 0.97         | 0.97           |
| Decision Tree        | 0.81     | 0.81            | 0.81         | 0.81           |
| Random Forest        | 0.87     | 0.87            | 0.87         | 0.87           |

### Visualisasi Perbandingan Akurasi
![Perbandingan Akurasi](https://i.ibb.co.com/wsCvqbb/output.png)
Berdasarkan visualisasi di atas, algoritma Logistic Regression adalah yang terbaik dengan akurasi tertinggi sebesar **97%**. Hal ini menunjukkan bahwa Logistic Regression mampu mempelajari pola data dengan sangat baik dan menghasilkan prediksi yang akurat untuk masalah klasifikasi harga perangkat mobile.

### Analisis Hasil Berdasarkan Konteks Data dan Proyek

1. **Keberhasilan Proyek**  
   Proyek ini dapat dikatakan berhasil karena model Logistic Regression mampu mencapai akurasi 97%, yang menunjukkan bahwa model ini sangat andal dalam mengklasifikasikan perangkat ke dalam kategori harga berdasarkan spesifikasi teknisnya.

2. **Pencapaian Tujuan**  
   Tujuan utama proyek adalah mengembangkan model prediktif untuk mengklasifikasikan perangkat ke dalam empat kategori harga dan mengidentifikasi algoritma terbaik berdasarkan evaluasi akurasi. Berdasarkan hasil evaluasi, Logistic Regression terbukti menjadi algoritma terbaik. Dengan demikian, proyek ini telah berhasil mencapai tujuannya.

3. **Relevansi dengan Masalah dan Solusi yang Diinginkan**  
   Masalah utama yang diangkat adalah kesulitan dalam menentukan segmen harga perangkat mobile yang optimal. Hasil model yang sangat akurat ini memberikan solusi berbasis data yang relevan dan praktis untuk produsen dan konsumen.  
   - **Produsen** dapat menggunakan model ini untuk menetapkan harga yang sesuai dengan spesifikasi produk baru, meningkatkan daya saing di pasar.  
   - **Konsumen** dapat memanfaatkan model ini untuk membuat keputusan pembelian yang lebih terinformasi.

4. **Konteks Data dan Implementasi Nyata**  
   Dataset yang digunakan memiliki persebaran data target yang seimbang, sehingga model tidak mengalami bias dalam memprediksi kategori harga. Hal ini memastikan bahwa hasil model dapat diimplementasikan dengan baik dalam sistem rekomendasi atau strategi pemasaran yang lebih efektif.

5. **Potensi Perbaikan**  
   Meskipun Logistic Regression menunjukkan hasil terbaik, model lain seperti Random Forest dapat dieksplorasi lebih lanjut dengan hyperparameter tuning untuk meningkatkan akurasinya. Selain itu, metrik lain seperti precision, recall, dan F1-score dapat digunakan untuk memberikan gambaran performa yang lebih holistik.
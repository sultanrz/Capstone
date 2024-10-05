# MODEL Daegu Apartment

### Capstone 3 Purwadhika by .....

# INTRO

Apartemen menjadi pilihan utama dalam pemenuhan kebutuhan perumahan di perkotaan karena keterbatasan lahan dan gaya hidup modern yang cepat. Harga apartemen dipengaruhi oleh berbagai faktor, baik internal (misalnya luas unit, jumlah kamar) maupun eksternal (misalnya lokasi, akses transportasi). Memahami bagaimana faktor-faktor ini mempengaruhi harga apartemen sangat penting bagi pemilik unit, agen properti, atau perusahaan untuk menentukan strategi penetapan harga yang tepat.
Penjual apartemen sering kali kesulitan menentukan harga jual yang sesuai dengan pasar. Jika harga terlalu tinggi, akan sulit menarik pembeli, sementara jika harga terlalu rendah, potensi keuntungan tidak akan maksimal. Oleh karena itu, memprediksi harga apartemen berdasarkan faktor-faktor tersebut menjadi solusi yang relevan untuk menyesuaikan dengan kondisi pasar yang dinamis.


# Problem Statement

Pemilik apartemen sering kali tidak memiliki pengetahuan yang cukup untuk menentukan harga jual yang tepat. Jika harga unit yang mereka tawarkan terlalu tinggi, maka mereka akan kesulitan menjual. Namun, jika terlalu rendah, mereka berpotensi kehilangan keuntungan besar. Oleh karena itu, tantangan utama adalah bagaimana kita dapat membantu pemilik apartemen memprediksi harga pasar yang ideal berdasarkan faktor-faktor internal dan eksternal yang relevan.

# Goals

Tujuan utama dari analisis ini adalah untuk membangun model yang dapat memprediksi harga apartemen berdasarkan fitur-fitur yang ada, seperti luas unit, jumlah kamar tidur, lokasi, dan faktor lainnya. Dengan model ini, kita bisa membantu penjual apartemen menentukan harga yang kompetitif di pasar, mengurangi risiko harga terlalu tinggi atau rendah, dan memungkinkan mereka untuk memaksimalkan keuntungan.
Selain itu, model ini juga diharapkan dapat mengidentifikasi faktor-faktor yang paling signifikan dalam memengaruhi harga, sehingga memberikan wawasan kepada pemilik atau pengembang tentang aspek mana yang harus diperhatikan dalam menentukan harga.


# Analytics Approach

Pendekatan yang digunakan adalah membangun model regresi yang dapat memprediksi harga apartemen berdasarkan berbagai fitur. Algoritma regresi akan diterapkan untuk mempelajari hubungan antara fitur-fitur apartemen dan harga jualnya.
Beberapa langkah yang akan dilakukan:
1.	Data Understanding: Menganalisis dataset untuk memahami fitur-fitur utama yang berpengaruh terhadap harga apartemen, seperti luas unit, jumlah kamar, lokasi, fasilitas, dan aksesibilitas.
2.	Data Cleaning & Feature Engineering: Membersihkan data dari nilai-nilai yang hilang atau tidak valid dan membuat fitur baru jika diperlukan (misalnya, mengonversi kategori seperti lokasi ke bentuk numerik yang bisa digunakan model).
3.	Modeling: Menggunakan algoritma regresi (misalnya, Linear Regression, Decision Tree Regressor, atau Random Forest Regressor) untuk memprediksi harga apartemen berdasarkan fitur yang ada.
4.	Evaluation: Menggunakan metrik evaluasi seperti Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), dan R-squared untuk mengukur performa model.
Dengan analisis ini, kita dapat memberikan rekomendasi harga yang lebih akurat untuk penawaran apartemen di platform.
Untuk kasus prediksi harga apartemen, metrik evaluasi akan sedikit berbeda dibandingkan dengan kasus klasifikasi seperti prediksi pembatalan pemesanan di industri hospitality. Karena ini adalah masalah regresi, metrik evaluasi yang relevan adalah metrik yang dapat mengukur seberapa baik model dalam memprediksi harga apartemen.


# Metric Evaluation

Pada kasus prediksi harga apartemen, berikut adalah beberapa metrik evaluasi yang digunakan untuk menilai performa model regresi:

1. **Mean Absolute Error (MAE):**  
   MAE mengukur rata-rata dari selisih absolut antara nilai aktual dan nilai prediksi. Semakin kecil nilai MAE, semakin baik model dalam memprediksi harga apartemen.

   **Rumus:**
   $$
   MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y_i}|
   $$

   - **Interpretasi:** Nilai MAE menunjukkan rata-rata kesalahan dalam satuan yang sama dengan harga apartemen. Kesalahan yang lebih kecil berarti prediksi model lebih akurat.

2. **Mean Squared Error (MSE):**  
   MSE adalah rata-rata dari selisih kuadrat antara nilai aktual dan nilai prediksi. MSE lebih sensitif terhadap outliers, sehingga kesalahan besar akan lebih ditekankan.

   **Rumus:**
   $$
   MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y_i})^2
   $$

   - **Interpretasi:** Semakin kecil MSE, semakin baik performa model. MSE menghukum kesalahan yang lebih besar dengan lebih keras, sehingga cocok untuk kasus dengan variasi harga yang besar.

3. **Root Mean Squared Error (RMSE):**  
   RMSE adalah akar dari MSE, yang juga sensitif terhadap outliers tetapi lebih mudah dipahami karena mengembalikan nilai kesalahan ke skala yang sama dengan target harga apartemen.

   **Rumus:**
   $$
   RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y_i})^2}
   $$

   - **Interpretasi:** Semakin kecil nilai RMSE, semakin akurat prediksi harga apartemen. Ini memberikan gambaran yang jelas tentang seberapa jauh prediksi berbeda dari harga aktual.

4. **R-squared (R²):**  
   R-squared menunjukkan proporsi variasi dalam target (harga apartemen) yang bisa dijelaskan oleh fitur-fitur yang digunakan oleh model. Nilainya berkisar antara 0 dan 1.

   **Rumus:**
   $$
   R^2 = 1 - \frac{\sum_{i=1}^{n} (y_i - \hat{y_i})^2}{\sum_{i=1}^{n} (y_i - \bar{y})^2}
   $$

   - **Interpretasi:** R² mendekati 1 menunjukkan bahwa model mampu menjelaskan sebagian besar variasi dalam harga apartemen. Nilai yang lebih rendah mengindikasikan bahwa ada fitur yang belum dimasukkan atau model belum optimal.

### Kesimpulan Metrik

- **MAE** memberikan pemahaman tentang seberapa besar kesalahan rata-rata yang dihasilkan model dalam prediksi harga apartemen.
- **MSE** dan **RMSE** lebih cocok untuk kasus dengan variasi harga yang besar dan memperhatikan outliers.
- **R-squared** memberikan gambaran umum tentang seberapa baik model dalam menjelaskan variasi harga berdasarkan fitur yang ada.

Dengan menggunakan metrik-metrik ini, kita dapat mengevaluasi performa model secara menyeluruh dan memberikan rekomendasi berdasarkan hasil evaluasi.


# Strategi dalam Konteks Bisnis

1. MAE akan sangat penting bagi pemilik apartemen yang ingin memaksimalkan keuntungan tanpa terlalu jauh dari harga pasar. Metrik ini memberikan gambaran tentang seberapa besar kesalahan harga yang harus mereka perkirakan.
2. RMSE bisa lebih bermanfaat bagi pemilik apartemen di segmen kelas atas, di mana kesalahan harga yang besar akan berdampak lebih besar pada keuntungan potensial.
3. R-squared membantu pemilik atau perusahaan properti dalam memahami apakah semua faktor relevan telah dimasukkan ke dalam model, sehingga dapat meningkatkan keputusan strategis.

# Library dataset

Untuk dataset yang digunakan merupakan data apartement diambil dari, source: https://drive.google.com/drive/folders/1fmkyfjrzuJNaH02sXhp5vUxqum9bH0Fx

Data: data_daegu_apartment.csv

# Preprocessing

Feature Engineering

Penanganan Nilai Hilang:
Untuk kolom 'YearBuilt', Anda membuat kolom ordinal 'YearBuilt_ord' dengan mengelompokkan nilai-nilai 'YearBuilt' ke dalam kategori ordinal berdasarkan rentang tahun. Ini membantu mengubah fitur kontinu menjadi fitur kategorikal yang terurut.

Encoding

1. One-Hot Encoding:

One-Hot Encoding diterapkan pada kolom-kolom kategorikal seperti 'HallwayType', 'TimeToSubway', 'SubwayStation', dan 'SalePrice_binned'. Teknik ini mengubah nilai-nilai kategorikal menjadi representasi numerik dengan membuat kolom baru untuk setiap kategori, sehingga model dapat memproses fitur kategorikal dengan lebih baik.

2. Ordinal Encoding:

Ordinal Encoding diterapkan pada kolom 'YearBuilt'. Teknik ini mengubah nilai-nilai 'YearBuilt' menjadi nilai ordinal yang mencerminkan urutan kategori, seperti rentang tahun, untuk membantu model memahami urutan atau tingkat keparahan dari fitur tersebut.

3. Tanpa Encoding:

Kolom-kolom numerikal seperti 'N_FacilitiesNearBy(ETC)', 'N_FacilitiesNearBy(PublicOffice)', 'N_SchoolNearBy(University)', 'N_Parkinglot(Basement)', 'N_FacilitiesInApt', 'Size(sqf)', dan 'YearBuilt' dipertahankan dalam bentuk aslinya tanpa encoding karena mereka sudah dalam format numerik yang bisa langsung digunakan oleh model regresi.
Scaling

4. Tanpa Scaling:


Karena Anda tidak menggunakan K-Nearest Neighbors (KNN) dan fokus pada model regresi, Anda tidak perlu menerapkan scaling pada fitur. Model regresi seperti Linear Regression, Random Forest, dan Gradient Boosting umumnya tidak memerlukan fitur untuk diskalakan.
Dengan langkah-langkah ini, data siap untuk proses pemodelan regresi tanpa perlu mempertimbangkan scaling jika model yang digunakan tidak membutuhkannya.

# BENCHMARK MODEL

Penjelasan Metrik Evaluasi:

1. Mean Absolute Error (MAE):

Menunjukkan rata-rata perbedaan absolut antara nilai prediksi dengan nilai sebenarnya. Dalam kasus ini, model Random Forest memiliki MAE terendah (15,039.58), menunjukkan bahwa prediksi harga apartemen rata-rata meleset sebesar sekitar 15.039 unit harga.


2. Mean Squared Error (MSE):

MSE memperhitungkan kuadrat dari selisih antara nilai prediksi dan nilai sebenarnya, sehingga memberikan penalti yang lebih besar untuk kesalahan prediksi yang lebih besar. Model dengan Random Forest juga menunjukkan MSE terendah, yang berarti lebih stabil dalam meminimalisir kesalahan besar.

3. Root Mean Squared Error (RMSE):

RMSE adalah akar kuadrat dari MSE, menunjukkan kesalahan prediksi dalam satuan yang sama dengan variabel target (dalam hal ini, harga). Lagi-lagi, Random Forest unggul dengan RMSE 20,248.20.

4. Mean Absolute Percentage Error (MAPE):

MAPE mengukur kesalahan rata-rata dalam bentuk persentase dari nilai sebenarnya. MAPE rendah pada Random Forest (7.93%) berarti model ini memiliki kesalahan prediksi yang relatif kecil dibandingkan harga sebenarnya.

5. R-squared (R²):

Mengukur seberapa baik model dapat menjelaskan variabilitas data. Semua model memiliki R² sekitar 0.95-0.96, menunjukkan bahwa mereka dapat menjelaskan sekitar 95-96% variabilitas harga apartemen, dengan Random Forest dan Gradient Boosting memiliki performa yang sangat baik.

6. Fit Time & Score Time:

Fit Time menunjukkan waktu yang dibutuhkan untuk melatih model, dan Score Time menunjukkan waktu yang dibutuhkan untuk memprediksi data uji. Random Forest memiliki fit time lebih panjang dibandingkan model lainnya, tetapi hasil prediksi dan metrik evaluasi menjadikannya sebanding.

Dengan hasil di atas, Random Forest tampaknya menjadi model yang paling cocok karena memiliki kesalahan prediksi yang lebih rendah dan mampu menjelaskan variabilitas data dengan baik.


# TUNNING HYPER PARAMETER

#### Kesimpulan Hasil

1. Best Parameters:

learning_rate: 0.1
max_depth: 5
min_samples_split: 10
n_estimators: 100
Kesimpulan: Parameter hyperparameter terbaik yang ditemukan adalah learning_rate 0.1, max_depth 5, min_samples_split 10, dan n_estimators 100. Ini menunjukkan bahwa model berperforma paling baik dengan pengaturan ini, yang memungkinkan model untuk belajar dari data secara efektif tanpa overfitting.

2. Best Score (Negative MSE):

Nilai: -442117730.5451827
Kesimpulan: Skor terbaik (dalam hal Negative MSE) adalah -442117730.5451827, yang menunjukkan bahwa model dengan parameter terbaik memiliki MSE terendah yang terukur dalam evaluasi cross-validation.

3. Test Mean Squared Error (MSE):

Nilai: 404781355.4413911
Kesimpulan: MSE pada data uji adalah 404781355.4413911. Nilai ini menunjukkan rata-rata dari kuadrat kesalahan prediksi model pada data uji. Meskipun MSE ini cukup besar, ini adalah indikasi seberapa baik model memperkirakan variasi dalam data uji.

4. Mean Absolute Error (MAE):

Nilai: 15103.448908797267
Kesimpulan: MAE adalah 15103.45, yang menunjukkan rata-rata kesalahan absolut dalam prediksi harga apartemen. Ini berarti rata-rata perbedaan antara harga sebenarnya dan harga yang diprediksi adalah sekitar $15,103.45. Nilai ini memberikan gambaran langsung tentang akurasi model dalam satuan yang sama dengan target.

5. Root Mean Squared Error (RMSE):

Nilai: 20119.178796397013
Kesimpulan: RMSE adalah 20119.18, yang merupakan akar kuadrat dari MSE. RMSE memberikan ukuran kesalahan prediksi yang lebih jelas dalam satuan yang sama dengan target. Nilai ini menunjukkan rata-rata deviasi prediksi dari nilai aktual, yang membantu dalam memahami sejauh mana model salah prediksi.

7. Mean Absolute Percentage Error (MAPE):

Nilai: 7.94%
Kesimpulan: MAPE adalah 7.94%, yang mengukur rata-rata kesalahan prediksi dalam persentase dari nilai aktual. Ini berarti model, secara rata-rata, memiliki kesalahan prediksi sekitar 7.94% dari harga sebenarnya. MAPE memberikan konteks tentang akurasi model dalam hal persentase kesalahan.

8. R-squared (R²):

Nilai: 0.9624656117934515
Kesimpulan: R² adalah 0.9625, yang menunjukkan bahwa model dapat menjelaskan sekitar 96.25% dari variasi dalam harga apartemen berdasarkan fitur yang digunakan. Nilai R² yang mendekati 1 menunjukkan bahwa model sangat baik dalam menangkap hubungan antara fitur dan harga apartemen, serta mampu menjelaskan sebagian besar variabilitas harga.

Kesimpulan Umum
Model Gradient Boosting Regressor dengan parameter terbaik menunjukkan performa yang sangat baik dalam memprediksi harga apartemen, dengan R² yang tinggi menunjukkan kemampuan model dalam menjelaskan variasi harga.
MAE dan RMSE menunjukkan bahwa model memiliki kesalahan prediksi yang relatif besar dalam nilai absolut, tetapi MAPE yang rendah menunjukkan akurasi yang baik dalam konteks persentase.
Meskipun MSE dan RMSE memiliki nilai yang cukup besar, ini penting untuk mengevaluasi dampak dari outliers dan besar kecilnya kesalahan prediksi.
Secara keseluruhan, hasil ini menunjukkan bahwa model yang dioptimalkan dengan GridSearchCV memiliki performa yang solid dalam memprediksi harga apartemen dan dapat menjadi alat yang berguna untuk analisis harga di pasar apartemen.

# Pengujian, Kesimpulan, dan Rekomendasi

### Conclusion and Recommendation

1. Kesimpulan:

Akurasi Model: Model regresi harga apartemen dan model klasifikasi kategori harga telah memberikan hasil yang memuaskan. Prediksi harga untuk data baru sebesar $82,693.72 dengan kategori harga "Sangat Rendah" menunjukkan bahwa model dapat mengestimasi harga apartemen dengan baik. Metrik evaluasi seperti Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), dan R-squared (R²) menunjukkan bahwa model telah mencapai performa yang baik dalam hal akurasi prediksi dan kemampuan menjelaskan variasi harga.

Parameter Terbaik dan Penilaian Model: Melalui GridSearchCV, parameter terbaik untuk model Gradient Boosting Regressor ditemukan, yaitu learning_rate=0.1, max_depth=5, min_samples_split=10, dan n_estimators=100. Nilai negatif MSE yang diperoleh selama pencarian parameter menunjukkan bahwa model yang terlatih memiliki performa yang sangat baik dengan MSE pada data uji sebesar 404,781,355.44.

2. Rekomendasi:

Penggunaan Model: Model ini sangat cocok untuk digunakan dalam situasi di mana estimasi harga apartemen diperlukan. Ini termasuk aplikasi di pasar real estate untuk menentukan harga jual atau membeli apartemen. Model ini dapat diandalkan dalam kondisi yang serupa dengan data pelatihan.

Keandalan dan Batasan: Keandalan model mungkin menurun jika data baru sangat berbeda dari data pelatihan atau dalam kondisi pasar yang berubah secara signifikan. Model ini mungkin tidak optimal untuk data di luar rentang yang telah dilatih atau untuk jenis apartemen yang sangat berbeda.

Dampak pada Proses Bisnis: Implementasi model ini dapat meningkatkan efisiensi dan akurasi dalam proses penetapan harga apartemen. Penjual dapat menentukan harga yang lebih kompetitif dan pembeli dapat memahami nilai pasar dengan lebih baik. Ini berpotensi meningkatkan transparansi dan kepuasan dalam transaksi real estate.

Pekerjaan Mendatang: Proyek ini memiliki keterbatasan terkait cakupan data, model yang digunakan, dan batasan waktu. Untuk meningkatkan model di masa depan, disarankan untuk memperluas dataset dengan lebih banyak fitur relevan, mencoba model-model canggih lainnya, dan melakukan pembaruan secara berkala untuk menangkap perubahan dalam tren pasar. Penelitian lebih lanjut juga bisa mencakup validasi model pada dataset yang lebih besar atau berbeda untuk meningkatkan generalisasi dan akurasi.

# Prediksi Harga Apartemen di Kota Daegu Korea Selatan

# Business Problem Understanding
## Context
Daegu Merupakan salah satu kota metropolitan di Korea Selatan, memiliki populasi 2.4 juta jiwa membuat Daegu menjadi kota dengan populasi terbesar ke 4 setelah Seoul, Busan dan Incheon (https://www.worldometers.info/world-population/south-korea-population/) (https://www.daegu.go.kr/english/index.do?menu_id=00939612). Apartemen menempati sekitar 75% dari total transaksi perumahan dalam setahun, yang merupakan ruang hidup representatif bagi sebagian besar warga(https://journal.khousing.or.kr/articles/article/NGwa/). Hal ini disebabkan karena terbatasnya lahan yang tersedia di Korea Selatan, membuat pengembang properti membangun propertinya tinggi ke atas. Pasar properti di Daegu, khususnya apartemen mengalami pertumbuhan yang signifikan seiring dengan meningkatnya urbanisasi dan permintaan akan hunian yang nyaman dan modern. Namun, dengan meningkatnya persaingan, penting bagi pengembang properti dan pemilik apartemen untuk memahami dinamika pasar dan preferensi pelanggan.

## Problem Statement
Para agen properti di Daegu menghadapi tantangan dalam menentukan harga sewa dan jual yang kompetitif serta memahami faktor-faktor yang mempengaruhi permintaan dan penawaran. Tanpa pemahaman yang mendalam tentang tren pasar, preferensi penyewa/pembeli, dan harga pasar yang tepat, mereka berisiko kehilangan potensi keuntungan dan mengalami kesulitan dalam menarik pelanggan. Oleh karena itu dibutuhkan model untuk memprediksi harga yang sesuai agar agen properti dapat dengan mudah menentukan harga dan memenuhi target penjualan.

## Goals
Berdasarkan permasalahan tersebut, para agen properti memerlukan model yang dapat memprediksi harga pasaran yang sesuai dengan fasilitas yang diberikan oleh setiap apartemen. Model ini harus dibuat sebaik mungkin berdasarkan berbagai parameter seperti lokasi, ukuran, fasilitas, dan kondisi pasar. Dengan demikian para agen properti dapat menentukan harga sewa/jual yang lebih kompetitif, dan memberikan kepuasan terhadap penyewa/pembeli.

## Analytic Approach
Jadi yang akan dilakukan adalah menganalisis data untuk menemukan pola dari fitur-fitur yang tersedia yang akan membedakan satu apartemen dengan apartemen lainnya. Kemudian membuat suatu model regresi yang akan membantu para agen properti untuk menentukan harga sewa/jual apartemen yang sesuai dengan fitur-fiturnya.

## Metric Evaluation
Evaluasi metric yang akan digunakan adalah :
- **MAE** : Mean Absolute Error. Mengukur rata-rata kesalahan absolut antara harga prediksi dengan harga aktual untuk mengukur akurasi model prediksi. Semakin nilai MAE mendekati 0 atau semakin kecil nilai MAE, hasilnya akan semakin bagus.
- **RMSE** : Root Mean Squared Error. Mengukur akar kuadrat dari rata-rata kesalahan kuadrat untuk memberikan penalti lebih besar pada kesalahan yang lebih besar. Semakin nilai RMSE mendekati 0 atau semakin kecil nilai RMSE hasilnya akan semakin bagus.
- **MAPE** : Mean Absolute Percentage Error. Mengukur kesalahan prediksi dalam bentuk persentase dari nilai aktual. Semakin kecil presentase MAPE semakin bagus juga hasilnya.
- **R-square** : Menilai proporsi variansi dalam data harga yang dapat dijelaskan oleh model. Semakin nilai R-square mendekati 1 semakin bagus modelnya
- **K-fold cross validation** juga digunakan sebagai metode evaluasi performa model yang dilakukan dengan membagi dataset menjadi 5 partisi yang sama besar lalu model akan dilatih pada 4 partisi dan diuji pada partisi yang tersisa. Prosedur ini akan dilakukan sebanyak 5 kali dengan partisi yang berbeda-beda sebagai data validasi dan data training sehingga akhirnya performa model akan dihitung berdasarkan rata-rata performa. Metode ini berguna untuk menghindari overfitting atau underfitting dan untuk mendapatkan generalisasi model yang lebih baik.

# Hasil 
| Model | Test R2 |	Test RMSE |	Test MAE |	Test MAPE |
| --- | --- | --- | --- | --- |
| Random Forest Before Tuning |	0.78342 |	47965.312352 |	38929.266181 |	0.1989 |
| Random Forest | 0.784564 |	47838.45505 |	38735.30816 |	0.198424 |

Metrik evaluasi yang digunakan pada model meliputi nilai R2, RMSE, MAE, dan MAPE. Berdasarkan nilai MAPE yang dihasilkan setelah tuning hyperparameter, yaitu sekitar 19.84%, dapat disimpulkan bahwa apabila model ini digunakan untuk memperkirakan harga apartemen di Daegu dalam rentang harga yang serupa dengan data pelatihan (maksimal harga 585,840 Won), maka estimasi harga rata-rata akan meleset sekitar 19.84% dari harga sebenarnya. 

# Rekomendasi
Untuk meningkatkan kinerja model dan memperoleh hasil prediksi yang lebih akurat, kami menyarankan beberapa langkah berikut:
- **Penambahan Fitur yang Lebih Korelatif dengan Target**: Menambahkan fitur yang memiliki korelasi tinggi dengan target ('SalePrice'), seperti letak lantai dan jenis penghangat dan pendingin ruangan, dapat meningkatkan kemampuan model dalam memprediksi harga apartemen. Selain itu, memperbarui dataset dengan data terkini dari apartemen di kota Daegu akan meningkatkan kapasitas prediksi model.
- **Penggunaan Model Deep Learning yang Lebih Kompleks**: Dengan penambahan data yang signifikan, model deep learning yang lebih kompleks, seperti Convolutional Neural Networks (CNN) atau Long Short-Term Memory (LSTM), dapat dieksplorasi. Namun, jika jumlah data dan fitur tetap seperti dataset saat ini, kompleksitas tambahan mungkin tidak memberikan peningkatan hasil yang signifikan.
- **Penggunaan Teknik Ensemble**: Menggabungkan hasil dari beberapa model dengan teknik ensemble, seperti stacking atau boosting, dapat meningkatkan akurasi prediksi. Metode ini memanfaatkan kekuatan dari berbagai model untuk menghasilkan hasil yang lebih robust dan andal.
- **Optimisasi Hyperparameter**: Menggunakan teknik optimisasi hyperparameter, seperti Bayesian Optimization, untuk model yang ada (misalnya, XGBoost atau Random Forest) dapat membantu menemukan kombinasi parameter yang optimal, sehingga meningkatkan kinerja model secara keseluruhan.


# Prediksi Harga Apartemn di Kota Daegu Korea Selatan

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
- MAE : Mean Absolute Error. Mengukur rata-rata kesalahan absolut antara harga prediksi dengan harga aktual untuk mengukur akurasi model prediksi. Semakin nilai MAE mendekati 0 atau semakin kecil nilai MAE, hasilnya akan semakin bagus.
- RMSE : Root Mean Squared Error. Mengukur akar kuadrat dari rata-rata kesalahan kuadrat untuk memberikan penalti lebih besar pada kesalahan yang lebih besar. Semakin nilai RMSE mendekati 0 atau semakin kecil nilai RMSE hasilnya akan semakin bagus.
- MAPE : Mean Absolute Percentage Error. Mengukur kesalahan prediksi dalam bentuk persentase dari nilai aktual. Semakin kecil presentase MAPE semakin bagus juga hasilnya.
- R-square : Menilai proporsi variansi dalam data harga yang dapat dijelaskan oleh model. Semakin nilai R-square mendekati 1 semakin bagus modelnya
- K-fold cross validation juga digunakan sebagai metode evaluasi performa model yang dilakukan dengan membagi dataset menjadi 5 partisi yang sama besar lalu model akan dilatih pada 4 partisi dan diuji pada partisi yang tersisa. Prosedur ini akan dilakukan sebanyak 5 kali dengan partisi yang berbeda-beda sebagai data validasi dan data training sehingga akhirnya performa model akan dihitung berdasarkan rata-rata performa. Metode ini berguna untuk menghindari overfitting atau underfitting dan untuk mendapatkan generalisasi model yang lebih baik.

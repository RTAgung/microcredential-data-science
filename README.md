# Hasil Tugas Akhir

### Branch
- [master](https://github.com/RTAgung/microcredential-data-science/tree/master) = semua berkas-berkas pelatihan penuh
- [deploy](https://github.com/RTAgung/microcredential-data-science/tree/deploy) = hasil tugas akhir yang telah di deploy

## Analisis Prediksi Tingkat Curah Hujan Tahunan

Data diambil dari website resmi Badan Pusat Statistik mengenai iklim Indonesia yang berupa :

- Jumlah Curah Hujan dan Jumlah Hari Hujan di Stasiun Pengamatan BMKG, 2011-2015 (https://www.bps.go.id/statictable/2017/02/08/1959/jumlah-curahhujan-dan-jumlah-hari-hujan-di-stasiun-pengamatan-bmkg-2011-2015.html)
- Tekanan Udara dan Penyinaran Matahari di Stasiun Pengamatan BMKG, 2011-2015 (https://www.bps.go.id/statictable/2017/02/09/1962/tekanan-udaradan-penyinaran-matahari-di-stasiun-pengamatan-bmkg-2011-2015.html)
- Kecepatan Angin dan Kelembaban di Stasiun Pengamatan BMKG, 2011-2015 (https://www.bps.go.id/statictable/2017/02/08/1960/kecepatanangin-dan-kelembaban-di-stasiun-pengamatan-bmkg-2011-2015.html)
- Suhu Minimum, Rata-Rata, dan Maksimum di Stasiun Pengamatan BMKG (oC), 2011-2015 (https://www.bps.go.id/statictable/2017/02/09/1961/suhu-minimumrata-rata-dan-maksimum-di-stasiun-pengamatan-bmkg-oc-2011-2015.html)

### Preprocessing
- Exploratory Data Analysis
- Handling Duplicated Data
- Handling Missing Value
    - Drop NaN pada Fitur Target
    - Imputation pada Fitur Prediktor _(menggunakan linear regression)_
- Handling Outlier _(winsorizing)_
- Feature Selection _(correlation value)_
- Feature Scaling _(standardization)_
- Splitting data
    - Data Training (80%) = 130 sample
    - Data Testing (20%) = 32 sample

### Model Selection
Using Grid Search CV
- Linear Regression
- Polynomial Regression (degree=2)
- Support Vector Machine (C=3, degree=1, gamma=0.06)
- Random Forest (max_depth=150, max_features='log2', n_estimators=10)
- Gradient Boosting (learning_rate=0.06, max_depth=2, n_estimators=50, subsample=0.3)

Score :
|                          | 1-MAE    | 1-MSE    | 1-RMSE   | R2 Score |
|--------------------------|----------|----------|----------|----------|
| Linear   Regression      | 0.584569 | 0.735168 | 0.485381 | 0.65869  |
| Polynomial   Regression  | 0.529741 | 0.673286 | 0.428411 | 0.578939 |
| Support   Vector Machine | 0.517861 | 0.663731 | 0.420113 | 0.566624 |
| Random   Forest          | 0.452804 | 0.549725 | 0.328975 | 0.419697 |
| Gradient   Boosting      | 0.500119 | 0.627905 | 0.390004 | 0.520453 |

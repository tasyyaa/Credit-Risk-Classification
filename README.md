# Laporan Proyek Machine Learning - Tasya Putri Aliya
**Credit Risk Classification**
Laporan ini disusun untuk memenuhi persyaratan *Submission* Proyek Pertama Machine Learning Terapan Dicoding.

## Domain Proyek
  Topik yang diangkat dari proyek ini yaitu mengenai bidang ekonomi dan bisnis yang berfokus pada evaluasi risiko kredit suatu nasabah di perbankan. Evaluasi ini bertujuan untuk menentukan bahwa nasabah layak untuk mendapatkan kredit atau tidak.
### Latar Belakang
  Sebagai negara berkembang, Indonesia, dalam meningkatkan pertumbuhan ekonomi tidak dapat dipisahkan dari peran bank. Salah satu peran bank yang dianggap cukup penting adalah pemberian kredit kepada masyarakat. Hal ini dapat mendukung perekonomian dan meningkatkan standar hidup masyarakat [1]. Namun, tidak semua kredit yang diberikan dapat berjalan dengan lancar. Menurut data Otoritas Jasa Keuangan (OJK) pada tahun 2015-2019, rata-rata jumlah kredit macet atau pinjaman bermasalah di Indonesia berada pada angka 2.37%-3.93% dan menurut data Bank Mandiri sendiri besar kredit macet di Bank Mandiri mencapai Rp1,2 Triliun [2]. Tentu hal tersebut bukanlah angka yang kecil. 
  
  Besarnya total kredit macet ini jelas menjadi suatu perhatian bagi bank karena banyaknya dampak buruk dari adanya kredit macet ini. Dampak buruk tersebut, antara lain arus kas yang tidak lancar. Hal ini dapat menyebabkan bank tidak lagi mampu memberikan kredit kepada nasabah lainnya. Selain itu, peningkatan tingkat kredit macet dapat mengganggu profitabilitas perusahaan [3]. Salah satu ukuran profitabilitas yang menurun adalah Return on Assets (ROA), penurunan ini disebabkan oleh kinerja perusahaan yang kurang optimal dalam menggunakan asetnya. Kemudian, Loan to Deposit Ratio adalah ukuran kemampuan bank untuk membiayai kembali dana yang ditarik oleh deposan, dan memiliki dampak positif pada bank dalam bentuk pendapatan, misalnya dalam bentuk kredit. Tingkat likuiditas yang rendah di sebuah bank dapat menyebabkan perubahan dalam profitabilitas perusahaan yang menurun [4]. Hal ini terjadi karena perusahaan tidak mampu mendistribusikan dana tersebut.
  
  Maka dari itu, untuk dapat menyelesaikan permasalahan tersebut dilakukan penilaian credit risk dari nasabah yang akan melakukan kredit di bank untuk menilai kelayakan suatu nasabah dalam mendapatkan kredit dan kemampuannya dalam menyelesaikan kredit tersebut. Selain itu, semakin gentarnya credit risk ini juga disebabkan oleh ekonomi dunia berada dalam risiko krisis keuangan lainnya akibat evaluasi risiko kredit yang tidak efektif sebut IMF [5]. Betapa pentingnya evaluasi risiko kredit ini yang menjadi dasar dari dibuatnya program klasifikasi risiko kredit untuk dapat menyelesaikan permasalahan ini.

## Business Understanding
  Bagian ini akan membahas mengenai problem statements, goals, dan solution statements berdasarkan latar belakang yang telah dijabarkan.
### Problem Statements
  Berdasarkan latar belakang yang telah dijabarkan sebelumnya didapatkan tiga problem statements yang akan digunakan pada proyek ini, yaitu
1. Berdasarkan seluruh kriteria yang dimiliki oleh nasabah, kriteria apa yang paling mempengaruhi kelayakan nasabah dari kredit macet?
2. Berdasarkan seluruh kriteria yang dimiliki oleh nasabah, kriteria apa yang membuat suatu nasabah dilabeli dapat memiliki risiko kredit macet?
3. Model klasifikasi apa yang dapat berjalan baik untuk mengklasifikasikan permasalahan evaluasi risiko kredit ini?
### Goals
  Berdasarkan latar belakang serta problem statements yang telah dirancang, maka dibuatlah goals dari proyek ini, yaitu:
1. Untuk mengetahui kriteria (feature) yang paling mempengaruhi kelayakan dari nasabah dari adanya kredit macet.
2. Untuk mengetahui kriteria (feature) yang membuat suatu nasabah dilabeli dapat memiliki risiko kredit macet.
3. Untuk membuat model klasifikasi Machine Learning yang memiliki akurasi baik dalam menyelesaikan permasalahan evaluasi risiko kredit.
### Solution Statements
Berdasarkan problem statements dan goals yang telah dibuat, maka terdapat solution statements untuk menyelesaikannya pada proyek ini, yaitu:
1. Melakukan data understanding dan data preparation sebelum menggunakan data ke dalam model agar dataset sudah bersih dan layak untuk digunakan.
2. Membangun dan mengevaluasi beberapa model klasifikasi Machine Learning seperti Decision Tree, K-Nearest Neighbors, Backpropagation Neural Network, Random Forest, dan Logistic Regression untuk menemukan model yang paling akurat dalam memprediksi risiko kredit macet.
3. Melakukan validasi dan pengujian model menggunakan metode cross-validation dan evaluasi metrik seperti akurasi, precision, recall, dan F1-score untuk memastikan model yang dipilih memiliki kinerja yang baik.
   
## Data Understanding
Dataset yang digunakan pada proyek klasifikasi risiko kredit nasabah ini merupakan dataset yang dimiliki oleh [https://www.kaggle.com/ppb00x] yang dirilisnya di platform Kaggle tahun 2023 yang dapat diakses pada link berikut [https://www.kaggle.com/datasets/ppb00x/credit-risk-customers/data].

Pada tahap data understanding ini dilakukan beberapa tahapan yang bertujuan untuk dapat memehami lebih lanjut mengenai dataset yang sedang digunakan. Pertama-tama adalah penjelasan mengenai setiap variabel atau feature yang akan digunakan yang terdapat pada dataset ini

### Variabel-variabel pada Credit Risk dataset adalah sebagai berikut:
1. checking_status: The currently balance account
2. duration: duration of the credit payment, in months.
3. credit_history: Is the customer credit history. It can have the following values:
   - existing paid: currently credit process;
   - all paid: all the credit abre paid by the customer;
   - delayed previously: past delays at the credit payment;
   - critical/other existing credit: critical credit accounts;
   - no credits/all paid: customer that never gets credit.b
4. purpose: porpouse of the credit requested.
5. credit_amount: Amount of the credit requested
6. savings_status: Balance account of savings/ bond.
7. employment:How many years the customer has employed.
8. installment_commitment: Percentual that the customer cannot reach due to the income. When a customer takes a credit, the installment cannot ultrapass a percentual of customer income.
9. personal_status: if is divorced, married, etc.
10. other_parties: Another part involde on th credit, like guarantos ("fiador").
11. residence_since: How many year the customer has in the country.
12. property_magnitude: The good of the customer.
13. age: The age of the customer.
14. other_payment_plans: If the customer has another credit line and how the type (store, bank, etc).
15. housing:The housing customer type, could be own, for free or rent.
16. existing_credits: Number of existing credits at this bank.
17. job: This represents whats type of job the customer has. Could be skilled, unskilled resident, high qualify/self emp/mgmt and unemp/unskilled non res.
18. num_dependents: The number of depedents that live wth the customer.
19. own_telephone: If the customer has a telephone.
20. foreign_worker: If the customer is a foreign or not.
21. class: Our target. If the credit is good or bad to the bank.

### Data Information and Description
  Tahapan ini dilakukan untuk mengetahui berapa baris data yang dimiliki oleh dataset dan bagaimana tipe datanya. Berdasarkan hasil didapatkan bahwa data Credit Risk memiliki baris sejumlah **1000 data** dengan tiap variabelnya memiliki tipe data sebagai berikut
![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/40af5102-1f09-4ff1-a508-e6bdb95adc54)

  Berdasarkan hasil tersebut, terdapat **14 variabel** yang memiliki tipe data yang tidak sesuai yaitu **object**, seharusnya 14 variabel tersebut memiliki tipe data berupa **category**. 14 variabel tersebut dapat dilihat pada gambar di atas.
  Karena ketidaksesuaian tipe data tersebut, maka dilakukan penyesuaian tipe data sesuai dengan tipe data yang seharusnya yaitu category dan setelah perubahan tipe data maka hasilnya menjadi seperti berikut
  
![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/c7b00bc8-6db3-42d4-bd4c-9f6200b5214a)

Pada dasarnya variabel **own_telephone**, **foreign_worker**, dan **class** dapat dibuat menjadi tipe data bool, namun perubahan itu akan dilakukan pada tahap data preparation saja untuk memudahkan tahapan EDA.

### Explanatory Data Analysis (EDA)
  Explanatory Data Analysis merupakan tahapan yang bertujuan untuk dapat memahami karakteristik dari data yang dimiliki. Tahapan ini akan sangat membantu untuk dapat memahami apa saja yang harus dilakukan dengan karakteristik data yang ada termasuk proses apa yang cocok untuk tahap data preparation. EDA sendiri terdiri atas dua jenis, yaitu **Univariate Analysis** dan **Multivariate Analysis**. Berikut hasil dari EDA ini
- **Univariate Analysis**
  Yaitu suatu analisis untuk jenis analisis data yang melibatkan pemeriksaan dan deskripsi satu variabel yang bertujuan untuk memahami dan menggambarkan karakteristik dasar dari variabel tersebut. Hasil dari univariate analysis dataset ini adalah
  - Categorical Features
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/3870d547-ba52-4160-9386-3088eaddea36)
    
    Berdasarkan hasil grafik di atas didapatkan bahwa sebagian besar nasabah saat ini sedang memiliki status **no checking** yang berarti nasabah sedang tidak memiliki kredit aktif saat ini
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/bc75ccc6-18e8-4560-bbc9-cf3a56eb3f9b)
    
    Dilihat dari grafik dapat disimpulkan bahwa lebih dari setengah nasabah saat ini sedang memiliki proses kredit
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/63fc48cf-adb6-4b27-81f5-7de78e82deb3)
    
    Berdasarkan hasil didapatkan bahwa alasan dari permintaan kredit sangatlah beragam dengan tertinggi dipegang oleh **radio/tv** dan terendah dipegang oleh tiga alasan lain yaitu **perabotan rumah tangga**, **pelatihan ulang**, dan **lainnya**
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/37ff9139-46a2-42fc-8e07-ecc6ebf9d34a)
    
    Untuk besaran simpanan yang dimiliki nasabah lebih dari setengah data menunjukkan bahwa nasabah mayoritas memiliki simpanan sebesar **kurang dari 100 dolar**
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/87fc8e6c-e1cd-4621-be05-5b99019fb95e)
    
    Data ini menggambarkan kebanyakan nasabah memiliki pengalaman kerja yang menengah yaitu **lebih atau sama dengan satu tahun dan kurang dari 4 tahun**
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/22a40dcc-1681-48c3-8830-1aa6cb62c05f)
    
    Berdasarkan data didapatkan bahwa sebagain besar data merupakan **laki-laki single**
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/bfb5e420-f8d6-4a1d-8b82-1bed17dde15f)
    
    Lebih dari 80% nasabah **tidak memiliki** pihak lain
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/fa651c3d-a500-4514-8f1b-242a44041461)
    
    Berdasarkan grafik yang ada didapatkan bahwa properti terbanyak yang digunakan sebagai jaminan kredit adalah **mobil**
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/5dfe2042-2bd3-47a0-a17f-0cb572704531)
    
    Dilihat dari grafik sekitar 80% nasabah **tidak memiliki credit line lain**
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/3ae397ec-3de9-4ea4-a1ad-ce3f0f8882e9)
    
    70% nasabah **memiliki rumah sendiri**
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/3d9657b0-2197-4342-92d1-2b6f86b03e6c)
    
    Jika dilihat dari grafik didapatkan bahwa lebih dari setengah nasabah merupakan pekerja dibidang yang membutuhkan keterampilan
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/631005ea-407d-493e-8ab8-06ac11507787)
    
    Berdasarkan grafik 60% nasabah tidak memiliki telepon
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/b5fbe6db-895e-474b-b010-405658b6485e)
    
    Berdasarkan data yang ada di grafik hampir seluruh nasabah merupakan orang asing
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/ede862c6-60b1-4e36-9717-5fb21cdb46b0)
    
    Terakhir, berdasarkan data didapatkan bahwa 70% nasabah memiliki risiko kredit yang baik dan layak untuk mendapatkan kredit.

  - Numerical Features
    Pada numerical features digunakan dua jenis diagram untuk menggambarkannya, yaitu histogram dan box plot
    **Histogram**
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/aba2d47c-9466-45e7-84a3-62883feb00aa)
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/0031696c-a0f2-4cd6-be59-854ab1ff6dfa)
    
    Berdasarkan histogram yang ada dapat dilihat bahwa data yang cocok untuk dianalisis dengan bentuk grafik ini hanya **duration**, **credit_amount**, dan **age**. Hal ini disebabkan karena persebarannya yang luas, sedangkan variabel lain memiliki kategori nomor yang menyebabkan tidak ada persebaran data. Namun, jika dilihat dari **credit_amount** dan **age** didapatkan bahwa data right-skewed yaitu sebagain besar nilai berada di sebelah kiri atau dibawah mean.
    
    **Box Plot**
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/ef891a9b-978f-46db-9980-432b88f74e04)
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/b03f688d-5376-4d36-b8ff-e3ab74b73406)
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/7f464fdc-5bd1-4419-9609-13dedfb2e9d7)
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/66c67ff2-a96c-4931-aa4e-cce99010869c)
    
    Berdasarkan hasil visualisasi oleh Box Plot didapatkan gambaran bahwa banyak outlier pada variabel **credit_amount** dan **umur** yaitu variabel yang memiliki persebaran besar. Dengan diketahuinya variabel dengan outlier yang besar maka dapat dilakukan pengutamaan penghapusan outlier pada dua variabel tersebut.
- **Multivariate Analysis**
  - Categorical Values
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/0192a9ee-3079-4dfd-bc67-8b52619e7876)
    
    Berdasarkan hasil ini didapatkan bahwa nasabah dengan tidak pernah kredit sama sekali dengan nasabah yang memiliki lebih dari 200 dolar kredit sama-sama memiliki risiko kredit yang baik yang berarti variabel checking_status seharusnya tidak mempengaruhi secara besar
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/f0a41cbe-240c-40df-afaa-a138020ee67d)
    
    Secara mengejutkan berdasarkan hasil yang didapatkan nasabah yang pernah telat membayar kredit memiliki risiko kredit yang lebih baik dibandingkan nasabah yang sudah membayar semua kreditnya atau tidak pernah melakukan pengajuan kredit. Hal ini juga menunjukkan bahwa variabel ini kemungkinan tidak terlalu berpengaruh
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/443577a4-40e6-4bd3-aa44-1f97ea310afd)
    
    Berdasarkan hasil hampir semua kategori memiliki hasil yang sama, dengan **pelatihan ulang** memiliki hasil risiko kredit terbaik, ini dapat disebabkan oleh sedikitnya data dari kategori tersebut. Namun, berdasarkan hal ini dapat diketahui bahwa variabel ini kemungkinan tidak terlalu berpengaruh
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/b22e75b0-5782-4eb2-abb5-75dce8519d46)
    
    Berdasarkan hasil grafik didapatkan bahwa semakin tinggi simpanan yang dimilikinya maka semakin baik risiko kredit nasabah tersebut. Hal ini dapat menunjukkan hubungan yang tinggi dan positif
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/a8efde52-e529-4a36-b273-8c21ccf9322d)

    Sama seperti sebelumnya, dari hasil didapatkan bahwa semakin lama nasabah bekerja maka risiko kreditnya akan semakin baik
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/466c173d-e367-4e9c-9195-39624955c2ac)
    
    Jika dilihat dari hasil grafik semua kategori memiliki risiko kredit yang hampir sama dan menunjukkan bahwa variabel ini tidak terlalu berpengaruh
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/120b1d48-1387-450d-85c5-3aecc32074a7)
    
    Berdasarkan grafik didapatkan bahwa nasabah yang memiliki pihak lain dalam invoicenya sebagai guarantor memiliki risiko kredit yang lebih baik, namun jika memiliki pihak lain sebagai co applicant di dalam invoicenya akan memiliki risiko kredit yang lebih buruk dibandingkan tidak memiliki pihak lain
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/23b03ace-8465-4e7f-b769-34beab748bb6)
    
    Dapat dilihat bahwa barang jaminan berupa real estate memiliki risiko kredit lebih baik dibandingkan lainnya, namun properti yang tidak diketahui memiliki risiko yang buruk karena tidak diketahui apa yang akan dijaminkan. Variabel ini mungkin saja cukup berpengaruh dalam penilaian
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/12ecadfc-852c-4607-8a21-2cda1ff52942)
    
    Berdasarkan hasil akan lebih baik jika nasabah tidak memiliki credit line lain
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/d8484916-9fad-4572-bbc2-6bc16404d6d8)
    
    Berdasarkan dari hasil yang didapatkan, dapat dilihat bahwa nasabah dengan kepemilikan rumah sendiri memiliki risiko kredit yang lebih baik dibandingkan nasabah dengan rumah yang gratis atau menyewa. Variabel ini mungkin berpengaruh dalam penilaian kredit walaupun tidak signifikan
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/d0357477-d5e1-4294-a5b2-45d6ab1c89ca)
    
    Berdasarkan hasil didapatkan bahwa seluruh kategori memiliki risiko kredit yang sama. Variabel ini mungkin tidak berpengaruh
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/280e617c-da61-4818-a427-96398bc33080)
    
    Sama seperti sebelumnya, kedua kategori ini juga memiliki risiko kredit yang sama yang berarti variabel ini mungkin tidak berpengaruh
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/74bce709-1991-4249-a096-19a4621ed875)
    
    Berdasarkan hasil yang didapatkan maka dapat dilihat bahwa pekerja asing memiliki risiko kredit yang lebih buruk dibandingkan pekerja lokal yang menunjukkan bahwa variabel ini mungkin saja berpangaruh

  - Numerical Values
    
    ![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/43555b64-c735-4866-90bc-91c2c19fc4ae)
    
    Scatter Plot tersebut menggambarkan persebaran data tiap variabel dengan variabel lain terhadap variabel target yaitu class. Warna dari titik menggambarkan variabel class dengan oranye berarti baik atau good dan biru berarti buruk atau bad. Jika dilihat dari hasil sebagian besar menunjukkan tidak adanya hubungan yang erat karena persebaran yang cukup rata. Untuk dapat melihat persebaran yang sesungguhnya dapat menggunakan korelasi.
     
### Korelasi
  Korelasi merupakan ukuran statistik yang menunjukkan sejauh mana dua variabel berkaitan satu sama lain dan menunjukkan arah dan kekuatan hubungan antara dua variabel. Digunakan untuk mengidentifikasi apakah perubahan satu variabel terikat dengan perubahan variabel lain. Korelasi sendiri memiliki dua jenis yaitu positif berarti ketika satu variabel meningkat maka nilai variabel lain akan meningkat juga, dan korelasi negatif yaitu ketika satu variabel meningkat maka nilai variabel lain cenderung menurun. Besaran korelasi berkisar antara -1 hingga 1 dengan semakin mendekati 1 atau -1 maka korelasi semakin kuat.
  
![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/408701b6-7421-4fbb-82e0-04cd984bec0f)

Berdasarkan hasil korelasi ini tidak ditemukan bagian yang menunjukkan variabel class karena class masih berupa tipe data category. Untuk dapat melihat hasil dari korelasi class maka akan dilakukan data preparation terlebih dahulu. Namun, berdasarkan heatmap yang sudah ada dapat dilihat bahwa tidak ada korelasi yang cukup besar antar variabel kecuali besaran kredit dengan durasinya.

## Data Preparation
Data preparation merupakan proses yang melibatkan beberapa langkah untuk mengubah data mentah menjadi format yang sesuai dan siap digunakan dalam analisis atau model prediktif. Pada proyek ini digunakan beberapa metode data preparation dimulai dari yang paling standar yaitu mencari missing value hingga feature scaling.

### Memeriksa Missing Value
Memeriksa missing value merupakan metode untuk mencari value yang hilang atau kosong. Kosong ini dapat berbentuk tidak ada data, NaN, atau bertuliskan unknown. Namun, tidak semua tulisan unknown merupakan missing value terkadang none atau unknown dapat juga merupakan sebuah kategori yang valid yang menggambarkan keadaan pada saat itu. Pemeriksaan ini bertujuan untuk memastikan kualitas dari data dengan memastikan data sudah sesuai. Pemeriksaan menggunakan **isnull()** untuk melihat value kosong dan juga dilakukan pemeriksaan data dengan tulisan unknown dan yang memungkinkan, namun untuk kata none tidak dianggap sebagai missing value karena merupakan sebuah kategori. Didapatkan bahwa tidak terdapat missing value pada data

### Memeriksa Data Duplikat
Memeriksa data duplikat dilakukan untuk mencari data yang sama persis dengan data lainnya (duplikat). Data duplikat akan lebih baik untuk dihapus untuk menjamin kualitas data dan memastikan tidak adanya bias. Pada proyek ini pemeriksaan menggunakan **duplicated()**

### Outlier Handling
Proses ini merupakan proses mengidentifikasi, menganalisis, dan menangani data yang menyimpang jauh dari sebagian besar data lainnya. Proses ini perlu dilakukan karena adanya outlier akan menurunkan kualitas data dan memungkinkan terjadinya bias serta untuk dapat meningkatkan akurasi dari model yang dimiliki. Handling dari outlier ini dilakukan dengan menghapus data dengan outliers. Pada proyek ini dilakukan outlier handling dengan metode 
z_hold dengan menggunakan threshold 3 dan didapatkan 48 data yang dihapus dikarenakan mengandung outliers sehingga saat ini hanya tersisa 952 data.

### Melakukan categorical encoding
Categorical encoding merupakan proses mengubah variabel kategorikal menjadi format numerik sehingga dapat digunakan dalam Machine Learning hal ini disebabkan banyak algoritma Machine Learning yang tidak dapat memproses data categorical. Sehingga proses ini perlu dilakukan agar data dapat diproses pada seluruh algoritma Machine Learning dan juga untuk mengurangi adanya kesalahan interpretasi. Pada proyek ini dilakukan encoding dengan menggunakan label encoding, sebelum melakukan encoding terhadap variabel categorical, dilakukan terlebih dahulu encoding untuk tiga variabel **own_telephone**, **foreign_worker**, dan **class** menjadi 1, 0 kemudian dilakukan encoding menggunakan label encoding yaitu konversi setiap kategori menjadi nilai numerik yang unik. 

### Korelasi setelah pembersihan data
Pada bagian ini dilakukan perhitungan korelasi antara variabel yang sudah mengalami pembersihan data sehingga seluruh data sudah memiliki tipe data yang sama dan tidak ada outliers lagi. Berikut hasil korelasi tersebut

![image](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/9aaac8c9-fb52-4fd6-810e-9602d968bf33)
![download (5)](https://github.com/tasyyaa/Credit-Risk-Classification/assets/100066633/751812b3-b3e3-4c1b-b2d7-c82dd0b9af57)

Berdasarkan hasil di atas sudah dapat terlihat korelasi antara variabel dengan variabel target yaitu class. Jika dilihat berdasarkan hasil korelasi tidak ada korelasi yang cukup kuat antara variabel independen dengan variabel target baik positif atau negatif. Namun, diputuskan untuk menggunakan tiga variabel dengan korelasi terkuat yaitu **checking_status**, **purpose**, dan **age**

### PCA
Principal Component Analysis (PCA) merupakan teknik statistik yang digunakan untuk mengurangi dimensi data dengan cara mengubah data asli yang memiliki banyak variabel menjadi beberapa variabel utama. Tujuan dari PCA ini adalah untuk mengurangi dimensi data sehingga mengurangi kekompleksan data dan mengurangi overfitting juga. Pada proyek ini dilakukan PCA untuk ketiga variabel yang akan digunakan tadi yaitu **checking_status**, **purpose**, dan **age**. Kemudian ketiganya dirangkum ke dalam suatu variabel bernama PCA.

### Data Balancing
Data balancing merupakan proses penyeimbangan jumlah sampel di setiap variabel pada dataset yang tidak seimbang. Hal ini dilakukan untuk menghindari terjadinya bias pada model karena terdapat lebih banyak data pada suatu kategori. Di kasus proyek ini data balancing dilakukan untuk menyeimbangkan data dari variabel class yang sebelumnya sebanyak **677 data** merupakan **risiko kredit baik** dan **275 data** merupakan **risiko kredit buruk**. Hal ini terlihat sangat tidak seimbang dan berisiko untuk bias menghasilkan risiko kredit baik karena model lebih sering mendapatkan data tersebut. Oleh karena itu dilakukan data balancing dengan **balancer** yang kemudian menghasilkan **677 data** untuk data risiko kredit baik maupun buruk.

### Data Splitting
Data splitting adalah proses membagi dataset menjadi dua subset terpisah yaitu training dataset dan testing dataset. Training dataset dibuat untuk digunakan dalam melatih model sedangkan testing dataset dibuat untuk menguji performa model terhadap data yang belum pernah dilihatnya. Proses ini perlu dilakukan karena untuk dapat melihat kinerja model apakah model sudah berjalan baik atau masih overfitting maupun underfitting. Data splitting pada studi kasus kali ini menggunakan library dari sklearn.model_selection yaitu train_test_split dengan membagi menjadi **80%** data training dan **20%** data testing. Pembagian ini didasarkan oleh jumlah data training yang harus lebih banyak dari data testing. Jumlah sampel data train adalah **1083 data** dan jumlah sampel data test adalah **271 data**

### Feature Scaling
Feature scaling merupakan proses normalisasi atau standarisasi dari variabel-variabel dalam dataset sehingga masing-masing memiliki skala yang serupa. Tujuan utamanya adalah untuk memastikan bahwa semua fitur memiliki pengaruh yang seimbang terhadap model machine learning. Pada kasus ini dilakukan feature scaling pada variabel dengan persebaran yang besar yaitu **duration**, **credit_amount**, dan **PCA** yang memiliki standar devisiasi besar tidak seperti variabel lainnya. Feature scaling dilakukan dengan menggunakan **StandardScaler()** dan hasil setelah feature scaling yaitu seluruh standar devisiasi berada pada rentang **1**


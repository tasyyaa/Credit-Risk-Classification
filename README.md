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


### Explanatory Data Analysis (EDA)

### Korelasi

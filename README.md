# Laporan Proyek Machine Learning - Tasya Putri Aliya
**Credit Risk Classification**
Laporan ini disusun untuk memenuhi persyaratan *Submission* Proyek Pertama Machine Learning Terapan Dicoding.

## Domain Proyek
  Topik yang diangkat dari proyek ini yaitu mengenai bidang ekonomi dan bisnis yang berfokus pada evaluasi risiko kredit suatu nasabah di perbankan. Evaluasi ini bertujuan untuk menentukan bahwa nasabah layak untuk mendapatkan kredit atau tidak.
### Latar Belakang
  Sebagai negara berkembang, Indonesia, dalam meningkatkan pertumbuhan ekonomi tidak dapat dipisahkan dari peran bank. Salah satu peran bank yang dianggap cukup penting adalah pemberian kredit kepada masyarakat. Hal ini dapat mendukung perekonomian dan meningkatkan standar hidup masyarakat [1]. Namun, tidak semua kredit yang diberikan dapat berjalan dengan lancar. Menurut data Otoritas Jasa Keuangan (OJK) pada tahun 2015-2019, rata-rata jumlah kredit macet atau pinjaman bermasalah di Indonesia berada pada angka 2.37%-3.93% dan menurut data Bank Mandiri sendiri besar kredit macet di Bank Mandiri mencapai Rp1,2 Triliun [2]. Tentu hal tersebut bukanlah angka yang kecil. 
  Besarnya total kredit macet ini jelas menjadi suatu perhatian bagi bank karena banyaknya dampak buruk dari adanya kredit macet ini. Dampak buruk tersebut, antara lain arus kas yang tidak lancar. Hal ini dapat menyebabkan bank tidak lagi mampu memberikan kredit kepada nasabah lainnya. Selain itu, peningkatan tingkat kredit macet dapat mengganggu profitabilitas perusahaan [3]. Salah satu ukuran profitabilitas yang menurun adalah Return on Assets (ROA), penurunan ini disebabkan oleh kinerja perusahaan yang kurang optimal dalam menggunakan asetnya. Kemudian, Loan to Deposit Ratio adalah ukuran kemampuan bank untuk membiayai kembali dana yang ditarik oleh deposan, dan memiliki dampak positif pada bank dalam bentuk pendapatan, misalnya dalam bentuk kredit. Tingkat likuiditas yang rendah di sebuah bank dapat menyebabkan perubahan dalam profitabilitas perusahaan yang menurun [4]. Hal ini terjadi karena perusahaan tidak mampu mendistribusikan dana tersebut.
  Maka dari itu, untuk dapat menyelesaikan permasalahan tersebut dilakukan penilaian credit risk dari nasabah yang akan melakukan kredit di bank untuk menilai kelayakan suatu nasabah dalam mendapatkan kredit dan kemampuannya dalam menyelesaikan kredit tersebut. Selain itu, semakin gentarnya credit risk ini juga disebabkan oleh ekonomi dunia berada dalam risiko krisis keuangan lainnya akibat evaluasi risiko kredit yang tidak efektif sebut IMF [5]. Betapa pentingnya evaluasi risiko kridit ini yang menjadi dasar dari dibuatnya program klasifikasi risiko kredit untuk dapat menyelesaikan permasalahan ini.

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

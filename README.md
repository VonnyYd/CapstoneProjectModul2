# CapstoneProjectModul2VY
Capstone Project Module 2 ini bertujuan untuk mengimplementasikan materi SQL, data manipulation, data visualization, dan statistics yang telah dipelajari oleh siswa dalam sebuah project. Dengan mengerjakan Capstone Project Module 2 ini, diharapkan siswa mampu melatih diri dalam membuat rangkaian analisis. Dalam projek ini, siswa akan memposisikan diri sebagai data analyst dalam sebuah perusahaan. Siswa akan membuat rangkaian pertanyaan berdasarkan keperluan bisnis dan masalah yang mungkin dihadapi oleh perusahaan terkait sesuai dengan data yang didapatkan.

Oleh sebab itu, melalui file README.md ini saya akan menjelaskan beberapa hal mengenai Capstone Project Module 2 yang sudah saya kerjakan. 

# **Latar Belakang**  
Dalam mengimplementasikan teori pembelajaran yang telah dilakukan, suatu perusahaan maskapai penerbangan akan melakukan Analisa terhadap kepuasan penumpang/pelanggannya. Pengukuran terhadap kepuasan pelanggan adalah kunci penting untuk bisnis modern karena dapat memberikan kontribusi yang signifikan terhadap upaya peningkatan kualitas layanan yang berkelanjutan. Oleh sebab itu, diambillah histori dataset yang dimiliki untuk melakukan identifikasi dan Analisa lebih lanjut. 

# **Rumusan Masalah**  
Rumusan masalah ini akan memuat pertanyaan yang hendak dijawab atau pertanyaan tentang masalah yang akan dibahas serta diuraikan pada tahap – tahap selanjutnya.  

Perusahaan ingin mengetahui **Variabel - variabel mana sajakah yang mempengarui tingkat kepuasan pelanggan ?**. Jawaban dari pertanyaan ini akan sangat membantu perusahaan untuk membangun strategi pertahanan serta peningkatan kepuasan pelanggan. Hal ini juga akan menjadi kontribusi yang signifikan terhadap upaya peningkatan kualitas layanan yang berkelanjutan karena pengambilan keputusan didasarkan pada data serta pengujian.  

Bentuk analisa/pengujian akan dilakukan dengan melihat pola hubungan variabel - variabel kategori/penilai terhadap variabel kepuasan pelanggan.  

# **Langkah Kerja**  
## **1.) Menampilkan Data**
Langkah kerja pertama akan diawali dengan menampilkan dataset yang dimiliki. Dataset ini berisikan informasi - informasi terkait hasil survei kepuasan pelanggan maskapai penerbangan yang terdiri dari 23 kolom, yaitu :  
* Id                        = Nomor yang digunakan untuk menginisiasikan pelanggan.  
* Gender                    = Jenis kelamin pelanggan, terdiri dari Wanita dan Pria.  
* Customer Type             = Jenis pelanggan, terdiri dari Pelanggan setia dan Pelanggan tidak setia.  
* Age                       = Usia sebenarnya dari pelanggan.  
* Type of Travel            = Tujuan penerbangan pelanggan, terdiri dari Perjalanan Pribadi dan Perjalanan Bisnis.  
* Class                     = Jenis Kelas perjalanan pelanggan di pesawat, terdiri dari Bisnis, Eco, dan Eco Plus.  
* Flight distance           = Jarak penerbangan saat itu, yang dilakukan oleh masing – masing pelanggan.  
* Inflight wifi service     = Tingkat kepuasan layanan wifi dalam pesawat. 
* Departure/Arrival time convenient = Tingkat kepuasan pelanggan terhadap ketepatan waktu Keberangkatan/Kedatangan. 
* Ease of Online booking    = Tingkat kepuasan pelanggan terhadap pemesanan online.   
* Gate location             = Tingkat kepuasan pelanggan terhadap lokasi gate.   
* Food and drink            = Tingkat kepuasan pelanggan terhadap Makanan dan Minuman.  
* Online boarding           = Tingkat kepuasan pelanggan terhadap boarding online.   
* Seat comfort              = Tingkat kepuasan pelanggan terhadap kenyamanan tempat duduk.   
* Inflight entertainment    = Tingkat kepuasan pelanggan terhadap fasilitas hiburan dalam pesawat.   
* On-board service          = Tingkat kepuasan pelanggan terhadap layanan On-board.  
* Leg room service          = Tingkat kepuasan pelanggan terhadap space ruang untuk Kaki pada kursi pesawat.  
* Baggage handling          = Tingkat kepuasan pelanggan terhadap penanganan bagasi.  
* Check-in service          = Tingkat kepuasan pelanggan terhadap pelayanan Check-in.  
* Inflight service          = Tingkat kepuasan pelanggan terhadap pelayanan dalam pesawat.  
* Cleanliness               = Tingkat kepuasan pelanggan terhadap Kebersihan.  
* Departure Delay in Minutes= Keterlambatan saat keberangkatan dalam satuan menit.  
* Arrival Delay in Minutes  = Keterlambatan saat kedatangan dalam satuan menit.  
* Satisfaction              = Tingkat kepuasan pelanggan terhadap maskapai penerbangan, terdiri dari penilaian Puas, dan netral atau tidak puas.

## **2.) Data Understanding and Cleaning**  
Kemudian, pada langkah kedua kita akan mengenali lebih dalam mengenai dataset yang akan digunakan melalui tahapan *data understanding*. Selain itu, juga akan dilakukan proses pembersihan data atau sering disebut *data cleaning*. Data Cleaning memiliki peranan penting sebagai tahap awal pengolahan data. Hal ini disebabkan data yang kotor dapat mempengaruhi hasil pengujian yang dilakukan. Proses Data cleaning biasanya terdiri dari menangani data Anomali, yaitu: missing value, data outlier, data formatting, dan/atau data duplikat.  

**Data Info**  
Untuk melihat gambaran awal dari dataset yang dimiliki, kita dapat menggunakan rumusan kode (df.info()). Melalui cara ini kita dapat melihat kolom apa saja dalam dataset, jumlah baris data yang terisi (tidak kosong), dan tipe datanya.  
Adapun informasi - informasi yang diperhatikan dari dataset ini, yaitu : 
-   Dataset ini memiliki 103904 baris dan 25 kolom data  
-   Pada judul tabel pertama dan kedua, yaitu Unnamed:0 dan id, sebenarnya kolom ini tidak dibutuhkan dan apabila dihapus, maka tidak akan memengaruhi klasifikasi. Jadi ada baiknya untuk disingkirkan. 
-	Kolom data “Arrival Delay in Minutes” memiliki 310 nilai yang hilang dan tipe datanya adalah 'float64'. Sehingga, perlu dilakukan penanganan pada data kosong serta pengubahan tipe data.  
-   Pada data ke 8 sampai ke 21, yaitu : 'Inflight wifi service', 'Departure/Arrival time convenient', 'Ease of Online booking', 'Gate location', 'Food and drink', 'Online boarding', 'Seat comfort', 'Inflight entertainment', 'On-board service', 'Leg room service', 'Baggage handling', 'Checkin service', 'Inflight service', 'Cleanliness' memiliki tipe data int64. Sebenarnya, isi dari data - data ini adalah penilaian kategori. Sehingga, perlu dilakukan pengubahan pada tipe datanya.  
-   Isi dari data ke 8 sampai ke 21 adalah Penilaian 0 : Tidak ingin mengisi, 1 : Sangat tidak puas, 2 : Tidak puas, 3 : Biasa saja, 4 : Puas, 5 : Sangat Puas. Sehingga, kita juga akan melakukan penggantian inisiasi dari isi dalam data ini.  

Dari informasi yang telah didapatkan di atas, langkah berikutnya yang akan dilakukan adalah sebagai berikut.  
- **`Pertama`**, kita akan menghapus data kolom yang tidak diperlukan, yaitu data Unnamed:0 dan id dari dataset. Hal ini juga termasuk dalam bentuk Data Formatting. 
- **`Kedua`**, lakukan penanganan pada *Missing Value* atau data kosong.  
Dalam hal ini, kita perlu melakukan pengujian korelasi pada variabel - variabel yang berisikan data numerik dan membuat serta menampilkan Heatmap. Hal ini berguna untuk visualisasi data, agar kita lebih mudah melihat dan memahami adanya hubungan antar variabel atau judul tabel. Selain itu, kita juga dapat mengetahui hubungan keberadaan data kosong terhadap variabel lainnya.    
  - **Pengujian Korelasi**  
Korelasi adalah tentang asosiasi dan tidak berimplikasi pada sebab akibat. Korelasi hanya mengukur seberapa kuat hubungan dan arah hubungan. Nilai korelasi berkisar pada -1 < r < 1, serta arah positif (+) dan arah negatif (-). Arah positif artinya bila satu variabel naik, maka variabel lain juga naik. Sedangkan, arah negatif memiliki hubungan yang berkebalikan, seperti hubungan populasi tikus di sawah dengan produksi padi.  
    Hasil korelasi dapat dinilai dari standar.  
      - Nilai 0 - 0.3     : berarti hubungan lemah
      - Nilai 0.3 - 0.7   : berarti hubungannya sedang
      - Nilai 0.7 - 1     : berarti kekuatan hubungannya kuat  
  - **Visualisasi Heatmap**  
Heatmap korelasi menampilkan matriks korelasi 2 dimensi antara dua variable atau lebih. Heatmap ini menggunakan sel berwarna atau dalam skala monokromatik. Nilai dimensi pertama muncul di baris tabel, sedangkan nilai dimensi kedua diwakili oleh kolom tabel. Nilai warna sel mengikuti besaran pengukuran nilai korelasi. Biasanya semakin berkorelasi warnanya semakin gelap atau bisa sebaliknya. Melalui plot ini, Anda dapat mengidentifikasi pola dan anomali dari korelasi dengan lebih cepat.  
Dari tampilan Heatmap yang sudah dibuat, terlihat bahwa variabel 'Arrival Delay in Minutes' berkorelasi atau memiliki hubungan yang kuat dengan variabel 'Departure Delay in Minutes'. Dalam menangani data kosong atau *Missing Value*, ada 2 cara yang dapat dilakukan, yaitu:  
      - Pertama, menghapus baris/kolom yang berisi *missing value*. Tidak disarankan pemakaian langsung, karena dapat mempengaruhi distribusi dan hasil pengujian statistik.  
      - Kedua, mengisi data yang kosong. Cara ini disarankan. Ada beberapa metode yang bisa digunakan untuk mengisi *missing value*, cara yang paling baik adalah dengan mengisi data yang hilang dengan nilai sebenarnya, atau sedekat mungkin dengan nilai asli. Dalam analisis ini, kita akan  mengisi *missing value* berdasarkan kolom lain yang secara statistik berkaitan dengan kolom yang memiliki *missing value*. Jika masih ada kolom yang tidak bisa diisi, barulah kita mengisi dengan angka *mean, median* atau *modus*. Menghapus data akan menjadi opsi terakhir.  

  Dari rumusan kode melihat jumlah data yang hilang dalam dataset (*Missing Value*), terdapat 310 data kosong di kolom 'Arrival Delay in Minutes'. Kemudian, melalui  pembagian data - data kosong di kolom 'Arrival Delay in Minutes' ini berdasarkan kolom 'satisfaction', terlihat bahwa pelanggan yang bersifat 'neutral or dissatisfied' sebanyak 182 tidak melakukan pengisian pada kolom 'Arrival Delay in Minutes'. Angka ini lebih banyak jika dibandingkan dengan pelanggan yang bersifat 'satisfied'. Oleh sebab itu, kita bisa berasumsi bahwa pelanggan yang bersifat netral atau tidak puas, tentunya enggan untuk mengisi lama waktu keterlambatan pada kedatangan. Untuk itu, kita akan mengisi data kosong di kolom 'Arrival Delay in Minutes' menggunakan `median` berdasarkan kategori pada kolom 'satisfaction'. Selain itu, alasan lain dari pemilihan nilai median untuk mengisi nilai pada data kosong adalah karena dilihat dari histogram yang telah dibentuk, gambaran sebaran data pada kolom 'Arrival Delay in Minutes' memiliki distribusi tidak normal. Grafik tersebut menunjukan distribusi yang condong ke kanan. Sehingga, data kosong (Missing Value) yang terdapat pada kolom 'Arrival Delay in Minutes' di isi dengan nilai median. 

  Setelah berhasil mengisi data kosong pada kolom 'Arrival Delay in Minutes'. Kita akan membentuk scatterplot dari variabel kolom 'Arrival Delay in Minutes' dan 'Departure Delay in Minutes' untuk melihat hubungan antar keduanya. Apakah keduanya memiliki hubungan linear atau tidak ? Hasilnya adalah titik - titik sebaran data di atas kurang lebih membentuk garis lurus dari pojok kiri bawah ke kanan atas. Dengan demikian, dapat disimpulkan bahwa variabel kolom 'Arrival Delay in Minutes' dan 'Departure Delay in Minutes' memiliki hubungan yang linier.  

  Hasil pengisian data yang hilang cukup logis dan dapat dijelaskan sebagai berikut. Jika penerbangan pelanggan maskapai tertunda selama waktu tertentu saat keberangkatan ('Departure Delay in Minutes'), maka penerbangan akan tertunda dengan jumlah waktu yang sama saat mendarat/datang ('Arrival Delay in Minutes'). 


























































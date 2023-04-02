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

- **`Ketiga`**, lakukan pebgubahan tipe data 'Arrival Delay in Minutes' dari float menjadi integer.  
- **`Keempat`**, lakukan pengubahan tipe data pada data - data kolom yang berisikan penilaian kategori. Pada variabel/judul tabel 'satisfaction' tidak akan kita ubah karena merupakan variabel target.
- **`Kelima`**, mengubah isi data pada kolom - kolom kategori dengan penilaian 0 : Tidak ingin mengisi, 1 : Sangat tidak puas, 2 : Tidak puas, 3 : Biasa saja, 4 : Puas, 5 : Sangat Puas.  
- **`Keenam`**, kita perlu mengecek keberadaan data duplikat. Hal ini dilakukan dengan identifikasi baris duplikat menggunakan fungsi (duplicated()). Lalu, gunakan fungsi (print) untuk menampilkan baris duplikat. Hasilnya terlihat bahwa tidak ada data duplikat pada dataset kita.  
- **`Ketujuh`**, dataset sudah siap digunakan untuk pengolahan data berikutnya. Tidak lupa juga, dataset ini disimpan ke dalam file dataset yang baru untuk digunakan dalam pengolahan visualisasi dalam Tableau.  

## **3.) Exploratory Data Analysis**  
Exploratory Data Analysis (EDA) merupakan proses dalam proyek Analisis Data yang dilakukan dengan cara menyelidiki dataset untuk menemukan pola, dan anomali, serta membentuk hipotesis berdasarkan pemahaman tentang dataset yang dimiliki. Exploratory Data Analysis biasanya dilakukan dengan pembuatan ringkasan statistik data numerik dalam dataset dan membuat berbagai macam visualisasi grafik untuk memahami data dengan lebih baik.  
Adapun beberapa visualisasi grafik yang akan digunakan pada analisis ini, yaitu:  
- Histogram adalah representasi grafis yang akurat dari distribusi data numerik dan perkiraan distribusi probabilitas dari variabel kuantitatif. Histogram hanya digunakan untuk memplot frekuensi kemunculan skor dalam kumpulan data kontinu yang telah dibagi ke dalam kelas-kelas, yang disebut bins. Pada analisis ini, histogram akan digunakan untuk menampilkan data sebaran serta melihat distribusi data pada kolom 'Age', 'Flight Distance', 'Departure Delay in Minutes', dan 'Arrival Delay in Minutes'.
- Countplot adalah grafik sederhana yang digunakan untuk menghitung jumlah data berdasarkan kategorinya. Pada analisis ini, countplot akan digunakan untuk menampilkan data pada 'Gender', 'Customer Type', 'Type of Travel', 'Class', dan 'satisfaction'.
- Pie Chart atau Diagram lingkaran adalah grafik melingkar yang dibagi menjadi beberapa bagian. Besarnya potongan dalam diagram menunjukkan besarnya proporsi dari jumlah total yang diwakilinya. Diagram lingkaran paling cocok dipakai untuk menggambarkan proporsi tiap - tiap bagian dari keseluruhan informasi tertentu. Oleh karena itu, pada Exploratory Data Analysis ini, juga akan menampilkan Pie Chart pada beberapa data agar lebih mudah untuk dipahami. Pie chart yang dibentuk akan menggunakan startangle = 90. Startangle adalah nilai awal rotasi object atau sudut awal dalam menggambar busur/lingkaran. Apabila tidak ditentukan, maka sudut awal grafik akan mengikuti defaultnya yaitu 0. Data yang akan ditampilkan meliputi: 'Inflight wifi service', 'Departure/Arrival time convenient', 'Ease of Online booking', 'Gate location', 'Food and drink', 'Online boarding', 'Seat comfort', 'Inflight entertainment', 'On-board service', 'Leg room service', 'Baggage handling', 'Checkin service', 'Inflight service', dan 'Cleanliness' 

## **4.) Pengujian Statistik dan Analisis Data**  
Statistik adalah sebuah ilmu untuk mendesain penelitian dan analisis data dalam penelitian. Statistik dapat dideskripsikan sebagai metode untuk mengumpulkan, menganalisis, memaknai atau menginterpretasi, dan membuat kesimpulan dari data. Oleh karena itu, pada tahap ini kita melakukan pengujian statistik dengan tujuan, yaitu  menerjemahkan data menjadi sebuah pengetahuan dan memahami keadaan di lingkungan perusahaan atau sosial. Statistik yang digunakan pada analisa di bawah ini adalah statistik inferensial, yaitu cabang statistik yang menggunakan sampel data untuk membuat kesimpulan dari fenomena apa pun dalam populasi.  

Mari kita lakukan analisis untuk mencari tahu **pola hubungan variabel - variabel kategori / penilai terhadap variabel kepuasan pelanggan (satisfaction)**.  

Analisis ini dilakukan dengan membandingkan data 'satisfaction' pelanggan yang bersifat 'satisfied' dan 'neutral or dissatisfied' berdasarkan beberapa variabel kategori penilai. Hal ini dikarenakan dari 103,904 data yang dimiliki, hanya 45,025 data pelanggan yang bersifat 'satisfied' atau puas. Oleh sebab itu, kita perlu berhati-hati dalam membandingkan data. Pembandingan lebih baik dilakukan berdasarkan ratio, terutama pada data bertipe kategorikal.

# **5.) Kesimpulan dan Rekomendasi**  
Dari hasil analisis dan pengujian yang telah kita lakukan di atas, dapat di tarik **kesimpulan bahwa variabel - variabel yang mempengaruhi tingkat kepuasan pelanggan dan membutuhkan perbaikan adalah 'Gender', 'Customer Type', 'Type of Travel', 'Class', 'Inflight wifi service', 'Ease of Online booking', 'Food and drink', 'Online boarding', 'Inflight entertainment', 'Leg room service', dan 'Cleanliness'**. Berikut adalah penjabaran serta rekomendasi yang diberikan, berkaitan dengan kesimpulan yang diambil.  

**A.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Gender' dan 'satisfaction'`, dapat ditarik kesimpulan bahwa `pelanggan dengan gender "Female" memiliki penilaian` 'satisfied' dan `'neutral or dissatisfied' yang` lebih `banyak` di bandingkan dengan pelanggan dengan gender "Male". Didapatkan angka penilaian tertinggi pada pelanggan gender "Female" dengan ketentuan "neutral or dissatisfied" sebanyak 30,193. Sehingga, `perlu dibangun usulan perbaikan pada variabel ini secara spesifik`. Rekomendasi yang dapat diberikan adalah sebagai berikut. 
- Memberikan promo potongan harga khusus pada pelanggan "Female" di waktu tertentu (Misalnya: di hari ibu).
- Menyediakan kebutuhan khusus wanita sebagai fasilitas tambahan. (Seperti: pembalut, koyo, dsb).  
- Menyediakan fasilitas dukungan bagi orang tua dan ibu hamil. (Seperti: layanan transpotasi khusus, tambahan bantal penyangga, kursi roda, atau lainnya)

**B.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Customer Type' dan 'satisfaction'`, dapat dilihat bahwa pelanggan dengan tipe "Loyal" memiliki penilaian 'satisfied' dan 'neutral or dissatisfied' yang lebih tinggi/banyak di bandingkan dengan pelanggan dengan tipe "disloyal". Namun, jika diperhatikan kembali, `terdapat angka penilaian yang tinggi pada tipe pelanggan "Loyal" dengan ketentuan 'neutral or dissatisfied'`, yaitu sebesar 44,390. Sehingga, `perlu dibangun usulan perbaikan pada variabel ini secara spesifik`. Rekomendasi yang dapat diberikan adalah sebagai berikut.  
- Membangun sistem membership pada maskapai penerbangan  
- Memberikan kemudahan dalam mengakses fasilitas tambahan yang disediakan maskapai kepada pelanggan yang 'Loyal'. (Seperti: kendaraan menuju gate di dalam bandara, tambahan potongan diskon pada transaksi dengan cara tertentu, dsb) 
- Memberikan fasilitas khusus atau voucher belanja pada pelanggan yang telah melakukan transaksi hingga kurun jumlah serta waktu tertentu.   

**C.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Type of Travel' dan 'satisfaction'`, dapat dilihat bahwa pelanggan dengan tipe penerbangan "Business" memiliki penilaian 'satisfied' dan 'neutral or dissatisfied' yang lebih tinggi/banyak di bandingkan dengan pelanggan dengan tipe "Personal". Walaupun `penilaian pelanggan` 'satisfied' pada tipe penerbangan "Business" merupakan nilai yang paling tinggi, yang menempati peringkat `kedua tertinggi` berikutnya `adalah pelanggan 'neutral or dissatisfied' pada tipe penerbangan "Business"`, yaitu sebesar 29,909. Oleh sebab itu, `perlu dibangun rekomendasi spesifik` yang dapat mempertahankan dan meningkatkan kepuasan pelanggan. Di antaranya :  
- Memberikan kuota atau ketentuan jumlah bagasi lebih kepada pelanggan dengan jenis penerbangan 'Business'.  
- Memberikan bantuan layanan bebas antri check in, shuttle, dan masuk pesawat.  
- Memberikan fasilitas pengambilan bagasi.  

**D.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Class' dan 'satisfaction'`, dapat dilihat bahwa `pelanggan dengan tipe kelas penerbangan "Eco" memiliki penilaian tertinggi pada kategori 'neutral or dissatisfied'`. Sehingga, `perlu dilakukan upaya perbaikan` dengan usulan sebagai berikut. 
- Menjalin kerjasama dengan maskapai lain, guna memberikan promo tambahan, serta mengembangkan networking.  
- Meningkatkan armada shuttle saat musim keberangkatan sangat tinggi.    
- Membangun strategi pesawat cadangan (*standby*) di beberapa kota yang diindetifikasi mengalami masalah beberapa waktu terakhir.  

**E.)** `Pada pengujian statistik yang telah dilakukan terhadap variabel 'satisfaction' dengan variabel 'Age'`, didapatkan hasil bahwa data - data dalam `variabel 'Age' tidak berdistribusi normal`. Kemudian, melalui pengujian rata - rata dua populasi independen non parametrik, dapat disimpulkan bahwa `terdapat perbedaan yang signifikan antara pelanggan 'satisfied' dengan 'neutral or dissatisfied' berdasarkan variabel 'Age'`. Dari boxplot yang telah digambarkan, `terlihat perbedaannya adalah sebagian besar pelanggan yang bersifat 'neutral or dissatisfied' berusia antara 25 - 50 tahun (usia rata-rata mereka sedikit di atas 30 tahun). Sedangkan, pelanggan yang bersifat 'satisfied' memiliki  berusia antara 35 - 50 tahun (dengan usia rata-rata di atas 40 tahun)`.  

**F.)** `Pada pengujian statistik yang telah dilakukan terhadap variabel 'satisfaction' dengan variabel 'Flight Distance'`, didapatkan hasil bahwa data - data dalam `variabel 'Flight Distance' tidak berdistribusi normal`. Kemudian, melalui pengujian rata - rata dua populasi independen non parametrik, dapat disimpulkan bahwa `terdapat perbedaan yang signifikan antara pelanggan 'satisfied' dengan 'neutral or dissatisfied' berdasarkan variabel 'Flight Distance'`. Melalui boxplot yang telah tergambar, `terlihat perbedaannya adalah pelanggan dengan jarak penerbangan yang jauh, kebanyakan merasa 'satisfied' atau puas. Sedangkan, pelanggan dengan penilaian 'neutral or dissatisfied' memiliki banyak data outlier`.  

**G.)** `Pada pengujian statistik yang telah dilakukan terhadap variabel 'satisfaction' dengan variabel 'Departure Delay in Minutes'`, didapatkan hasil bahwa data - data dalam `variabel 'Departure Delay in Minutes' tidak berdistribusi normal`. Kemudian, melalui pengujian rata - rata dua populasi independen non parametrik, dapat disimpulkan bahwa `tidak ada perbedaan yang signifikan antara pelanggan 'satisfied' dengan 'neutral or dissatisfied' berdasarkan variabel 'Departure Delay in Minutes'`. Dari gambar boxplot yang terbentuk, dapat dilihat bahwa `terdapat banyak sekali data outlier. Namun, bentuk kedua gambaran plot data memang mirip antara pelanggan 'satisfied' dengan 'neutral or dissatisfied' terhadap variabel 'Departure Delay in Minutes'`.  

**H.)** `Pada pengujian statistik yang telah dilakukan terhadap variabel 'satisfaction' dengan variabel 'Arrival Delay in Minutes'`, didapatkan hasil bahwa data - data dalam `variabel 'Arrival Delay in Minutes' tidak berdistribusi normal`. Kemudian, melalui pengujian rata - rata dua populasi independen non parametrik, dapat disimpulkan bahwa `tidak ada perbedaan yang signifikan antara pelanggan 'satisfied' dengan 'neutral or dissatisfied' berdasarkan variabel 'Arrival Delay in Minutes'`. Dari gambar boxplot yang terbentuk, dapat dilihat bahwa `terdapat banyak sekali data outlier. Namun, bentuk kedua gambaran plot data memang mirip antara pelanggan 'satisfied' dengan 'neutral or dissatisfied' terhadap variabel 'Arrival Delay in Minutes'`.

**I.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Inflight wifi service' dan 'satisfaction'`, dapat dilihat utamanya adalah pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan banyak `mengisi atau merasa 'Tidak puas' dan 'Biasa Saja'` terhadap variabel 'Inflight wifi service'. Sehingga, `perlu dilakukan upaya perbaikan` yang berkaitan dengan variabel ini. Usulan perbaikan yang dapat dilakukan diantaranya seperti berikut ini.  
- Petugas dalam pesawat perlu menginformasikan adanya layanan wifi dalam pesawat. Hal ini dikarenakan pada umumnya masyarakat hanya mengerti bahwa tidak bisa menggunakan jaringan telefon / internet saat di pesawat. 
- Petugas dalam pesawat juga harus memberikan edukasi terhadap layanan wifi dalam pesawat ini. (Seperti: Biaya penggunaan, resiko penggunaan, dan batasan pengguna)  
- Petugas dalam pesawat dapat memberikan informasi penawaran rangkaian lengkap layanan konektivitas dalam penerbangan yang terpercaya (contoh : inmarsat)  

**J.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Departure/Arrival time convenient' dan 'satisfaction'`, dapat dilihat utamanya adalah pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Puas' dan 'Sangat Puas'` terhadap variabel 'Departure/Arrival time convenient'. Sehingga, `tidak perlu dilakukan upaya perbaikan`.  

**K.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Ease of Online booking' dan 'satisfaction'`, dapat dilihat utamanya adalah pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Tidak puas' dan 'Biasa saja'` terhadap variabel 'Ease of Online booking'. `Sehingga, perlu dilakukan upaya perbaikan` yang berkaitan dengan variabel ini. Usulan perbaikan yang dapat dilakukan diantaranya seperti berikut ini.  
- Perusahaan maskapai penerbangan perlu menyediakan segala media yang dapat diusahakan untuk menjangkau semua kalangan pelanggan yang ingin melakukan penerbangan. Contoh : E-Commerce, Website Resmi, WhatsApp Resmi, Akun Media Soial, Aplikasi Resmi, Nomor Telefon yang bisa dihubungi secara langsung, dsb.
- Perusahaan maskapai harus membangun sistem yang mudah digunakan serta dipelajari, tampilan grafis yang terarah pada tujuan pengguna dengan mudah, dan menghindari error yang berlebihan.  
- Memasang informasi edukasi diberbagai media atau iklan mengenai penerbangan, agar informasi yang disampaikan benar - benar menjangkau berbagai kalangan masyarakat.  

**L.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Gate location' dan 'satisfaction'`, dapat dilihat utamanya adalah pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa saja' dan` disusul dengan penilaian tertinggi kedua, yaitu `'Puas'` terhadap variabel 'Gate location'. Sehingga, `tidak perlu dilakukan upaya perbaikan`. 

**M.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Food and drink' dan 'satisfaction'`, dapat dilihat utamanya adalah pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa Saja' dan 'Tidak puas'` terhadap variabel 'Food and drink'. Sehingga, `perlu dilakukan upaya perbaikan` yang berkaitan dengan variabel ini. Usulan perbaikan yang dapat dilakukan diantaranya seperti berikut ini.  
- Memperhatikan tingkat higienis/kebersihan dari makanan.
- Memilih makanan dan minuman yang tepat untuk ditawarkan secara gratis dengan melihat lamanya penerbangan penumpang.  
- Menawarkan makanan dan minuman tambahan yang menarik serta terjangkau harganya.  

**N.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Online boarding' dan 'satisfaction'`, dapat dilihat utamanya adalah pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa saja' dan` disusul dengan penilaian tertinggi kedua, yaitu `'Tidak puas'` terhadap variabel 'Online boarding'. Sehingga, `perlu dilakukan upaya perbaikan` yang berkaitan dengan variabel ini. Usulan perbaikan yang dapat dilakukan diantaranya seperti berikut ini.  
- Perusahaan maskapai penerbangan perlu menyediakan fasilitas kemudahan melakukan 'Online boarding' dari mana saja dengan meyediakannya melalui berbagai media. 
- Perusahaan dapat menyediakan link resmi dan melakukan broadcasting melalui akun media sosial yang terjangkau oleh pelanggan mengenai 'Online boarding' yang sudah bisa dilakukan pada waktu tertentu. Media sosial ini dapat berupa WhatsApp atau SMS.
- Menghindari terjadinya error saat para pelanggan menggunakan program yang dibentuk untuk 'Online boarding'.  

**O.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Seat comfort' dan 'satisfaction'`, dapat dilihat utamanya adalah pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa saja' dan` disusul dengan penilaian tertinggi kedua, yaitu `'Puas'` terhadap variabel 'Seat comfort'. Sehingga, `tidak perlu dilakukan upaya perbaikan`. 

**P.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Inflight entertainment' dan 'satisfaction'` menunjukkan pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa saja' dan` disusul dengan penilaian tertinggi kedua, yaitu `'Tidak Puas'` terhadap variabel 'Inflight entertainment'. Sehingga, `perlu dilakukan upaya perbaikan` yang berkaitan dengan variabel ini. Usulan perbaikan yang dapat dilakukan diantaranya seperti berikut ini.  
- Perusahaan maskapai dapat menawarkan sewa fasilitas layanan berbayar kepada pelanggan mengenai 'Inflight entertainment' selama penerbangan. (contoh: *tablet full of games*, MP3, *phone for entertainment likes spotify, podcast, news*, dan lainnya) 

**Q.)** `Dari hasil cross tabulasi dan grafik antara variabel 'On-board service' dan 'satisfaction'`, dapat dilihat bahwa pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa saja' dan` disusul dengan penilaian tertinggi kedua, yaitu `'Puas'` terhadap variabel 'On-board service'. Sehingga, `tidak perlu dilakukan upaya perbaikan`. 

**R.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Leg room service' dan 'satisfaction'` menunjukkan bahwa pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa saja' dan` disusul dengan penilaian tertinggi kedua, yaitu `'Tidak Puas'` terhadap variabel 'Leg room service'. Sehingga, `perlu dilakukan upaya perbaikan` yang berkaitan dengan variabel ini. Usulan perbaikan yang dapat dilakukan diantaranya seperti berikut ini.  
- Perusahaan maskapai penerbangan perlu melakukan penelitian secara berkala terhadap persentil ukuran tubuh manusia yang disesuaikan dengan genetika ras masyarakat, guna membetuk aisle yang pas untuk pelanggan secara umum.  
- Perusahaan maskapai penerbangan dapat menyediakan penawaran harga tiket sesuai dengan variasi luas tempat duduk di dalam pesawat.  
- Perusahaan maskapai penerbangan dapat menyediakan fasilitas tempat duduk dalam pesawat yang lebih luas untuk ditawarkan kepada pelanggan yang sekiranya akan melakukan penerbangan yang lama atau jauh.  

**S.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Baggage handling' dan 'satisfaction'`, terlihat bahwa pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Puas' dan` disusul dengan penilaian tertinggi kedua, yaitu `'Biasa Saja'` terhadap variabel 'Baggage handling'. Sehingga, `tidak perlu dilakukan upaya perbaikan`. 

**T.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Checkin service' dan 'satisfaction'` menunjukkan pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa Saja' dan 'Puas'` terhadap variabel 'Checkin service'. Sehingga, `tidak perlu dilakukan upaya perbaikan`. 

**U.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Inflight service' dan 'satisfaction'` menunjukkan pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Puas' dan` disusul dengan pengisian penilaian tertinggi kedua, yaitu `'Biasa Saja'` terhadap variabel 'Inflight service'. Sehingga, `tidak perlu dilakukan upaya perbaikan`. 

**V.)** `Dari hasil cross tabulasi dan grafik antara variabel 'Cleanliness' dan 'satisfaction'`, dapat dilihat bahwa pelanggan dengan penilaian 'neutral or dissatisfied' dari variabel 'satisfaction' secara keseluruhan `banyak mengisi atau merasa 'Biasa Saja' dan disusul dengan pengisian penilaian tertinggi kedua, yaitu 'Puas' dan 'Tidak Puas'` terhadap variabel 'Cleanliness'. Sehingga, `perlu dilakukan upaya perbaikan`. Usulan perbaikan dapat berupa hal - hal berikut.  
- Melakukan proses desinfeksi dan pembersihan pesawat secara berkala.  
- Melakukan pembersihan dan desinfeksi setiap pelanggan selesai menggunakan toilet.  
- Melakukan pembersihan secara mendetail terkait fasilitas *Inflight Entertainment*, bantal, dan selimut setiap selesai penerbangan. (Seperti diganti dengan unit baru yang sudah dibersihkan, unit lama dikumpulkan untuk dilaundry, dsb.)  


**Notes :** Adapun `usulan - usulan tambahan` yang dapat membantu perusahaan dalam meningkatkan kepuasan pelanggan. Usulan ini pun `dapat berkaitan dengan poin E sampai H`. Diantaranya adalah :
- Meningkatkan Frekuensi penerbangan.  
- Pihak maskapai harus memberikan informasi keterlambatan kepada pelanggannya paling lambat 45 menit sebelum keberangkatan beserta alasannya melalui berbagai media. Hal ini dilakukan agar informasi benar - benar tersampaikan dan diterima oleh pelanggan.  
- Apabila terjadi keterlambatan, pihak maskapai harus memberikan informasi mengenai kepastian penerbangan. Hal ini berguna bagi pelanggan untuk mengantisipasi diri apabila pesawat gagal terbang atau berangkat.  
- Apabila terjadi gangguan di luar kendali (seperti: cuaca), maka pihak maskapai harus menyampaikan informasi keterlambatan sejak gangguan terjadi.  
- Maskapai penerbangan perlu membangun strategi untuk mengatasi keterlambatan yang terjadi di luar dari faktor yang tidak dapat dikendalikan (seperti: cuaca). Misalnya, membuat fasilitas dan sistem proses pengisian bahan bakar yang siap siaga serta cepat, membangun alur keluar dan masuk penumpang serta 'luggage' (barang-barang penumpang yang boleh dibawa kedalam kabin pesawat) ke pesawat secara efisien dan efektif, sistem antrian dan pemasangan garbarata yang tepat dan cepat, membangun sistem pengaturan rotasi kru dan pesawat yang produktif, serta lainnnya.  
- Perubahan jadwal penerbangan harus diberitahukan kepada pelanggan paling lambat 24 jam sebelum jadwal penerbangan sebenarnya.
- Maskapai dapat menyediakan ruang tunggu khusus, yang mana fasilitasnya lebih nyaman untuk para penumpang/pelanggan yang mengalami *delay*. Atau memberikan promo diskon tambahan, untuk penggunaan ruang tunggu khusus bagi penumpang.pelanggan yang mengalami *delay*. 
- Melakukan perawatan pesawat secara berkala, guna memperhatikan keamanan dalam penerbangan serta efisiensi jadwal penerbangan.  



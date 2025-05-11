# Laporan Proyek Machine Learning - Muhammad Ricky Rizaldi

## Project Overview
### Latar Belakang
Perkembangan teknologi digital telah mendorong transformasi besar dalam dunia pendidikan, salah satunya melalui hadirnya platform Massive Open Online Courses (MOOC) seperti Coursera. Platform ini menawarkan ribuan kursus dari berbagai bidang yang dapat diakses oleh siapa saja, kapan saja, dan dari mana saja. Fenomena ini memberikan peluang besar bagi individu untuk meningkatkan kompetensinya secara mandiri dan fleksibel. Berdasarkan laporan Class Central, pada tahun 2023 tercatat lebih dari 142 juta pengguna yang terdaftar di Coursera, dengan ratusan ribu kursus aktif yang berasal dari berbagai institusi ternama di seluruh dunia. Angka ini menunjukkan bahwa pembelajaran daring telah menjadi pilihan utama dalam menjawab kebutuhan pendidikan masa kini yang dinamis dan inklusif.

Namun, seiring meningkatnya jumlah kursus dan konten multimedia seperti video pembelajaran, tantangan baru muncul. Banyak pengguna merasa kesulitan dalam menemukan kursus atau video yang benar-benar sesuai dengan kebutuhan, minat, atau latar belakang mereka. Tingginya volume konten menyebabkan overload informasi yang justru dapat menghambat proses belajar. Kelimpahan video pembelajaran yang tersedia ini sering kali justru membuat pencarian video yang relevan menjadi sulit dan memakan waktu, karena tidak semua video memiliki topik yang sesuai atau deskripsi yang lengkap (Ramadhan dan Musdholifah, 2021)

Selain itu, lonjakan informasi digital dan jumlah pengguna yang besar menciptakan tantangan teknis dalam memprediksi preferensi pembelajar. Hal ini mendorong kebutuhan mendesak akan sistem rekomendasi pembelajaran daring yang mampu menyaring dan menyajikan konten secara personal. Dalam konteks ini, sistem rekomendasi tidak hanya berfungsi sebagai alat bantu pencarian, tetapi juga sebagai strategi filtrasi cerdas yang mampu mengarahkan pengguna pada materi pembelajaran yang paling sesuai dengan kebutuhan mereka secara efisien dan terukur (Jena _et al_., 2023).

### Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan
Jika masalah overload informasi pada platform pembelajaran daring tidak diatasi dengan tepat maka dapat menyebabkan pengalaman belajar yang tidak optimal. Banyak pengguna yang berhenti di tengah jalan atau bahkan tidak memulai kursus sama sekali karena bingung memilih dari sekian banyak opsi yang tersedia. Sementara itu, pendekatan rekomendasi yang bersifat general dan tidak dipersonalisasi juga sering kali gagal menangkap preferensi unik setiap individu. Menurut Jena _et al_. (2023), sistem rekomendasi e-learning memainkan peran vital dalam meningkatkan efisiensi pencarian kursus dan menjaga keberlanjutan proses pembelajaran.

Oleh karena itu, pengembangan sistem rekomendasi yang cerdas, akurat, dan personal menjadi sangat penting untuk meningkatkan efektivitas pembelajaran daring. Proyek ini bertujuan untuk mengembangkan sistem rekomendasi kursus dengan pendekatan hybrid yang menggabungkan metode Content-Based Filtering (CBF) dan Collaborative Filtering (CF) berbasis deep learning. Pendekatan CBF akan memanfaatkan fitur konten seperti nama kursus dan institusi penyedia untuk memberikan rekomendasi yang relevan secara topik, terutama bagi pengguna baru yang belum memiliki cukup riwayat aktivitas (cold-start problem). Sementara itu, pendekatan CF memanfaatkan data interaksi pengguna, seperti rating dan ulasan, untuk mengidentifikasi pola preferensi dan memberikan rekomendasi berbasis kesamaan antar pengguna.

Melalui kombinasi dua pendekatan ini, sistem yang dikembangkan diharapkan mampu memberikan pengalaman rekomendasi yang lebih akurat, kontekstual, dan adaptif terhadap perilaku pengguna. Dengan mengintegrasikan teknik pemrosesan bahasa alami, pembobotan TF-IDF, serta model embedding berbasis Recommender Net, proyek ini tidak hanya menampilkan kapabilitas machine learning dalam menyelesaikan masalah nyata di dunia pendidikan, tetapi juga memberikan kontribusi nyata dalam mendukung pembelajaran yang lebih inklusif, efisien, dan terarah.

### Penelitian Terkait
Berbagai studi terdahulu telah menunjukkan potensi signifikan sistem rekomendasi dalam mendukung personalisasi pembelajaran, terutama melalui pendekatan Collaborative Filtering (CF) dan Content-Based Filtering (CBF). Penerapan metode ini terbukti mampu meningkatkan akurasi, efisiensi, dan relevansi rekomendasi dalam berbagai konteks edukasi digital.
- Li (2020) mengembangkan platform pendidikan daring yang mengintegrasikan algoritma Collaborative Filtering dalam arsitektur hybrid berkinerja tinggi berbasis HTML5. Dengan pendekatan server-client melalui framework populer dan pemrosesan lintas platform, sistem ini mampu menyajikan rekomendasi kursus yang lebih personal. Algoritma CF yang dimodifikasi secara signifikan meningkatkan akurasi dan efisiensi, sementara fitur pembelajaran video on-demand dan sesi langsung memperkaya pengalaman pengguna.
- Adilaksa (2021) menekankan pendekatan Content-Based Filtering dalam sistem rekomendasi mata kuliah pilihan dengan mengandalkan profil akademik mahasiswa dan isi silabus. Kemiripan antara pengguna dan konten dihitung menggunakan cosine similarity berbobot. Evaluasi melalui kuesioner dan pengujian akurasi menunjukkan tingkat diversitas rekomendasi sebesar 81,67% dan akurasi sebesar 64%, menjadikannya relevan sebagai acuan dalam representasi konten edukatif.
- Dalam studi yang dilakukan Permana (2024), sistem rekomendasi berbasis Collaborative Filtering dimodifikasi dengan pendekatan cosine similarity dan diperkuat oleh arsitektur RecommenderNet menggunakan Convolutional Neural Networks (CNN). Walaupun diterapkan pada konteks pariwisata, metode ini memperlihatkan kapabilitas deep learning dalam memahami pola preferensi pengguna secara mendalam. Evaluasi menggunakan RMSE menunjukkan hasil yang menjanjikan (nilai terbaik 0,2579), dan pendekatan embedding ini relevan untuk pengembangan sistem rekomendasi kursus berbasis interaksi pengguna.
- Pradana (2022) membandingkan dua pendekatan utama—Content-Based Filtering dan Collaborative Filtering—dalam konteks kegiatan ekstrakurikuler. Hasil evaluasi menunjukkan bahwa model CBF berbasis Multinomial Naive Bayes memperoleh akurasi lebih tinggi (74%) dibanding CF berbasis Gaussian Naive Bayes (56%). Temuan ini menegaskan bahwa CF memerlukan basis data interaksi yang lebih kaya untuk mencapai performa optimal, sementara CBF lebih efektif saat metadata konten tersedia secara lengkap.
- Ramadhan (2021) mengembangkan sistem rekomendasi video pembelajaran menggunakan Content-Based Filtering berdasarkan kecocokan antara deskripsi video YouTube dan silabus mata kuliah. Menggunakan cosine similarity, sistem menghasilkan lima rekomendasi dengan rata-rata metrik relevance, novelty, serendipity, dan diversitas sebesar 81,13%. Pendekatan ini menunjukkan efektivitas CBF dalam menyaring konten multimedia edukatif yang relevan dengan kebutuhan akademik.
- Fiarni (2019) melalui penelitian dalam bidang e-commerce menerapkan metode cosine similarity dalam sistem rekomendasi produk berbasis Content-Based Filtering. Dengan klasifikasi produk dan pengguna berdasarkan perilaku transaksi, sistem menghasilkan precision sebesar 100% dan recall 93,47%. Meskipun tidak berada dalam domain edukasi, teknik yang digunakan dapat diadaptasi dalam sistem rekomendasi kursus untuk menghitung kesamaan konten berdasarkan atribut deskriptif.

### Referensi
- Li, J & Ye, Z. (2020). [Course Recommendations in Online Education Based on Collaborative Filtering Recommendation Algorithm](https://onlinelibrary.wiley.com/doi/abs/10.1155/2020/6619249).
- Adilaksa, Y., & Musdholifah, A. (2021). [Recommendation System for Elective Courses using Content-based Filtering and Weighted Cosine Similarity](https://ieeexplore.ieee.org/document/9702788/).
- Permana, K.E., Rahmat, A.B., Wicaksana, D.A., & Ardianto, D. (2024). [Collaborative filtering-based Madura Island tourism recommendation system using RecommenderNet](https://www.bio-conferences.org/articles/bioconf/abs/2024/65/bioconf_btmic2024_01080/bioconf_btmic2024_01080.html).
- Pradana, D.S., Prajoko, P., & Hartawan, G.P. (2022). [Perbandingan Algoritma Content-Based Filtering dan Collaborative Filtering dalam Rekomendasi Kegiatan Ekstrakurikuler Siswa](https://ojs.stmik-banjarbaru.ac.id/index.php/progresif/article/view/854).
- Ramadhan, F., & Musdholifah, A. (2021). [Online Learning Video Recommendation System Based on Course and Syllabus Using Content-Based Filtering](https://journal.ugm.ac.id/ijccs/article/view/65623).
- Fiarni, C., & Maharani, H. (2019). [Product Recommendation System Design Using Cosine Similarity and Content-based Filtering Methods](https://journal.ugm.ac.id/ijitee/article/view/45538).
- Jena, K.K., Bhoi, S.K., Malik, T.K., Sahoo, K.S., Jhanjhi, N.Z., Bhatia, S., Amsaad, F., (2023). [E-Learning Course Recommender System Using Collaborative Filtering Models](https://www.mdpi.com/2079-9292/12/1/157).

  
## Business Understanding
Tujuan dari proyek ini adalah untuk mengembangkan sistem rekomendasi kursus Coursera yang dapat membantu pengguna menemukan kursus yang relevan dan sesuai dengan preferensi atau minat mereka. Platform MOOC seperti Coursera menawarkan ribuan kursus dari berbagai bidang, yang dapat menimbulkan overload informasi bagi pengguna, terutama bagi pemula atau pengguna yang tidak memiliki riwayat interaksi sebelumnya. Oleh karena itu, sistem rekomendasi yang cerdas dan personal sangat dibutuhkan agar proses pencarian kursus menjadi lebih efisien dan terarah.

Dalam proyek ini, pendekatan yang digunakan terdiri dari dua jenis yaitu menggunakan Content-Based Filtering (CBF) dengan teknik representasi teks seperti TF-IDF dan cosine similarity untuk mengukur kemiripan antar kursus dan menggunakan Collaborative Filtering (CF) berdasarkan pendekatan Neural Collaborative Filtering (Recommender Net) untuk mempelajari pola interaksi pengguna terhadap kursus. Pendekatan CBF diharapkan dapat memberikan solusi terhadap permasalahan cold-start user, sedangkan pendekatan CF dapat memanfaatkan data historis interaksi pengguna untuk meningkatkan personalisasi. Dengan adanya sistem ini, pengguna tidak hanya diberikan daftar kursus populer, tetapi rekomendasi yang disesuaikan dengan karakteristik, minat, atau interaksi mereka sebelumnya. Hal ini diharapkan dapat meningkatkan kepuasan belajar pengguna sekaligus efektivitas penggunaan platform Coursera.

### Problem Statements
1. Bagaimana cara membuat sistem rekomendasi yang mampu menangani kebutuhan pengguna baru dan pengguna aktif platform Coursera?
2. Bagaimana merancang sistem rekomendasi kursus berbasis konten menggunakan pendekatan TF-IDF dan cosine similarity agar mampu menyarankan kursus yang serupa dengan preferensi pengguna?
3. Bagaimana membangun sistem Collaborative Filtering berbasis Neural Collaborative Filtering (Recommender Net) yang mampu belajar dari interaksi pengguna terhadap kursus secara efisien?

### Goals
1. Menyediakan sistem rekomendasi yang dapat mengatasi masalah cold-start user sekaligus meningkatkan relevansi rekomendasi bagi pengguna aktif platform Coursera.
2. Mengembangkan sistem Content-Based Filtering dengan pendekatan representasi teks menggunakan TF-IDF dan pengukuran kemiripan antar kursus dengan cosine similarity.
3. Mengembangkan sistem Collaborative Filtering dengan pendekatan Recommender Net berbasis embedding untuk mempelajari pola interaksi pengguna terhadap kursus.

### Solution statements
- **Solusi 1:** Membangun sistem Content-Based Filtering yang merekomendasikan kursus berdasarkan kesamaan konten dengan kursus yang telah diminati pengguna. Representasi konten akan dihasilkan menggunakan teknik TF-IDF dari fitur seperti judul dan institusi kursus, kemudian dilakukan pengukuran kemiripan menggunakan cosine similarity untuk menghasilkan daftar kursus yang relevan. Sistem ini ditujukan untuk pengguna baru yang belum banyak berinteraksi dengan platform.
- **Solusi 2:** Membangun sistem Collaborative Filtering menggunakan pendekatan Neural Collaborative Filtering (Recommender Net) dengan memanfaatkan embedding untuk merepresentasikan pengguna dan kursus. Sistem ini akan dilatih menggunakan data historis ulasan atau rating dari pengguna dan bertujuan untuk memberikan rekomendasi berdasarkan preferensi kolektif pengguna lain yang memiliki pola interaksi serupa.
- **Solusi 3:** Mengintegrasikan kedua pendekatan tersebut untuk menciptakan sistem yang adaptif baik terhadap pengguna baru maupun pengguna lama. Sistem Content-Based Filtering akan menangani cold-start user, sementara sistem Collaborative Filtering akan menyajikan rekomendasi berbasis interaksi yang lebih personal. Pendekatan ini diharapkan meningkatkan cakupan dan relevansi rekomendasi yang dihasilkan.

  
## Data Understanding
Dataset yang digunakan pada proyek sistem rekomendasi kursus Coursera ini terdiri dari dua bagian utama, yaitu dataset kursus dan dataset ulasan pengguna. Dataset ini bertujuan untuk memberikan wawasan tentang konten kursus serta perilaku pengguna dalam memberikan ulasan dan penilaian terhadap kursus yang mereka ikuti di platform Coursera. Dataset ini diambil dari sumber terbuka dan dapat diakses melalui tautan berikut [Course Reviews on Coursera-Kaggle](https://www.kaggle.com/datasets/imuhammad/course-reviews-on-coursera). Berikut adalah deskripsi dari kedua dataset:  
  
**1. Coursera Courses Dataset**  
   Dataset ini berisi informasi tentang 623 kursus yang tersedia di Coursera. Setiap baris data mewakili satu kursus yang ditawarkan oleh berbagai institusi dari seluruh dunia. Dataset ini 
   berguna sebagai sumber data utama dalam membangun sistem Content-Based Filtering, terutama melalui fitur-fitur teks seperti judul kursus dan institusi penyedia.
   Variabel-variabel dalam dataset ini adalah sebagai berikut:
  - **name (karakter):** Nama dari kursus, digunakan untuk representasi konten dalam sistem rekomendasi berbasis teks.
  - **institution (karakter):** Institusi penyelenggara kursus, seperti universitas atau organisasi profesional.
  - **course_url (karakter):** Tautan langsung menuju halaman kursus di platform Coursera.
  - **course_id (karakter):** ID unik yang merepresentasikan setiap kursus dan digunakan untuk menggabungkan dengan dataset ulasan.

**2. Coursera Reviews Dataset**
  Dataset ini mencakup sekitar 1,45 juta ulasan pengguna terhadap berbagai kursus Coursera. Setiap baris data merepresentasikan satu ulasan yang diberikan oleh seorang pengguna terhadap sebuah 
  kursus, termasuk tanggal ulasan, teks ulasan, dan skor rating. Dataset ini sangat berguna untuk membangun sistem Collaborative Filtering berbasis Neural Collaborative Filtering karena memuat 
  interaksi antara pengguna dan kursus.
  Variabel-variabel dalam dataset ini adalah sebagai berikut:
  - **reviews (karakter):** Isi teks dari ulasan yang diberikan oleh pengguna terhadap kursus.
  - **reviewers (karakter)**: Nama atau ID dari pengguna yang memberikan ulasan.
  - **date_reviews (datetime):** Tanggal publikasi ulasan.
  - **rating (integer):** Skor penilaian yang diberikan untuk kursus, biasanya dalam skala 1–5.
  - **course_id (karakter):** ID kursus yang diulas, digunakan untuk penggabungan dengan dataset Coursera Courses.

### Tahapan Pemahaman Data
**Course Dataset**
1. Tahapan pertama adalah melakukan Exploratory Data Analisis menggunakan .info() untuk menampilkan ringkasan informasi struktur dataset berupa tipe data dan jumlah dataset, kemudian melakukan metode statistik deskriptif dengan fungsi .describe() untuk mengetahui sebaran data dan gambaran distribusi data. Pada tahap ini terlihat bahwa data memiliki 623 baris data dan masing masing diwakili oleh course_id yang berbeda-beda.
 
  ![image](https://github.com/user-attachments/assets/27bdc44c-71fc-4396-b0c4-59f2eed65b58)
  ![image](https://github.com/user-attachments/assets/07249d38-07c3-4625-af64-229096628cf6)

2. Selanjutnya melakukan pengecekan kondisi data dengan menampilkan data duplikat dan missing value yang ada pada dataset. Walaupun di deskriptif terlihat ada judul yang duplikat tapi institusi dan course_idnya berbeda sehingga data tidak mengandung data duplikat serta tidak terdapat data dengan missing value.

    ![image](https://github.com/user-attachments/assets/407cd0c4-33b3-4c7d-8b8d-c4a979c7c028) ![image](https://github.com/user-attachments/assets/ccb0ae11-2638-4a05-9999-f3ab8b9def00)


3. Terakhir melakukan pengenalan data dengan melakukan pengecekan unique course untuk melihat bagaimana isi data dari name course serta distribusi course per institusi pembuat untuk mempertimbangkan relevansi antar course. Pada data terlihat ada 623 data dengan judul yang mengandung symbol, angka dan font non ASCII, dilihat dari institusi terdapat beberapa institusi yang mengunggah beberapa kelasnya di coursera.
 
     ![image](https://github.com/user-attachments/assets/9200185b-e0b0-4189-b25e-eacdb0a4767b)
     ![image](https://github.com/user-attachments/assets/0e54e731-7458-4412-a8c8-8213062aec7d)

**Reviews Dataset**
1. Tahapan pertama masih sama yaitu menampilkan ringkasan informasi struktur dataset kemudian melakukan metode statistik deskriptif untuk melihat sebaran dan gambaran distribusi data. Pada data terlihat mengandung 1454711 baris data yang mana cukup banyak, sekilas terlihat pada deskriptif rating dominan bintang 5 dan ada user yang terlihat memiliki review lebih banyak dari total kelas, selain itu terlihat course_id hanya mengandung 604 kelas yang menunjukkan ada beberapa kelas yang belum pernah di rating oleh user.

    ![image](https://github.com/user-attachments/assets/981f1111-a98f-4377-938f-3917fffc224d)
    ![image](https://github.com/user-attachments/assets/c11a77d3-69dc-4b64-a5c5-6bb98d8b9f0d)

2. Selanjutnya untuk memastikan dilakukan pendalaman dengan melihat kelas yang tidak pernah dirating terlihat ada 19 baris data, distribusi rating juga terlihat dominan di bintang 4-5, selanjutnya dilakukan pendalaman pada fitur terlihat ada beberapa kelas yang dominan di rating seperti python, kemudian ada beberapa user yang memiliki rating dengan jumlah melebihi kelas menunjukkan adanya duplicate data.

    ![image](https://github.com/user-attachments/assets/09cca218-0708-4b15-8f64-c4464a320bd7)  
    ![image](https://github.com/user-attachments/assets/771c20ff-fc3b-452c-9470-66f4879c9a88)  
    ![image](https://github.com/user-attachments/assets/bf86953f-a919-42ef-96eb-034381ad9a04)
    ![image](https://github.com/user-attachments/assets/c8f722f6-d0a1-49ac-bcee-a075141b309b)

4. Kemudian dilakukan pengecekan data duplikat dan benar saja terdapat 948595 baris data duplikat yang diberikan oleh user yang sama, terlihat bahwa ada beberapa user yang memberikan 2-3 kali ulasan dengan nilai rating yang sama. Selain itu dilakukan juga pengenalan bagaimana jumlah review per waktu di mana terlihat lonjakan user review di tahun 2020-2021. Selanjutnya dilakukan tahapan pengecekan missing value terlihat ada missing value pada fitur reviews yang berisi ulasan namun hal ini tidak masalah karena fitur ini tidak akan digunakan.

    ![image](https://github.com/user-attachments/assets/139bc7a3-3dcf-462a-845c-676fe58b982a) ![image](https://github.com/user-attachments/assets/c5dbb195-80a6-4f1d-9e2f-07da383c1690) 
    ![image](https://github.com/user-attachments/assets/a93b1700-1ca1-4fd3-b084-b1f6967d4405) ![image](https://github.com/user-attachments/assets/ea92bbec-282a-4b13-8c36-c80758ecbc2c)  
     
6. Terakhir dilakukan pengecekan sparsity untuk mengetahui seberapa banyak course yang tidak diisi rating oleh user. Terlihat jumlah elemen pada matriks yang dihasilkan sebesar 173.836.032 dengan sparsity sebesar 0,9971 yang menunjukkan bahwa banyak user yang hanya mereview sedikit course.

## Data Preparation
Tahap persiapan atau prapemrosesan data merupakan langkah krusial dalam analisis data dan pengembangan model machine learning. Tanpa proses ini, data yang tidak bersih, tidak lengkap, atau tidak konsisten dapat menimbulkan kesalahan dalam analisis, menurunkan akurasi model, dan menghasilkan keputusan yang kurang tepat. Oleh karena itu, prapemrosesan menjadi tahap penting untuk memastikan data dalam kondisi siap dan optimal guna menghasilkan insight serta model yang berkualitas. Berdasarkan hasil Exploratory Data Analysis sebelumnya, terdapat beberapa langkah yang perlu dilakukan:
### Preprocessing Course Dataset
1. Pada dataset course dilakukan proses pembersihan fitur text yang ada pada data, meliputi pembersihan angka, tanda baca, newline, dan spasi ganda. Kemudian dilakukan tahapan casefolded untuk mengubah text menjadi huruf kecil untuk menyamakan konteks. fitur yang dilakukan data cleaning hanya fitur institusi dan course_id saja (course_id dipilih karena mengandung kata kunci berbeda untuk tiap course dibandingkan name course yang mengandung nama yang sama).
2. Selanjutnya untuk fitur course_id yang sudah dibersihkan kemudian dilakukan pengecekan apakah textnya termasuk huruf ASCII (kemungkinan dalam alphabet inggris), jika iya maka akan dilakukan pemrosesan lanjutan meliputi tokenisasi untuk memecah kata yang akan di proses, filtering untuk menghapus stopword atau kata kurang bermakna pada text dalam bahasa inggris, terakhir dilakukan lematisasi untuk mengurangi kompleksitas fitur dengan mengubah text ke bentuk dasar kamus.

    ![image](https://github.com/user-attachments/assets/09400a5e-0d4d-4e6e-a486-039d34ba3aa9)

3. Setelah semua proses selesai dibuat fitur baru bernama content yang berisi kata kunci course dari course_id dan institusi pembuat course. Tujuannya Membuat representasi gabungan dari kata kunci dan institusi sebagai identitas konten kursus. Fitur ini akan digunakan untuk menghitung kemiripan antar kursus dalam sistem rekomendasi berbasis konten.

    ![image](https://github.com/user-attachments/assets/1c2644e6-b36a-4b17-bc5f-34fd60d9aae5)

### Preprocessing Reviews Dataset
1. Pada tahapan EDA telah diketahui bahwa terdapat 948595 data duplikat sehingga data tersebut akan dihapus namun dengan tetap mempertahankan satu nilai rating berdasarkan rating paling terbaru untuk menjaga relevansi terhadap preferensi terkini pengguna. Tujuannya penghapusan duplikat adalah untuk menghindari bias akibat pengulangan data dan memastikan setiap interaksi user-course dihitung satu kali. Menjaga satu entri terbaru memastikan data tetap relevan secara temporal.

    ![image](https://github.com/user-attachments/assets/83a1343d-bcc9-4bda-8a29-06901b71779b)

2. Selanjutnya dataset reviews yang sudah dibersihkan dari duplikat dilakukan penggabungan dengan course dataset berdasarkan kesamaan dalam course_id menggunakan cara inner join untuk memastikan data-data yang tidak terdapat pada kedua dataset (belum pernah di review) tidak akan digunakan kedalam pelatihan.
    ![image](https://github.com/user-attachments/assets/216e6f2b-afa6-4b20-a884-aa57dea9ef02)

3. Kemudian berdasarkan tahapan EDA yang menunjukkan bahwa sparsitynya tinggi. Hal ini bisa membuat model kesulitan belajar pola dan menurunkan akurasi prediksi karena user dengan terlalu sedikit interaksi biasanya tidak cukup informatif. Oleh karena itu akan dilakukan sedikit penanganan terhadap hal ini dengan melakukan filter user yang memiliki rating diatas 3 course saja yang akan digunakan, sebaliknya user yang dibawah itu akan dihapus. Adapun pemilihan filter diatas 3 sebagai treshold untuk menjaga keseimbangan antara kualitas dan kuantitas data.

    ![image](https://github.com/user-attachments/assets/55027c99-e4f2-4b17-8a53-166811e2ec6b)

4. Setelah dilakukan filtering data selajutnya akan dilakukan normalisasi atau scaling terhadap fitur rating yang berada di rentang 1-5, normalisasi dilakukan menggunakan MinMaxScaler untuk mengurangi kompleksitas fitur dan mempermudah model dalam melakukan pemrosesan dalam menentukan suka atau tidak sukanya user terhadap course. Adapun metode MinMax Scaling sendiri adalah teknik penskalaan yang mengubah nilai fitur ke dalam rentang 0 hingga 1, teknik ini dipilih karena sederhana, tidak mengubah distribusi asli data secara signifikan, dan cocok untuk menjaga proporsi nilai dalam fitur yang memiliki skala berbeda. Rumus MinMax Scaling adalah:

$$
X_{\text{scaled}} = \frac{X - X_{\text{min}}}{X_{\text{max}} - X_{\text{min}}}
$$

  - $` X `$ adalah nilai original.  
  - $` X_{\text{min}} `$ dan $` X_{\text{max}} `$ adalah nilai minimum dan maksimum dari fitur.

5. Berikutnya dilakukan encoding untuk fitur kategorikal yang akan digunakan dalam pelatihan model diantaranya fitur reviewers yang berisi nama user dan fitur course_id yang berisi kata kunci course atau ID dari course. Hasilnya, terdapat 37.034 nilai unik untuk user dan 603 nilai unik untuk course. Proses ini penting agar model dapat memahami data kategorikal yang secara default tidak dapat diolah oleh model numerik.

   ![image](https://github.com/user-attachments/assets/8d52e04c-66e7-4e11-80a0-08730eb37041)

7. Terakhir dilakukan data splitting dengan mengacak keseluruhan isi dataset terlebih dahulu untuk mencegah bias (shuffling), selanjutnya dilakukan splitting yaitu memisahkan data pelatihan dan validasi untuk mengevaluasi performa model secara obyektif dengan proporsi 80% data training dan 20% data validasi di mana X terdiri dari user_encoded dan course encoded, serta y yang berisi rating normalized.

    ![image](https://github.com/user-attachments/assets/31a0d92f-7d6c-42ff-b0f1-426bd8971299)


## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

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
1. Tahap pertama adalah melakukan Exploratory Data Analysis (EDA) dengan menampilkan ringkasan struktur data menggunakan .info() untuk melihat tipe data dan jumlah entri, serta .describe() untuk memperoleh gambaran statistik deskriptif dan distribusi data. Dari hasil ini terlihat bahwa dataset terdiri dari 623 baris, masing-masing merepresentasikan satu kursus yang berbeda berdasarkan course_id.
 
  ![image](https://github.com/user-attachments/assets/27bdc44c-71fc-4396-b0c4-59f2eed65b58)
  ![image](https://github.com/user-attachments/assets/07249d38-07c3-4625-af64-229096628cf6)

2. Selanjutnya dilakukan pemeriksaan kondisi data, khususnya terkait data duplikat dan missing value. Meskipun terdapat judul kursus yang tampak serupa, masing-masing memiliki institusi dan course_id yang berbeda. Oleh karena itu, tidak ditemukan data duplikat maupun nilai kosong (missing value) dalam dataset ini.

    ![image](https://github.com/user-attachments/assets/407cd0c4-33b3-4c7d-8b8d-c4a979c7c028) ![image](https://github.com/user-attachments/assets/ccb0ae11-2638-4a05-9999-f3ab8b9def00)


3. Tahap terakhir adalah pengenalan isi data. Dilakukan analisis terhadap unique course name dan distribusi kursus berdasarkan institusi untuk menilai relevansi dan keragaman konten. Terdapat 623 kursus dengan judul yang bervariasi, beberapa mengandung simbol, angka, serta karakter non-ASCII. Beberapa institusi diketahui menawarkan lebih dari satu kursus di Coursera.
 
     ![image](https://github.com/user-attachments/assets/9200185b-e0b0-4189-b25e-eacdb0a4767b)
     ![image](https://github.com/user-attachments/assets/0e54e731-7458-4412-a8c8-8213062aec7d)

**Reviews Dataset**
1. Proses analisis dimulai dengan menampilkan informasi struktur data dan deskriptif statistik. Dataset ini terdiri dari 1.454.711 baris yang mana merupakan jumlah data yang cukup besar. Terlihat bahwa rating bintang 5 mendominasi. Selain itu, terdapat user yang memberikan lebih banyak ulasan dibanding jumlah kursus yang tersedia. Selain itu hanya terlihat 604 course_id, yang mengindikasikan bahwa beberapa kursus belum pernah diberi rating oleh pengguna.

    ![image](https://github.com/user-attachments/assets/981f1111-a98f-4377-938f-3917fffc224d)
    ![image](https://github.com/user-attachments/assets/c11a77d3-69dc-4b64-a5c5-6bb98d8b9f0d)

2. Untuk memperdalam analisis, dilakukan identifikasi terhadap kursus yang belum pernah diberi rating dan ditemukan 19 judul yang belum pernah di rating. Kemudian juga dilakukan pengecekan lebih lanjut di mana dapat diketahui informasi bahwa distribusi rating cenderung tinggi, mayoritas di bintang 4–5. Analisis fitur menunjukkan bahwa kursus seperti Python mendominasi rating. Selain itu, ditemukan user yang memberikan rating lebih banyak dari jumlah kelas yang tersedia, mengindikasikan adanya data duplikat.

    ![image](https://github.com/user-attachments/assets/09cca218-0708-4b15-8f64-c4464a320bd7)  
    ![image](https://github.com/user-attachments/assets/771c20ff-fc3b-452c-9470-66f4879c9a88)  
    ![image](https://github.com/user-attachments/assets/bf86953f-a919-42ef-96eb-034381ad9a04)
    ![image](https://github.com/user-attachments/assets/c8f722f6-d0a1-49ac-bcee-a075141b309b)

3. Selanjutnya dilakukan pemeriksaan terhadap data duplikat dan ditemukan sebanyak 948.595 baris duplikat dari user yang sama. Beberapa user memberikan ulasan 2–3 kali dengan nilai rating yang sama. Selain itu, dilakukan analisis jumlah review berdasarkan waktu, dan ditemukan lonjakan aktivitas pengguna pada tahun 2020–2021. Pemeriksaan terhadap missing value menunjukkan adanya nilai kosong pada fitur reviews, namun hal ini tidak menjadi masalah karena fitur tersebut tidak digunakan dalam analisis lebih lanjut.

    ![image](https://github.com/user-attachments/assets/139bc7a3-3dcf-462a-845c-676fe58b982a) ![image](https://github.com/user-attachments/assets/c5dbb195-80a6-4f1d-9e2f-07da383c1690) 
    ![image](https://github.com/user-attachments/assets/a93b1700-1ca1-4fd3-b084-b1f6967d4405) ![image](https://github.com/user-attachments/assets/ea92bbec-282a-4b13-8c36-c80758ecbc2c)  
     
4. Tahap terakhir adalah pemeriksaan sparsity dari matriks user–course untuk mengetahui sejauh mana kursus telah diulas oleh pengguna. Matriks yang terbentuk memiliki total elemen sebesar 173.836.032 dengan nilai sparsity 0,9971, menunjukkan bahwa sebagian besar user hanya memberikan rating pada sedikit kursus.

## Data Preparation
Tahap persiapan atau prapemrosesan data merupakan langkah krusial dalam analisis data dan pengembangan model machine learning. Tanpa proses ini, data yang tidak bersih, tidak lengkap, atau tidak konsisten dapat menimbulkan kesalahan dalam analisis, menurunkan akurasi model, dan menghasilkan keputusan yang kurang tepat. Oleh karena itu, prapemrosesan menjadi tahap penting untuk memastikan data dalam kondisi siap dan optimal guna menghasilkan insight serta model yang berkualitas. Berdasarkan hasil Exploratory Data Analysis sebelumnya, terdapat beberapa langkah yang perlu dilakukan:
### Preprocessing Course Dataset
1. **Cleaning Data Text**: Pada dataset course dilakukan proses pembersihan fitur text yang ada pada data, meliputi pembersihan angka, tanda baca, newline, dan spasi ganda. Kemudian dilakukan tahapan casefolded untuk mengubah text menjadi huruf kecil untuk menyamakan konteks. fitur yang dilakukan data cleaning hanya fitur institusi dan course_id saja (course_id dipilih karena mengandung kata kunci berbeda untuk tiap course dibandingkan name course yang mengandung nama yang sama).
2. **Pembersihan Lanjutan Untuk Data Text:** Selanjutnya untuk fitur course_id yang sudah dibersihkan kemudian dilakukan pengecekan apakah textnya termasuk huruf ASCII (kemungkinan dalam alphabet inggris), jika iya maka akan dilakukan pemrosesan lanjutan meliputi tokenisasi untuk memecah kata yang akan di proses, filtering untuk menghapus stopword atau kata kurang bermakna pada text dalam bahasa inggris, terakhir dilakukan lematisasi untuk mengurangi kompleksitas fitur dengan mengubah text ke bentuk dasar kamus.

    ![image](https://github.com/user-attachments/assets/09400a5e-0d4d-4e6e-a486-039d34ba3aa9)

3. **Pembuatan Fitur Gabungan content:** Setelah semua proses selesai dibuat fitur baru bernama content yang berisi kata kunci course dari course_id dan institusi pembuat course. Tujuannya Membuat representasi gabungan dari kata kunci dan institusi sebagai identitas konten kursus. Fitur ini akan digunakan untuk menghitung kemiripan antar kursus dalam sistem rekomendasi berbasis konten.

    ![image](https://github.com/user-attachments/assets/1c2644e6-b36a-4b17-bc5f-34fd60d9aae5)

4. **Ekstraksi Fitur dengan TF-IDF:** Setelah pembuatan fitur content yang berisi gabungan teks dari course_id dan institution, dilakukan proses ekstraksi fitur menggunakan metode TF-IDF (Term Frequency-Inverse Document Frequency). Proses ini bertujuan untuk mengubah teks gabungan dari fitur course_id dan institution menjadi representasi numerik yang dapat diproses oleh model machine learning. TF-IDF (Term Frequency-Inverse Document Frequency) adalah teknik yang mengukur seberapa penting suatu kata dalam sebuah dokumen relatif terhadap seluruh kumpulan dokumen. Pada dasarnya, TF-IDF mengkombinasikan dua komponen utama: Term Frequency (TF) dan Inverse Document Frequency (IDF). TF mengukur seberapa sering suatu kata muncul dalam sebuah dokumen, diukur dengan rumus:

$$ 
TF = \frac{\text{Jumlah kemunculan kata}}{\text{Jumlah kata dalam dokumen}} 
$$  
    Sedangkan IDF mengukur seberapa penting kata tersebut dalam seluruh koleksi dokumen, dengan rumus:  
$$ 
IDF = \log \left( \frac{\text{Jumlah dokumen}}{\text{Jumlah dokumen yang mengandung kata}} \right)
$$  

     Dengan mengalikan nilai TF dan IDF, kita mendapatkan TF-IDF, yang memberikan bobot lebih tinggi pada kata-kata yang muncul sering dalam dokumen tertentu, tetapi jarang muncul di 
     dokumen lain. Matriks hasil dari TF-IDF ini kemudian digunakan untuk menghitung kemiripan antar kursus dalam sistem rekomendasi berbasis konten. Setiap kursus direpresentasikan 
     sebagai sebuah dokumen, dan kata-kata dalam konten dianggap sebagai fitur. Proses ini dilakukan dengan menggunakan TfidfVectorizer dari library sklearn, yang mengubah kumpulan teks 
     menjadi vektor numerik dalam bentuk matriks sparse. Matriks ini memiliki ukuran (jumlah kursus) × (jumlah kata unik), di mana setiap selnya menunjukkan bobot pentingnya kata tertentu 
     dalam kursus tertentu. Tahapan ini sangat penting karena membantu mengurangi dimensi data yang terlalu besar dan tak terstruktur, meningkatkan relevansi kata-kata yang unik dalam 
     kursus, dan pada akhirnya memungkinkan model untuk lebih akurat dalam menghitung kemiripan antar kursus.
     
  ![image](https://github.com/user-attachments/assets/339dd3e4-2d95-486f-9bd1-e01fd8a3c094)


### Preprocessing Reviews Dataset
1. **Penghapusan Duplikat pada Reviews Dataset:** Pada tahapan EDA telah diketahui bahwa terdapat 948595 data duplikat sehingga data tersebut akan dihapus namun dengan tetap mempertahankan satu nilai rating berdasarkan rating paling terbaru untuk menjaga relevansi terhadap preferensi terkini pengguna. Tujuannya penghapusan duplikat adalah untuk menghindari bias akibat pengulangan data dan memastikan setiap interaksi user-course dihitung satu kali. Menjaga satu entri terbaru memastikan data tetap relevan secara temporal.

    ![image](https://github.com/user-attachments/assets/83a1343d-bcc9-4bda-8a29-06901b71779b)

2. **Penggabungan Dataset Reviews dan Course:** Dataset reviews yang telah dibersihkan kemudian digabungkan dengan dataset course menggunakan metode inner join berdasarkan course_id. Hal ini bertujuan agar hanya kursus yang benar-benar telah direview oleh pengguna yang digunakan untuk pelatihan model, sehingga memperkuat relevansi data pelatihan.

     ![image](https://github.com/user-attachments/assets/216e6f2b-afa6-4b20-a884-aa57dea9ef02)

4. **Filtering User dengan Interaksi Rendah:** Hasil EDA menunjukkan bahwa data bersifat sangat sparsity, artinya banyak pengguna hanya memberikan sedikit rating. Untuk mengurangi noise dan meningkatkan kualitas pelatihan, dilakukan filtering user dengan cara mengambil pengguna yang memberikan rating pada lebih dari 3 kursus saja yang akan dipertahankan. Pengguna yang memiliki ≤3 interaksi dihapus. Alasan pemilihan threshold ini adalah untuk menyeimbangkan antara kualitas (relevansi pola interaksi) dan kuantitas (jumlah total data yang masih mencukupi untuk pelatihan).

    ![image](https://github.com/user-attachments/assets/55027c99-e4f2-4b17-8a53-166811e2ec6b)

5. **Normalisasi Fitur Rating:** Setelah dilakukan filtering data selajutnya akan dilakukan normalisasi atau scaling terhadap fitur rating yang berada di rentang 1-5, normalisasi dilakukan menggunakan MinMaxScaler untuk mengurangi kompleksitas fitur dan mempermudah model dalam melakukan pemrosesan dalam menentukan suka atau tidak sukanya user terhadap course. Adapun metode MinMax Scaling sendiri adalah teknik penskalaan yang mengubah nilai fitur ke dalam rentang 0 hingga 1, teknik ini dipilih karena sederhana, tidak mengubah distribusi asli data secara signifikan, dan cocok untuk menjaga proporsi nilai dalam fitur yang memiliki skala berbeda. Rumus MinMax Scaling adalah:

$$
X_{\text{scaled}} = \frac{X - X_{\text{min}}}{X_{\text{max}} - X_{\text{min}}}
$$

  - $` X `$ adalah nilai original.  
  - $` X_{\text{min}} `$ dan $` X_{\text{max}} `$ adalah nilai minimum dan maksimum dari fitur.

6. **Encoding Fitur Kategorikal:** Berikutnya dilakukan encoding untuk fitur kategorikal yang akan digunakan dalam pelatihan model diantaranya fitur reviewers yang berisi nama user dan fitur course_id yang berisi kata kunci course atau ID dari course tidak dapat langsung diproses oleh model numerik. Oleh karena itu, dilakukan proses Label Encoding untuk mengubah nilai string menjadi nilai numerik. Hasilnya, terdapat 37.034 nilai unik untuk user dan 603 nilai unik untuk course. Proses ini penting agar data dapat diolah dalam arsitektur embedding pada model.

   ![image](https://github.com/user-attachments/assets/8d52e04c-66e7-4e11-80a0-08730eb37041)

7. **Shuffling Dataset:** langkah berikutnya adalah melakukan pengacakan data (data shuffling) sebelum dilakukan proses pemisahan data (data splitting). Pengacakan dilakukan menggunakan sintaks berikut:  

    ![image](https://github.com/user-attachments/assets/67d52fd7-7d74-4ef6-aa9f-88e901da9c4f)

   Pada sintaks di atas, sample(frac=1) berfungsi untuk mengambil 100% data dalam filtered_df dan mengacak urutannya secara acak. Parameter frac=1 berarti seluruh baris akan diambil dan 
   disusun ulang. Sementara itu, random_state=42 berfungsi sebagai penentu nilai awal (seed) dari proses pengacakan, sehingga hasilnya dapat direproduksi secara konsisten setiap kali kode 
   dijalankan. Pemilihan angka 42 bersifat arbitrer, tetapi penetapan nilai random_state secara eksplisit penting agar hasil eksperimen dapat dikontrol dan diulang dengan hasil yang sama. 
   Proses shuffling ini merupakan teknik penting dalam tahapan data preparation karena dataset asli sering kali memiliki urutan data yang tidak acak. Misalnya, data mungkin disusun 
   berdasarkan waktu submit review, ID pengguna, atau jenis kursus tertentu. Jika tidak dilakukan pengacakan, model berisiko mempelajari pola dari urutan data yang tidak mewakili 
   distribusi data secara keseluruhan. Hal ini dapat menyebabkan bias dalam proses pelatihan, dan berdampak pada penurunan akurasi serta generalisasi model. Dengan melakukan pengacakan 
   sebelum membagi data menjadi data pelatihan dan validasi, maka distribusi data menjadi lebih merata dan representatif. Ini akan meningkatkan objektivitas saat mengevaluasi performa 
   model karena data yang digunakan untuk pelatihan dan validasi memiliki keragaman yang seimbang.

8. **Splitting Dataset:** Setelah proses shuffling, dilakukan pemisahan dataset menjadi dua bagian, yaitu data pelatihan (training) dan data validasi (validation). Proporsi yang digunakan adalah 80% untuk pelatihan dan 20% untuk validasi. Data training digunakan untuk melatih model agar mampu mengenali pola dalam data, sementara data validasi digunakan untuk mengukur kemampuan generalisasi model terhadap data yang belum pernah dilihat sebelumnya. Pemisahan ini dilakukan dengan menyusun X sebagai fitur yang terdiri dari user_encoded dan course_encoded, serta y sebagai label berupa rating_normalized.
   
    ![image](https://github.com/user-attachments/assets/31a0d92f-7d6c-42ff-b0f1-426bd8971299)


## Modeling
Pada tahap ini, saya membangun dua pendekatan sistem rekomendasi untuk mempersonalisasi pengalaman belajar pengguna di platform Coursera, yaitu dengan cara Content-Based Filtering (CBF) dan Collaborative Filtering (CF) menggunakan Neural Collaborative Filtering (Recommender Net). Kedua pendekatan ini dirancang untuk saling melengkapi, agar sistem mampu menangani kebutuhan pengguna baru (cold-start) maupun pengguna aktif dengan riwayat interaksi yang banyak.

### 1. Content Based Filtering 
Sistem rekomendasi berbasis konten bertujuan untuk merekomendasikan course kepada pengguna berdasarkan kemiripan antar course dari segi deskripsi/topik. Pendekatan ini sangat berguna terutama untuk menangani permasalahan cold start, yakni ketika pengguna belum memberikan cukup rating (misalnya kurang dari 3 course), di mana pendekatan Collaborative Filtering tidak memiliki cukup data untuk memprediksi preferensi. Adapun tahapannya meliputi:
1. **Menggunakan TF-IDF (Term Frequency-Inverse Document Frequency)** untuk mentransformasi teks dari content menjadi representasi numerik dari teks deskripsi dalam bentuk vektor numerik dengan menekankan kata-kata yang penting dalam suatu dokumen namun jarang muncul di dokumen lain. Dalam konteks sistem rekomendasi berbasis konten, TF-IDF digunakan untuk mengekstrak kata-kata kunci dari deskripsi course sehingga sistem dapat menghitung kemiripan antar course dan merekomendasikan course yang memiliki konten serupa secara relevan. Pada kasus ini saya menggunakan parameter default.
2. **Menggunakan cosine similarity** untuk menghitung kesamaan antar course dari Matrix TF-IDF yang dihasilkan sebelumnya. Nilai similarity ini berkisar antara 0 hingga 1 yang menunjukkan tingkat kemiripan antar course. Secara matematis, cosine similarity antara dua vektor \( A \) dan \( B \) didefinisikan sebagai:

  $$
  \text{cosine similarity}(A, B) = \frac{A \cdot B}{\|A\| \|B\|}
  $$
  
  - \( A dot B \) adalah **dot product** dari vektor \(A \) dan \( B \).
  - \( \|A\| \) dan \( \|B\| \) adalah **magnitudo** dari vektor \( A \) dan \( B \), yang dapat dihitung menggunakan rumus:
  
  $$
  \|A\| = \sqrt{\sum_{i=1}^{n} A_i^2} \quad \text{dan} \quad \|B\| = \sqrt{\sum_{i=1}^{n} B_i^2}
  $$
  
 Sehingga rumusnya menjadi,
  
  $$
  \text{cosine similarity}(A, B) = \frac{\sum_{i=1}^{n} A_i B_i}{\sqrt{\sum_{i=1}^{n} A_i^2} \times \sqrt{\sum_{i=1}^{n} B_i^2}}
  $$
  
3. **Menyusun Top-N recommendation** berdasarkan skor kemiripan tertinggi terhadap kursus yang disukai pengguna dengan membangun fungsi course_recommendations() yang bekerja sebagai berikut:
  - Mengambil nama course input dari pengguna.
  - Menghitung top-k course terdekat berdasarkan cosine similarity (dalam kasus ini, k=5).
  - Mengecek kesamaan antara isi konten course target dengan rekomendasi berdasarkan token intersection dari kolom content.
  - Menandai apakah sebuah course dianggap relevan.
  - Melakukan evaluasi akurasi rekomendasi dengan metrik Precision, Recall, dan F1-score, menggunakan relevansi isi sebagai dasar evaluasi.

  ![image](https://github.com/user-attachments/assets/7486df58-a66f-4a6e-8364-45b8fb91d141)

**Kelebihan:**  
  - Mampu mengatasi masalah cold-start user (pengguna baru tanpa riwayat).
  - Tidak membutuhkan data interaksi pengguna.
  - Cepat dalam proses prediksi setelah matriks similarity terbentuk.  
  
**Kekurangan:**
  - Tidak mempertimbangkan preferensi atau perilaku kolektif pengguna lain.
  - Rekomendasi cenderung terbatas pada kursus yang mirip kontennya, sehingga kurang eksploratif.
  - Terbatas pada informasi fitur yang tersedia

### 2. Collaborative Filtering
Untuk melengkapi sistem rekomendasi yang andal, saya juga mengimplementasikan pendekatan Collaborative Filtering (CF) menggunakan arsitektur Neural Collaborative Filtering (NCF) yaitu RecommenderNet. Pendekatan ini memanfaatkan interaksi historis antara pengguna dan course untuk mempelajari preferensi pengguna dalam bentuk latent factors (representasi tersembunyi).

**Arsitektur Model**  
Model RecommenderNet yang dikembangkan memiliki struktur sebagai berikut:
  - Dua lapisan embedding untuk merepresentasikan masing-masing pengguna dan course dalam vektor berdimensi 32.
  - Bias embedding untuk masing-masing entitas (pengguna dan course) guna mengakomodasi rata-rata preferensi individual.
  - Operasi dot product antara user dan course embedding untuk menghitung tingkat kesukaan.
  - Aktivasi sigmoid pada output akhir untuk menghasilkan nilai prediksi antara 0 dan 1.
  - Regularisasi L2 ditambahkan untuk menghindari overfitting, dan model dikompilasi menggunakan loss BinaryCrossentropy serta optimizer RMSprop (RMSprop 
    dipilih karena Adam dan AdamW sebelumnya menyebabkan overfitting).

**Pelatihan Model**  
Model dilatih menggunakan data rating user-course yang telah diencoding. Proses pelatihan dilengkapi dengan:
  - Early Stopping untuk menghentikan pelatihan saat validasi loss stagnan.
  - ReduceLROnPlateau untuk menurunkan learning rate saat model tidak mengalami peningkatan.
  - CustomModelCheckpoint untuk menyimpan model terbaik berdasarkan RMSE dan loss toleransi.
Proses training dilakukan selama maksimum 100 epoch dengan validasi split dan batch size 32 karena ukuran 16 terlalu lambat dan 64 menyebabkan overfitting.

**Hasil Pelatihan**  
Setelah proses pelatihan selesai, model menunjukkan performa yang stabil dengan hasil sebagai berikut:
  - loss: 0.3024
  - root_mean_squared_error: 0.1896
  - val_loss: 0.3078
  - val_root_mean_squared_error: 0.1924

**Prediksi Rekomendasi**  
Setelah model dilatih, sistem melakukan rekomendasi dibuat dengan langkah berikut:
  - Memilih satu user acak dari data rating.
  - Mengambil course yang belum pernah diambil oleh user tersebut.
  - Melakukan prediksi rating untuk seluruh course tersebut.
  - Mengurutkan prediksi berdasarkan skor tertinggi dan mengambil 10 teratas.
  - Menampilkan course yang paling disukai sebelumnya oleh user dan hasil rekomendasi.

  ![image](https://github.com/user-attachments/assets/0dd743f8-9849-4951-8cd1-c84fc463bcfe)

**Kelebihan:**  
  - Mampu mempelajari pola interaksi kompleks antar pengguna dan kursus.
  - Rekomendasi bersifat lebih personal karena berdasarkan perilaku pengguna sebelumnya.

**Kekurangan:**  
  - Tidak bekerja baik untuk pengguna baru (cold-start) atau kursus baru tanpa data interaksi.
  - Membutuhkan data dalam jumlah besar dan proses training yang lebih intensif.
  - Rentan terhadap overfitting jika tidak dilakukan regularisasi dengan baik.

### Kesimpulan Model
Pada tahap pemodelan, dua pendekatan sistem rekomendasi berhasil dibangun untuk meningkatkan personalisasi pengalaman belajar pengguna di platform Coursera, yaitu Content-Based Filtering (CBF) dan Collaborative Filtering (CF) dengan Neural Collaborative Filtering (NCF). Top-N Recommendation yang dihasilkan keduanya juga cukup relevan. Masing-masing pendekatan memiliki kekuatan yang saling melengkapi, di mana CBF efektif dalam menangani permasalahan cold-start karena hanya mengandalkan informasi konten dengan memanfaatkan kemiripan konten berbasis teks untuk merekomendasikan kursus serupa, sementara CF memberikan rekomendasi yang lebih personal dengan memanfaatkan pola interaksi historis pengguna didukung NCF yang mampu mempelajari preferensi tersembunyi pengguna dari data interaksi.


## Evaluation
Pada proyek sistem rekomendasi kursus ini, digunakan dua pendekatan utama yaitu Content-Based Filtering (CBF) dan Collaborative Filtering (CF) berbasis Neural Collaborative Filtering (NCF). Setiap pendekatan dievaluasi menggunakan metrik yang sesuai dengan jenis data dan tujuan dari model. 

### 1. Content-Based Filtering (CBF)
Untuk pendekatan CBF, sistem merekomendasikan kursus berdasarkan kemiripan konten dengan kursus target. Dalam kasus ini evaluasi relevansi dilakukan secara heuristik berdasarkan tumpang tindih kata dalam konten kursus, dan tidak merepresentasikan validasi terhadap interaksi pengguna sesungguhnya. Tahapan evaluasi untuk CBF meliputi:  
**1. Pemilihan Kursus Terdekat Berdasarkan Kemiripan Konten**  
   Pertama-tama, sistem mencari kursus yang paling mirip dengan kursus target berdasarkan nilai kemiripan kosinus (cosine similarity). Nilai-nilai kemiripan ini disimpan 
   dalam sebuah dataframe similarity_data, yang berisi skor kemiripan antara kursus target dan seluruh kursus lainnya. Sistem kemudian mengambil top-k kursus yang memiliki 
   skor kemiripan tertinggi, dan mengabaikan kursus asal agar tidak direkomendasikan kembali.  
**2. Penilaian Relevansi Berdasarkan Kesamaan Konten**  
   Untuk mengevaluasi seberapa "mirip" kursus yang direkomendasikan, sistem membandingkan konten (tags) dari kursus target dengan setiap kursus yang direkomendasikan. 
   Konten diubah menjadi kumpulan kata (set), lalu dicek apakah ada irisan antara konten target dan konten rekomendasi. Jika ada kesamaan, maka kursus dianggap relevan.  
**3. Menyusun Label untuk Evaluasi**  
   Untuk menghitung metrik evaluasi, sistem membuat dua daftar:
   - y_true berisi label ground truth, yaitu [1, 1, ..., 1] sebanyak jumlah kursus yang direkomendasikan. Asumsinya, semua kursus yang direkomendasikan seharusnya relevan.
   - y_pred berisi hasil evaluasi dari langkah sebelumnya: 1 jika kontennya dianggap mirip (relevan), dan 0 jika tidak.  
  
**4. Menghitung Precision, Recall, dan F1-score**  
Dengan y_true dan y_pred, tiga metrik utama dapat dihitung yaitu:  
   1. **Precision**
      Precision digunakan untuk mengukur seberapa banyak rekomendasi yang dihasilkan benar-benar relevan dengan kursus target. Dalam konteks ini, relevansi ditentukan 
      berdasarkan kemiripan tag atau konten antara kursus target dan hasil rekomendasi. Formula untuk precision adalah:

       $$\text{Precision} = \frac{TP}{TP + FP}$$

      Di mana True Positives (Relevan): Kursus yang direkomendasikan dan memiliki tag/konten serupa dengan kursus target dan False Positives (Tidak Relevan): Kursus yang 
      direkomendasikan tetapi tidak memiliki kemiripan konten.

   2. **Recall**
      Recall mengukur seberapa banyak kursus relevan yang berhasil direkomendasikan dari seluruh kursus yang seharusnya bisa direkomendasikan. Formula untuk recall adalah:

      $$\text{Recall} = \frac{TP}{TP + FN}$$

      Dalam konteks ini, Recall dihitung dengan asumsi bahwa seluruh hasil rekomendasi seharusnya relevan (karena ground truth terbatas), sehingga nilainya bisa sedikit 
      bias namun tetap informatif.

   3. **F1-Score**
      F1-score merupakan harmonic mean dari Precision dan Recall, memberikan keseimbangan antara keduanya. Formula F1-score adalah:

      $$\text{F1 Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$$

      Nilai F1-score yang tinggi menandakan bahwa sistem tidak hanya memberikan banyak hasil relevan (precision tinggi), tetapi juga menangkap sebagian besar dari hasil 
      yang seharusnya direkomendasikan (recall tinggi).

Hasil evaluasi menunjukkan nilai Precision, Recall, dan F1-Score sebesar 1.0, menandakan bahwa semua kursus yang direkomendasikan oleh sistem memiliki kemiripan konten/tag yang tinggi terhadap kursus target. Hal ini menunjukkan bahwa pendekatan CBF cukup efektif untuk menangkap kesamaan konten dalam konteks dataset ini.
                  
  ![image](https://github.com/user-attachments/assets/cf6c8fab-6408-42a6-b268-d474f657f55b)
  ![image](https://github.com/user-attachments/assets/a3d7e05d-085e-4ed8-b4a4-32df9681dbe6)

### 2. Collaborative Filtering
Untuk pendekatan CF, digunakan model neural network (RecommenderNet) yang dilatih menggunakan embedding dari user_id dan course_id, serta dikompilasi menggunakan fungsi loss Binary Crossentropy dan **metrik evaluasi utama Root Mean Squared Error (RMSE)**.  
  
**RMSE (Root Mean Squared Error)**  
**RMSE** digunakan untuk mengukur seberapa akurat prediksi interaksi (dalam hal ini rating atau preferensi) antara pengguna dan kursus yang dihasilkan oleh sistem rekomendasi dibandingkan dengan rating yang sebenarnya diberikan oleh pengguna. RMSE menunjukkan akar rata-rata kuadrat dari kesalahan antara rating prediksi dan rating aktual.

- **Rumus RMSE**:  

  $` RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2} `$

  - $`(y_i)`$ adalah rating aktual, dan $`(\hat{y}_i)`$ adalah rating prediksi.

Semakin kecil nilai RMSE, semakin baik performa model dalam memprediksi preferensi pengguna terhadap kursus. 

Nilai RMSE yang lebih kecil menunjukkan prediksi yang lebih akurat. Dalam proyek ini, model mencapai nilai RMSE sebesar ±0.18, yang menandakan bahwa model mampu memprediksi preferensi pengguna terhadap kursus dengan tingkat kesalahan yang rendah, di mana ini sudah cukup bagus untuk sekelas sistem rekomendasi CBF.

  ![image](https://github.com/user-attachments/assets/957b003a-9886-43f5-a9f6-7a36edc63470)

### Kesimpulan Evaluasi  
Berdasarkan hasil evaluasi, sistem rekomendasi kursus ini menunjukkan performa yang baik pada kedua pendekatan yang digunakan. Pada pendekatan Content-Based Filtering (CBF), sistem berhasil merekomendasikan kursus yang sangat relevan berdasarkan kesamaan konten, ditunjukkan oleh nilai precision, recall, dan F1-score yang mencapai 1.0. Hal ini mengindikasikan bahwa sistem mampu menangkap kemiripan informasi secara efektif antara kursus target dan rekomendasinya. Sementara itu, pendekatan Collaborative Filtering (CF) berbasis Neural Collaborative Filtering (NCF) menunjukkan kinerja prediksi yang cukup akurat dengan nilai Root Mean Squared Error (RMSE) sebesar sekitar 0.18. Nilai ini menunjukkan bahwa model dapat mempelajari preferensi pengguna dengan tingkat kesalahan yang relatif rendah. Secara keseluruhan, metrik yang digunakan telah sesuai dengan karakteristik data dan tujuan dari masing-masing pendekatan, serta memberikan gambaran menyeluruh mengenai efektivitas sistem dalam memberikan rekomendasi yang relevan dan personal.

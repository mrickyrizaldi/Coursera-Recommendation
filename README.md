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
- Solusi 1: Membangun sistem Content-Based Filtering yang merekomendasikan kursus berdasarkan kesamaan konten dengan kursus yang telah diminati pengguna. Representasi konten akan dihasilkan menggunakan teknik TF-IDF dari fitur seperti judul dan institusi kursus, kemudian dilakukan pengukuran kemiripan menggunakan cosine similarity untuk menghasilkan daftar kursus yang relevan. Sistem ini ditujukan untuk pengguna baru yang belum banyak berinteraksi dengan platform.
- Solusi 2: Membangun sistem Collaborative Filtering menggunakan pendekatan Neural Collaborative Filtering (Recommender Net) dengan memanfaatkan embedding untuk merepresentasikan pengguna dan kursus. Sistem ini akan dilatih menggunakan data historis ulasan atau rating dari pengguna dan bertujuan untuk memberikan rekomendasi berdasarkan preferensi kolektif pengguna lain yang memiliki pola interaksi serupa.
- Solusi 3: Mengintegrasikan kedua pendekatan tersebut untuk menciptakan sistem yang adaptif baik terhadap pengguna baru maupun pengguna lama. Sistem Content-Based Filtering akan menangani cold-start user, sementara sistem Collaborative Filtering akan menyajikan rekomendasi berbasis interaksi yang lebih personal. Pendekatan ini diharapkan meningkatkan cakupan dan relevansi rekomendasi yang dihasilkan.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai jumlah data, kondisi data, dan informasi mengenai data yang digunakan. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

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

# Ringkasan Paper

**Molecular Investigation on Active Compounds in Papaya Leaves (Carica papaya Linn) as Anti-Malaria Using Network Pharmacology, Molecular Docking, Clustering-Based Analysis and Molecular Dynamics Simulation**

Malaria masih menjadi masalah kesehatan global yang serius karena disebabkan oleh parasit Plasmodium yang ditularkan melalui gigitan nyamuk Anopheles betina. Di Indonesia, lebih dari 400.000 kasus malaria dilaporkan, dengan prevalensi tertinggi di Provinsi Papua. Pengobatan malaria umumnya masih bergantung pada Artemisinin, namun penggunaan jangka panjang memicu resistensi parasit serta efek samping seperti gangguan ginjal dan hati. Daun pepaya (Carica papaya Linn) diketahui mengandung alkaloid, flavonoid, saponin, tanin, dan terpenoid yang dilaporkan memiliki aktivitas antimalaria, namun senyawa bioaktif spesifik dan mekanisme molekulernya belum banyak diungkap secara ilmiah. 

Penelitian ini bertujuan mengidentifikasi senyawa bioaktif daun pepaya yang berpotensi sebagai antimalaria, mengungkap target protein terkait malaria, serta memahami mekanisme dan stabilitas ikatannya terhadap protein parasit Plasmodium falciparum melalui pendekatan network pharmacology dan simulasi molekuler. 

Penelitian diawali dengan pengumpulan tujuh belas senyawa aktif daun pepaya dari database IJAH Analytics beserta struktur SMILES dari PubChem. Target protein senyawa diprediksi menggunakan TargetNet, SuperPred, dan SwissTargetPrediction, lalu disandingkan dengan target terkait malaria dari GeneCards. Jaringan protein-protein interaction (PPI) dianalisis menggunakan STRING dan Cytoscape (CytoNCA) untuk menentukan hub gene utama. Selanjutnya, molecular docking dengan AutoDock Vina dilakukan terhadap protein parasit Falcipain-2, dilanjutkan simulasi molecular dynamics (AMBER20, 100 ns) dan analisis k-means clustering untuk memvalidasi situs ikatan senyawa terbaik. 

Sebanyak 23 protein target yang beririsan antara senyawa daun pepaya dan malaria berhasil diidentifikasi, dengan STAT3 sebagai hub gene peringkat pertama berdasarkan analisis topologi jaringan. Hasil docking terhadap Falcipain-2 menunjukkan lima senyawa, yaitu Beta-cryptoxanthin, Gibberellic acid, Heptadecane-9-carboxylic acid, Citroxanthin, dan Carpaine, memiliki afinitas ikatan lebih tinggi dibanding Artemisinin sebagai kontrol. Simulasi MD selama 100 ns menunjukkan seluruh kompleks tetap stabil, dengan Citroxanthin menghasilkan energi ikatan MM-GBSA terbaik sebesar -36,08 kkal/mol. Analisis clustering dari 1000 iterasi docking mengonfirmasi cluster 1 (65,4%) sebagai situs ikatan dominan Citroxanthin, dengan residu TRP201 berperan penting, menyerupai pola ikatan Artemisinin pada reseptor yang sama. 

Kelebihan penelitian ini terletak pada integrasi network pharmacology dengan molecular docking, simulasi MD, dan clustering, sehingga prediksi target serta stabilitas kompleks ligan-reseptor dapat divalidasi secara komputasional berlapis. Namun, penelitian ini sepenuhnya bersifat in silico tanpa validasi eksperimental in vitro maupun in vivo, sehingga belum memperhitungkan aspek bioavailabilitas, metabolisme, ekskresi, dan toksisitas senyawa yang penting untuk memastikan efikasi obat yang sesungguhnya. 

Penelitian ini menunjukkan bahwa pendekatan komputasional berlapis, mulai dari network pharmacology, docking, hingga MD simulation dan clustering, mampu menyaring kandidat obat alami secara efisien sebelum masuk ke tahap eksperimen yang mahal dan memakan waktu. Citroxanthin dari daun pepaya menjadi contoh nyata bagaimana senyawa alami berpotensi menjadi alternatif antimalaria di tengah meningkatnya resistensi terhadap Artemisinin, sekaligus menegaskan pentingnya uji lanjutan in vitro dan in vivo sebelum menuju uji klinis.


## Methods and Results Illustration

<img width="1300" height="760" alt="infografis" src="https://github.com/user-attachments/assets/e3cdef26-64ef-4732-96c0-ccf9a1fc2e18" />


*Gambar 1. Ringkasan alur metode dan hasil utama penelitian Arwansyah et al. (2025) mengenai potensi senyawa aktif daun pepaya (Carica papaya Linn) sebagai antimalaria.*

# Portfolio - In Silico Drug Discovery

## 📌 Capstone Project (Final)
- [Laporan Capstone - Polyphyllin I vs Hepatocellular Carcinoma](Laporan_Singkat_Capstone_PolyphyllinI_HCC.md)
- Data pendukung: folder [`data/`](data), [`docking_files/`](docking_files), [`visualizations/`](visualizations)

## 📝 Tugas Mingguan
- [Week 1 - Network Pharmacology (Carica papaya Linn vs Malaria)](07_Zaskia%20Adyarizki%20S_Week1.md)
- [Week 2 - Network Pharmacology (QLYD vs Atherosclerosis)](07_Zaskia%20Adyarizki%20S_Week2.md)
- [Week 3 - Molecular Docking (PPARG vs Wogonin)](07_Zaskia%20Adyarizki%20S_Week3.md)

# Capstone Project: In Silico Drug Discovery
## Eksplorasi Mekanisme Molekuler Polyphyllin I terhadap Hepatocellular Carcinoma (HCC)

Proyek ini mengeksplorasi mekanisme molekuler **Polyphyllin I** (saponin steroid dari *Paris polyphylla*) terhadap **Hepatocellular Carcinoma (HCC)** melalui pendekatan **network pharmacology** dan **molecular docking**, mereplikasi dan mengembangkan lebih lanjut metodologi dari paper acuan:

> Chen, Y., Wang, Q., Bian, S., Dong, J., Xiong, J., & Le, J. (2025). Exploration of the mechanism of Polyphyllin I against hepatocellular carcinoma based on network pharmacology, molecular docking and experimental validation. *Discover Oncology*, 16, 941. https://doi.org/10.1007/s12672-025-02341-5

## Ringkasan Temuan

- **65 gen target potensial** teridentifikasi dari irisan 352 target senyawa (SwissTargetPrediction + PharmMapper) dan 972 target penyakit HCC (GeneCards + OMIM + PharmGKB)
- **10 hub gene teratas** (cytoHubba, metode Degree): STAT3, ALB, AKT1, EGFR, ESR1, CASP3, HIF1A, MMP9, SRC, PTGS2
- **Enrichment KEGG**: Pathways in Cancer, Hepatocellular carcinoma, PI3K-Akt signaling pathway — konsisten dengan paper acuan
- **Molecular docking** terhadap KDR (VEGFR2, PDB 6XVJ): afinitas terbaik **-9,1675 kkal/mol** (SwissDock, metode Attracting Cavities 2.0), lebih kuat dari ambang -6,0 kkal/mol yang dilaporkan paper acuan

## Workflow Analisis

1. **Identifikasi senyawa** — PubChem (CID 11018329)
2. **Prediksi target senyawa** — SwissTargetPrediction, PharmMapper (+ UniProt ID Mapping), STITCH
3. **Identifikasi target penyakit** — GeneCards, OMIM, PharmGKB
4. **Irisan target** — Venny 2.1
5. **Jaringan PPI** — STRING (confidence ≥ 0,4) + Cytoscape
6. **Identifikasi hub gene** — cytoHubba (metode Degree)
7. **Enrichment analysis** — ShinyGO (GO Biological Process, Molecular Function, KEGG Pathway)
8. **Pemilihan target docking** — berdasarkan hub gene + KEGG pathway
9. **Binding site prediction** — PrankWeb
10. **Molecular docking** — SwissDock (metode Attracting Cavities 2.0)

## Catatan Metodologis

- Database STITCH tidak menemukan entri untuk Polyphyllin I (database sudah tidak aktif/unsupported sejak 2016)
- PDB 1VR2 (struktur apo KDR) awalnya dipilih tetapi gagal diproses SwissDock karena beberapa residu memiliki atom rantai samping tidak lengkap; diganti dengan PDB 6XVJ (resolusi lebih tinggi, 1,78 Å)
- 12 dari 297 Uniprot ID hasil PharmMapper tidak berhasil dipetakan ke simbol gen resmi karena penamaan identifier yang sudah usang
- Gen VDR (bagian dari 65 gen irisan) tidak menunjukkan interaksi dengan gen lain pada jaringan PPI confidence ≥0,4, sehingga tidak muncul sebagai node dalam network

## Author

Zaskia Adyarizki Salsabila — Kelompok Belajar 07

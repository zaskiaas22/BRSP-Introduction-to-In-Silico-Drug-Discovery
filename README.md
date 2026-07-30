# Capstone Project: In Silico Drug Discovery
## Eksplorasi Mekanisme Molekuler Polyphyllin I terhadap Hepatocellular Carcinoma (HCC)

Proyek ini mengeksplorasi mekanisme molekuler **Polyphyllin I** (saponin steroid dari *Paris polyphylla*) terhadap **Hepatocellular Carcinoma (HCC)** melalui pendekatan **network pharmacology** dan **molecular docking**, mereplikasi dan mengembangkan lebih lanjut metodologi dari paper acuan:

> Chen, Y., Wang, Q., Bian, S., Dong, J., Xiong, J., & Le, J. (2025). Exploration of the mechanism of Polyphyllin I against hepatocellular carcinoma based on network pharmacology, molecular docking and experimental validation. *Discover Oncology*, 16, 941. https://doi.org/10.1007/s12672-025-02341-5

## Ringkasan Temuan

- **65 gen target potensial** teridentifikasi dari irisan 352 target senyawa (SwissTargetPrediction + PharmMapper) dan 972 target penyakit HCC (GeneCards + OMIM + PharmGKB)
- **10 hub gene teratas** (cytoHubba, metode Degree): STAT3, ALB, AKT1, EGFR, ESR1, CASP3, HIF1A, MMP9, SRC, PTGS2
- **Enrichment KEGG**: Pathways in Cancer, Hepatocellular carcinoma, PI3K-Akt signaling pathway — konsisten dengan paper acuan
- **Molecular docking** terhadap KDR (VEGFR2, PDB 6XVJ): afinitas terbaik **-9,1675 kkal/mol** (SwissDock, metode Attracting Cavities 2.0), lebih kuat dari ambang -6,0 kkal/mol yang dilaporkan paper acuan

## Struktur Repository

```
├── Laporan_Singkat_Capstone_PolyphyllinI_HCC.docx   # Laporan lengkap (Pendahuluan, Metode, Hasil, Kesimpulan)
├── Laporan_Singkat_Capstone_PolyphyllinI_HCC.md      # Versi Markdown (untuk preview GitHub)
├── data/
│   ├── 01_target_senyawa_SwissTargetPrediction.csv
│   ├── 02_target_senyawa_PharmMapper_raw.csv
│   ├── 03_target_senyawa_PharmMapper_UniProtMapping.tsv
│   ├── 04_target_senyawa_PharmMapper_final.csv
│   ├── 05_target_senyawa_GABUNGAN_352gen.csv
│   ├── 06_target_penyakit_GeneCards_833gen.csv
│   ├── 07_target_penyakit_OMIM_193gen.csv
│   ├── 08_target_penyakit_PharmGKB_12gen.csv
│   ├── 09_target_penyakit_GABUNGAN_972gen.csv
│   ├── 10_gen_irisan_65gen.csv
│   ├── 11_STRING_PPI_network_cleaned.tsv
│   └── 12_docking_results_50poses.csv
├── docking_files/
│   └── docking_input_PolyphyllinI_KDR.txt            # SMILES, PDB ID, parameter docking lengkap
└── visualizations/
    ├── 00_pubchem_polyphyllin_I.png
    ├── 01_venn_diagram_irisan.png
    ├── 02_PPI_network_cytoscape_import.png
    ├── 03_hub_gene_cytoHubba.jpg
    ├── 04_enrichment_GO_biological_process.png
    ├── 05_enrichment_GO_molecular_function.png
    ├── 06_enrichment_KEGG_pathway.png
    ├── 07_prankweb_binding_site_6XVJ.png
    ├── 08_swissdock_query_config.png
    └── 09_docking_pose_cluster9_TERBAIK.png
```

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

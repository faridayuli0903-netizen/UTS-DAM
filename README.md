# UTS Data Acquisition & Management (UTS-DAM)

## Data Diri

- **Nama:** Yuliana Farida
- **NIM:** 2501010372
- **Kelas / Program Studi:** Kelas F — S1 Informatika, INSTIKI
- **Email:** 2501010372@instiki.ac.id
- **Topik:** Sektor Budaya Provinsi Bali (Warisan Budaya & Museum) per Kabupaten/Kota

## Goal / Tujuan

Mengumpulkan, mengidentifikasi kolom PII/quasi-identifier, memvalidasi Data Ethics Checklist (9 butir) dan izin `robots.txt` (`True`), membersihkan, serta menggabungkan data sektor Budaya & Museum di Provinsi Bali dari tiga metode akuisisi (Unduh Dataset Terbuka, REST API SPARQL, dan Web Scraping HTML) menjadi satu tabel terintegrasi per Kabupaten/Kota (`one_to_one`).

## Sumber Data & URL

| No | Metode Akuisisi | Nama Sumber | URL | File Raw (`Data/Raw/`) | File Process (`Data/Process/`) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Unduh Dataset Terbuka | Daftar Museum Resmi Provinsi Bali (Wikipedia Open Data) | https://id.wikipedia.org/wiki/Daftar_museum_di_Bali | `dataset_budaya_bali_raw.csv` | `dataset_budaya_bersih.csv` |
| 2 | REST API | Wikidata Query Service SPARQL API (Entitas Budaya & Pura Bali) | https://query.wikidata.org/sparql | `api_wikidata_sparql_raw.json` | `api_wikidata_budaya_bali.csv` |
| 3 | Web Scraping | Wikipedia Bahasa Indonesia — Daftar Kabupaten dan Kota di Bali | https://id.wikipedia.org/wiki/Daftar_kabupaten_dan_kota_di_Bali | `wikipedia_kabupaten_kota_bali.html` | `hasil_scraping_wilayah_bali.csv` |
| 4 | Gabungan | Hasil Integrasi 3 Sumber (9 Kabupaten/Kota Bali) | — | — | `hasil_gabungan_budaya_bali.csv` & `.json` |

## Struktur Repositori

```text
UTS-DAM/
├── Data/
│   ├── Raw/                              # Menyimpan data mentah asli dari 3 sumber
│   │   ├── dataset_budaya_bali_raw.csv
│   │   ├── api_wikidata_sparql_raw.json
│   │   └── wikipedia_kabupaten_kota_bali.html
│   └── Process/                          # Menyimpan data bersih berbentuk tabel & gabungan
│       ├── dataset_budaya_bersih.csv
│       ├── api_wikidata_budaya_bali.csv
│       ├── hasil_scraping_wilayah_bali.csv
│       ├── hasil_gabungan_budaya_bali.csv
│       ├── hasil_gabungan_budaya_bali.json
│       └── visual_budaya_bali.png
├── docs/                                 # Dokumentasi etika, kepatuhan robots.txt & provenance
│   ├── data_ethics_checklist.csv
│   ├── provenance.csv
│   └── robots_check.json
├── UTS_DAM_2501010372.ipynb              # Notebook utama lengkap (Konfigurasi + Soal 1 s.d. 5)
├── Download_CSV.ipynb                    # Notebook akuisisi dataset terbuka & estimasi storage
├── API.ipynb                             # Notebook akuisisi data entitas budaya via REST API Wikidata
├── Scrapping.ipynb                       # Notebook pemeriksaan robots.txt, etika & penggabungan
└── README.md                             # Dokumentasi utama proyek UTS

# UTS Data Acquisition & Management (UTS-DAM)

## Data Diri
- **Nama:** Yuliana Farida
- **NIM:** 2501010372
- **Kelas / Program Studi:** Kelas F — S1 Informatika, INSTIKI
- **Email:** 2501010372@instiki.id
- **Topik:** Sektor Budaya Provinsi Bali (Warisan Budaya & Museum)

## Goal / Tujuan
Mengumpulkan, mengidentifikasi kolom PII/quasi-identifier, memvalidasi Data Ethics Checklist (9 butir) dan izin `robots.txt` (`True`), membersihkan, serta menggabungkan data sektor Budaya & Museum di Provinsi Bali dari tiga metode akuisisi (Unduh Dataset Terbuka, MediaWiki Action API, dan Web Scraping HTML) menjadi satu tabel terintegrasi (`one_to_one`) beserta visualisasinya.

## Sumber Data & URL
| No | Metode Akuisisi | Nama Sumber | URL | File Raw (`data/raw/`) | File Processed (`data/processed/`) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Unduh Dataset Terbuka | Dataset Terbuka Sektor Budaya Bali (120 objek, 9 kab/kota) | https://bali.bps.go.id/ | `dataset_budaya_bali.csv` | — |
| 2 | REST API | MediaWiki Action API Wikipedia Bahasa Indonesia (4 kategori budaya Bali, 91 artikel) | https://id.wikipedia.org/w/api.php | `api_kategori_budaya_bali.json`, `api_kategori_tarian_bali.json`, `api_kategori_museum_di_bali.json`, `api_kategori_pura_di_bali.json` | `api_budaya_bali_wikipedia.csv` |
| 3 | Web Scraping | Wikipedia Bahasa Indonesia — Daftar Museum di Bali (35 museum) | https://id.wikipedia.org/wiki/Daftar_museum_di_Bali | `robots_wikipedia.txt`, `scraping_daftar_museum_bali.html`, `scraping_kategori_museum_bali.html` | `scraping_museum_bali.csv` |
| 4 | Gabungan & Visual | Hasil Integrasi (`left join`, `validate="one_to_one"`) & Grafik | — | — | `gabungan_budaya_bali_api_scraping.csv`, `gabungan_budaya_bali_api_scraping.metadata.json`, `visualisasi_budaya_bali.png` |

## Struktur Repositori
```text
UTS-DAM/
├── data/
│   ├── raw/                                          # Data mentah asli (tidak diubah)
│   │   ├── api_kategori_budaya_bali.json
│   │   ├── api_kategori_museum_di_bali.json
│   │   ├── api_kategori_pura_di_bali.json
│   │   ├── api_kategori_tarian_bali.json
│   │   ├── dataset_budaya_bali.csv
│   │   ├── robots_wikipedia.txt
│   │   ├── scraping_daftar_museum_bali.html
│   │   └── scraping_kategori_museum_bali.html
│   └── processed/                                    # Data hasil olah, metadata & visualisasi
│       ├── api_budaya_bali_wikipedia.csv
│       ├── gabungan_budaya_bali_api_scraping.csv
│       ├── gabungan_budaya_bali_api_scraping.metadata.json
│       ├── scraping_museum_bali.csv
│       └── visualisasi_budaya_bali.png
├── docs/                                             # Dokumentasi etika, kepatuhan robots.txt & provenance
│   ├── bukti_robots_txt.csv
│   ├── data_ethics_checklist.csv
│   ├── data_ethics_checklist.md
│   └── provenance.csv
├── UTS_DAM_2501010372.ipynb                          # Notebook utama lengkap (Konfigurasi + Soal 1 s.d. 5)
├── Download_CSV.ipynb                                # Notebook akuisisi dataset terbuka & estimasi storage
├── API.ipynb                                         # Notebook akuisisi data entitas budaya via REST API
├── Scrapping.ipynb                                   # Notebook pemeriksaan robots.txt, etika & penggabungan
└── README.md                                         # Dokumentasi utama proyek UTS

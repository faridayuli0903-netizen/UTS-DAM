# UTS Data Acquisition & Management (UTS-DAM)

## Data Diri
- **Nama:** Yuliana Farida
- **NIM:** 2501010372
- **Kelas / Program Studi:** Kelas F — S1 Informatika, INSTIKI
- **Email:** faridayuli0903@gmail.com
- **Topik:** Sektor Budaya Provinsi Bali (Warisan Budaya & Museum) per Kabupaten/Kota

## Goal / Tujuan
Mengumpulkan, mengidentifikasi kolom PII/quasi-identifier, memvalidasi Data Ethics Checklist (9 butir) dan izin `robots.txt` (`True`), membersihkan, serta menggabungkan data sektor Budaya & Museum di Provinsi Bali dari tiga metode akuisisi (Unduh Berkas CSV, REST API JSON, dan Web Scraping HTML) menjadi satu tabel terintegrasi per Kabupaten/Kota (`one_to_one`).

## Sumber Data & URL
| No | Metode Akuisisi | Nama Sumber | URL | File Raw (`Data/Raw/`) | File Process (`Data/Process/`) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Unduh Berkas | Dataset Terbuka Museum & Budaya (TidyTuesday) | https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2022/2022-11-22/museums.csv | `dataset_museum_budaya.csv` | `dataset_budaya_bersih.csv` |
| 2 | REST API | Wikidata Action API (Entitas Budaya & Museum Bali) | https://www.wikidata.org/w/api.php | `wikidata_budaya_*.json` | `api_wikidata_budaya_bali.csv` |
| 3 | Web Scraping | Katalog Publikasi Travel & Budaya (Books to Scrape) | https://books.toscrape.com/catalogue/category/books/travel_2/index.html | `katalog_travel_budaya_web.html` | `hasil_scraping_wilayah_bali.csv` |
| 4 | Gabungan | Hasil Integrasi 3 Sumber (9 Kabupaten/Kota Bali) | — | — | `hasil_gabungan_budaya_bali.csv` |

## Struktur Repositori
```text
UTS-DAM/
├── Data/
│   ├── Raw/                         # Menyimpan data mentah asli dari 3 sumber
│   │   ├── dataset_museum_budaya.csv
│   │   ├── wikidata_budaya_*.json
│   │   └── katalog_travel_budaya_web.html
│   └── Process/                     # Menyimpan data bersih berbentuk tabel & gabungan
│       ├── dataset_budaya_bersih.csv
│       ├── api_wikidata_budaya_bali.csv
│       ├── hasil_scraping_wilayah_bali.csv
│       ├── hasil_gabungan_budaya_bali.csv
│       └── visual_budaya_bali.png
├── UTS_DAM_2501010372.ipynb         # Notebook utama lengkap (Konfigurasi + Soal 1 s.d. 5)
├── Download_CSV.ipynb               # Notebook proses pembersihan data CSV/Excel
├── API.ipynb                        # Notebook akuisisi & pembersihan data REST API Wikidata
├── Scrapping.ipynb                  # Notebook pengecekan izin scraping (robots.txt), etika & penggabungan
└── README.md                        # Dokumentasi utama proyek UTS

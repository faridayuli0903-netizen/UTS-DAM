# UTS Data Acquisition & Management (UTS DAM)

## Data Diri
* **Nama:** Yuliana Farida
* **NIM:** 2501010372
* **Kelas / Program Studi:** Kelas F — S1 Informatika
* **Institusi:** Institut Bisnis dan Teknologi Indonesia (INSTIKI)
* **Email:** faridayuli0903@gmail.com
* **Topik:** Sektor Budaya Provinsi Bali (Warisan Budaya & Museum) per Kabupaten/Kota

## Goal / Tujuan
Mengumpulkan, mengidentifikasi aspek privasi/etika (PII & *quasi-identifier*), membersihkan, dan menggabungkan data sektor Budaya & Museum di Provinsi Bali dari tiga metode akuisisi (Unduh Berkas Dataset Terbuka, REST API Open-Meteo, dan Web Scraping HTML) menjadi satu tabel terintegrasi per Kabupaten/Kota dengan validasi `one_to_one` tanpa duplikasi.

## Sumber Data & URL
| No | Metode Akuisisi | Nama Sumber | URL | Format Raw | Format Process |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Unduh Berkas | Dataset Terbuka Museum & Budaya (TidyTuesday) | https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2022/2022-11-22/museums.csv | CSV (`dataset_museum_budaya.csv`) | CSV (`dataset_budaya_bersih.csv`) |
| 2 | REST API | Open-Meteo Historical Weather API (Bali 2025) | https://archive-api.open-meteo.com/v1/archive | JSON (`openmeteo_bali_2025_gabungan.json`) | CSV (`cuaca_harian_bersih.csv`) |
| 3 | Web Scraping | Katalog Publikasi Travel & Budaya (Books to Scrape) | https://books.toscrape.com/catalogue/category/books/travel_2/index.html | HTML (`katalog_travel_budaya_web.html`) & CSV (`tabel_mentah_web.csv`) | CSV (`hasil_scraping_wilayah_bali.csv`) |

## Struktur Repositori
* `UTS_DAM_2501010372.ipynb` — Notebook Google Colab lengkap (Soal 1 s.d. Soal 5).
* `Data/Raw/` — Data mentah hasil unduhan berkas (CSV), respons REST API (JSON), dan hasil *web scraping* (HTML/CSV) tanpa modifikasi.
* `Process/` — Data bersih hasil olah masing-masing sumber, tabel gabungan akhir (`hasil_gabungan_budaya_bali.csv` & `.json`), serta visualisasi (`visual_budaya_bali.png`).
* `docs/` — Dokumentasi *provenance* & hash MD5 (`provenance.csv`), bukti pengecekan `robots.txt` dengan status `can_fetch: true` (`robots_check.json`), klasifikasi PII (`klasifikasi_pii.csv`), *Data Ethics Checklist* (`data_ethics_checklist.csv`), estimasi penyimpanan (`estimasi_storage.csv`), dan metadata gabungan (`metadata_gabungan.json`).

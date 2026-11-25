# UTS Data Acquisition & Management - Sektor Budaya Provinsi Bali

* **Nama:** Yuliana Farida
* **NIM:** 2501010372
* **Kelas:** F (Informatika - INSTIKI)
* **Topik:** Sektor Budaya Provinsi Bali (Warisan Budaya & Museum)

## Struktur Repositori
* `UTS_DAM_2501010372.ipynb` — Notebook utama Python untuk proses akuisisi, etika data, pembersihan, penggabungan (`one_to_one`), dan visualisasi data.
* `Data/Raw/` — Data mentah hasil unduhan dataset publik museum (`dataset_museum_budaya.csv`), data historis cuaca 2025 dari API Open-Meteo (9 wilayah Bali), dan halaman statis portal resmi BPK Bali Kemendikbud (`profil_budaya_bali_kemdikbud.html`).
* `Data/Process/` — Dataset bersih hasil normalisasi (`dataset_budaya_bersih.csv`, `cuaca_harian_bersih.csv`, `hasil_scraping_wilayah_bali.csv`), data gabungan terintegrasi (`hasil_gabungan_budaya_bali.csv` & `.json`), serta visualisasi grafik (`visual_budaya_bali.png`).
* Dokumentasi Etika & Tata Kelola (`provenance.csv`, `data_ethics_checklist.csv`, `klasifikasi_pii.csv`, `estimasi_storage.csv`, `robots_check.json`, `metadata_gabungan.json`).

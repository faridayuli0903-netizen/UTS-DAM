# UTS_DAM_2501010372 — Data Acquisition & Management

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/faridayuli0903-netizen/UTS-DAM/blob/main/UTS_DAM_2501010372.ipynb)

## 1. Data Diri
| Keterangan | Identitas |
| :--- | :--- |
| **Nama** | Yuliana Farida |
| **NIM** | 2501010372 |
| **Program Studi** | Informatika — Management Data Analyst |
| **Kelas** | F |
| **Mata Kuliah** | Data Acquisition & Management |
| **Dosen** | Dr. I Gede Totok Suryawan, S.Kom., M.T. |

---

## 2. Sumber / URL
| No. | Metode Akuisisi | Sumber | URL | Bentuk Data |
| :---: | :--- | :--- | :--- | :--- |
| 1 | Unduh dataset | Dataset Publik Museum & Warisan Budaya | URL aktual dicatat pada `docs/provenance.csv` | CSV |
| 2 | API | Open-Meteo Historical Weather API (9 Kab/Kota Bali) | `https://archive-api.open-meteo.com/v1/archive` | JSON |
| 3 | Web scraping | Portal Resmi BPK Bali Kemendikbud | URL halaman aktual dicatat pada `docs/provenance.csv` dan `docs/robots_check.json` | HTML / tabel |

> **Catatan:** URL dataset dan halaman scraping yang benar-benar berhasil diakses telah diverifikasi dari hasil notebook dan tercatat di `provenance.csv`.

---

## 3. Goal / Tujuan
Topik yang digunakan adalah **Sektor Budaya Provinsi Bali (Warisan Budaya & Museum) per Kabupaten/Kota**. Tujuan pengerjaan adalah mengakuisisi data museum/warisan budaya melalui dataset terbuka, mengambil data historis cuaca tahun 2025 untuk 9 wilayah di Bali melalui API Open-Meteo, serta melakukan web scraping dari halaman portal resmi BPK Bali Kemendikbud yang lolos pemeriksaan `robots.txt`. Data dari sumber-sumber tersebut kemudian dibersihkan, dinormalisasi, dan digabungkan (`one_to_one`) berdasarkan kunci wilayah untuk menghasilkan tabel analisis dan visualisasi.

---

## 4. Data Raw
Folder `Data/Raw/` digunakan untuk menyimpan seluruh hasil akuisisi mentah tanpa perubahan:

| Jenis Data | Nama File | Format | Keterangan |
| :--- | :--- | :--- | :--- |
| Dataset unduhan | `dataset_museum_budaya.csv` | CSV | Dataset asli museum & budaya |
| Data API | `openmeteo_bali_2025_gabungan.json` & 9 file kab/kota | JSON | Respons mentah Open-Meteo |
| Data scraping | `profil_budaya_bali_kemdikbud.html`, `tabel_mentah_web.csv` | HTML / CSV | Halaman statis BPK Bali Kemendikbud |

---

## 5. Process
Folder `Data/Process/` digunakan untuk menyimpan data hasil pembacaan, normalisasi, pembersihan, penggabungan, dan visualisasi:

| Hasil Proses | Nama File | Format |
| :--- | :--- | :--- |
| Dataset budaya bersih | `dataset_budaya_bersih.csv` | CSV |
| Data API cuaca ternormalisasi | `cuaca_harian_bersih.csv` | CSV |
| Data scraping terstruktur | `hasil_scraping_wilayah_bali.csv` | CSV |
| Hasil penggabungan (`one_to_one`) | `hasil_gabungan_budaya_bali.csv` & `.json` | CSV / JSON |
| Visualisasi hasil gabungan | `visual_budaya_bali.png` | PNG |

---

## 6. Dokumentasi
Dokumentasi tata kelola dan etika data berisi catatan asal-usul data (*provenance*), *Data Ethics Checklist*, bukti pemeriksaan `robots.txt`, klasifikasi PII, estimasi *storage*, dan metadata hasil penggabungan (`provenance.csv`, `data_ethics_checklist.csv`, `klasifikasi_pii.csv`, `estimasi_storage.csv`, `robots_check.json`, `metadata_gabungan.json`).

---

## 7. Cara Menjalankan
1. Buka notebook `UTS_DAM_2501010372.ipynb` melalui Google Colab atau Jupyter.
2. Isi email pribadi pada Colab Secrets dengan nama `EMAIL_PRIBADI`, atau file `.env` jika dijalankan secara lokal.
3. Jalankan seluruh sel notebook secara berurutan.
4. Periksa bahwa dataset mentah tersimpan di `Data/Raw/`, hasil olahan di `Data/Process/`, dan dokumentasi etika/provenance tersedia lengkap.

---

## 8. Struktur Folder
```text
UTS-DAM/
├── README.md
├── UTS_DAM_2501010372.ipynb
├── Data/
│   ├── Raw/               # Data mentah hasil unduhan, API, dan scraping
│   └── Process/           # Data bersih, hasil merge, dan visualisasi
├── provenance.csv         # Catatan sumber dan lisensi data
├── data_ethics_checklist.csv
├── klasifikasi_pii.csv
├── estimasi_storage.csv
├── robots_check.json
└── metadata_gabungan.json

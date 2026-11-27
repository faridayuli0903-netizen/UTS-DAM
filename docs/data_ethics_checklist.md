# Data Ethics Checklist

|    | aspek                                        | status   | bukti                                                                                                                                                |
|---:|:---------------------------------------------|:---------|:-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  1 | Sumber data dan URL dicantumkan              | Ya       | 8 entri provenance (URL, tanggal akses, MD5) -> docs/provenance.csv                                                                                  |
|  2 | Lisensi data diperiksa dan dicatat           | Ya       | Dataset (a): data terbuka pemerintah; API & Scraping (b/c): CC BY-SA 4.0 Wikipedia Bahasa Indonesia                                                  |
|  3 | robots.txt / Terms of Service diperiksa      | Ya       | robots.txt Wikipedia disimpan (MD5 8dd94bf3d01cbb25e0af4e64c0485433); can_fetch=True -> docs/bukti_robots_txt.csv                                    |
|  4 | Kolom PII diidentifikasi                     | Ya       | Pemindaian nama kolom + regex (email, HP, NIK). PII: tidak ada; quasi-identifier: [['dataset_a', 'kecamatan']]                                       |
|  5 | PII dihapus, di-mask, atau di-pseudonimisasi | Ya       | Tidak ada data pribadi individu yang disimpan; seluruh entitas merupakan objek budaya/museum publik                                                  |
|  6 | Prinsip minimalisasi data diterapkan         | Ya       | Hanya mengambil field relevan (ID halaman, judul artikel, kategori budaya, dan URL referensi)                                                        |
|  7 | Potensi bias sampel dianalisis               | Ya       | Artikel Wikipedia Bahasa Indonesia bergantung pada kelengkapan kontribusi komunitas sehingga objek budaya lokal Bali tertentu mungkin belum tercakup |
|  8 | Tujuan penggunaan data dinyatakan eksplisit  | Ya       | Hanya untuk tugas akademik UTS Data Acquisition & Management (tidak untuk komersial)                                                                 |
|  9 | Rencana retensi dan penghapusan data ada     | Ya       | Disimpan di repositori GitHub UTS-DAM hingga penilaian semester selesai, kemudian data mentah lokal dibersihkan                                      |

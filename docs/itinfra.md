# IT Service Analysis and Performance Management
Penilaian teknis (*Technical Assessment*) untuk posisi **TEC Associate – IT Service Analysis and Performance Management** umumnya menguji gabungan antara fondasi kerangka kerja manajemen layanan IT (ITSM), kemampuan analisis data/kinerja, logika pemecahan masalah (incident/problem management), dan keterampilan komunikasi bisnis.

---

## Pendahuluan 

### **Core Focus Areas (Materi Utama yang Diuji)**

1. **IT Service Management (ITSM) & Framework ITIL**
* **Service Level Management:** Pemahaman mendalam tentang perbedaan SLA (*Service Level Agreement*), OLA (*Operational Level Agreement*), dan UC (*Underpinning Contract*).
* **Core Lifecycle Processes:** Cara menangani *Incident Management* (penanganan cepat), *Problem Management* (analisis akar masalah/RCA), *Change Management*, dan *Request Fulfillment*.
* **Metrics & KPIs:** Memahami korelasi indikator kinerja seperti *MTTR* (Mean Time to Repair), *MTBF* (Mean Time Between Failures), *First Contact Resolution* (FCR), dan *Service Availability (%)*.


2. **Performance Management & Data Analytics**
* **Analisis Tren Kinerja:** Membaca data metrik sistem/layanan, mengidentifikasi *bottleneck*, serta mendeteksi penurunan performa sebelum terjadi insiden fatal.
* **Pemrosesan Data:** Penggunaan fungsi *spreadsheet* (Excel: PivotTable, VLOOKUP/XLOOKUP, kondisional logic) atau SQL dasar untuk memfilter data *log* / tiket insiden.
* **Pembuatan Dashboard/Reporting:** Memahami prinsip dasar penyajian visualisasi data melalui diagram atau dashboard (Power BI/Tableau) untuk laporan manajemen.


3. **Problem Solving & Case Studies (Studi Kasus)**
* **Root Cause Analysis (RCA):** Penggunaan metode seperti *5 Whys* atau *Fishbone Diagram* (Ishikawa) saat dihadapkan pada skenario kegagalan sistem.
* **Prioritisasi Insiden:** Penilaian *Impact* (dampak bisnis) vs *Urgency* (urgensi waktu) untuk menentukan matriks prioritas (P1/Critical hingga P4/Low).


4. **Business Communication & Stakeholder Engagement**
* Penerjemahan data teknis menjadi laporan analitis yang dapat dipahami oleh pihak manajemen atau *non-technical stakeholders*.

---

### **Format Umum Penilaian Teknis**

* **Pilihan Ganda / Kuis Konseptual (Online):** Menguji pemahaman teori ITIL, KPI manajemen layanan, dan skenario penanganan insiden.
* **Studi Kasus Analisis Data (Excel/Dataset):** Anda diberikan data *raw* tiket layanan (misal: 500 baris log insiden) dan diminta menghitung metrik utama, menemukan tren penyebab kegagalan terbanyak, serta membuat ringkasan rekomendasi.
* **Penulisan Laporan / Dashboard Challenge:** Menyusun *Executive Summary* singkat berdasarkan data kinerja sistem yang buruk.

---

### **Strategi & Panduan Persiapan Step-by-Step**

1. **Pelajari Ulang Metrik Utama ITSM**
* Pastikan Anda tahu cara menghitung:
* $\text{Availability (\%)} = \frac{\text{Total Operating Time} - \text{Downtime}}{\text{Total Operating Time}} \times 100$
* $\text{MTTR} = \frac{\text{Total Downtime}}{\text{Jumlah Insiden}}$

2. **Kuasai Keterampilan Excel untuk Analisis Data**
* Berlatih mengelompokkan data tiket berdasarkan kategori insiden, tim penanggung jawab, dan durasi penyelesaian menggunakan Pivot Table.
* Gunakan visualisasi sederhana (Bar chart/Line chart) untuk menggambarkan tren bulanan insiden.

3. **Gunakan Kerangka Struktural Saat Menjawab Studi Kasus**
* Gunakan pendekatan **STAR** (*Situation, Task, Action, Result*) untuk soal naratif atau **RCA 5-Whys** saat menganalisis insiden sistem.


4. **Fokus pada Dampak Bisnis (Business Impact)**
* Dalam setiap analisis performa, selalu hubungkan *downtime* teknis dengan dampaknya pada operasional perusahaan (misal: kerugian finansial, penurunan kepuasan pengguna/CSAT).

---

## SLA (Service Level Agreement), OLA (Operational Level Agreement), dan UC (Underpinning Contract)
Ketiga istilah ini adalah komponen utama dalam kerangka **ITIL (IT Infrastructure Library)** yang digunakan untuk mengatur komitmen kualitas layanan (*Service Level Management*).

Perbedaannya terletak pada **pihak yang terikat** (*siapa dengan siapa*) dan **sifat hukum/internalnya**.

---

### **Tabel Perbedaan SLA, OLA, dan UC**

| Fitur | SLA (*Service Level Agreement*) | OLA (*Operational Level Agreement*) | UC (*Underpinning Contract*) |
| --- | --- | --- | --- |
| **Pihak Terikat** | Penyedia Layanan IT $\leftrightarrow$ **Nasabah/Bisnis** (Eksternal IT) | Tim IT Internal $\leftrightarrow$ **Tim IT Internal Lainnya** | Penyedia Layanan IT $\leftrightarrow$ **Vendor/Pihak Ketiga** |
| **Sifat Dokumen** | Kesepakatan Tingkat Layanan Bisnis | Kesepakatan Operasional Internal | Kontrak Hukum Mengikat (*Legal Contract*) |
| **Fokus Utama** | Ekspektasi & performa layanan dari kacamata pengguna/bisnis. | Ketergantungan antar-tim internal untuk mendukung SLA. | Komitmen spesifik vendor pendukung (hardware, jaringan, dsb). |
| **Contoh Kasus** | Aplikasi Mobile Banking harus aktif 99.9% dalam sebulan. | Tim *Database Administrator* (DBA) wajib menyelesaikan masalah kuota basis data dalam **30 menit** jika diminta Tim *Application Support*. | Vendor *Data Center* menjamin ketersediaan listrik & pendingin server sebesar 99.99% dengan denda jika melanggar. |

---

### **Analogi Sederhana: Restoran**

Bayangkan sebuah **Restoran**:

1. **SLA (Restoran $\leftrightarrow$ Pelanggan):**
Restoran berjanji kepada pelanggan: *"Makanan Anda akan disajikan dalam waktu **15 menit** setelah dipesan."* Jika lewat, pelanggan mendapat kompensasi.
2. **OLA (Koki $\leftrightarrow$ Pelayan Internal):**
Agar janji 15 menit ke pelanggan terwujud, tim internal membuat aturan: Koki harus selesai memasak dalam **10 menit**, sehingga Pelayan punya waktu **5 menit** untuk mengantar makanan ke meja.
3. **UC (Restoran $\leftrightarrow$ Pemasok Daging Eksternal):**
Restoran memiliki kontrak resmi berbadan hukum dengan pemasok daging: *"Pemasok wajib mengantar daging segar setiap jam 6 pagi. Jika terlambat, pemasok dikenakan denda potongan pembayaran."*

---

### **Bagaimana Ketiganya Saling Menopang?**

Secara hierarki, **OLA dan UC adalah fondasi untuk mencapai SLA**.

* Jika vendor melanggar **UC** (misal: penyedia internet/ISP mati total), maka tim internal akan gagal memenuhi **OLA** mereka.
* Jika **OLA** internal gagal, secara otomatis janji **SLA** kepada pengguna/bisnis akan *breach* (terlanggar).

---

## Incident Management, Problem Management, Change Management, dan Request Fulfillment
Cara menangani Incident Management (penanganan cepat), Problem Management (analisis akar masalah/Root Cause Analysis), Change Management, dan Request Fulfillment. 

Keempat proses ini adalah bagian inti dari pengelolaan layanan IT (*IT Service Management* / ITIL). Cara mudah memahaminya adalah melihat **tujuan utama** dan **alur kerja** dari masing-masing proses.

---

### **Incident Management (Penanganan Cepat / *Firefighting*)**

* **Tujuan Utama:** Memulihkan layanan yang terganggu **secepat mungkin** agar dampak ke bisnis minimal (*workaround* / solusi sementara sangat diperbolehkan).
* **Prinsip:** *"Yang penting sistem jalan dulu, cari tahu penyebabnya nanti."*

```
[Terjadi Gangguan] ➔ [Pencatatan & Prioritisasi] ➔ [Diagnosa Sederhana] ➔ [Solusi Sementara (Workaround)] ➔ [Layanan Pulih/Tutup Tiket]

```

**Langkah Penanganan:**

1. **Pencatatan (*Logging*):** Catat tiket insiden beserta detail gejalanya.
2. **Kategorisasi & Prioritisasi:** Tentukan prioritas berdasarkan **Impact** (berapa banyak pengguna/sistem yang berdampak) dan **Urgency** (seberapa mendesak).
3. **Penerapan *Workaround* (Solusi Sementara):**
* *Contoh:* Server aplikasi kehabisan memori (*hang*).
* *Tindakan cepat:* Lakukan *restart* server agar aplikasi bisa dipakai kembali dalam 5 menit, meskipun kita belum tahu kenapa memorinya bisa penuh.


4. **Eskalasi:** Jika Tim Level 1 (*Helpdesk*) tidak bisa menyelesaikan dalam durasi target SLA, langsung salurkan ke Tim Level 2 (*Infrastructure/App Support*).

---

### **Problem Management (Analisis Akar Masalah / RCA)**

* **Tujuan Utama:** Mengidentifikasi **akar penyebab** (*root cause*) dari insiden yang berulang atau insiden besar (*Major Incident*), serta mencegah insiden serupa terjadi kembali di masa depan.
* **Prinsip:** *"Cari tahu kenapa bisa rusak, lalu perbaiki secara permanen."*

```
[Identifikasi Tren Insiden] ➔ [Analisis Akar Masalah (RCA)] ➔ [Identifikasi Solusi Permanen] ➔ [Pengajuan Change Request (RFC)]

```

**Langkah Penanganan:**

1. **Analisis Tren / Pemicu:** Mengumpulkan tiket insiden yang jalurnya sama (misal: server aplikasi *hang* 3 kali dalam seminggu).
2. **Root Cause Analysis (RCA):** Gunakan metode seperti **5 Whys** atau **Fishbone Diagram** untuk melacak hingga ke sumber masalah.
* *Hasil analisis dari contoh di atas:* Server *hang* ternyata disebabkan oleh *memory leak* pada kodingan aplikasi versi terbaru.


3. **Dokumentasi *Known Error*:** Catat masalah dan solusi sementaranya dalam Basis Pengetahuan (*Knowledge Base*).
4. **Buat Usulan Perbaikan Permanen:** Mengajukan permintaan perubahan sistem (*Request for Change*) ke tim pengembang untuk memperbaiki *bug* kodingan tersebut.

---

### **Change Management (Pengelolaan Perubahan)**

* **Tujuan Utama:** Memastikan setiap perubahan pada sistem IT (seperti *update* aplikasi, ganti server, atau ubah konfigurasi) dilakukan secara terstruktur **tanpa menyebabkan gangguan/downtime baru**.
* **Prinsip:** *"Uji coba dulu, minta persetujuan, dan siapkan rencana pembatalan (rollback)."*

```
[Pengajuan Perubahan (RFC)] ➔ [Evaluasi Risiko] ➔ [Persetujuan (CAB)] ➔ [Implementasi & Pengujian] ➔ [Review Pasca-Perubahan]

```

**Langkah Penanganan:**

1. **Pengajuan *Request for Change* (RFC):** Tim teknis mengajukan dokumen rencana perubahan.
2. **Analisis Dampak & Risiko:** Menilai dampak perubahan, waktu eksekusi (biasanya di *non-business hours*), dan menyiapkan **Rollback Plan** (langkah mengembalikan sistem ke kondisi semula jika *update* gagal).
3. **Persetujuan oleh CAB (*Change Advisory Board*):** Tim manajemen dan perwakilan bisnis meninjau apakah perubahan tersebut aman untuk diimplementasikan.
4. **Implementasi & Tinjauan:** Eksekusi perubahan, lakukan pengujian, dan tutup RFC jika sukses.

---

### **Request Fulfillment (Pemenuhan Permintaan Standar)**

* **Tujuan Utama:** Menangani **permintaan rutin** dari pengguna yang *bukan merupakan gangguan atau sistem rusak*.
* **Prinsip:** *"Layanan standar, risikonya rendah, dan memiliki prosedur yang sudah jelas."*

```
[Pengguna Minta Akses/Barang] ➔ [Verifikasi & Persetujuan Atasan] ➔ [Eksekusi Otomatis/Manual] ➔ [Konfirmasi ke Pengguna]

```

**Contoh & Langkah Penanganan:**

* **Contoh Kasus:** Karyawan baru minta akun email, permintaan ganti kata sandi (*reset password*), atau permintaan laptop baru.
* **Langkah:**
1. Pengguna memilih menu permintaan di portal mandiri (*Self-Service Portal*).
2. Sistem mengirimkan alur persetujuan (*approval*) otomatis ke atasan pengguna.
3. Setelah disetujui, tim IT (atau sistem otomatis) membuatkan akun/menyerahkan perangkat.
4. Tiket ditutup.



---

### **Rangkuman Perbandingan Singkat**

| Proses | Pemicu / Trigger | Pertanyaan Utama | Contoh Skenario |
| --- | --- | --- | --- |
| **Incident Management** | Sistem mati / Error | *"Bagaimana cara menyalakannya kembali dengan cepat?"* | Printer kantor tidak bisa mencetak dokumen penting. |
| **Problem Management** | Insiden berulang | *"Mengapa printer ini terus-menerus mati setiap jam 2 siang?"* | Ditemukan kabel listrik printer mengelupas dan menyebabkan korsleting berkala. |
| **Change Management** | Rencana perbaikan/upgrade | *"Apakah aman jika kita mengganti seluruh sistem printer minggu depan?"* | Mengganti seluruh unit printer tua dengan model baru yang hemat energi. |
| **Request Fulfillment** | Permintaan pengguna | *"Tolong berikan saya akses ke printer lantai 3."* | Karyawan baru meminta hak akses mencetak di area kerjanya. |

---

## MTTR, MTBF, FCR, dan Service Availability (%)
Indikator kinerja seperti MTTR (Mean Time to Repair), MTBF (Mean Time Between Failures), First Contact Resolution (FCR), dan Service Availability. Keempat metrik ini saling terhubung secara matematika dan operasional untuk mengukur **kesehatan, keandalan, dan efisiensi layanan IT**.

---

### **Matriks Pengertian & Fokus Metrik**

| Metrik | Definisi Singkat | Jenis Indikator | Arah Ideal |
| --- | --- | --- | --- |
| **MTTR** (*Mean Time to Repair*) | Rata-rata waktu yang dibutuhkan untuk **memperbaiki** sistem dari saat rusak hingga kembali normal. | Efisiensi Pemulihan | **Semakin Rendah** ($\downarrow$) |
| **MTBF** (*Mean Time Between Failures*) | Rata-rata jarak waktu operasi normal **di antara dua kegagalan** (mengukur ketahanan sistem). | Keandalan (*Reliability*) | **Semakin Tinggi** ($\uparrow$) |
| **FCR** (*First Contact Resolution*) | Persentase insiden yang berhasil diselesaikan pada **kontak pertama** tanpa perlu disalurkan (*escalate*). | Efisiensi *Helpdesk* / L1 | **Semakin Tinggi** ($\uparrow$) |
| **Service Availability (%)** | Persentase total waktu sistem dapat **beroperasi normal** dan diakses oleh pengguna. | Hasil Akhir Bisnis | **Mendekati 100%** ($\uparrow$) |

---

### **Peta Korelasi Antar-Indikator**

#### **A. Hubungan Matematika: MTTR + MTBF -> Service Availability (%)**

Secara teknis, ketersediaan layanan (*Availability*) adalah hasil kalkulasi langsung dari ketahanan sistem (MTBF) dan kecepatan pemulihan (MTTR):

$$\text{Service Availability (\%)} = \left( \frac{\text{MTBF}}{\text{MTBF} + \text{MTTR}} \right) \times 100\%$$

* **Skenario 1:** Jika sistem jarang rusak (**MTBF tinggi**), namun saat rusak butuh waktu sangat lama untuk perbaikan (**MTTR tinggi**), nilai *Availability* akan turun drastis.
* **Skenario 2:** Jika sistem sering rusak (**MTBF rendah**), tetapi tim IT bisa memulihkannya dalam hitungan detik (**MTTR sangat rendah**), nilai *Availability* dapat tetap terjaga tinggi.

#### **B. Hubungan Operasional: FCR -> MTTR**

* **Korelasi Positif:** Ketika tingkat **FCR tinggi**, artinya tim *Helpdesk* (Level 1) mampu menyelesaikan sebagian besar insiden ringan secara langsung di awal.
* **Dampak ke MTTR:** Tiket insiden tidak perlu ditumpuk atau dilempar-lempar antar-tim teknis (L2/L3), sehingga total waktu pemulihan insiden rata-rata (**MTTR**) otomatis menjadi jauh **lebih cepat / rendah**.

---

### **Efek Domino dalam Manajemen Layanan IT**

```
[FCR Tinggi] 
   ↓ (Tiket selesai cepat di kontak pertama)
[MTTR Rendah] 
   ↓ (Total durasi downtime berkurang)
[Service Availability Tinggi] 
   ↑ (Didukung oleh MTBF yang tinggi / sistem jarang rusak)

```

1. **Peningkatan FCR** memangkas penundaan penanganan -> **Menurunkan MTTR**.
2. **Penurunan MTTR** ditambah **MTBF yang tinggi** (sistem stabil) -> **Memaksimalkan Service Availability**.
3. **Hasil Akhir:** Biaya operasional IT menurun, kepuasan pengguna (*CSAT*) meningkat, dan target SLA perusahaan tercapai.
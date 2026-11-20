# ETAC Accreditation Dashboard — Diploma Kejuruteraan Elektrik (Tenaga Hijau)

## Top-Level Overview

**Tujuan:** Membina fail HTML statik yang berfungsi sebagai dashboard interaktif untuk persediaan akreditasi ETAC bagi program Diploma Kejuruteraan Elektrik (Tenaga Hijau) di peringkat Politeknik / Kolej Komuniti.

**Skop:**
- 3 tahun data: 2022/23, 2023/24, 2024/25
- 11 Program Outcomes (PO1–PO11) berdasarkan standard ETAC
- 5 topik tenaga hijau: Solar PV, Angin, Smart Grid, EV, Penyimpanan Tenaga
- Output: fail `etac-dashboard.html` yang boleh dibuka terus di mana-mana browser tanpa pelayan web

**Pendekatan:** HTML statik tunggal menggunakan ECharts (CDN) untuk carta interaktif. Semua data disematkan terus dalam fail (tiada keperluan API atau back-end). Reka bentuk menggunakan CSS grid dan warna yang sesuai dengan tema akademik/profesional.

**Bukan dalam skop:**
- Sambungan ke pangkalan data sebenar
- Log masuk / pengesahan pengguna
- Eksport laporan automatik

---

## Sub-Tasks

---

### Sub-Task 1 — Struktur Asas HTML & Navigasi Tab

**Status:** `[ ] pending`

**Intent:**
Mewujudkan kerangka HTML dengan navigasi tab supaya setiap bahagian dashboard (PO, CO, Pelajar, CQI, Tenaga Hijau) boleh diakses secara berasingan tanpa memuat semula halaman.

**Expected Outcomes:**
- Fail `etac-dashboard.html` wujud dan boleh dibuka di browser
- Header menunjukkan nama program, institusi (placeholder), dan tahun semakan
- 5 tab navigasi: Program Outcomes | Course Outcomes | Prestasi Pelajar | CQI | Tenaga Hijau
- ECharts dimuat dari CDN

**Todo List:**
1. Cipta fail `etac-dashboard.html` dengan struktur HTML5 penuh
2. Tambah metadata (charset, viewport, title)
3. Muat ECharts via CDN `<script>` tag
4. Bina CSS untuk header, tab navigasi, panel kandungan, dan grid carta
5. Tambah JavaScript tab-switching (tunjuk/sembunyikan panel)
6. Masukkan placeholder `[NAMA INSTITUSI]` dan `[NAMA PROGRAM]` dalam header

**Relevant Context:**
- ECharts CDN: `https://cdn.jsdelivr.net/npm/echarts@5/dist/echarts.min.js`
- Tiada framework luar diperlukan selain ECharts
- Warna tema: hijau (#16a34a), biru (#1d4ed8), kelabu gelap (#1e293b)

---

### Sub-Task 2 — Tab Program Outcomes (PO Achievement)

**Status:** `[ ] pending`

**Intent:**
Memaparkan pencapaian 11 PO merentas 3 tahun sesi (2022/23 – 2024/25) untuk menunjukkan trend dan membuktikan program memenuhi tahap sasaran ETAC.

**Expected Outcomes:**
- Bar chart berkumpulan: pencapaian PO1–PO11 bagi setiap sesi (3 kumpulan bar)
- Garis rujukan "Target" (contoh: 65%) pada carta
- Line chart trend: carta kedua menunjukkan trend PO terpilih merentasi 3 tahun
- Jadual ringkasan: status Capai / Tidak Capai untuk setiap PO pada sesi terkini

**Todo List:**
1. Tambah bahagian `<div id="tab-po">` dalam fail HTML
2. Cipta data sampel realistik: 11 PO × 3 sesi (peratus pencapaian)
3. Render bar chart berkumpulan PO Achievement menggunakan ECharts
4. Render line chart trend PO (PO1, PO2, PO3 sebagai contoh)
5. Bina jadual HTML ringkasan status PO (capai/tidak capai) dengan warna hijau/merah

**Relevant Context:**
- PO1–PO11 mengikut standard ETAC untuk program diploma kejuruteraan
- Tahap sasaran lazim: 65% pelajar mencapai sekurang-kurangnya tahap 3 (skala 4)
- Data sampel perlu realistik: julat 60–85% pencapaian

---

### Sub-Task 3 — Tab Course Outcomes (CO Achievement & CO-PO Mapping)

**Status:** `[ ] pending`

**Intent:**
Memaparkan pencapaian Course Outcomes (CO) bagi mata pelajaran teras dan menunjukkan pemetaan CO-PO yang diperlukan oleh panel ETAC untuk membuktikan keselarasan kurikulum.

**Expected Outcomes:**
- Bar chart horizontal: pencapaian CO bagi 6–8 mata pelajaran teras
- Heatmap / jadual berwarna CO-PO mapping (CO sebagai baris, PO sebagai lajur)
- Legenda jelas untuk nilai pemetaan (H=High, M=Medium, L=Low)

**Todo List:**
1. Tambah bahagian `<div id="tab-co">` dalam fail HTML
2. Cipta data sampel: 6 kursus teras dengan 3–4 CO setiap satu
3. Render bar chart horizontal pencapaian CO per kursus
4. Bina jadual CO-PO mapping menggunakan HTML table dengan CSS warna (hijau=H, kuning=M, biru=L)
5. Tambah legenda di bawah jadual mapping

**Relevant Context:**
- Kursus teras cadangan: Asas Elektrik, Elektronik Kuasa, Sistem Solar PV, Teknologi Angin, Smart Grid, Penyimpanan Tenaga, Projek Akhir
- CO-PO mapping perlu konsisten dengan Sub-Task 2 (PO1–PO11)

---

### Sub-Task 4 — Tab Prestasi Pelajar

**Status:** `[ ] pending`

**Intent:**
Memaparkan prestasi keseluruhan pelajar merentas 3 sesi untuk membuktikan keberkesanan program kepada panel ETAC.

**Expected Outcomes:**
- Bar chart: kadar lulus keseluruhan per sesi (%)
- Bar chart: taburan GPA pelajar (< 2.0, 2.0–2.49, 2.5–2.99, 3.0–3.49, 3.5–4.0)
- Line chart: kadar pengambilan vs graduasi vs pekerjaan (3 tahun)
- Kad ringkasan KPI: bilangan pelajar berdaftar, kadar lulus, kadar graduan bekerja

**Todo List:**
1. Tambah bahagian `<div id="tab-student">` dalam fail HTML
2. Cipta data sampel realistik untuk 3 sesi
3. Render bar chart kadar lulus keseluruhan
4. Render bar chart taburan GPA
5. Render line chart pengambilan → graduasi → pekerjaan
6. Bina 4 kad KPI di bahagian atas tab (HTML + CSS grid)

**Relevant Context:**
- Kadar lulus lazim program diploma: 85–95%
- Kadar graduan bekerja: sasaran ETAC biasanya > 80% dalam 6 bulan selepas graduan

---

### Sub-Task 5 — Tab CQI (Continuous Quality Improvement)

**Status:** `[ ] pending`

**Intent:**
Memaparkan proses CQI (Closing the Loop) yang merupakan elemen kritikal dalam penilaian ETAC — membuktikan bahawa pihak program mengambil tindakan berdasarkan keputusan OBE.

**Expected Outcomes:**
- Pie chart: status tindakan CQI (Selesai / Dalam Proses / Belum Mula)
- Bar chart: perbandingan PO sebelum dan selepas tindakan CQI
- Jadual tindakan CQI: senarai isu, tindakan, pihak bertanggungjawab, status

**Todo List:**
1. Tambah bahagian `<div id="tab-cqi">` dalam fail HTML
2. Cipta data sampel: 8–10 tindakan CQI merentas 3 sesi
3. Render pie chart status tindakan CQI
4. Render bar chart perbandingan PO Before vs After CQI
5. Bina jadual HTML tindakan CQI dengan warna status

**Relevant Context:**
- CQI perlu menunjukkan "loop tertutup": isu dikenal pasti → tindakan diambil → keputusan bertambah baik
- Contoh tindakan: tambah waktu amali, semak modul, lawatan industri, bengkel kemahiran

---

### Sub-Task 6 — Tab Tenaga Hijau (Green Energy Coverage)

**Status:** `[ ] pending`

**Intent:**
Memaparkan liputan topik tenaga hijau dalam kurikulum dan pencapaian projek pelajar berkaitan teknologi tenaga hijau — menunjukkan kerelevanan program dengan industri semasa.

**Expected Outcomes:**
- Radar chart: liputan kurikulum 5 topik (Solar PV, Angin, Smart Grid, EV, Penyimpanan Tenaga)
- Bar chart: bilangan projek akhir mengikut kategori tenaga hijau (3 sesi)
- Pie chart: agihan kredit jam kursus berkaitan tenaga hijau vs elektrik am

**Todo List:**
1. Tambah bahagian `<div id="tab-green">` dalam fail HTML
2. Cipta data sampel radar (skor liputan 0–100 untuk 5 topik)
3. Render radar chart liputan kurikulum tenaga hijau
4. Render bar chart berkumpulan projek akhir mengikut topik (3 sesi)
5. Render pie chart agihan kredit kursus

**Relevant Context:**
- 5 topik: Solar PV, Angin, Smart Grid, EV (Kenderaan Elektrik), Penyimpanan Tenaga
- Radar chart sesuai untuk menunjukkan keseimbangan liputan kurikulum kepada panel ETAC

---

### Sub-Task 7 — Kemasan Akhir & Responsif

**Status:** `[ ] pending`

**Intent:**
Memastikan dashboard kelihatan profesional, mudah dicetak, dan berfungsi pada skrin laptop mahupun paparan projektor semasa pembentangan panel ETAC.

**Expected Outcomes:**
- Dashboard berfungsi pada lebar skrin 1024px ke atas
- Semua carta mempunyai tajuk, label paksi, dan tooltip yang jelas
- Footer menunjukkan tarikh penjanaan dan versi dashboard
- Fail HTML tunggal yang lengkap tanpa kebergantungan luar selain ECharts CDN

**Todo List:**
1. Semak semua carta mempunyai `title` dan label yang sesuai dalam Bahasa Melayu
2. Tambah CSS `@media print` untuk cetakan bersih
3. Tambah footer dengan tarikh dan nombor versi
4. Uji tab switching dan pastikan semua carta dirender dengan betul
5. Pastikan placeholder `[NAMA INSTITUSI]` dan `[NAMA PROGRAM]` jelas untuk digantikan

**Relevant Context:**
- Saiz skrin standard untuk pembentangan: 1366×768 (laptop) atau 1920×1080 (projektor)
- Fail akhir: `etac-dashboard.html` dalam workspace folder

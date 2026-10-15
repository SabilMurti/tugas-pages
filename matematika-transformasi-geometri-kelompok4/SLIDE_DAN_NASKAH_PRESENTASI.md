# PANDUAN LENGKAP ISI SLIDE & NASKAH PRESENTASI KELOMPOK 4
## TEMA: TRANSFORMASI GEOMETRI ROTASI 2D IKON LAMBANG SMKN 9 SEMARANG
**Kelas:** XII PPLG (Pengembangan Perangkat Lunak dan Gim) — SMK Negeri 9 Semarang  
**Durasi Total Presentasi:** 7 – 10 Menit (Sesuai Ketentuan Resmi Tugas Matematika Fase F)  
**Berkas Presentasi Digital:** [`SLIDE_PRESENTASI_KELOMPOK_4.pptx`](./SLIDE_PRESENTASI_KELOMPOK_4.pptx) (16:9 Widescreen Siap Pakai di OnlyOffice & PowerPoint)  
**Produk Aplikasi Web Interaktif:** [https://tinyurl.com/rotasi-smkn9](https://tinyurl.com/rotasi-smkn9) *(Alternatif: [https://da.gd/V0UF](https://da.gd/V0UF))*

---

## ⏱️ TABEL ALOKASI WAKTU & PEMBAGIAN PERAN KELOMPOK (7–10 MENIT)

| Slide | Topik Slide | Durasi | Presenter | Fokus Utama |
| :---: | :--- | :---: | :---: | :--- |
| **1** | **Cover Judul & Identitas Tim** | 30 detik | Moderator / Presenter 1 | Salam pembuka, perkenalan anggota kelompok 4, latar topik |
| **2** | **Latar Belakang & Desain Objek** | 1 menit | Presenter 1 | Filosofi lambang SMKN 9, kurva Bézier, korelasi kejuruan PPLG |
| **3** | **Landasan Teori Matriks Rotasi** | 1.5 menit | Presenter 2 | Operator matriks $R_\alpha$, 3 rumus praktis sudut kuadran (90°, 180°, 270°) |
| **4** | **Pemodelan Koordinat Cartesius** | 1.5 menit | Presenter 2 | 5 Titik sudut utama ($A, E, C, B, D$) & titik kontrol kelengkungan |
| **5** | **Live Demo Aplikasi Web Interaktif** | 2 menit | Presenter 3 | Simulasi kanvas Cartesius, slider rotasi, drag-drop, scan QR Code |
| **6** | **Tabel Hasil Perhitungan 4 Kuadran** | 1 menit | Presenter 3 | Komparasi koordinat titik sudut di Kuadran I, II, III, dan IV |
| **7** | **Pembuktian Ilmiah Sifat Isometri** | 1 menit | Presenter 4 | Uji keliling (31.272 satuan) & uji luas Shoelace Gauss (52.53 satuan luas) |
| **8** | **Relevansi Nyata Industri PPLG** | 1 menit | Presenter 4 | CSS Transform 2D, HTML5 Canvas Game Engine, aset vektor SVG |
| **9** | **Kesimpulan Proyek** | 30 detik | Presenter 4 | 4 Inti temuan matematis & manfaat integrasi software engineering |
| **10** | **Penutup & Sesi Tanya Jawab (Q&A)** | 2 menit | Seluruh Tim | Terima kasih, ajakan scan QR Code, jawaban atas pertanyaan guru/rekan |

---

## 🖥️ RINCIAN ISI KONTEN SLIDE & NASKAH UJARAN (SLIDE BY SLIDE)

### SLIDE 1: COVER / JUDUL PROYEK
* **Warna Latar:** *Deep Navy Blue* (`#0F172A`)
* **Badge Atas:** `KURIKULUM MERDEKA FASE F • MATEMATIKA TINGKAT LANJUT`
* **Judul Utama di Layar:**  
  **TRANSFORMASI GEOMETRI ROTASI 2D**
* **Subjudul di Layar:**  
  *Pemodelan dan Analisis Lambang SMK Negeri 9 Semarang Berbasis Koordinat Cartesius dan Kurva Bézier*
* **Informasi Tim di Layar:**  
  * Kelompok 4 — Kelas XII PPLG
  * SMK Negeri 9 Semarang • Tahun Ajaran 2026/2027
  * Alokasi Waktu: 7 – 10 Menit

> **🎙️ Naskah Ujaran Presenter 1 (Moderator) — Durasi: 30 Detik:**  
> *"Assalamu’alaikum warahmatullahi wabarakatuh. Selamat pagi kami ucapkan kepada Bapak/Ibu guru penilai matematika serta rekan-rekan kelas XII PPLG yang kami banggakan.*  
> *Kami dari **Kelompok 4** pada kesempatan pagi hari ini dengan bangga mempresentasikan karya proyek kolaboratif matematika terapan kami yang berjudul:*  
> *'Desain dan Analisis Transformasi Geometri Rotasi 2D pada Ikon Lambang SMK Negeri 9 Semarang Berbasis Koordinat Cartesius dan Kurva Bézier'.*  
> *Proyek ini memadukan konsep matematika rotasi matriks trigonometri dengan grafika komputer rekayasa perangkat lunak. Mari kita awali dari latar belakang pemilihan objek."*

---

### SLIDE 2: LATAR BELAKANG & PEMILIHAN OBJEK
* **Header:** `01. LATAR BELAKANG & PEMILIHAN OBJEK`
* **Subjudul:** *Mengapa Memilih Lambang SMKN 9 Semarang dan Mengapa Kurva Bézier?*
* **Tampilan Konten di Layar (2 Kartu Berdampingan):**
  * **Kartu Kiri (🛡️ Identitas Geometri Lambang Sekolah):**
    * **Objek Utama:** Lambang Resmi SMK Negeri 9 Semarang berbentuk *Perisai Segilima Berlekuk (Heraldic Crest Shield)*.
    * **Makna Filosofis:** Melambangkan perlindungan moral, integritas kokoh, dan ketangguhan mutu kompetensi vokasi.
    * **Titik Pusat Putar:** Titik origin $O(0,0)$ pada bidang koordinat Cartesius.
    * **Arah Rotasi:** Standar berlawanan jarum jam ($+\alpha$) pada sudut istimewa kuadran $90^\circ, 180^\circ,$ dan $270^\circ$.
  * **Kartu Kanan (✒️ Urgensi Kurva Bézier & Vektor Grafis):**
    * **Tantangan Nyata:** Lambang sekolah memiliki sisi melengkung yang luwes, bukan sekadar poligon garis lurus kaku.
    * **Analogi Pen Tool:** Kurva Bézier bekerja seperti alat Pen Tool di Figma/Adobe Illustrator yang dikendalikan oleh *Titik Kontrol (Control Points)*.
    * **Kekekalan Bentuk:** Titik pengendali lengkung ikut diputar oleh matriks rotasi yang sama persis sehingga bentuk logo tidak pernah rusak atau cacat.

> **🎙️ Naskah Ujaran Presenter 1 — Durasi: 1 Menit:**  
> *"Bapak/Ibu guru dan teman-teman sekalian, sebagai siswa kejuruan PPLG, kita terbiasa melihat logo aplikasi atau ikon antarmuka digital di layar komputer. Namun di balik keindahan visual tersebut, terdapat struktur matematika murni.*  
> *Kelompok kami memilih **Lambang Resmi SMK Negeri 9 Semarang** sebagai objek penelitian. Bingkai terluar lambang sekolah kita berbentuk **Perisai Segilima Berlekuk** yang gagah.*  
> *Tantangan terbesar yang kami hadapi adalah: lambang perisai ini memiliki sayap yang melengkung aerodinamis. Jika kita hanya menarik garis lurus biasa, bentuk logo sekolah akan terlihat kaku dan patah.*  
> *Oleh karena itu, kami menerapkan metode **Kurva Bézier**—yaitu teknologi garis lengkung berbasis titik kontrol penarik, sama seperti saat kita mendesain menggunakan Pen Tool di Figma. Seluruh titik sudut dan titik kontrol ini kami petakan ke bidang koordinat Cartesius dengan pusat rotasi di titik $O(0,0)$."*

---

### SLIDE 3: LANDASAN TEORI MATRIKS OPERATOR ROTASI
* **Header:** `02. LANDASAN TEORI MATRIKS OPERATOR ROTASI`
* **Subjudul:** *Formulasi Perkalian Matriks 2D terhadap Titik Pusat O(0,0)*
* **Tampilan Konten di Layar:**
  * **Kotak Formula Utama (Atas):**  
    $$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} \implies \begin{cases} x' = (x \cdot \cos\alpha) - (y \cdot \sin\alpha) \\ y' = (x \cdot \sin\alpha) + (y \cdot \cos\alpha) \end{cases}$$
  * **3 Kartu Kuadran di Bawah:**
    * **A. Rotasi $+90^\circ$ (Kuadran II):**  
      $\cos 90^\circ = 0, \sin 90^\circ = 1$ | Matriks: $\begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$ | **Rumus Praktis: $(x, y) \to (-y, x)$**  
      *(Aturan cepat: Tukar posisi $x$ dan $y$, lalu beri tanda negatif pada nilai $x$ baru).*
    * **B. Rotasi $+180^\circ$ (Kuadran III):**  
      $\cos 180^\circ = -1, \sin 180^\circ = 0$ | Matriks: $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$ | **Rumus Praktis: $(x, y) \to (-x, -y)$**  
      *(Aturan cepat: Posisi $x$ dan $y$ tetap, ubah kedua tanda menjadi lawannya/negatif).*
    * **C. Rotasi $+270^\circ$ (Kuadran IV):**  
      $\cos 270^\circ = 0, \sin 270^\circ = -1$ | Matriks: $\begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}$ | **Rumus Praktis: $(x, y) \to (y, -x)$**  
      *(Aturan cepat: Tukar posisi $x$ dan $y$, lalu beri tanda negatif pada nilai $y$ baru).*

> **🎙️ Naskah Ujaran Presenter 2 — Durasi: 1.5 Menit:**  
> *"Sekarang mari kita masuk ke inti pembuktian aljabar matriksnya.*  
> *Untuk memutar sebuah titik $P(x, y)$ sebesar sudut $\alpha$ terhadap pusat $O(0,0)$, kita mengalikan koordinat vektor kolom dengan **Matriks Operator Rotasi ($R_\alpha$)** berordo $2 \times 2$.*  
> *Ketika kita mensubstitusikan sudut-sudut istimewa kuadran ke dalam nilai trigonometrinya, kita mendapatkan tiga rumus praktis yang sangat elegan:*  
> *Pertama, pada rotasi $+90^\circ$, nilai cosinus nol dan sinus satu, sehingga menghasilkan rumus praktis: **$(x, y)$ memetakan ke $(-y, x)$** di Kuadran II.*  
> *Kedua, pada rotasi $+180^\circ$, nilai cosinus minus satu dan sinus nol, menghasilkan bayangan terbalik: **$(x, y)$ memetakan ke $(-x, -y)$** di Kuadran III.*  
> *Ketiga, pada rotasi $+270^\circ$, matriks menghasilkan bayangan: **$(x, y)$ memetakan ke $(y, -x)$** di Kuadran IV.*  
> *Ketiga rumus ini berlaku mutlak, baik untuk titik sudut poligon maupun untuk titik kontrol lengkung kurva Bézier."*

---

### SLIDE 4: PEMODELAN KOORDINAT CARTESIUS
* **Header:** `03. PEMODELAN KOORDINAT CARTESIUS`
* **Subjudul:** *5 Titik Sudut Utama & Titik Kontrol Lengkung pada Posisi Awal (0° — Kuadran I)*
* **Tampilan Konten di Layar:**
  * **Kartu Kiri (📍 5 Titik Sudut Utama Poligon):**
    * **Titik A (6.0, 1.8):** Ujung lancip paling bawah, poros utama ujung tombak perisai.
    * **Titik B (10.4, 11.7):** Pinggang kanan terluar bingkai perisai.
    * **Titik C (8.5, 13.0):** Bahu atas kanan dihubungkan garis datar horizontal.
    * **Titik D (3.5, 13.0):** Bahu atas kiri yang sejajar mendatar dengan titik C.
    * **Titik E (1.6, 11.7):** Pinggang kiri terluar (simetris terhadap titik B).
  * **Kartu Kanan (🎛️ Titik Kontrol Lengkung Bézier):**
    * Sayap kanan melengkung dari A(6.0, 1.8) ke B(10.4, 11.7) dikendalikan oleh:
      * **$C_1(9.7, 3.2)$:** Menarik lengkungan awal ke arah kanan bawah.
      * **$C_2(11.0, 5.4)$:** Menjaga kelengkungan tetap proporsional.
      * **$C_3(10.3, 8.8)$:** Menghubungkan kurva masuk mulus ke pinggang titik B.
    * **Kaidah Matematis:** Titik kontrol ikut dirotasikan secara simultan: $C'(x'_c, y'_c) = R_\alpha \cdot C(x_c, y_c)$.

> **🎙️ Naskah Ujaran Presenter 2 — Durasi: 1.5 Menit:**  
> *"Bagaimana bentuk lambang SMKN 9 ini didefinisikan ke dalam angka koordinat?*  
> *Pada posisi awal ($0^\circ$), seluruh bentuk lambang kami letakkan di **Kuadran I** dengan 5 titik sudut utama:*  
> *Ujung lancip perisai berada di **Titik A (6.0, 1.8)**. Pinggang kanan dan kiri berada di **Titik B (10.4, 11.7)** dan **Titik E (1.6, 11.7)**.*  
> *Sedangkan mahkota bahu atas perisai dihubungkan oleh garis horizontal mendatar dari **Titik D (3.5, 13.0)** ke **Titik C (8.5, 13.0)**.*  
> *Di antara titik A dan titik B, kami memasang 3 titik kontrol Bézier: $C_1, C_2,$ dan $C_3$. Titik kontrol inilah yang menarik garis lurus menjadi lekukan dinamis.*  
> *Saat sistem kami memutar perisai, algoritma komputasi kami menghitung posisi baru titik sudut dan titik kontrol secara bersamaan."*

---

### SLIDE 5: LIVE DEMO APLIKASI WEB INTERAKTIF & AKSES QR
* **Header:** `04. PRODUK APLIKASI WEB INTERAKTIF (LIVE DEMO)`
* **Subjudul:** *Simulasi Real-Time Transformasi Geometri Berbasis React, TypeScript & Canvas*
* **Tampilan Konten di Layar:**
  * **Kolom Kiri (💻 Fitur Unggulan Web):**
    * **Kanvas Cartesius Interaktif:** Grid beresolusi tinggi dengan indikator 4 kuadran dan poros putar $O(0,0)$.
    * **Kendali Rotasi Real-Time:** Slider putar bebas ($0^\circ$–$360^\circ$) dan tombol pintas kuadran ($90^\circ, 180^\circ, 270^\circ$).
    * **Drag & Drop Titik Sudut:** Memungkinkan eksperimen manipulasi titik secara langsung di layar kanvas.
    * **Ekspor Vektor SVG Resmi:** Fitur unduh aset vektor standar W3C resolusi tak terbatas (ringan <10 KB).
    * **Salin Path Koordinat:** Penyalinan instan koordinat path Bézier ke clipboard programmer.
  * **Kolom Kanan (📱 Kartu Akses QR Code):**
    * Gambar QR Code beresolusi tinggi di tengah kartu.
    * Tautan Singkat: **`tinyurl.com/rotasi-smkn9`**
    * Alternatif Cadangan: **`da.gd/V0UF`**

> **🎙️ Naskah Ujaran Presenter 3 — Durasi: 2 Menit:**  
> *(Arahkan pandangan dan gestur tangan ke layar atau demonstrasikan langsung aplikasi web di peramban)*  
> *"Untuk menguji kebenaran teori ini secara visual dan interaktif, kelompok kami membangun sebuah **aplikasi web interaktif** menggunakan React, TypeScript, dan HTML5 Canvas API.*  
> *Bisa kita saksikan bersama di layar proyektor:*  
> *Pada sudut $0^\circ$, logo SMKN 9 berdiri tegak di Kuadran I.*  
> *Saat tombol $90^\circ$ ditekan, kanvas secara instan memutar logo ke Kuadran II. Perhatikan bahwa ujung lancip titik A langsung menempati posisi $(-1.8, 6.0)$, dan garis bahu yang tadinya mendatar kini berubah tegak lurus vertikal di koordinat $x = -13$.*  
> *Begitu pula saat diputar ke $180^\circ$ (Kuadran III), lambang sekolah terbalik sempurna, dan pada $270^\circ$ (Kuadran IV), lambang sekolah rebah ke arah kanan.*  
> *Aplikasi ini juga menyediakan fitur unduh SVG resolusi tinggi dan fitur drag-and-drop.*  
> *Bapak/Ibu guru dan teman-teman dapat langsung menguji aplikasi ini sekarang melalui ponsel masing-masing dengan memindai **QR Code** yang tertera di slide atau mengakses tautan singkat **tinyurl.com/rotasi-smkn9**."*

---

### SLIDE 6: TABEL PERHITUNGAN HASIL ROTASI DI 4 KUADRAN
* **Header:** `05. HASIL PERHITUNGAN KOORDINAT 4 KUADRAN`
* **Subjudul:** *Komparasi Titik Sudut Utama pada Setiap Posisi Sudut Putaran*
* **Tampilan Konten di Layar (Tabel Data Terstruktur):**

| Titik Sudut | Posisi Awal 0° (Kuadran I) | Rotasi +90° (Kuadran II) | Rotasi +180° (Kuadran III) | Rotasi +270° (Kuadran IV) |
| :---: | :---: | :---: | :---: | :---: |
| **Titik A (Poros Bawah)** | **(6.0, 1.8)** | **(-1.8, 6.0)** | **(-6.0, -1.8)** | **(1.8, -6.0)** |
| **Titik B (Pinggang Kanan)** | **(10.4, 11.7)** | **(-11.7, 10.4)** | **(-10.4, -11.7)** | **(11.7, -10.4)** |
| **Titik C (Bahu Kanan)** | **(8.5, 13.0)** | **(-13.0, 8.5)** | **(-8.5, -13.0)** | **(13.0, -8.5)** |
| **Titik D (Bahu Kiri)** | **(3.5, 13.0)** | **(-13.0, 3.5)** | **(-3.5, -13.0)** | **(13.0, -3.5)** |
| **Titik E (Pinggang Kiri)** | **(1.6, 11.7)** | **(-11.7, 1.6)** | **(-1.6, -11.7)** | **(11.7, -1.6)** |

> **🎙️ Naskah Ujaran Presenter 3 — Durasi: 1 Menit:**  
> *"Berikut adalah rangkuman matriks koordinat hasil perhitungan kami pada kelima titik sudut utama.*  
> *Mari kita perhatikan konsistensi aturan matematika kuadran:*  
> *1. Pada Kuadran I ($0^\circ$), seluruh koordinat bernilai positif $(+, +)$.*  
> *2. Pada Kuadran II ($90^\circ$), nilai absis menjadi negatif dan ordinat positif $(-, +)$, sesuai aturan $(x, y) \to (-y, x)$.*  
> *3. Pada Kuadran III ($180^\circ$), kedua nilai absis dan ordinat menjadi negatif $(- , -)$, sesuai aturan $(x, y) \to (-x, -y)$.*  
> *4. Pada Kuadran IV ($270^\circ$), nilai absis positif dan ordinat negatif $(+, -)$, sesuai aturan $(x, y) \to (y, -x)$.*  
> *Seluruh angka di tabel ini telah terverifikasi secara presisi melalui simulasi software dan perhitungan analitis manual kelompok kami."*

---

### SLIDE 7: PEMBUKTIAN ILMIAH SIFAT ISOMETRI
* **Header:** `06. PEMBUKTIAN SIFAT ISOMETRI`
* **Subjudul:** *Verifikasi Matematis Kekekalan Panjang Sisi dan Luas Bangun Poligon*
* **Tampilan Konten di Layar:**
  * **Kartu Kiri (📏 1. Kekekalan Keliling / Jarak Euclidean):**
    * Rumus Jarak: $d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$
    * Sisi sayap $AB = EA = \sqrt{117.37} \approx 10.834\text{ satuan}$
    * Sisi pinggang $BC = DE = \sqrt{5.30} \approx 2.302\text{ satuan}$
    * Sisi bahu atas $CD = \sqrt{25.00} = 5.000\text{ satuan}$
    * **TOTAL KELILING = 31.272 satuan panjang (100% IDENTIK di 4 Kuadran)**
  * **Kartu Kanan (📐 2. Kekekalan Luas / Shoelace Formula Gauss):**
    * Metode: Perkalian Silang Determinan Tali Sepatu Gauss
    * Total Jumlah Determinan $(\Sigma) = 105.06\text{ satuan}$
    * **LUAS TOTAL = ½ × |105.06| = 52.53 satuan luas (100% KONSTAN di semua sudut)**
  * **Banner Kesimpulan Bawah:**  
    *KESIMPULAN UJI: Luas dan keliling terbukti 100% konstan tanpa perubahan. Ini membuktikan secara ilmiah bahwa rotasi merupakan Transformasi Isometri Sejati!*

> **🎙️ Naskah Ujaran Presenter 4 — Durasi: 1 Menit:**  
> *"Pertanyaan kritis yang sering diajukan adalah: Apakah objek yang diputar mengalami perubahan ukuran atau luas?*  
> *Untuk membuktikannya secara ilmiah, kelompok kami melakukan dua pengujian ketat:*  
> *Pertama, **Uji Keliling dengan Jarak Euclidean Pythagoras**: Kami menghitung kelima segmen sisi perisai di keempat kuadran. Hasil penjumlahan menghasilkan angka keliling yang persis sama, yaitu **31.272 satuan panjang**.*  
> *Kedua, **Uji Luas dengan Shoelace Formula (Metode Tali Sepatu Gauss)**: Kami mengalikan koordinat secara menyilang melingkar. Hasil luas poligon perisai di posisi $0^\circ, 90^\circ, 180^\circ,$ maupun $270^\circ$ bernilai stabil konstan tepat **52.53 satuan luas**.*  
> *Kekekalan keliling dan kekekalan luas ini menjadi bukti otentik bahwa transformasi rotasi merupakan **Transformasi Isometri Sejati**—bentuk dan ukuran lambang sekolah tidak pernah memuai ataupun menyusut."*

---

### SLIDE 8: RELEVANSI DENGAN KEJURUAN PPLG
* **Header:** `07. RELEVANSI DENGAN KEJURUAN PPLG`
* **Subjudul:** *Bagaimana Ilmu Matematika Bekerja di Balik Layar Industri Perangkat Lunak & Gim*
* **Tampilan Konten di Layar (3 Kartu Kejuruan):**
  * **🌐 1. CSS Transform 2D (Web UI/UX):**
    * Sintaks kode: `transform: rotate(90deg);`
    * Mesin peramban web (*browser engine*) mengeksekusi perkalian matriks affine pada GPU komputer untuk merender animasi rotasi tombol dan antarmuka pada 60 FPS tanpa lag.
  * **🎮 2. HTML5 Canvas & Game 2D API:**
    * Sintaks kode: `context.rotate((sudut * Math.PI) / 180);`
    * Pengembang gim menerapkan manipulasi matriks rotasi langsung di dalam *Render Loop* untuk memutar aset pesawat, karakter, atau proyektil senjata terhadap titik pivot.
  * **📐 3. Format Vektor SVG Berbasis XML:**
    * Grafis tidak berbasis piksel bitmap pecah, melainkan formula matematis Bézier Path.
    * Berkas logo SMKN 9 berukuran sangat ringan (<10 KB), tajam tanpa batas di layar ponsel beresolusi Retina.

> **🎙️ Naskah Ujaran Presenter 4 — Durasi: 1 Menit:**  
> *"Sebagai calon software engineer di jurusan PPLG, kami menyadari bahwa proyek ini bukan sekadar tugas matematika di atas lembar kertas, melainkan fondasi langsung teknologi yang kami kembangkan setiap hari.*  
> *Ketika kita membuat tombol web berputar menggunakan kode CSS `transform: rotate(90deg)`, browser sebenarnya sedang memproses matriks trigonometri yang baru saja kita pelajari.*  
> *Ketika teman-teman mengembangkan gim 2D menggunakan Unity atau HTML5 Canvas, perputaran karakter terhadap bidikan mouse dikalkulasi menggunakan fungsi rotasi kanvas Cartesius.*  
> *Dan dengan memodelkan lambang sekolah ke dalam format vektor SVG, aset logo sekolah memiliki ukuran sangat kecil di bawah 10 Kilobyte dan dapat diperbesar tanpa pernah pecah."*

---

### SLIDE 9: KESIMPULAN KELOMPOK 4
* **Header:** `08. KESIMPULAN KELOMPOK 4`
* **Subjudul:** *Ringkasan Hasil Pembelajaran Proyek Matematika Terapan Kelas XII PPLG*
* **Tampilan Konten di Layar (4 Kotak Ringkasan Inti):**
  * **1. Deterministik & Presisi Matriks:** Rotasi 2D terhadap $O(0,0)$ mematuhi kaidah matriks trigonometri secara eksak dengan tiga aturan pemetaan baku: $(-y, x)$ pada $90^\circ$, $(-x, -y)$ pada $180^\circ$, dan $(y, -x)$ pada $270^\circ$.
  * **2. Keutuhan Geometri dengan Kurva Bézier:** Penambahan titik kontrol terbukti menjaga keindahan lekukan sayap logo sekolah tanpa mengalami distorsi atau kecacatan bentuk.
  * **3. Terbukti Memenuhi Sifat Isometri Sejati:** Uji jarak membuktikan keliling konstan (31.272 satuan) dan uji Shoelace membuktikan luas konstan (52.53 satuan luas).
  * **4. Matematika adalah Pondasi Rekayasa Software:** Matematika terbukti merupakan logika esensial di balik algoritma grafika komputer dan arsitektur perangkat lunak modern.

> **🎙️ Naskah Ujaran Presenter 4 — Durasi: 30 Detik:**  
> *"Dapat kami simpulkan bahwa:*  
> *Perhitungan matriks rotasi 2D, pemodelan kurva Bézier, dan pembuktian isometri telah berhasil kami integrasikan ke dalam produk perangkat lunak interaktif yang dapat diuji secara nyata.*  
> *Proyek ini memberikan pelajaran berharga bagi kami: matematika adalah bahasa universal logika yang menghidupkan setiap piksel dan algoritma di dunia rekayasa perangkat lunak."*

---

### SLIDE 10: PENUTUP & SESI TANYA JAWAB (Q&A)
* **Warna Latar:** *Deep Navy Blue* (`#0F172A`)
* **Teks Utama:** **TERIMA KASIH**
* **Subteks:** *Sesi Presentasi Selesai • Dibuka Sesi Diskusi & Tanya Jawab (Q&A)*
* **Visual Tengah:** Kartu Dark Slate berisi **Gambar QR Code Aplikasi Web**
* **Tautan Akses di Bawah QR:** `tinyurl.com/rotasi-smkn9`
* **Footer Identitas:** *Kelompok 4 • Kelas XII PPLG • SMK Negeri 9 Semarang*

> **🎙️ Naskah Ujaran Presenter 1 (Moderator) — Durasi: 30 Detik (Menuju Q&A):**  
> *"Demikian presentasi dari Kelompok 4 mengenai Transformasi Geometri Rotasi 2D Lambang SMK Negeri 9 Semarang.*  
> *Kami mengucapkan terima kasih yang sebesar-besarnya kepada Bapak/Ibu guru atas bimbingannya, serta kepada rekan-rekan sekalian atas perhatiannya yang luar biasa.*  
> *Sekarang, kami membuka sesi diskusi dan tanya jawab. Kepada Bapak/Ibu guru dan teman-teman yang ingin menyampaikan pertanyaan atau tanggapan, kami persilakan dengan senang hati. Terima kasih!"*

---

## 💡 PANDUAN MENJAWAB PERTANYAAN KRITIS GURU & AUDIENS (Q&A CHEATSHEET)

### Pertanyaan 1: Mengapa kelompok kalian memilih pusat rotasi di titik $O(0,0)$ dan bukan di titik tengah perisai?
> **Jawaban Terbaik (Dijawab oleh Presenter 2 atau 3):**  
> *"Terima kasih atas pertanyaannya, Bapak/Ibu.*  
> *Pemilihan titik pusat di origin $O(0,0)$ kami dasarkan pada tujuan utama kurikulum tugas ini, yaitu mengkaji pemetaan titik antar-kuadran I, II, III, dan IV secara fundamental. Jika kami memutar perisai pada titik beratnya sendiri (sekitar koordinat $x = 6.0, y = 7.4$), bangun hanya akan berputar di tempat di dalam Kuadran I tanpa berpindah kuadran.*  
> *Namun, secara matematis kelompok kami juga telah menyiapkan rumus rotasi terhadap titik sebarang $P(a,b)$, yaitu dengan mentranslasikan objek ke origin $(-a, -b)$, melakukan perkalian matriks rotasi, lalu mentranslasikannya kembali $(+a, +b)$."*

### Pertanyaan 2: Bagaimana kalian bisa menjamin bahwa kurva lengkung Bézier tidak rusak, gepeng, atau penyok saat diputar?
> **Jawaban Terbaik (Dijawab oleh Presenter 1 atau 4):**  
> *"Secara komputasi grafika, kurva Bézier memiliki sifat yang disebut **Affine Invariance (Kekekalan Transformasi Affine)**.*  
> *Artinya, kita tidak perlu memutar jutaan titik piksel di sepanjang garis lengkung satu per satu. Kita cukup memutar titik-titik kontrol penariknya ($C_1, C_2, C_3$) menggunakan matriks rotasi yang sama persis dengan titik sudut utama.*  
> *Ketika titik kontrol ikut berputar secara presisi, algoritma kurva parametrik komputer akan otomatis menggambar lengkungan yang persis identik tanpa mengalami penyusutan maupun distorsi."*

### Pertanyaan 3: Mengapa uji luas menggunakan rumus Shoelace (tali sepatu) dan bukan rumus luas segitiga biasa?
> **Jawaban Terbaik (Dijawab oleh Presenter 4):**  
> *"Bentuk perisai lambang SMKN 9 adalah poligon segilima sembarang yang memiliki sisi atas mendatar dan dua sisi bawah melengkung runcing. Bangun seperti ini tidak memiliki alas dan tinggi yang sederhana.*  
> *Rumus Gauss Shoelace Formula adalah standar baku dalam ilmu geodesi dan grafika komputer untuk menghitung luas poligon sembarang berbasis koordinat Cartesius. Dengan mengalikan koordinat secara menyilang melingkar, kita mendapatkan luas yang 100% akurat tanpa perlu memecah poligon menjadi banyak segitiga kecil yang rawan kesalahan pembulatan."*

---
*Naskah dan berkas slide presentasi ini disusun secara profesional oleh Kelompok 4 (XII PPLG SMKN 9 Semarang).*

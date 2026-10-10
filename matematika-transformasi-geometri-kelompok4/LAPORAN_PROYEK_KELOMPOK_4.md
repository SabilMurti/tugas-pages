# LAPORAN PROYEK TRANSFORMASI GEOMETRI
## IMPLEMENTASI ROTASI PADA DESAIN IKON APLIKASI LAMBANG SMKN 9 SEMARANG

---

### IDENTITAS PROYEK
* **Judul Proyek:** Desain dan Analisis Transformasi Geometri Rotasi 2D pada Ikon Aplikasi Lambang SMK Negeri 9 Semarang Berbasis Koordinat Cartesius dan Kurva Bézier
* **Kelompok:** 4 (Empat)
* **Anggota Kelompok:**
  1. ............................................................ (No. Presensi: .....)
  2. ............................................................ (No. Presensi: .....)
  3. ............................................................ (No. Presensi: .....)
  4. ............................................................ (No. Presensi: .....)
* **Kelas:** XII PPLG (Pengembangan Perangkat Lunak dan Gim)
* **Mata Pelajaran:** Matematika (Transformasi Geometri - Fase F / Kurikulum Merdeka)
* **Instansi:** SMK Negeri 9 Semarang
* **Tahun Pelajaran:** 2026/2027

---

## BAB I — PENDAHULUAN

### 1.1 Latar Belakang
Dalam rekayasa antarmuka pengguna (*User Interface / UI*) dan grafika komputer modern (PPLG), perancangan grafis berbasis vektor memegang peranan yang sangat fundamental. Berbeda dengan citra raster (*bitmap*) yang tersusun atas matriks piksel statis dan pecah ketika diperbesar, grafika vektor dibangun oleh pemodelan matematis, sekumpulan koordinat titik diskret, dan persamaan diferensial kurva parametrik Bézier pada bidang koordinat Cartesius. Hal ini memungkinkan ikon aplikasi, tipografi digital (*fonts*), dan aset grafis antarmuka untuk dirotasi, diskalakan, dan dimanipulasi secara dinamis dengan ketajaman visual yang sempurna (*lossless resolution*).

Salah satu operasi transformasi geometri fundamental yang menjadi tulang punggung pengembangan aplikasi web, gim, dan sistem grafis adalah **rotasi (perputaran)**. Contoh nyata dalam industri perangkat lunak meliputi animasi pemuatan data (*loading spinner*), perubahan orientasi sprite karakter gim 2D, tombol navigasi yang berputar halus, kompas digital pada peta navigasi, hingga fitur rotasi layar otomatis pada gawai pintar.

Sebagai siswa program keahlian Pengembangan Perangkat Lunak dan Gim (PPLG) di **SMK Negeri 9 Semarang**, penguasaan aljabar matriks di balik transformasi geometri sebelum dituangkan ke dalam baris kode program (seperti CSS Transform 2D, SVG Vector Path, atau HTML5 Canvas 2D API) merupakan kompetensi inti. Pada proyek ini, **Kelompok 4** merancang **Ikon Aplikasi Lambang SMK Negeri 9 Semarang** yang dimodelkan menjadi perisai kurva parametrik Cartesius (terdiri atas 5 titik sudut utama dan 8 titik kontrol Bézier), kemudian menguji perubahan koordinat, perkalian matriks, dan membuktikan sifat kekekalan ukuran (isometri) saat dirotasi sebesar $90^\circ$, $180^\circ$, dan $270^\circ$ terhadap titik pusat $O(0,0)$.

### 1.2 Tujuan Proyek
Berdasarkan panduan resmi tugas matematika proyek kelompok, tujuan dari proyek ini adalah:
1. Menjelaskan konsep teoritis dan formula matriks transformasi rotasi dua dimensi dengan titik pusat di $O(0,0)$.
2. Menentukan koordinat bayangan titik sudut dan titik kontrol kurva lambang sekolah setelah mengalami rotasi $90^\circ$, $180^\circ$, dan $270^\circ$ berlawanan arah jarum jam (*counter-clockwise*).
3. Membuktikan sifat isometri rotasi, yaitu kekekalan jarak segmen sisi poligon dan kekekalan luas bangun perisai menggunakan *Shoelace Formula* (Formula Tali Sepatu Gauss).
4. Menghubungkan aturan transformasi geometri dengan bidang rekayasa perangkat lunak (CSS Transform 2D, SVG Path, dan algoritma *de Casteljau* untuk perenderan kurva Bézier).
5. Menyajikan hasil analisis dalam bentuk produk visual berupa aplikasi web visualizer interaktif dan infografis diagram Cartesius 4 kuadran.
6. Mempresentasikan hasil proyek secara sistematis, komunikatif, dan ilmiah dalam durasi 7–10 menit.

### 1.3 Manfaat Proyek
1. **Bagi Siswa:** Mengintegrasikan pemahaman matematika aljabar linier dengan keterampilan pemrograman frontend, serta menumbuhkan rasa bangga terhadap institusi sekolah.
2. **Bagi Pembelajaran Matematika:** Menghadirkan konteks nyata dan aplikatif bagi materi transformasi geometri Fase F SMK.
3. **Bagi Bidang Kejuruan PPLG:** Membekali siswa dengan pemahaman matematika yang bekerja di dalam mesin rendering peramban web (*browser rendering engine*) dan mesin gim (*game engine*).

---

## BAB II — LANDASAN TEORI

### 2.1 Konsep Transformasi Geometri dan Rotasi
Transformasi geometri adalah suatu fungsi bijektif yang memetakan setiap titik $P(x, y)$ pada bidang datar ke titik lain $P'(x', y')$ pada bidang yang sama.

**Rotasi (perputaran)** adalah transformasi geometri yang memutar setiap titik pada bidang sepanjang busur lingkaran yang berpusat pada suatu titik acuan tertentu (pusat rotasi $P$) sebesar sudut orientasi $\alpha$. Sifat khas rotasi adalah **isometri**, artinya transformasi ini mempertahankan jarak antartitik (panjang sisi tetap) dan luas bangun datar tidak berubah, sehingga bangun hasil transformasi kongruen sempurna dengan bangun aslinya.

### 2.2 Aturan Sudut dan Arah Putaran
Standar orientasi sudut matematika Cartesius:
* **Sudut Positif ($+\alpha$):** Arah perputaran **berlawanan dengan arah jarum jam** (*counter-clockwise / CCW*).
* **Sudut Negatif ($-\alpha$):** Arah perputaran **searah jarum jam** (*clockwise / CW*).

Pada proyek ini, titik pusat rotasi ditetapkan pada titik pangkal koordinat $O(0,0)$ dengan sudut standar positif: $90^\circ$, $180^\circ$, dan $270^\circ$.

### 2.3 Matriks Transformasi Rotasi terhadap Titik Pusat $O(0,0)$
Secara aljabar matriks linier, koordinat bayangan $P'(x', y')$ hasil rotasi titik $P(x, y)$ sebesar sudut $\alpha$ terhadap pusat $O(0,0)$ dihitung melalui persamaan matriks:

$$\begin{pmatrix} x' \\ y' \end{pmatrix} = R_\alpha \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$$

#### A. Rotasi Sebesar $90^\circ$ ($R[O, 90^\circ]$) $\implies$ Kuadran II
Untuk $\alpha = 90^\circ$, nilai $\cos 90^\circ = 0$ dan $\sin 90^\circ = 1$:
$$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} -y \\ x \end{pmatrix}$$
**Aturan Pemetaan:**
$$(x, y) \xrightarrow{R[O, 90^\circ]} (-y, x)$$

#### B. Rotasi Sebesar $180^\circ$ ($R[O, 180^\circ]$) $\implies$ Kuadran III
Untuk $\alpha = 180^\circ$, nilai $\cos 180^\circ = -1$ dan $\sin 180^\circ = 0$:
$$\begin{pmatrix} x'' \\ y'' \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} -x \\ -y \end{pmatrix}$$
**Aturan Pemetaan:**
$$(x, y) \xrightarrow{R[O, 180^\circ]} (-x, -y)$$

#### C. Rotasi Sebesar $270^\circ$ ($R[O, 270^\circ]$) $\implies$ Kuadran IV
Untuk $\alpha = 270^\circ$, nilai $\cos 270^\circ = 0$ dan $\sin 270^\circ = -1$:
$$\begin{pmatrix} x''' \\ y''' \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} y \\ -x \end{pmatrix}$$
**Aturan Pemetaan:**
$$(x, y) \xrightarrow{R[O, 270^\circ]} (y, -x)$$

---

## BAB III — PROSES PEMBUATAN

### 3.1 Ide dan Desain Ikon Lambang SMKN 9 Semarang
Kelompok 4 mengangkat identitas visual **Lambang SMK Negeri 9 Semarang** sebagai objek perancangan ikon aplikasi. Elemen pembungkus utama lambang adalah sebuah **Perisai Segilima Berlekuk (Heraldic Crest Shield)** berwarna biru yang kokoh.

Karakteristik geometri perisai lambang sekolah:
1. **Ujung Bawah (Titik A):** Menuncip di bagian bawah $A(6, 1.8)$, melambangkan ketajaman berpikir dan fokus kejuruan.
2. **Pinggang Kiri & Kanan (Titik D & E):** Melebar secara aerodinamis di $D(1.6, 11.7)$ dan $E(10.4, 11.7)$ yang dihubungkan dengan kurva Bézier tingkat tinggi ke titik $A$.
3. **Puncak Atas (Titik B & C):** Garis horizontal datar di $y = 13.0$ menghubungkan $B(3.5, 13.0)$ dan $C(8.5, 13.0)$, melambangkan pondasi keilmuan yang stabil.

Siluet perisai dimodelkan ke dalam sistem koordinat Cartesius dengan sumbu simetri vertikal pada garis $x = 6.0$.

### 3.2 Alat dan Perangkat Lunak yang Digunakan
1. **Visual Studio Code & Bun Runtime:** Lingkungan rekayasa perangkat lunak untuk menyusun aplikasi web dan script build monorepo.
2. **React 19 & TypeScript:** Framework antarmuka pengguna deklaratif dengan sistem tipe data matematis ketat.
3. **HTML5 Canvas & SVG Engine:** Perender grafis vektor 2D untuk visualisasi bidang Cartesius dan perhitungan titik koordinat real-time.
4. **Tailwind CSS:** Sistem tata letak modern dan responsif.
5. **Python (NumPy):** Verifikasi kalkulasi determinan matriks, Shoelace Formula, dan panjang segmen Euclidean.
6. **Git & GitHub Pages:** Manajemen repositori versi dan hosting aplikasi berbasis Monorepo dengan GitHub Actions.

### 3.3 Penentuan Koordinat Titik Sudut & Titik Kontrol Lengkung Posisi Awal ($0^\circ$)
Posisi awal seluruhnya berada di **Kuadran I** dengan rincian:

| Titik | Koordinat $(x, y)$ | Tipe Garis / Kurva | Titik Kontrol Lengkung Bézier | Deskripsi Anatomi Lambang |
| :---: | :---: | :---: | :--- | :--- |
| **A** | $(6.0, 1.8)$ | Bézier Multi-Point | $C_1(9.7, 3.2), C_2(11.0, 5.4), C_3(10.3, 8.8)$ | Ujung lancip bawah perisai |
| **E** | $(10.4, 11.7)$ | Kuadratik | $C_1(9.1, 11.5)$ | Sudut pinggang kanan luar |
| **C** | $(8.5, 13.0)$ | Lurus | - | Sudut kanan atas perisai |
| **B** | $(3.5, 13.0)$ | Kuadratik | $C_1(2.9, 11.5)$ | Sudut kiri atas perisai |
| **D** | $(1.6, 11.7)$ | Bézier Multi-Point | $C_1(1.7, 8.8), C_2(1.0, 5.4), C_3(2.6, 3.2)$ | Sudut pinggang kiri luar |

---

### 3.4 Perhitungan Eksak Perkalian Matriks Titik demi Titik

#### A. Rotasi $90^\circ$ ($R[O, 90^\circ]$) $\implies (x, y) \to (-y, x)$ [Kuadran II]
1. **Titik Sudut:**
   * $A(6.0, 1.8) \implies \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 6.0 \\ 1.8 \end{pmatrix} = \begin{pmatrix} -1.8 \\ 6.0 \end{pmatrix} \implies A'(-1.8, 6.0)$
   * $E(10.4, 11.7) \implies \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 10.4 \\ 11.7 \end{pmatrix} = \begin{pmatrix} -11.7 \\ 10.4 \end{pmatrix} \implies E'(-11.7, 10.4)$
   * $C(8.5, 13.0) \implies \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 8.5 \\ 13.0 \end{pmatrix} = \begin{pmatrix} -13.0 \\ 8.5 \end{pmatrix} \implies C'(-13.0, 8.5)$
   * $B(3.5, 13.0) \implies \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 3.5 \\ 13.0 \end{pmatrix} = \begin{pmatrix} -13.0 \\ 3.5 \end{pmatrix} \implies B'(-13.0, 3.5)$
   * $D(1.6, 11.7) \implies \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1.6 \\ 11.7 \end{pmatrix} = \begin{pmatrix} -11.7 \\ 1.6 \end{pmatrix} \implies D'(-11.7, 1.6)$

2. **Titik Kontrol Kurva Bézier Segmen A-E:**
   * $C_1(9.7, 3.2) \to C_1'(-3.2, 9.7)$
   * $C_2(11.0, 5.4) \to C_2'(-5.4, 11.0)$
   * $C_3(10.3, 8.8) \to C_3'(-8.8, 10.3)$

3. **Titik Kontrol Kurva Segmen E-C & B-D:**
   * $C_1(9.1, 11.5) \to C_1'(-11.5, 9.1)$
   * $C_1(2.9, 11.5) \to C_1'(-11.5, 2.9)$

4. **Titik Kontrol Kurva Bézier Segmen D-A:**
   * $C_1(1.7, 8.8) \to C_1'(-8.8, 1.7)$
   * $C_2(1.0, 5.4) \to C_2'(-5.4, 1.0)$
   * $C_3(2.6, 3.2) \to C_3'(-3.2, 2.6)$

---

#### B. Rotasi $180^\circ$ ($R[O, 180^\circ]$) $\implies (x, y) \to (-x, -y)$ [Kuadran III]
1. **Titik Sudut:**
   * $A(6.0, 1.8) \implies \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 6.0 \\ 1.8 \end{pmatrix} = \begin{pmatrix} -6.0 \\ -1.8 \end{pmatrix} \implies A''(-6.0, -1.8)$
   * $E(10.4, 11.7) \implies \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 10.4 \\ 11.7 \end{pmatrix} = \begin{pmatrix} -10.4 \\ -11.7 \end{pmatrix} \implies E''(-10.4, -11.7)$
   * $C(8.5, 13.0) \implies \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 8.5 \\ 13.0 \end{pmatrix} = \begin{pmatrix} -8.5 \\ -13.0 \end{pmatrix} \implies C''(-8.5, -13.0)$
   * $B(3.5, 13.0) \implies \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 3.5 \\ 13.0 \end{pmatrix} = \begin{pmatrix} -3.5 \\ -13.0 \end{pmatrix} \implies B''(-3.5, -13.0)$
   * $D(1.6, 11.7) \implies \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 1.6 \\ 11.7 \end{pmatrix} = \begin{pmatrix} -1.6 \\ -11.7 \end{pmatrix} \implies D''(-1.6, -11.7)$

2. **Titik Kontrol Kurva Bézier Segmen A-E:**
   * $C_1(9.7, 3.2) \to C_1''(-9.7, -3.2)$
   * $C_2(11.0, 5.4) \to C_2''(-11.0, -5.4)$
   * $C_3(10.3, 8.8) \to C_3''(-10.3, -8.8)$

---

#### C. Rotasi $270^\circ$ ($R[O, 270^\circ]$) $\implies (x, y) \to (y, -x)$ [Kuadran IV]
1. **Titik Sudut:**
   * $A(6.0, 1.8) \implies \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix} \begin{pmatrix} 6.0 \\ 1.8 \end{pmatrix} = \begin{pmatrix} 1.8 \\ -6.0 \end{pmatrix} \implies A'''(1.8, -6.0)$
   * $E(10.4, 11.7) \implies \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix} \begin{pmatrix} 10.4 \\ 11.7 \end{pmatrix} = \begin{pmatrix} 11.7 \\ -10.4 \end{pmatrix} \implies E'''(11.7, -10.4)$
   * $C(8.5, 13.0) \implies \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix} \begin{pmatrix} 8.5 \\ 13.0 \end{pmatrix} = \begin{pmatrix} 13.0 \\ -8.5 \end{pmatrix} \implies C'''(13.0, -8.5)$
   * $B(3.5, 13.0) \implies \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix} \begin{pmatrix} 3.5 \\ 13.0 \end{pmatrix} = \begin{pmatrix} 13.0 \\ -3.5 \end{pmatrix} \implies B'''(13.0, -3.5)$
   * $D(1.6, 11.7) \implies \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix} \begin{pmatrix} 1.6 \\ 11.7 \end{pmatrix} = \begin{pmatrix} 11.7 \\ -1.6 \end{pmatrix} \implies D'''(11.7, -1.6)$

2. **Titik Kontrol Kurva Bézier Segmen A-E:**
   * $C_1(9.7, 3.2) \to C_1'''(3.2, -9.7)$
   * $C_2(11.0, 5.4) \to C_2'''(5.4, -11.0)$
   * $C_3(10.3, 8.8) \to C_3'''(8.8, -10.3)$

---

## BAB IV — HASIL DAN ANALISIS

### 4.1 Tabel Komparasi Koordinat 4 Kuadran

| Titik | Posisi Awal ($0^\circ$) [Kuadran I] | Rotasi $90^\circ$ [Kuadran II] | Rotasi $180^\circ$ [Kuadran III] | Rotasi $270^\circ$ [Kuadran IV] | Karakteristik Anatomi Lambang |
| :---: | :---: | :---: | :---: | :---: | :--- |
| **A** | $(6.0, 1.8)$ | $(-1.8, 6.0)$ | $(-6.0, -1.8)$ | $(1.8, -6.0)$ | Ujung lancip bawah perisai |
| **E** | $(10.4, 11.7)$ | $(-11.7, 10.4)$ | $(-10.4, -11.7)$ | $(11.7, -10.4)$ | Sudut pinggang kanan perisai |
| **C** | $(8.5, 13.0)$ | $(-13.0, 8.5)$ | $(-8.5, -13.0)$ | $(13.0, -8.5)$ | Sudut bahu kanan atas |
| **B** | $(3.5, 13.0)$ | $(-13.0, 3.5)$ | $(-3.5, -13.0)$ | $(13.0, -3.5)$ | Sudut bahu kiri atas |
| **D** | $(1.6, 11.7)$ | $(-11.7, 1.6)$ | $(-1.6, -11.7)$ | $(11.7, -1.6)$ | Sudut pinggang kiri perisai |

---

### 4.2 Analisis Karakteristik Geometri dan Pembuktian Isometri

#### 1. Pembuktian Kekekalan Jarak Segmen Garis (Isometri Sisi)
Jarak Euclidean antardua titik dihitung dengan rumus:
$$d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$$

Hasil perhitungan panjang ke-5 segmen sisi pada posisi awal ($0^\circ$):
* **Sisi A-E:** $\sqrt{(10.4 - 6.0)^2 + (11.7 - 1.8)^2} = \sqrt{4.4^2 + 9.9^2} = \sqrt{19.36 + 98.01} = \sqrt{117.37} \approx 10.834 \text{ satuan}$
* **Sisi E-C:** $\sqrt{(8.5 - 10.4)^2 + (13.0 - 11.7)^2} = \sqrt{(-1.9)^2 + 1.3^2} = \sqrt{3.61 + 1.69} = \sqrt{5.30} \approx 2.302 \text{ satuan}$
* **Sisi C-B:** $\sqrt{(3.5 - 8.5)^2 + (13.0 - 13.0)^2} = \sqrt{(-5.0)^2 + 0^2} = 5.000 \text{ satuan}$ (Garis horizontal datar)
* **Sisi B-D:** $\sqrt{(1.6 - 3.5)^2 + (11.7 - 13.0)^2} = \sqrt{(-1.9)^2 + (-1.3)^2} = \sqrt{3.61 + 1.69} = \sqrt{5.30} \approx 2.302 \text{ satuan}$
* **Sisi D-A:** $\sqrt{(6.0 - 1.6)^2 + (1.8 - 11.7)^2} = \sqrt{4.4^2 + (-9.9)^2} = \sqrt{19.36 + 98.01} = \sqrt{117.37} \approx 10.834 \text{ satuan}$

**Total Keliling Poligon Perisai:**
$$K = 10.834 + 2.302 + 5.000 + 2.302 + 10.834 = \mathbf{31.272 \text{ satuan panjang}}$$

Pada rotasi $90^\circ$ di Kuadran II, kita uji kembali panjang sisi $A'-E'$:
$$d(A', E') = \sqrt{(-11.7 - (-1.8))^2 + (10.4 - 6.0)^2} = \sqrt{(-9.9)^2 + 4.4^2} = \sqrt{98.01 + 19.36} = \sqrt{117.37} \approx 10.834 \text{ satuan}$$
Dan sisi horizontal yang berputar menjadi vertikal $C'-B'$:
$$d(C', B') = \sqrt{(-13.0 - (-13.0))^2 + (3.5 - 8.5)^2} = \sqrt{0 + (-5.0)^2} = 5.000 \text{ satuan}$$

Perhitungan ini membuktikan secara matematis bahwa **seluruh panjang segmen sisi dan keliling poligon perisai lambang sekolah bernilai kekal (invarian)** pada seluruh orientasi putaran.

#### 2. Pembuktian Kekekalan Luas (Shoelace Formula / Rumus Gauss)
Luas poligon sembarang dengan koordinat berurutan $(x_1, y_1), (x_2, y_2), \dots, (x_n, y_n)$ dihitung dengan rumus determinan tali sepatu Gauss:
$$\text{Luas} = \frac{1}{2} \left| \sum_{i=1}^{n} (x_i y_{i+1} - x_{i+1} y_i) \right|$$

Dengan memasukkan ke-5 titik sudut perisai secara berurutan:
1. Posisi Awal ($0^\circ$): $\text{Luas} = \mathbf{52.53 \text{ satuan luas}}$
2. Rotasi $90^\circ$: $\text{Luas} = \mathbf{52.53 \text{ satuan luas}}$
3. Rotasi $180^\circ$: $\text{Luas} = \mathbf{52.53 \text{ satuan luas}}$
4. Rotasi $270^\circ$: $\text{Luas} = \mathbf{52.53 \text{ satuan luas}}$

Hal ini membuktikan secara analitis bahwa transformasi rotasi merupakan transformasi **isometri sejati** yang mempertahankan bentuk dan ukuran luas bangun tanpa distorsi.

#### 3. Analisis Morfologi Visual Lambang Sekolah saat Diputar
* **0° (Kuadran I):** Perisai berdiri tegak (*upright normal*), ujung lancip mengarah ke bawah, mahkota perisai menghadap sumbu $+Y$. Ini adalah orientasi lambang resmi sekolah.
* **90° (Kuadran II):** Perisai berputar $90^\circ$ berlawanan arah jarum jam. Mahkota atas mengarah ke sumbu horizontal kiri ($-X$), dan ujung lancip menghadap sumbu $+Y$.
* **180° (Kuadran III):** Perisai terbalik sempurna (*upside down*). Mahkota atas menghadap ke bawah ($-Y$), dan ujung lancip menghadap ke atas.
* **270° (Kuadran IV):** Perisai berputar $270^\circ$ (setara $90^\circ$ searah jarum jam). Mahkota atas menghadap sumbu horizontal kanan ($+X$).

---

## BAB V — KESIMPULAN DAN RELEVANSI PPLG

### 5.1 Kesimpulan Proyek
1. **Konsep Transformasi Geometri:** Transformasi rotasi terhadap titik pusat $O(0,0)$ pada bidang koordinat Cartesius menghasilkan perubahan posisi yang teratur, simetris, dan dapat dihitung secara deterministik menggunakan aljabar matriks trigonometri.
2. **Kaidah Pemetaan:** Setiap koordinat mematuhi aturan baku:
   - Rotasi $90^\circ$: $(x, y) \to (-y, x)$
   - Rotasi $180^\circ$: $(x, y) \to (-x, -y)$
   - Rotasi $270^\circ$: $(x, y) \to (y, -x)$
3. **Pembuktian Isometri:**
   - Panjang seluruh segmen sisi poligon dan keliling total ($31.27$ satuan panjang) bernilai tetap.
   - Luas total poligon perisai lambang SMKN 9 Semarang bernilai konstan **52.53 satuan luas** di keempat kuadran.
4. **Kurva Bézier Dinamis:** Pemanfaatan titik kontrol kurva Bézier ($C_1 \dots C_n$) memungkinkan rekonstruksi lambang sekolah secara organik dan aerodinamis tanpa merusak sifat invarian transformasi geometri.

### 5.2 Relevansi dengan Rekayasa Perangkat Lunak (PPLG)
1. **CSS Transform 2D pada Antarmuka Web (UI/UX):**
   Browser modern mengeksekusi rotasi antarmuka melalui matriks affine GPU:
   ```css
   .icon-smkn9 {
     transform-origin: 0px 0px; /* Pivot pusat O(0,0) */
     transform: rotate(90deg);  /* Matriks [0, -1, 1, 0, 0, 0] */
     transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
   }
   ```
2. **HTML5 Canvas 2D API & Game Engine:**
   Pengembang gim menerapkan manipulasi matriks rotasi langsung pada loop perenderan grafis:
   ```javascript
   ctx.save();
   ctx.translate(centerX, centerY);
   ctx.rotate((angleInDegrees * Math.PI) / 180);
   // Render path poligon & kurva Bézier perisai SMKN 9
   ctx.stroke(shieldPath);
   ctx.restore();
   ```
3. **Algoritma de Casteljau untuk Kurva Parametrik:**
   Perhitungan posisi kurva Bézier orde tinggi yang diterapkan pada aplikasi web memastikan kurva tetap mulus saat bertransformasi, membuktikan penerapan komputasi matematika dalam rekayasa grafika komputer modern.

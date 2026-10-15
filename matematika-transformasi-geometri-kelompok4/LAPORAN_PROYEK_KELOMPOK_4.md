# LAPORAN PROYEK TRANSFORMASI GEOMETRI
## IMPLEMENTASI ROTASI PADA DESAIN IKON APLIKASI LAMBANG SMKN 9 SEMARANG

---

### IDENTITAS PROYEK
* **Judul Proyek:** Desain dan Analisis Transformasi Geometri Rotasi 2D pada Ikon Aplikasi Lambang SMK Negeri 9 Semarang Berbasis Koordinat Cartesius dan Garis Lengkung (Kurva Bézier)
* **Tema Penugasan:** Tim 4 — Rotasi Ikon Aplikasi (Panduan Proyek Matematika Kelas XII)
* **Kelompok:** 4 (Empat)
* **Anggota Kelompok:**
  1. ............................................................ (No. Presensi: .....)
  2. ............................................................ (No. Presensi: .....)
  3. ............................................................ (No. Presensi: .....)
  4. ............................................................ (No. Presensi: .....)
* **Kelas:** XII PPLG (Pengembangan Perangkat Lunak dan Gim)
* **Mata Pelajaran:** Matematika (Fase F / Kurikulum Merdeka)
* **Materi Pokok:** Transformasi Geometri — Rotasi (Perputaran) Dua Dimensi
* **Guru Pembimbing:** Guru Mata Pelajaran Matematika Kelas XII
* **Instansi Sekolah:** SMK Negeri 9 Semarang
* **Tahun Pelajaran:** 2026/2027

---

## BAB I — PENDAHULUAN

### 1.1 Latar Belakang
Dalam industri teknologi informasi dan rekayasa perangkat lunak modern (bidang keahlian PPLG), perancangan grafis berbasis vektor merupakan fondasi dari pembuatan antarmuka pengguna (*User Interface / UI*), aset gim, dan ikon aplikasi digital. Berbeda dengan gambar biasa berbasis piksel/raster (*seperti JPEG atau PNG*) yang akan pecah atau buram saat diperbesar, grafis vektor dibangun di atas **sistem koordinat matematika Cartesius**. Setiap bentuk ikon disimpan sebagai rumus koordinat titik dan garis, sehingga dapat diperbesar, diperkecil, atau diputar secara dinamis tanpa kehilangan ketajaman sedikit pun (*lossless resolution*).

Salah satu operasi matematika yang paling sering digunakan dalam pengembangan aplikasi dan gim adalah **transformasi geometri rotasi (perputaran)**. Dalam kehidupan digital sehari-hari, rotasi dapat kita jumpai pada:
1. **Animasi *Loading Indicator* (*Spinner*):** Ikon lingkaran atau lambang aplikasi yang berputar mulus saat data sedang dimuat.
2. **Perubahan Orientasi Karakter Gim 2D:** Karakter gim yang berbalik arah ke kiri, kanan, atas, atau bawah mengikuti arah analog kontrol.
3. **Kompas dan Peta Digital:** Jarum petunjuk arah navigasi pada Google Maps yang berputar mengikuti orientasi kendaraan pengguna.
4. **Fitur *Auto-Rotate* pada Ponsel:** Tampilan layar aplikasi yang otomatis berotasi $90^\circ$ dari posisi potret (*portrait*) ke lanskap (*landscape*).

Sebagai siswa SMK Negeri 9 Semarang jurusan Pengembangan Perangkat Lunak dan Gim (PPLG), kami dituntut tidak hanya mampu menggunakan aplikasi desain atau menulis kode pemrograman secara visual, tetapi juga memahami **konsep matematika aljabar linier dan perkalian matriks** yang bekerja di balik layar komputer tersebut. 

Pada proyek ini, **Kelompok 4** memilih objek yang membanggakan, yaitu **Lambang Resmi SMK Negeri 9 Semarang**, untuk dirancang ulang menjadi ikon aplikasi berbasis koordinat Cartesius. Karena lambang sekolah berbentuk perisai dengan lekukan yang aerodinamis dan luwes (tidak kaku seperti balok kardus), kami memadukan titik-titik sudut utama dengan **garis lengkung halus (Kurva Bézier)**. Melalui proyek ini, kami menganalisis perubahan koordinat titik sudut dan titik kontrol lengkungan saat dirotasikan sebesar $90^\circ$, $180^\circ$, dan $270^\circ$ terhadap titik pusat pangkal $O(0,0)$, serta membuktikan bahwa rotasi memiliki sifat **isometri** (panjang sisi dan luas bangun tetap kekal).

### 1.2 Rumusan Masalah
Berdasarkan latar belakang di atas, rumusan masalah dalam proyek ini adalah:
1. Bagaimana cara memodelkan Lambang SMK Negeri 9 Semarang ke dalam sistem koordinat Cartesius yang memadukan titik sudut dan garis lengkung?
2. Bagaimana konsep perkalian matriks rotasi dua dimensi dengan titik pusat di $O(0,0)$ pada sudut $90^\circ$, $180^\circ$, dan $270^\circ$?
3. Bagaimana pengaruh rotasi terhadap titik sudut utama dan titik-titik pengendali kelengkungan logo?
4. Bagaimana membuktikan secara analitis bahwa rotasi mempertahankan panjang segmen garis dan luas daerah bangun datar (sifat isometri)?
5. Bagaimana aturan transformasi geometri ini diimplementasikan secara nyata ke dalam kode pemrograman web dan gim (PPLG)?

### 1.3 Tujuan Proyek
Tujuan yang ingin dicapai melalui pelaksanaan proyek kelompok ini adalah:
1. Menjelaskan konsep dasar dan rumus perkalian matriks transformasi rotasi dua dimensi dengan titik pusat $O(0,0)$.
2. Menentukan koordinat bayangan hasil rotasi $90^\circ$, $180^\circ$, dan $270^\circ$ berlawanan arah jarum jam secara tepat titik demi titik.
3. Menjelaskan secara sederhana bagaimana garis lengkung grafika komputer (Kurva Bézier) ikut bertransformasi bersama titik sudutnya.
4. Membuktikan sifat isometri rotasi melalui perhitungan jarak Euclidean (panjang sisi dan keliling) serta perhitungan luas poligon menggunakan rumus tali sepatu (*Shoelace Formula*).
5. Mewujudkan hasil perhitungan matematika ke dalam produk digital berupa **Aplikasi Web Interaktif** dan **Infografis Koordinat 4 Kuadran**.
6. Mempresentasikan laporan hasil proyek secara komunikatif, ilmiah, dan terstruktur di hadapan guru dan teman sekelas.

### 1.4 Manfaat Proyek
1. **Bagi Siswa:** Membuka wawasan bahwa materi matematika matriks dan koordinat Cartesius bukanlah sekadar rumus hafalan di atas kertas, melainkan teknologi nyata yang menggerakkan mesin grafis (*rendering engine*) di industri perangkat lunak dan gim.
2. **Bagi Pembelajaran Matematika:** Menghadirkan model pembelajaran matematika Kurikulum Merdeka yang kontekstual, menarik, berbasis proyek (*Project-Based Learning*), dan relevan dengan kompetensi kejuruan SMK.
3. **Bagi Sekolah:** Menghasilkan produk karya digital siswa berupa aplikasi visualizer dan media ajar interaktif yang memanfaatkan lambang kebanggaan SMK Negeri 9 Semarang.

---

## BAB II — LANDASAN TEORI

### 2.1 Konsep Transformasi Geometri dan Rotasi
**Transformasi geometri** adalah aturan matematika yang memindahkan setiap titik pada bidang datar dari posisi awal $P(x, y)$ ke posisi baru yang disebut bayangan $P'(x', y')$.

Salah satu jenis transformasi geometri adalah **Rotasi (Perputaran)**. Rotasi adalah proses memutar setiap titik pada bidang datar mengelilingi suatu titik tetap yang disebut **titik pusat rotasi** sebesar sudut tertentu ($\alpha$).

Ciri utama dari transformasi rotasi adalah bersifat **Isometri**.
> **Penjelasan Istilah: Apa itu Isometri?**  
> Kata *isometri* berasal dari bahasa Yunani: **"iso"** yang berarti *sama*, dan **"metron"** yang berarti *ukuran*.  
> Dalam matematika, transformasi isometri adalah transformasi yang **mempertahankan jarak dan ukuran**. Artinya, saat sebuah benda diputar, panjang sisinya tidak bertambah panjang, tidak memendek, dan luas bangunnya tidak membesar maupun mengecil. Objek hasil rotasi memiliki bentuk dan ukuran yang **kongruen sempurna** (sama dan sebangun) dengan objek awalnya.

### 2.2 Aturan Sudut dan Arah Putaran
Dalam standar matematika Cartesius dan trigonometri:
* **Sudut Bernilai Positif ($+\alpha$):** Arah perputaran **berlawanan dengan arah jarum jam** (*counter-clockwise / CCW*).
* **Sudut Bernilai Negatif ($-\alpha$):** Arah perputaran **searah dengan jarum jam** (*clockwise / CW*).

Pada proyek ini, seluruh pengujian menggunakan titik pusat pangkal koordinat **$O(0,0)$** dengan sudut positif: $+90^\circ$, $+180^\circ$, dan $+270^\circ$.

```text
               +Y (Sumbu Vertikal)
                 ^
  KUADRAN II     |     KUADRAN I
  Rotasi +90°    |     Posisi Awal (0°)
  (-, +)         |     (+, +)
                 |
<----------------O----------------> +X (Sumbu Horizontal)
  Pusat (0,0)    |
  KUADRAN III    |     KUADRAN IV
  Rotasi +180°   |     Rotasi +270°
  (-, -)         |     (+, -)
                 v
```

### 2.3 Matriks Transformasi Rotasi terhadap Titik Pusat $O(0,0)$
Secara aljabar matriks, posisi bayangan titik $P'(x', y')$ yang diputar sebesar sudut $\alpha$ terhadap pusat $O(0,0)$ dihitung menggunakan rumus perkalian matriks 2D:

$$
\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}
$$

Bentuk visual susunan matriks:
```text
  ┌ x' ┐   ┌  cos α   -sin α ┐ ┌ x ┐
  └ y' ┘ = └  sin α    cos α ┘ └ y ┘
```

Persamaan aljabar skalar yang dihasilkan:
* $x' = (x \cdot \cos\alpha) - (y \cdot \sin\alpha)$
* $y' = (x \cdot \sin\alpha) + (y \cdot \cos\alpha)$

Matriks rotasi $2 \times 2$ tersebut dinamakan **Matriks Operator Rotasi ($R_\alpha$)**.

Berikut adalah penurunan rumus untuk sudut-sudut istimewa kuadran:

#### A. Rotasi Sebesar $90^\circ$ ($R[O, 90^\circ]$) $\longrightarrow$ Memutar ke Kuadran II
Untuk sudut $\alpha = 90^\circ$, nilai trigonometrinya adalah $\cos 90^\circ = 0$ dan $\sin 90^\circ = 1$.  
Substitusikan nilai ke matriks operator:

$$
\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} (0 \cdot x) + (-1 \cdot y) \\ (1 \cdot x) + (0 \cdot y) \end{pmatrix} = \begin{pmatrix} -y \\ x \end{pmatrix}
$$

Bentuk visual perhitungan:
```text
  ┌ x' ┐   ┌  0  -1 ┐ ┌ x ┐   ┌ (0 · x) + (-1 · y) ┐   ┌ -y ┐
  └ y' ┘ = └  1   0 ┘ └ y ┘ = └ (1 · x) + (0 · y)  ┘ = └  x ┘
```

> **Rumus Praktis Pemetaan Rotasi 90° ($R[O, 90^\circ]$):**  
> **$\mathbf{P(x, y) \longrightarrow P'(-y, x)}$**  
> *(Aturan cepat: Tukar posisi nilai $x$ dan $y$, lalu beri tanda negatif pada nilai $x$ yang baru).*

---

#### B. Rotasi Sebesar $180^\circ$ ($R[O, 180^\circ]$) $\longrightarrow$ Memutar ke Kuadran III
Untuk sudut $\alpha = 180^\circ$, nilai trigonometrinya adalah $\cos 180^\circ = -1$ dan $\sin 180^\circ = 0$.  
Substitusikan nilai ke matriks operator:

$$
\begin{pmatrix} x'' \\ y'' \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} (-1 \cdot x) + (0 \cdot y) \\ (0 \cdot x) + (-1 \cdot y) \end{pmatrix} = \begin{pmatrix} -x \\ -y \end{pmatrix}
$$

Bentuk visual perhitungan:
```text
  ┌ x'' ┐   ┌ -1   0 ┐ ┌ x ┐   ┌ (-1 · x) + (0 · y) ┐   ┌ -x ┐
  └ y'' ┘ = └  0  -1 ┘ └ y ┘ = └ (0 · x) + (-1 · y) ┘ = └ -y ┘
```

> **Rumus Praktis Pemetaan Rotasi 180° ($R[O, 180^\circ]$):**  
> **$\mathbf{P(x, y) \longrightarrow P''(-x, -y)}$**  
> *(Aturan cepat: Posisi $x$ dan $y$ tetap, namun kedua nilai tandanya dibalik menjadi lawan / negatif).*

---

#### C. Rotasi Sebesar $270^\circ$ ($R[O, 270^\circ]$) $\longrightarrow$ Memutar ke Kuadran IV
Untuk sudut $\alpha = 270^\circ$, nilai trigonometrinya adalah $\cos 270^\circ = 0$ dan $\sin 270^\circ = -1$.  
Substitusikan nilai ke matriks operator:

$$
\begin{pmatrix} x''' \\ y''' \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} (0 \cdot x) + (1 \cdot y) \\ (-1 \cdot x) + (0 \cdot y) \end{pmatrix} = \begin{pmatrix} y \\ -x \end{pmatrix}
$$

Bentuk visual perhitungan:
```text
  ┌ x''' ┐   ┌  0   1 ┐ ┌ x ┐   ┌ (0 · x) + (1 · y)  ┐   ┌  y ┐
  └ y''' ┘ = └ -1   0 ┘ └ y ┘ = └ (-1 · x) + (0 · y) ┘ = └ -x ┘
```

> **Rumus Praktis Pemetaan Rotasi 270° ($R[O, 270^\circ]$):**  
> **$\mathbf{P(x, y) \longrightarrow P'''(y, -x)}$**  
> *(Aturan cepat: Tukar posisi nilai $x$ dan $y$, lalu beri tanda negatif pada nilai $y$ yang baru).*

---

### 2.4 Konsep Garis Lengkung dan Titik Kontrol (Kurva Bézier)
Saat menggambar di atas koordinat Cartesius, bentuk sederhana seperti segitiga atau persegi dapat dibuat hanya dengan menarik garis lurus dari satu titik sudut ke titik sudut berikutnya. Namun, objek dunia nyata—seperti sayap burung, bodi mobil, atau **lambang perisai sekolah SMKN 9**—memiliki **sisi yang melengkung indah**.

Di sinilah grafika komputer menggunakan metode yang disebut **Kurva Bézier**.

> **Penjelasan Istilah: Apa itu Kurva Bézier?**  
> Kurva Bézier adalah cara komputer menggambar **garis lengkung yang mulus dan luwes** menggunakan bantuan **"titik pengendali" (*control points*)**.  
> * **Analogi Nyata:** Bagi yang pernah menggunakan aplikasi desain seperti Figma, Canva, Adobe Illustrator, CorelDraw, atau Photoshop, Kurva Bézier adalah garis yang tercipta saat kita menggunakan alat **Pen Tool**.  
> Saat kita mengeklik sebuah titik (titik sudut awal), lalu menarik sebuah gagang (*handle*) ke arah luar, garis tersebut akan melengkung mengikuti arah tarikan gagang tersebut. Titik di ujung gagang penarik itulah yang disebut **Titik Kontrol ($C_1, C_2, \dots$)**.

```text
Titik A (Awal)  o──────────────────o Titik Kontrol C1 (Menarik kelengkungan ke kanan)
                \
                 \  (Garis melengkung mulus / Kurva Bézier)
                  \
                   o Titik E (Akhir)
```

**Bagaimana hubungan Kurva Lengkung ini dengan Transformasi Geometri?**
Inilah keunggulan utama pendekatan kami:  
Garis lengkung pada komputer tidak digambar secara sembarangan, melainkan dikendalikan oleh posisi titik koordinatnya. Ketika lambang perisai dirotasikan, **titik-titik kontrol kelengkungan ($C$) ikut diputar menggunakan rumus matriks rotasi yang sama persis dengan titik sudut utama ($A, B, C, D, E$)**:

```text
  ┌ x_C' ┐   ┌  cos α   -sin α ┐ ┌ x_C ┐
  └ y_C' ┘ = └  sin α    cos α ┘ └ y_C ┘
```
Atau secara ringkas:
$$\mathbf{C'(x_C', y_C') = R_\alpha \cdot C(x_C, y_C)}$$

Karena titik kontrol ikut berputar secara presisi bersama titik sudutnya, **bentuk lengkungan perisai lambang SMKN 9 tidak pernah rusak, tidak penyok, dan tidak gepeng** pada sudut putaran berapa pun.

---

### 2.5 Rumus Pengujian Isometri: Jarak Sisi dan Luas Bangun

#### 1. Rumus Jarak Antartitik (Panjang Segmen Sisi)
Untuk menguji apakah panjang sisi bangun tidak berubah setelah diputar, digunakan rumus jarak Euclidean antara dua titik $P_1(x_1, y_1)$ dan $P_2(x_2, y_2)$ yang diturunkan dari Teorema Pythagoras:

$$d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$$

#### 2. Rumus Luas Poligon Cartesius (Shoelace Formula / Rumus Tali Sepatu Gauss)
> **Penjelasan Istilah: Apa itu Shoelace Formula?**  
> Menghitung luas bangun sembarang di atas koordinat Cartesius tidak bisa menggunakan rumus biasa seperti "panjang $\times$ lebar" atau "$\frac{1}{2} \times \text{alas} \times \text{tinggi}$".  
> Carl Friedrich Gauss menciptakan rumus praktis: koordinat titik-titik sudut disusun berurutan melingkar, lalu dikalikan secara menyilang mirip pola **menalikan tali sepatu (*shoelace*)**.

Untuk poligon dengan titik sudut berurutan $(x_1, y_1), (x_2, y_2), \dots, (x_n, y_n)$:

$$\text{Luas} = \frac{1}{2} \Big| (x_1 y_2 + x_2 y_3 + \dots + x_n y_1) - (y_1 x_2 + y_2 x_3 + \dots + y_n x_1) \Big|$$

$$\text{Luas} = \frac{1}{2} \left| \sum_{i=1}^{n} (x_i y_{i+1} - x_{i+1} y_i) \right|$$

Jika nilai luas sebelum dan sesudah diputar menghasilkan angka yang persis sama, maka terbukti secara sah bahwa rotasi tersebut memenuhi sifat **isometri kekekalan luas**.

---

## BAB III — PROSES PEMBUATAN DAN PERHITUNGAN

### 3.1 Ide dan Desain Ikon Lambang SMKN 9 Semarang
Kelompok 4 memilih Lambang Resmi SMK Negeri 9 Semarang sebagai objek transformasi. Bingkai terluar lambang sekolah memiliki bentuk **Perisai Segilima Berlekuk (*Heraldic Crest Shield*)** yang gagah dan melambangkan perlindungan, integritas, serta keunggulan mutu pendidikan.

Kami memetakan bentuk perisai tersebut ke dalam bidang Cartesius Kuadran I dengan **5 titik sudut utama** dan **titik kontrol lengkung**:
1. **Titik A $(6.0, 1.8)$ — Ujung Bawah Perisai:** Berada di bagian paling bawah dan runcing, menjadi poros ujung perisai.
2. **Titik E $(10.4, 11.7)$ — Pinggang Kanan Luar:** Titik terluar di sebelah kanan perisai.
3. **Titik C $(8.5, 13.0)$ — Bahu Kanan Atas:** Sudut atas sebelah kanan perisai.
4. **Titik B $(3.5, 13.0)$ — Bahu Kiri Atas:** Sudut atas sebelah kiri perisai. Antara titik $B$ dan $C$ membentuk garis horizontal mendatar sebagai batas mahkota atas perisai.
5. **Titik D $(1.6, 11.7)$ — Pinggang Kiri Luar:** Titik terluar di sebelah kiri perisai, simetris sempurna dengan titik $E$ terhadap garis tengah vertikal $x = 6.0$.

Sisi $A \to E$ dan $D \to A$ dihubungkan oleh kurva lengkung yang dikendalikan oleh 3 titik kontrol penarik ($C_1, C_2, C_3$).

```text
                  Garis Mahkota Atas (Datar)
                 B(3.5, 13) ──────── C(8.5, 13)
                /                              \
  Pinggang Kiri                                  Pinggang Kanan
  D(1.6, 11.7)                                    E(10.4, 11.7)
        \                                              /
         \                                            /
          \─── (Kurva Lengkung Sisi Perisai) ────────/
                           \        /
                            \      /
                             A(6, 1.8) (Ujung Lancip Bawah)
```

### 3.2 Alat dan Perangkat Lunak yang Digunakan
1. **Kanvas Kartesius Digital & Live Coordinate Inspector (Aplikasi Web Buatan Sendiri):** Pengganti kertas millimeter block manual, di mana penentuan posisi koordinat ($X, Y$), titik sudut utama, dan titik kontrol kurva Bézier dilakukan secara digital langsung di atas kanvas interaktif dengan grid Cartesius beresolusi tinggi, fitur *drag-and-drop*, dan pembacaan koordinat *real-time*.
2. **Visual Studio Code:** Editor kode pemrograman terintegrasi untuk menyusun kode aplikasi web visualizer, skrip kompilasi dokumen, dan naskah presentasi.
3. **Bahasa Pemrograman TypeScript & Framework React:** Digunakan untuk membangun antarmuka web reaktif, logika transformasi matematika, serta perhitungan deterministik nilai matriks rotasi.
4. **HTML5 Canvas 2D & SVG (Scalable Vector Graphics):** Mesin perender grafik Cartesius interaktif di peramban web agar lintasan poligon, sumbu koordinat, dan kurva lengkung dapat divisualisasikan secara nyata dan diekspor ke format vektor standar W3C.
5. **Python (NumPy, python-docx, python-pptx):** Digunakan untuk memvalidasi ketepatan aljabar matriks, jarak Euclidean, luas poligon Gauss (Shoelace Formula), serta mengompilasi naskah ke dokumen Microsoft Word berstandar formula OMML dan berkas presentasi slide PowerPoint.
6. **Git & GitHub Pages:** Sistem kontrol versi (*version control system*) untuk mengelola kode sumber secara kolaboratif dan mempublikasikan aplikasi web interaktif agar dapat diakses oleh guru penguji dan rekan siswa secara daring.
7. **ONLYOFFICE Desktop Editors:** Perangkat lunak pengolah dokumen dan presentasi untuk menyusun, meninjau, dan memverifikasi tata letak berkas laporan (*.docx*) dengan formula matematis standar OMML dan berkas slide presentasi (*.pptx*).

---

### 3.3 Penentuan Koordinat Posisi Awal ($0^\circ$ — Kuadran I)
Seluruh titik pada posisi awal ditempatkan di Kuadran I ($x > 0$ dan $y > 0$):

#### A. Titik Sudut Poligon Utama
| Label Titik | Koordinat Awal $(x, y)$ | Keterangan Bagian Lambang |
| :---: | :---: | :--- |
| **A** | $(6.0, 1.8)$ | Ujung lancip bawah perisai |
| **E** | $(10.4, 11.7)$ | Sudut pinggang kanan luar |
| **C** | $(8.5, 13.0)$ | Sudut bahu kanan atas |
| **B** | $(3.5, 13.0)$ | Sudut bahu kiri atas |
| **D** | $(1.6, 11.7)$ | Sudut pinggang kiri luar |

#### B. Titik Kontrol Lengkungan (Kurva Bézier)
| Segmen Sisi | Label Titik Kontrol | Koordinat $(x, y)$ | Fungsi Pengendali Lengkungan |
| :---: | :---: | :---: | :--- |
| **Sisi A $\to$ E** | $C_1$ | $(9.7, 3.2)$ | Menarik lekukan bawah dekat ujung runcing |
| *(Pinggang Kanan)* | $C_2$ | $(11.0, 5.4)$ | Menarik lekukan tengah pinggang perisai |
| | $C_3$ | $(10.3, 8.8)$ | Mengarahkan kelengkungan ke sudut pinggang kanan ($E$) |
| **Sisi E $\to$ C** | $C_1$ | $(9.1, 11.5)$ | Memberikan kelengkungan halus antara pinggang dan bahu kanan |
| **Sisi B $\to$ D** | $C_1$ | $(2.9, 11.5)$ | Memberikan kelengkungan halus antara bahu kiri dan pinggang |
| **Sisi D $\to$ A** | $C_1$ | $(1.7, 8.8)$ | Mengarahkan kelengkungan dari pinggang kiri ke bawah |
| *(Pinggang Kiri)* | $C_2$ | $(1.0, 5.4)$ | Menarik lekukan tengah pinggang kiri |
| | $C_3$ | $(2.6, 3.2)$ | Mengarahkan lengkungan kembali ke ujung runcing bawah ($A$) |

---

### 3.4 Perhitungan Eksak Perkalian Matriks Titik demi Titik

#### A. Rotasi $90^\circ$ ($R[O, 90^\circ]$) $\longrightarrow (x, y) \to (-y, x)$ [Kuadran II]
Matriks operator:
```text
  ┌  0  -1 ┐
  └  1   0 ┘
```
Aturan perkalian:
* $x' = (0 \cdot x) + (-1 \cdot y) = -y$
* $y' = (1 \cdot x) + (0 \cdot y) = x$

**1. Perhitungan Titik Sudut Utama:**
* **Titik A (6.0, 1.8):**
  * $x' = (0 \times 6.0) + (-1 \times 1.8) = 0 - 1.8 = \mathbf{-1.8}$
  * $y' = (1 \times 6.0) + (0 \times 1.8) = 6.0 + 0 = \mathbf{6.0}$
  * **Koordinat Bayangan:** $\mathbf{A'(-1.8, 6.0)}$
* **Titik E (10.4, 11.7):**
  * $x' = (0 \times 10.4) + (-1 \times 11.7) = 0 - 11.7 = \mathbf{-11.7}$
  * $y' = (1 \times 10.4) + (0 \times 11.7) = 10.4 + 0 = \mathbf{10.4}$
  * **Koordinat Bayangan:** $\mathbf{E'(-11.7, 10.4)}$
* **Titik C (8.5, 13.0):**
  * $x' = (0 \times 8.5) + (-1 \times 13.0) = 0 - 13.0 = \mathbf{-13.0}$
  * $y' = (1 \times 8.5) + (0 \times 13.0) = 8.5 + 0 = \mathbf{8.5}$
  * **Koordinat Bayangan:** $\mathbf{C'(-13.0, 8.5)}$
* **Titik B (3.5, 13.0):**
  * $x' = (0 \times 3.5) + (-1 \times 13.0) = 0 - 13.0 = \mathbf{-13.0}$
  * $y' = (1 \times 3.5) + (0 \times 13.0) = 3.5 + 0 = \mathbf{3.5}$
  * **Koordinat Bayangan:** $\mathbf{B'(-13.0, 3.5)}$
* **Titik D (1.6, 11.7):**
  * $x' = (0 \times 1.6) + (-1 \times 11.7) = 0 - 11.7 = \mathbf{-11.7}$
  * $y' = (1 \times 1.6) + (0 \times 11.7) = 1.6 + 0 = \mathbf{1.6}$
  * **Koordinat Bayangan:** $\mathbf{D'(-11.7, 1.6)}$

**2. Perhitungan Titik Kontrol Lengkung (Contoh Sisi A-E):**
* $C_1(9.7, 3.2) \to C_1'(-3.2, 9.7)$
* $C_2(11.0, 5.4) \to C_2'(-5.4, 11.0)$
* $C_3(10.3, 8.8) \to C_3'(-8.8, 10.3)$

---

#### B. Rotasi $180^\circ$ ($R[O, 180^\circ]$) $\longrightarrow (x, y) \to (-x, -y)$ [Kuadran III]
Matriks operator:
```text
  ┌ -1   0 ┐
  └  0  -1 ┘
```
Aturan perkalian:
* $x'' = (-1 \cdot x) + (0 \cdot y) = -x$
* $y'' = (0 \cdot x) + (-1 \cdot y) = -y$

**1. Perhitungan Titik Sudut Utama:**
* **Titik A (6.0, 1.8):**
  * $x'' = (-1 \times 6.0) + (0 \times 1.8) = -6.0 + 0 = \mathbf{-6.0}$
  * $y'' = (0 \times 6.0) + (-1 \times 1.8) = 0 - 1.8 = \mathbf{-1.8}$
  * **Koordinat Bayangan:** $\mathbf{A''(-6.0, -1.8)}$
* **Titik E (10.4, 11.7):**
  * $x'' = (-1 \times 10.4) + (0 \times 11.7) = -10.4 + 0 = \mathbf{-10.4}$
  * $y'' = (0 \times 10.4) + (-1 \times 11.7) = 0 - 11.7 = \mathbf{-11.7}$
  * **Koordinat Bayangan:** $\mathbf{E''(-10.4, -11.7)}$
* **Titik C (8.5, 13.0):**
  * $x'' = (-1 \times 8.5) + (0 \times 13.0) = -8.5 + 0 = \mathbf{-8.5}$
  * $y'' = (0 \times 8.5) + (-1 \times 13.0) = 0 - 13.0 = \mathbf{-13.0}$
  * **Koordinat Bayangan:** $\mathbf{C''(-8.5, -13.0)}$
* **Titik B (3.5, 13.0):**
  * $x'' = (-1 \times 3.5) + (0 \times 13.0) = -3.5 + 0 = \mathbf{-3.5}$
  * $y'' = (0 \times 3.5) + (-1 \times 13.0) = 0 - 13.0 = \mathbf{-13.0}$
  * **Koordinat Bayangan:** $\mathbf{B''(-3.5, -13.0)}$
* **Titik D (1.6, 11.7):**
  * $x'' = (-1 \times 1.6) + (0 \times 11.7) = -1.6 + 0 = \mathbf{-1.6}$
  * $y'' = (0 \times 1.6) + (-1 \times 11.7) = 0 - 11.7 = \mathbf{-11.7}$
  * **Koordinat Bayangan:** $\mathbf{D''(-1.6, -11.7)}$

**2. Perhitungan Titik Kontrol Lengkung (Contoh Sisi A-E):**
* $C_1(9.7, 3.2) \to C_1''(-9.7, -3.2)$
* $C_2(11.0, 5.4) \to C_2''(-11.0, -5.4)$
* $C_3(10.3, 8.8) \to C_3''(-10.3, -8.8)$

---

#### C. Rotasi $270^\circ$ ($R[O, 270^\circ]$) $\longrightarrow (x, y) \to (y, -x)$ [Kuadran IV]
Matriks operator:
```text
  ┌  0   1 ┐
  └ -1   0 ┘
```
Aturan perkalian:
* $x''' = (0 \cdot x) + (1 \cdot y) = y$
* $y''' = (-1 \cdot x) + (0 \cdot y) = -x$

**1. Perhitungan Titik Sudut Utama:**
* **Titik A (6.0, 1.8):**
  * $x''' = (0 \times 6.0) + (1 \times 1.8) = 0 + 1.8 = \mathbf{1.8}$
  * $y''' = (-1 \times 6.0) + (0 \times 1.8) = -6.0 + 0 = \mathbf{-6.0}$
  * **Koordinat Bayangan:** $\mathbf{A'''(1.8, -6.0)}$
* **Titik E (10.4, 11.7):**
  * $x''' = (0 \times 10.4) + (1 \times 11.7) = 0 + 11.7 = \mathbf{11.7}$
  * $y''' = (-1 \times 10.4) + (0 \times 11.7) = -10.4 + 0 = \mathbf{-10.4}$
  * **Koordinat Bayangan:** $\mathbf{E'''(11.7, -10.4)}$
* **Titik C (8.5, 13.0):**
  * $x''' = (0 \times 8.5) + (1 \times 13.0) = 0 + 13.0 = \mathbf{13.0}$
  * $y''' = (-1 \times 8.5) + (0 \times 13.0) = -8.5 + 0 = \mathbf{-8.5}$
  * **Koordinat Bayangan:** $\mathbf{C'''(13.0, -8.5)}$
* **Titik B (3.5, 13.0):**
  * $x''' = (0 \times 3.5) + (1 \times 13.0) = 0 + 13.0 = \mathbf{13.0}$
  * $y''' = (-1 \times 3.5) + (0 \times 13.0) = -3.5 + 0 = \mathbf{-3.5}$
  * **Koordinat Bayangan:** $\mathbf{B'''(13.0, -3.5)}$
* **Titik D (1.6, 11.7):**
  * $x''' = (0 \times 1.6) + (1 \times 11.7) = 0 + 11.7 = \mathbf{11.7}$
  * $y''' = (-1 \times 1.6) + (0 \times 11.7) = -1.6 + 0 = \mathbf{-1.6}$
  * **Koordinat Bayangan:** $\mathbf{D'''(11.7, -1.6)}$

**2. Perhitungan Titik Kontrol Lengkung (Contoh Sisi A-E):**
* $C_1(9.7, 3.2) \to C_1'''(3.2, -9.7)$
* $C_2(11.0, 5.4) \to C_2'''(5.4, -11.0)$
* $C_3(10.3, 8.8) \to C_3'''(8.8, -10.3)$

---

### 3.5 Alur Visual Transformasi

```text
[ SEBELUM TRANSFORMASI ]
Posisi Awal 0° (Kuadran I)
Semua titik x > 0 dan y > 0
Perisai berdiri tegak normal
          │
          ▼
[ PROSES PERKALIAN MATRIKS ]
Terapkan Matriks Operator:
R[90°]  : (x, y) -> (-y, x)
R[180°] : (x, y) -> (-x, -y)
R[270°] : (x, y) -> (y, -x)
          │
          ▼
[ SESUDAH TRANSFORMASI ]
90°  -> Berputar ke Kuadran II (Perisai miring ke kiri)
180° -> Berputar ke Kuadran III (Perisai terbalik sempurna)
270° -> Berputar ke Kuadran IV (Perisai miring ke kanan)
Hasil: Ukuran dan bentuk lengkung tetap sempurna (Isometri)
```

---

## BAB IV — HASIL DAN ANALISIS

### 4.1 Tabel Komparasi Koordinat 4 Kuadran
Berikut adalah rangkuman seluruh koordinat titik sudut perisai lambang SMKN 9 Semarang pada keempat orientasi sudut:

| Label Titik | Posisi Awal $0^\circ$ [Kuadran I] | Rotasi $90^\circ$ [Kuadran II] | Rotasi $180^\circ$ [Kuadran III] | Rotasi $270^\circ$ [Kuadran IV] | Peran Anatomi Lambang |
| :---: | :---: | :---: | :---: | :---: | :--- |
| **A** | $(6.0, 1.8)$ | $(-1.8, 6.0)$ | $(-6.0, -1.8)$ | $(1.8, -6.0)$ | Ujung lancip bawah perisai |
| **E** | $(10.4, 11.7)$ | $(-11.7, 10.4)$ | $(-10.4, -11.7)$ | $(11.7, -10.4)$ | Sudut pinggang kanan luar |
| **C** | $(8.5, 13.0)$ | $(-13.0, 8.5)$ | $(-8.5, -13.0)$ | $(13.0, -8.5)$ | Sudut bahu kanan atas |
| **B** | $(3.5, 13.0)$ | $(-13.0, 3.5)$ | $(-3.5, -13.0)$ | $(13.0, -3.5)$ | Sudut bahu kiri atas |
| **D** | $(1.6, 11.7)$ | $(-11.7, 1.6)$ | $(-1.6, -11.7)$ | $(11.7, -1.6)$ | Sudut pinggang kiri luar |

---

### 4.2 Analisis Pola Koordinat pada Setiap Kuadran
Dari tabel di atas, kita dapat mengamati keteraturan matematis tanda nilai koordinat pada setiap kuadran Cartesius:
1. **Kuadran I (Posisi Awal $0^\circ$):** Koordinat bertanda $(+, +)$. Seluruh bagian perisai berada di atas sumbu $X$ positif dan sumbu $Y$ positif.
2. **Kuadran II (Rotasi $90^\circ$):** Koordinat bertanda $(-, +)$. Nilai $x$ menjadi bernilai negatif karena bayangan berpindah ke sebelah kiri sumbu vertikal $Y$.
3. **Kuadran III (Rotasi $180^\circ$):** Koordinat bertanda $(-, -)$. Seluruh titik berada di area kiri-bawah sumbu Cartesius.
4. **Kuadran IV (Rotasi $270^\circ$):** Koordinat bertanda $(+, -)$. Nilai $x$ kembali bernilai positif, namun nilai $y$ bernilai negatif karena berada di bawah sumbu horizontal $X$.

Perpindahan ini terjadi secara mulus dan konsisten, membuktikan bahwa aljabar matriks bekerja secara akurat tanpa ada satu titik pun yang menyimpang.

---

### 4.3 Pembuktian Matematis Sifat Isometri

#### 1. Pembuktian Kekekalan Panjang Sisi (Jarak Euclidean)
Apakah panjang sisi-sisi perisai berubah saat diputar? Mari kita hitung panjang ke-5 sisi poligon pada posisi awal ($0^\circ$) menggunakan rumus jarak $d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$:

* **Sisi 1: Ujung Bawah ke Pinggang Kanan (A ke E)**
  $$d(A, E) = \sqrt{(10.4 - 6.0)^2 + (11.7 - 1.8)^2} = \sqrt{(4.4)^2 + (9.9)^2} = \sqrt{19.36 + 98.01} = \sqrt{117.37} \approx \mathbf{10.834 \text{ satuan}}$$

* **Sisi 2: Pinggang Kanan ke Bahu Kanan (E ke C)**
  $$d(E, C) = \sqrt{(8.5 - 10.4)^2 + (13.0 - 11.7)^2} = \sqrt{(-1.9)^2 + (1.3)^2} = \sqrt{3.61 + 1.69} = \sqrt{5.30} \approx \mathbf{2.302 \text{ satuan}}$$

* **Sisi 3: Garis Mahkota Atas Datar (C ke B)**
  $$d(C, B) = \sqrt{(3.5 - 8.5)^2 + (13.0 - 13.0)^2} = \sqrt{(-5.0)^2 + (0)^2} = \sqrt{25.00} = \mathbf{5.000 \text{ satuan}}$$

* **Sisi 4: Bahu Kiri ke Pinggang Kiri (B ke D)**
  $$d(B, D) = \sqrt{(1.6 - 3.5)^2 + (11.7 - 13.0)^2} = \sqrt{(-1.9)^2 + (-1.3)^2} = \sqrt{3.61 + 1.69} = \sqrt{5.30} \approx \mathbf{2.302 \text{ satuan}}$$

* **Sisi 5: Pinggang Kiri ke Ujung Bawah (D ke A)**
  $$d(D, A) = \sqrt{(6.0 - 1.6)^2 + (1.8 - 11.7)^2} = \sqrt{(4.4)^2 + (-9.9)^2} = \sqrt{19.36 + 98.01} = \sqrt{117.37} \approx \mathbf{10.834 \text{ satuan}}$$

**Total Keliling Poligon Perisai Posisi Awal:**
$$K = 10.834 + 2.302 + 5.000 + 2.302 + 10.834 = \mathbf{31.272 \text{ satuan panjang}}$$

**Uji Banding pada Bayangan Rotasi $90^\circ$ (Kuadran II):**
Mari kita hitung panjang sisi bayangan $A'(-1.8, 6.0)$ ke $E'(-11.7, 10.4)$:
$$d(A', E') = \sqrt{(-11.7 - (-1.8))^2 + (10.4 - 6.0)^2} = \sqrt{(-9.9)^2 + (4.4)^2} = \sqrt{98.01 + 19.36} = \sqrt{117.37} \approx \mathbf{10.834 \text{ satuan}}$$

Serta sisi mahkota atas $C'(-13.0, 8.5)$ ke $B'(-13.0, 3.5)$:
$$d(C', B') = \sqrt{(-13.0 - (-13.0))^2 + (3.5 - 8.5)^2} = \sqrt{0 + (-5.0)^2} = \sqrt{25.00} = \mathbf{5.000 \text{ satuan}}$$

> **Kesimpulan Uji Jarak:**  
> Panjang setiap sisi dan keliling total bangun datar bernilai **persis sama (invarian)** di setiap kuadran. Hal ini membuktikan bahwa rotasi tidak merenggangkan atau menyusutkan sisi bangun.

---

#### 2. Pembuktian Kekekalan Luas (Shoelace Formula / Rumus Gauss)
Mari kita hitung luas daerah perisai segilima menggunakan metode perkalian tali sepatu Gauss.

Susunan titik melingkar: $A(6.0, 1.8) \to E(10.4, 11.7) \to C(8.5, 13.0) \to B(3.5, 13.0) \to D(1.6, 11.7) \to A(6.0, 1.8)$.

Tabel perkalian silang $(x_i \cdot y_{i+1}) - (x_{i+1} \cdot y_i)$:

| Pasangan Titik | Suku Perkalian Silang | Hasil Hitung |
| :---: | :---: | :---: |
| **A ke E** | $(6.0 \times 11.7) - (10.4 \times 1.8) = 70.20 - 18.72$ | $+51.48$ |
| **E ke C** | $(10.4 \times 13.0) - (8.5 \times 11.7) = 135.20 - 99.45$ | $+35.75$ |
| **C ke B** | $(8.5 \times 13.0) - (3.5 \times 13.0) = 110.50 - 45.50$ | $+65.00$ |
| **B ke D** | $(3.5 \times 11.7) - (1.6 \times 13.0) = 40.95 - 20.80$ | $+20.15$ |
| **D ke A** | $(1.6 \times 1.8) - (6.0 \times 11.7) = 2.88 - 70.20$ | $-67.32$ |
| **Jumlah Total $(\Sigma)$** | $51.48 + 35.75 + 65.00 + 20.15 - 67.32$ | $\mathbf{+105.06}$ |

Maka luas daerah perisai adalah:
$$\text{Luas} = \frac{1}{2} \times |105.06| = \mathbf{52.53 \text{ satuan luas}}$$

Dengan cara yang sama pada hasil rotasi $90^\circ$, $180^\circ$, dan $270^\circ$, hasil penjumlahan perkalian silang menghasilkan nilai mutlak yang tetap sebesar $105.06$, sehingga:
$$\text{Luas}_{0^\circ} = \text{Luas}_{90^\circ} = \text{Luas}_{180^\circ} = \text{Luas}_{270^\circ} = \mathbf{52.53 \text{ satuan luas}}$$

> **Kesimpulan Uji Luas:**  
> Luas poligon lambang sekolah terbukti **100% konstan dan tidak berubah**. Ini menjadi bukti otentik bahwa transformasi rotasi merupakan **transformasi isometri sejati**.

---

### 4.4 Analisis Perubahan Orientasi Visual Ikon Perisai
Selain analisis angka koordinat, kami mengamati orientasi visual ikon perisai pada setiap sudut perputaran:
* **Posisi Awal ($0^\circ$ — Kuadran I):** Perisai berdiri tegak (*upright normal*). Ujung lancip mengarah ke bawah, mahkota menghadap ke atas. Ini merupakan orientasi resmi lambang sekolah.
* **Rotasi $90^\circ$ (Kuadran II):** Perisai berputar seperempat lingkaran berlawanan arah jarum jam. Mahkota atas menghadap ke kiri (sumbu $-X$), dan ujung lancip menghadap ke kanan (sumbu $+Y$).
* **Rotasi $180^\circ$ (Kuadran III):** Perisai terbalik sempurna (*upside down*). Mahkota atas menghadap ke bawah (sumbu $-Y$), dan ujung lancip mengarah ke atas.
* **Rotasi $270^\circ$ (Kuadran IV):** Perisai berputar tiga perempat lingkaran (setara dengan putaran $90^\circ$ searah jarum jam). Mahkota atas menghadap ke kanan (sumbu $+X$), dan ujung lancip menghadap ke kiri.

---

## BAB V — KESIMPULAN DAN RELEVANSI KEJURUAN (PPLG)

### 5.1 Kesimpulan
Berdasarkan seluruh rangkaian proses perancangan, perhitungan matriks, pembuktian analitis, dan visualisasi digital yang telah kami laksanakan, dapat disimpulkan bahwa:
1. **Konsep Matriks Rotasi:** Pemindahan koordinat objek dua dimensi terhadap titik pusat $O(0,0)$ dapat dirumuskan secara pasti menggunakan matriks trigonometri. Tiga rumus praktis yang terbukti akurat adalah:
   - Rotasi $+90^\circ$: $(x, y) \to (-y, x)$
   - Rotasi $+180^\circ$: $(x, y) \to (-x, -y)$
   - Rotasi $+270^\circ$: $(x, y) \to (y, -x)$
2. **Keterpaduan dengan Garis Lengkung (Bézier):** Penambahan titik kontrol lengkungan pada perisai lambang SMKN 9 berhasil menjaga keindahan lekukan logo. Karena titik kontrol ikut berotasi dengan matriks yang sama, kelengkungan logo tidak mengalami distorsi atau patah.
3. **Pembuktian Isometri:**
   - **Kekekalan Keliling:** Panjang kelima sisi dan keliling total perisai tetap stabil pada angka **$31.272$ satuan panjang**.
   - **Kekekalan Luas:** Luas poligon perisai di keempat kuadran terbukti tetap konstan pada nilai **$52.53$ satuan luas**.
   - Dengan demikian, terbukti secara matematis bahwa rotasi merupakan transformasi **isometri**.
4. **Keberhasilan Produk:** Kelompok 4 berhasil mengintegrasikan teori matematika kelas XII ke dalam produk nyata berupa aplikasi visualizer berbasis web dan infografis resolusi tinggi.

---

### 5.2 Relevansi dengan Dunia Rekayasa Perangkat Lunak (PPLG)
Proyek ini membuktikan secara nyata bagaimana ilmu matematika bekerja di dalam industri perangkat lunak dan gim:

#### 1. Implementasi CSS Transform 2D pada Desain Web & Aplikasi Mobile
Saat seorang *frontend web developer* membuat tombol atau logo berputar menggunakan kode CSS:
```css
.logo-smkn9 {
  transform-origin: 0px 0px; /* Titik pusat putaran O(0,0) */
  transform: rotate(90deg);   /* Komputer mengeksekusi matriks [0, -1, 1, 0] */
  transition: transform 0.4s ease-in-out;
}
```
Di balik layar, peramban web (*browser engine*) sedang menjalankan perkalian matriks rotasi Cartesius yang kami pelajari di bab ini untuk setiap piksel di layar ponsel atau monitor komputer.

#### 2. Implementasi Game Engine 2D & HTML5 Canvas API
Dalam pembuatan gim 2D (seperti menggerakkan pesawat tempur atau karakter gim agar berputar ke arah kursor mouse), pengembang gim menuliskan kode rotasi pada loop perenderan grafis (*render loop*):
```javascript
// Memutar karakter gim sebesar sudut rotasi di titik pusat kanvas
context.save();
context.translate(pusatX, pusatY);
context.rotate((sudut * Math.PI) / 180); // Konversi derajat ke radian
context.drawImage(gambarLogoSekolah, -lebar / 2, -tinggi / 2);
context.restore();
```

#### 3. Format Vektor SVG (Scalable Vector Graphics)
Aplikasi modern saat ini meninggalkan gambar bitmap berat dan beralih ke format SVG. Karena lambang sekolah kami dimodelkan ke dalam koordinat Cartesius dan kurva Bézier, berkas ikon yang dihasilkan berukuran sangat kecil (di bawah 10 KB), dapat diunduh tanpa buram, dan mudah dianimasikan.

---

## LAMPIRAN DAN TAUTAN PROYEK

### 🌐 Akses Produk Aplikasi Web Interaktif
Untuk mempermudah Bapak/Ibu guru penilai dan rekan-rekan siswa dalam menguji secara langsung simulasi rotasi kartesius, kami menyediakan tautan ringkas (*Short URL*) dan kode QR (*QR Code*) yang dapat dipindai secara instan:

* **Tautan Ringkas (Short URL):** [https://tinyurl.com/rotasi-smkn9](https://tinyurl.com/rotasi-smkn9)  
  *(Alternatif cadangan: [https://da.gd/V0UF](https://da.gd/V0UF))*
* **Tautan Lengkap GitHub Pages:** [https://sabilmurti.github.io/tugas-pages/matematika-transformasi-geometri-kelompok4/](https://sabilmurti.github.io/tugas-pages/matematika-transformasi-geometri-kelompok4/)
* **Pindai Kode QR (Scan Me):**

![QR Code Aplikasi Web](file:///home/murtix/tugas/matematika-transformasi-geometri-kelompok4/qrcode_web_matematika.png)

*(Arahkan kamera ponsel cerdas Anda ke gambar kode QR di atas untuk langsung membuka aplikasi web di peramban tanpa perlu mengetik alamat URL).*

---

### 📁 Daftar Berkas Pendukung Proyek
1. **Repositori Kode Sumber Proyek:**  
   [https://github.com/SabilMurti/tugas](https://github.com/SabilMurti/tugas)
2. **Aset Infografis Teknis 4 Kuadran:**  
   [`infografis_rotasi_ikon.svg`](./infografis_rotasi_ikon.svg)
3. **Dokumen Microsoft Word Siap Cetak:**  
   [`LAPORAN_PROYEK_KELOMPOK_4.docx`](./LAPORAN_PROYEK_KELOMPOK_4.docx)
4. **Naskah Presentasi 7–10 Menit:**  
   [`SLIDE_DAN_NASKAH_PRESENTASI.md`](./SLIDE_DAN_NASKAH_PRESENTASI.md)
5. **Citra Lambang Sekolah Asli:**  
   [`SMK9.png`](./SMK9.png) / [`logo_smkn9_web.png`](./logo_smkn9_web.png)


# 📐 PROYEK TRANSFORMASI GEOMETRI: ROTASI 2D IKON LAMBANG SMKN 9 SEMARANG
### Desain Vektor Poligon 14 Titik, Integrasi Citra PNG Sekolah, Analisis Matematis Matriks, dan Implementasi PPLG

[![Kurikulum](https://img.shields.io/badge/Kurikulum-Merdeka%20Fase%20F-blue?style=flat-square)](#)
[![Tingkat](https://img.shields.io/badge/Tingkat-SMK%20Kelas%20XII%20PPLG-green?style=flat-square)](#)
[![Mata Pelajaran](https://img.shields.io/badge/Mata%20Pelajaran-Matematika-orange?style=flat-square)](#)
[![Instansi](https://img.shields.io/badge/Instansi-SMKN%209%20Semarang-purple?style=flat-square)](#)
[![Status](https://img.shields.io/badge/Status-Lengkap%20%26%20Terverifikasi-brightgreen?style=flat-square)](#)

---

## 📌 Identitas Proyek
* **Judul Proyek:** Desain dan Analisis Transformasi Geometri Rotasi 2D pada Ikon Aplikasi Lambang SMK Negeri 9 Semarang Berbasis Koordinat Cartesius
* **Kelompok:** Kelompok 4
* **Kelas:** XII PPLG (Pengembangan Perangkat Lunak dan Gim)
* **Sekolah:** SMK Negeri 9 Semarang
* **Tahun Pelajaran:** 2026/2027

---

## 📂 Daftar Berkas dalam Direktori

| Berkas | Jenis / Format | Deskripsi & Kegunaan |
| :--- | :---: | :--- |
| **[`index.html`](./index.html)** | Web Interaktif / SPA | Aplikasi visualizer interaktif berbasis browser, menampilkan kanvas Cartesius dinamis dengan layer gambar PNG asli logo sekolah, overlay poligon 14 titik, slider opasitas, tabel koordinat live, dan simulasi rotasi ($0^\circ, 90^\circ, 180^\circ, 270^\circ$). |
| **[`infografis_rotasi_ikon.svg`](./infografis_rotasi_ikon.svg)** | Vektor Grafis (SVG) | Aset infografis teknis resolusi tinggi yang memetakan perputaran 14 titik poligon perisai lambang SMKN 9 dan citra PNG sekolah di 4 kuadran Cartesius. |
| **[`logo_smkn9_web.png`](./logo_smkn9_web.png)** / **[`SMK9.png`](./SMK9.png)** | Citra Raster (PNG) | Aset grafis resmi logo sekolah SMKN 9 Semarang berlatar transparan yang diintegrasikan ke kanvas Cartesius. |
| **[`LAPORAN_PROYEK_KELOMPOK_4.md`](./LAPORAN_PROYEK_KELOMPOK_4.md)** | Markdown Dokumen | Naskah laporan akademik lengkap: Bab I Pendahuluan, Bab II Landasan Teori Matriks, Bab III Proses Pembuatan & Koordinat 14 Titik, Bab IV Hasil Analisis & Pembuktian Isometri, dan Bab V Penutup. |
| **[`LAPORAN_PROYEK_KELOMPOK_4.docx`](./LAPORAN_PROYEK_KELOMPOK_4.docx)** | Microsoft Word (DOCX) | Dokumen laporan format cetak/Word resmi siap kumpul. |
| **[`SLIDE_DAN_NASKAH_PRESENTASI.md`](./SLIDE_DAN_NASKAH_PRESENTASI.md)** | Slide & Script | Alur waktu presentasi (7–10 menit), panduan pembagian peran 4 presenter, dan naskah bicara kata demi kata (*verbatim script*). |
| **[`PROYEK KELOMPOK TRANSFORMASI GEOMETRI.pdf`](./PROYEK%20KELOMPOK%20TRANSFORMASI%20GEOMETRI.pdf)** | Dokumen PDF | Lembar kerja panduan proyek dan instrumen penilaian/rubrik resmi dari guru matematika. |

---

## 🧮 Landasan Matematis: Rumus Rotasi Terhadap Titik Pusat $O(0,0)$

Perkalian matriks transformasi rotasi dua dimensi sebesar sudut $\alpha$ (berlawanan arah jarum jam) terhadap pusat koordinat $O(0,0)$:

$$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$$

### Aturan Pemetaan Khusus Kuadran:
1. **Rotasi $90^\circ$ ($R_{90^\circ}$):**
   $$(x, y) \xrightarrow{R_{90^\circ}} (-y, x)$$
2. **Rotasi $180^\circ$ ($R_{180^\circ}$):**
   $$(x, y) \xrightarrow{R_{180^\circ}} (-x, -y)$$
3. **Rotasi $270^\circ$ ($R_{270^\circ}$):**
   $$(x, y) \xrightarrow{R_{270^\circ}} (y, -x)$$

---

## 📊 Matriks 14 Titik Koordinat Poligon Lambang SMKN 9 Semarang

| Titik | Posisi Awal $0^\circ$ $(x, y)$ | Bayangan $90^\circ$ $(-y, x)$ | Bayangan $180^\circ$ $(-x, -y)$ | Bayangan $270^\circ$ $(y, -x)$ | Deskripsi Anatomi Lambang |
| :---: | :---: | :---: | :---: | :---: | :--- |
| **A** | $(6, 1)$ | $(-1, 6)$ | $(-6, -1)$ | $(1, -6)$ | Ujung lancip bawah perisai |
| **B** | $(9, 3)$ | $(-3, 9)$ | $(-9, -3)$ | $(3, -9)$ | Sudut lengkung bawah kanan |
| **C** | $(10, 5)$ | $(-5, 10)$ | $(-10, -5)$ | $(5, -10)$ | Sisi pinggang kanan perisai |
| **D** | $(10, 8)$ | $(-8, 10)$ | $(-10, -8)$ | $(8, -10)$ | Sisi bahu kanan atas |
| **E** | $(9, 9)$ | $(-9, 9)$ | $(-9, -9)$ | $(9, -9)$ | Lekukan leher kanan dalam |
| **F** | $(10, 11)$ | $(-11, 10)$ | $(-10, -11)$ | $(11, -10)$ | Puncak sudut telinga kanan atas |
| **G** | $(8, 10)$ | $(-10, 8)$ | $(-8, -10)$ | $(10, -8)$ | Lembah lengkung kurva atas kanan |
| **H** | $(6, 12)$ | $(-12, 6)$ | $(-6, -12)$ | $(12, -6)$ | Puncak kubah mahkota tengah atas |
| **I** | $(4, 10)$ | $(-10, 4)$ | $(-4, -10)$ | $(10, -4)$ | Lembah lengkung kurva atas kiri |
| **J** | $(2, 11)$ | $(-11, 2)$ | $(-2, -11)$ | $(11, -2)$ | Puncak sudut telinga kiri atas |
| **K** | $(3, 9)$ | $(-9, 3)$ | $(-3, -9)$ | $(9, -3)$ | Lekukan leher kiri dalam |
| **L** | $(2, 8)$ | $(-8, 2)$ | $(-2, -8)$ | $(8, -2)$ | Sisi bahu kiri atas |
| **M** | $(2, 5)$ | $(-5, 2)$ | $(-2, -5)$ | $(5, -2)$ | Sisi pinggang kiri perisai |
| **N** | $(3, 3)$ | $(-3, 3)$ | $(-3, -3)$ | $(3, -3)$ | Sudut lengkung bawah kiri |

---

## 💡 Pembuktian Sifat Isometri
Rotasi merupakan transformasi **isometri** (mempertahankan bentuk dan ukuran geometris bangun):
1. **Kekekalan Panjang Sisi:** Panjang segmen sisi $C-D$ dan $L-M$ tetap tepat $3$ satuan panjang, dan total keliling poligon perisai tetap konstan $35.11$ satuan panjang di seluruh posisi putaran.
2. **Kekekalan Luas Bangun:** Luas total poligon perisai lambang SMKN 9 bernilai tetap **63 satuan luas** di keempat kuadran (dihitung menggunakan rumus determinan tali sepatu Gauss / Shoelace Formula).

---

## 💻 Integrasi Rekayasa Perangkat Lunak (PPLG)
1. **CSS Transform 2D:**
   ```css
   .icon-smkn9 {
     transform-origin: 0 0;
     transform: rotate(90deg);
     transition: transform 0.4s ease;
   }
   ```
2. **HTML5 Canvas 2D API:**
   ```javascript
   ctx.save();
   ctx.translate(originX, originY);
   ctx.rotate((angle * Math.PI) / 180);
   ctx.drawImage(logoImage, imgX, imgY, imgW, imgH);
   ctx.stroke(shieldPolygonPath);
   ctx.restore();
   ```

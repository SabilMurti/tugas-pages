# PANDUAN DAN NASKAH PRESENTASI KELOMPOK 4
## TEMA: ROTASI IKON APLIKASI LAMBANG SMKN 9 SEMARANG
**Kelas:** XII PPLG — SMK Negeri 9 Semarang  
**Durasi Total:** 7 – 10 Menit (Sesuai Ketentuan Resmi PDF Halaman 6)  

---

### RINGKASAN STRUKTUR WAKTU PRESENTASI (7–10 MENIT)
| Bagian | Alokasi Waktu | Pembicara Disarankan | Topik Utama |
| :--- | :---: | :---: | :--- |
| **1. Pembukaan** | 30 detik | Moderator / Anggota 1 | Salam pembuka, perkenalan anggota kelompok 4, judul proyek |
| **2. Pengenalan Proyek** | 1 menit | Anggota 1 | Latar belakang ikon lambang SMKN 9, kurva Bézier, korelasi PPLG |
| **3. Konsep Matematika** | 2 menit | Anggota 2 | Rumus matriks rotasi $R_\alpha$, trigonometri, aturan pemetaan kuadran terhadap pusat $O(0,0)$ |
| **4. Demonstrasi Produk** | 2–3 menit | Anggota 3 | Tampilan web interaktif, titik sudut ($A, E, C, B, D$), kanvas Cartesius dinamis, kurva Bézier |
| **5. Analisis Hasil** | 1 menit | Anggota 4 | Bukti sifat isometri (keliling = 31.27, luas = 52.53) & orientasi perisai di 4 kuadran |
| **6. Kesimpulan** | 30 detik | Anggota 4 / Moderator | Ringkasan matematis & penerapannya dalam industri perangkat lunak PPLG |
| **7. Tanya Jawab (Q&A)** | 2 menit | Seluruh Tim | Antisipasi jawaban ilmiah atas pertanyaan kritis dari guru & rekan sekelas |

---

## NASKAH LENGKAP PRESENTASI (VERBATIM SCRIPT)

### BAGIAN 1: PEMBUKAAN (30 Detik)
> **Slide 1: Cover Judul Proyek & Identitas Kelompok 4**

**Ujaran (Presenter 1):**
> *"Assalamu'alaikum warahmatullahi wabarakatuh, selamat pagi kepada Bapak/Ibu guru matematika dan rekan-rekan kelas XII PPLG yang kami banggakan.*  
> *Kami dari **Kelompok 4** yang beranggotakan [Sebutkan nama anggota 1, 2, 3, 4]. Pada hari ini, kami dengan bangga mempresentasikan hasil proyek transformasi geometri kami yang berjudul:*  
> ***'Desain dan Analisis Transformasi Geometri Rotasi 2D pada Ikon Aplikasi Lambang SMK Negeri 9 Semarang Berbasis Koordinat Cartesius dan Kurva Bézier'**.*  
> *Mari kita mulai dari pengenalan ide dasar proyek ini."*

---

### BAGIAN 2: PENGENALAN PROYEK (1 Menit)
> **Slide 2: Latar Belakang Desain Ikon Lambang SMKN 9 & Korelasi PPLG**

**Ujaran (Presenter 1):**
> *"Sebagai calon software engineer di bidang PPLG, kita mengetahui bahwa setiap elemen grafis digital—mulai dari logo aplikasi, tombol UI, hingga sprite gim—disusun oleh pemodelan matematis berbasis vektor.*  
> *Untuk proyek transformasi rotasi ini, kelompok kami mengangkat identitas kebanggaan sekolah kita, yaitu **Lambang Resmi SMK Negeri 9 Semarang**.*  
> *Secara geometris, lambang sekolah kita memiliki bingkai utama berupa **Perisai Segilima Berlekuk (Heraldic Crest Shield)**.*  
> *Siluet perisai ini kami modelkan ke dalam bidang koordinat Cartesius dengan 5 titik sudut utama ($A, E, C, B, D$) yang dipadukan dengan kurva parametrik Bézier multi-titik agar kelengkungan perisai tetap aerodinamis dan presisi.*  
> *Pusat rotasi yang kami gunakan adalah titik origin $O(0,0)$ dengan arah perputaran standar berlawanan arah jarum jam sebesar $90^\circ$, $180^\circ$, dan $270^\circ$."*

---

### BAGIAN 3: KONSEP MATEMATIKA (2 Menit)
> **Slide 3: Landasan Teori Matriks & Rumus Pemetaan Titik**

**Ujaran (Presenter 2):**
> *"Sekarang mari kita tinjau dasar matematisnya.*  
> *Perpindahan titik koordinat $(x, y)$ saat dirotasi sebesar sudut $\alpha$ terhadap pusat $O(0,0)$ dihitung melalui perkalian matriks trigonometri 2D:*  
> $$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$$  
> *Dari persamaan matriks umum ini, kita memperoleh tiga aturan pemetaan kuadran:*  
> 
> *1. **Rotasi $+90^\circ$ (Kuadran I ke Kuadran II):**  
> Karena $\cos 90^\circ = 0$ dan $\sin 90^\circ = 1$, matriks menghasilkan aturan: **$(x, y) \to (-y, x)$**.*  
> 
> *2. **Rotasi $+180^\circ$ (Kuadran I ke Kuadran III):**  
> Karena $\cos 180^\circ = -1$ dan $\sin 180^\circ = 0$, matriks menghasilkan aturan: **$(x, y) \to (-x, -y)$**.*  
> 
> *3. **Rotasi $+270^\circ$ (Kuadran I ke Kuadran IV):**  
> Karena $\cos 270^\circ = 0$ dan $\sin 270^\circ = -1$, matriks menghasilkan aturan: **$(x, y) \to (y, -x)$**.*  
> 
> *Yang menarik, aturan pemetaan matriks ini tidak hanya berlaku pada titik sudut poligon, melainkan juga berlaku secara invarian pada setiap titik kontrol kurva Bézier ($C_1, C_2, C_3$), sehingga bentuk lengkung perisai sekolah tetap mulus sempurna di setiap posisi putaran."*

---

### BAGIAN 4: DEMONSTRASI PRODUK (2–3 Menit)
> **Slide 4: Demonstrasi Aplikasi Web Interaktif & Kanvas Cartesius**

**Ujaran (Presenter 3):**
> *(Arahkan perhatian ke aplikasi web yang ditampilkan di layar proyektor)*  
> *"Untuk membuktikan perhitungan ini, kelompok kami mengembangkan **aplikasi web visualizer interaktif** yang dibangun menggunakan React, TypeScript, Tailwind CSS, dan HTML5 Canvas API.*  
> *Bisa kita saksikan pada kanvas Cartesius:*  
> *Perisai lambang SMKN 9 pada posisi awal $0^\circ$ berada di Kuadran I:*  
> * Titik paling bawah adalah ujung lancip perisai di **$A(6, 1.8)$**.  
> * Titik pinggang kanan di **$E(10.4, 11.7)$** dan pinggang kiri di **$D(1.6, 11.7)$**.  
> * Bahu atas dihubungkan oleh garis horizontal datar dari **$B(3.5, 13)$** ke **$C(8.5, 13)$**.  
> * Sisi sayap bawah diperhalus dengan 3 titik kontrol kurva Bézier $C_1, C_2, C_3$.*  
> 
> *Mari kita perhatikan saat dirotasi $90^\circ$:*  
> * Titik lancip $A(6, 1.8)$ berpindah tepat ke $A'(-1.8, 6.0)$ di Kuadran II.  
> * Sisi datar $B-C$ yang tadinya horizontal kini berputar menjadi vertikal di $x = -13$.*  
> 
> *Pada rotasi $180^\circ$:*  
> * Lambang terbalik sempurna ke Kuadran III, titik A berpindah ke $A''(-6.0, -1.8)$.*  
> 
> *Dan pada rotasi $270^\circ$:*  
> * Lambang berpindah ke Kuadran IV, titik A berada di $A'''(1.8, -6.0)$.*  
> 
> *Aplikasi kami juga dilengkapi fitur drag-and-drop titik secara real-time, penyalinan dan penempelan format Bézier langsung ke clipboard, serta dukungan ekspor infografis SVG beresolusi tinggi.*  
> *Bapak/Ibu guru dan teman-teman juga bisa langsung mencoba aplikasi ini melalui tautan singkat **tinyurl.com/rotasi-smkn9** atau memindai QR Code yang kami tampilkan di pojok slide."*

---

### BAGIAN 5: ANALISIS HASIL (1 Menit)
> **Slide 5: Analisis Karakteristik Geometri & Pembuktian Sifat Isometri**

**Ujaran (Presenter 4):**
> *"Dari hasil transformasi ini, kelompok kami melakukan verifikasi matematis yang membuktikan sifat **Isometri (Kekekalan Ukuran)**:*  
> 
> *Pertama, **Kekekalan Panjang Sisi (Jarak Euclidean):**  
> Kami menghitung panjang ke-5 sisi perisai. Sisi sayap $A-E$ dan $D-A$ bernilai tepat **10.834 satuan**, sisi bahu bernilai **2.302 satuan**, dan sisi atas bernilai tepat **5.000 satuan**. Keliling total poligon perisai konstan bernilai **31.272 satuan panjang** di seluruh sudut rotasi.*  
> 
> *Kedua, **Kekekalan Luas Bangun (Shoelace Formula):**  
> Dihitung menggunakan rumus determinan tali sepatu Gauss, luas total poligon perisai SMKN 9 pada posisi $0^\circ$, $90^\circ$, $180^\circ$, maupun $270^\circ$ bernilai tepat **52.53 satuan luas**. Tidak ada pemuaian, penyusutan, maupun distorsi bentuk.*  
> 
> *Ketiga, **Morfologi Orientasi:**  
> Pada $0^\circ$ perisai tegak normal, pada $90^\circ$ perisai rebah ke kiri, pada $180^\circ$ terbalik ke bawah, dan pada $270^\circ$ rebah ke kanan."*

---

### BAGIAN 6: KESIMPULAN (30 Detik)
> **Slide 6: Kesimpulan & Relevansi Industri Perangkat Lunak (PPLG)**

**Ujaran (Presenter 4 / Moderator):**
> *"Sebagai kesimpulan:*  
> *1. Rotasi 2D terhadap pusat $O(0,0)$ mematuhi kaidah pemetaan aljabar matriks yang eksak dan terbukti merupakan transformasi isometri sejati.*  
> *2. Dalam industri rekayasa perangkat lunak (PPLG), rumus matematika inilah yang dieksekusi secara nyata oleh GPU peramban web pada properti **CSS `transform: rotate()`**, mesin perenderan **HTML5 Canvas API**, serta optimasi aset vektor **SVG Path**.*  
> *Pemahaman matematika ini membuktikan bahwa rekayasa software tingkat lanjut selalu berakar dari logika matematika yang kuat.*  
> *Sekian presentasi dari Kelompok 4. Terima kasih atas perhatian Bapak/Ibu guru dan rekan-rekan sekalian. Wassalamu'alaikum warahmatullahi wabarakatuh."*

---

### BAGIAN 7: SESI TANYA JAWAB (Q&A) (2 Menit)

#### Pertanyaan 1: Mengapa pusat rotasi dipilih di titik $O(0,0)$ dan bukan di titik tengah perisai?
> **Jawaban:**  
> *"Pusat rotasi di titik $O(0,0)$ dipilih karena sesuai dengan instruksi kurikulum tugas utama yang mengkaji pemetaan titik antar-kuadran I, II, III, dan IV secara fundamental. Jika dirotasikan pada titik berat atau tengah perisai $(6, 7.4)$, bangun hanya akan berputar di tempat pada Kuadran I tanpa berpindah kuadran. Namun rumus matriks rotasi terhadap titik sebarang $P(a,b)$ tetap kami sediakan di dalam aplikasi web kami melalui translasi ke origin, rotasi, lalu translasi balik."*

#### Pertanyaan 2: Bagaimana memastikan kurva lengkung Bézier tidak rusak atau gepeng saat dirotasi?
> **Jawaban:**  
> *"Secara matematis, kurva Bézier memiliki sifat yang disebut **Affine Invariance (Kekekalan Transformasi Affine)**. Artinya, untuk merotasikan sebuah kurva Bézier, kita cukup merotasikan titik-titik kontrolnya ($C_1, C_2, C_3$) menggunakan matriks rotasi yang sama persis dengan titik sudutnya. Titik-titik pada lengkungan yang dihasilkan algoritma de Casteljau akan otomatis berputar mulus tanpa distorsi apa pun."*

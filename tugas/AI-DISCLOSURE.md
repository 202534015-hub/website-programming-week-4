# AI DISCLOSURE — Tugas 4 Layout Fleksibel

## 1. Penggunaan AI

Dalam pengerjaan Tugas 4 — Layout Fleksibel, saya menggunakan AI sebagai alat bantu untuk memahami materi, mengevaluasi kode, menemukan kemungkinan masalah layout, dan membantu menyusun dokumentasi.

AI digunakan sebagai pendamping dalam proses belajar dan bukan sebagai pengganti pemahaman atau pengerjaan mandiri.

Kode yang digunakan tetap diperiksa, diuji, dan disesuaikan kembali dengan kebutuhan tugas.

---

## 2. Tujuan Penggunaan AI

AI digunakan untuk membantu:

- Memahami konsep Flexbox.
- Memahami penggunaan flex, flex-basis, flex-wrap, dan gap.
- Memahami penggunaan min-width: 0 pada flex item.
- Memahami penggunaan position: relative dan position: absolute.
- Mengevaluasi kemungkinan horizontal overflow.
- Mengevaluasi responsive reflow.
- Mengevaluasi source order.
- Membantu menyusun dokumentasi hasil pengujian.
- Membantu mengidentifikasi bagian kode yang perlu diperbaiki.

---

## 3. Contoh Prompt yang Digunakan

Beberapa contoh prompt yang digunakan selama pengerjaan:

> "Bantu saya mengerjakan Tugas 4 Layout Fleksibel sesuai instruksi dosen."

> "Cek apakah CSS ini sudah menggunakan Flexbox dengan benar."

> "Apakah penggunaan flex-basis dan min-width: 0 pada layout ini sudah sesuai?"

> "Cek apakah ada kemungkinan horizontal overflow pada CSS ini."

> "Kalau ada yang perlu diganti pada file CSS, langsung buatkan versi final keseluruhannya."

> "Bantu membuat EVIDENCE.md dan AI-DISCLOSURE.md sesuai requirement tugas."

Prompt digunakan untuk meminta penjelasan, evaluasi, dan saran perbaikan terhadap kode yang sedang dikerjakan.

---

## 4. Saran AI yang Digunakan

### 4.1 Flexbox pada Navigasi

Navigasi menggunakan Flexbox dan flex-wrap.

Implementasi yang digunakan:

    .nav-list {
      display: flex;
      flex-wrap: wrap;
      gap: var(--space-1);
    }

Penggunaan flex-wrap: wrap memungkinkan link navigasi berpindah ke baris berikutnya ketika ruang horizontal tidak mencukupi.

### 4.2 Flexbox pada Main dan Aside

Layout utama menggunakan Flexbox.

Implementasi yang digunakan:

    .page-layout {
      width: min(100% - 2rem, 70rem);
      margin-inline: auto;
      display: flex;
      flex-wrap: wrap;
      gap: var(--space-3);
      align-items: flex-start;
    }

Main menggunakan ukuran fleksibel:

    .page-layout > main {
      flex: 1 1 36rem;
      min-width: 0;
    }

Aside juga menggunakan ukuran fleksibel:

    .page-layout > aside {
      flex: 1 1 16rem;
      min-width: 0;
    }

Dengan pendekatan tersebut, main dan aside dapat berada berdampingan ketika ruang mencukupi dan dapat melakukan reflow ketika viewport menjadi sempit.

### 4.3 Flexbox pada Card

Daftar card menggunakan Flexbox.

Implementasi yang digunakan:

    .card-list {
      display: flex;
      flex-wrap: wrap;
      gap: var(--space-2);
    }

Setiap card menggunakan ukuran fleksibel:

    .card-list > .card {
      flex: 1 1 16rem;
      min-width: 0;
    }

Dengan demikian, card dapat menyesuaikan ruang yang tersedia tanpa menggunakan fixed width untuk layout card.

### 4.4 Pencegahan Horizontal Overflow

AI membantu mengidentifikasi pentingnya min-width: 0 pada flex item.

Implementasi yang digunakan:

    .page-layout > main {
      flex: 1 1 36rem;
      min-width: 0;
    }

    .page-layout > aside {
      flex: 1 1 16rem;
      min-width: 0;
    }

    .card-list > .card {
      flex: 1 1 16rem;
      min-width: 0;
    }

    .card {
      min-width: 0;
      overflow: hidden;
    }

Selain itu, media dibuat responsif dengan max-width: 100% dan height: auto.

Teks juga diberikan aturan overflow-wrap: anywhere untuk membantu mencegah teks panjang menyebabkan overflow horizontal.

### 4.5 Badge dengan Positioning

Badge pada card unggulan menggunakan position: relative dan position: absolute.

Card unggulan menggunakan:

    .card--featured {
      position: relative;
      padding-block-start: 3rem;
    }

Badge menggunakan:

    .badge {
      position: absolute;
      inset-block-start: 0.75rem;
      inset-inline-end: 0.75rem;
      padding: 0.25rem 0.5rem;
      color: #ffffff;
      background: var(--color-primary);
      border-radius: var(--radius);
    }

position: relative pada card digunakan sebagai acuan posisi bagi badge yang menggunakan position: absolute.

Padding bagian atas card juga diperbesar agar badge tidak menutupi judul.

---

## 5. Modifikasi yang Saya Lakukan

Saran dari AI tidak digunakan secara langsung tanpa pemeriksaan.

Saya melakukan penyesuaian terhadap kode, antara lain:

- Menghapus width: 100% dari .card.
- Menghapus margin-block-end dari .card.
- Menggunakan flex: 1 1 16rem pada card.
- Menambahkan min-width: 0 pada flex item.
- Mempertahankan flex-wrap.
- Mempertahankan penggunaan gap.
- Memastikan main tidak menggunakan fixed width.
- Memastikan main dan aside dapat berubah menjadi satu kolom pada viewport sempit.
- Memastikan gambar tidak melebihi container.
- Mempertahankan source order HTML.
- Tidak menggunakan CSS order untuk mengubah urutan visual.
- Tidak menggunakan float sebagai metode layout utama.
- Mempertahankan indikator keyboard focus.
- Menyesuaikan padding card unggulan agar badge tidak menutupi judul.

---

## 6. Pengujian yang Dilakukan

Kode yang telah diperbaiki diuji menggunakan browser dan DevTools.

Pengujian yang dilakukan meliputi:

- Wide viewport.
- Viewport sekitar 320 CSS px.
- Flexbox overlay pada DevTools.
- Zoom browser 200%.
- Responsive reflow.
- Pemeriksaan horizontal overflow.

Hasil pengujian menunjukkan bahwa:

- Main dan aside dapat berada berdampingan pada viewport yang cukup lebar.
- Main dan aside dapat berubah menjadi satu kolom pada viewport sempit.
- Card dapat melakukan wrapping.
- Navigasi dapat melakukan wrapping.
- Badge tetap berada pada posisi yang sesuai.
- Gambar tetap berada di dalam container.
- Source order tetap mengikuti struktur HTML.

---

## 7. Pengujian yang Masih Dilengkapi

Beberapa pemeriksaan berikut merupakan bagian dari proses verifikasi akhir:

- Pengujian keyboard menggunakan tombol Tab.
- Pemeriksaan Console DevTools.
- Pemeriksaan Network DevTools.
- Pemeriksaan HTML menggunakan Nu HTML Checker.
- Dokumentasi final hasil git log --oneline.

Bukti untuk pemeriksaan tersebut akan ditambahkan setelah seluruh pengujian selesai dilakukan.

---

## 8. Pembelajaran yang Diperoleh

Melalui proses pengerjaan ini, saya memahami bahwa:

1. Flexbox dapat digunakan untuk membuat layout yang menyesuaikan ruang yang tersedia.
2. flex-wrap memungkinkan flex item berpindah ke baris berikutnya.
3. gap digunakan untuk mengatur jarak antar-flex item.
4. flex-basis dapat digunakan sebagai ukuran awal flex item.
5. min-width: 0 dapat membantu flex item mengecil ketika ruang tersedia terbatas.
6. position: relative dapat digunakan sebagai acuan posisi untuk elemen yang menggunakan position: absolute.
7. Source order penting untuk menjaga struktur dokumen dan urutan fokus keyboard.
8. Responsive layout harus diuji pada viewport lebar dan sempit.
9. Layout yang terlihat baik pada layar lebar belum tentu aman pada layar sempit.
10. Pengujian diperlukan untuk menemukan masalah overflow dan alignment.
11. Perubahan CSS harus diuji kembali setelah dilakukan agar hasil akhirnya sesuai dengan kebutuhan tugas.

---

## 9. Peran AI

AI digunakan sebagai:

- Pendamping belajar.
- Pemberi penjelasan konsep.
- Reviewer kode.
- Pemberi saran perbaikan.
- Pembantu penyusunan dokumentasi.

AI tidak digunakan sebagai pengganti proses pengujian dan pemahaman terhadap kode.

Saya tetap bertanggung jawab terhadap:

- Kode akhir.
- Modifikasi kode.
- Pengujian.
- Dokumentasi.
- Hasil akhir tugas.
- Kemampuan menjelaskan implementasi yang digunakan.

---

## 10. Tanggung Jawab Pengguna

Setiap saran dari AI diperiksa kembali sebelum diterapkan.

Kode akhir disesuaikan dengan:

- Instruksi Tugas 4.
- Materi yang dipelajari.
- Struktur HTML yang sudah dibuat.
- Hasil pengujian pada browser.
- Hasil pengujian responsive layout.
- Kebutuhan accessibility.
- Ketentuan source order dan Flexbox.

Saya memastikan bahwa kode yang digunakan dapat saya jelaskan dan modifikasi kembali apabila diperlukan.

---

## 11. Pernyataan

Saya memahami bahwa penggunaan AI dalam tugas ini harus disertai pemahaman terhadap kode yang digunakan.

AI digunakan sebagai alat bantu dalam proses belajar, evaluasi, dan dokumentasi.

Setiap saran AI yang diterapkan diperiksa dan disesuaikan dengan instruksi tugas serta hasil pengujian.

Kode akhir merupakan hasil dari proses belajar, pemeriksaan, modifikasi, dan pengujian yang dilakukan selama pengerjaan Tugas 4.
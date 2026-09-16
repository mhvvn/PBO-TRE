# MODUL PRAKTIKUM
# Pemrograman Berorientasi Objek

## Struktur Algoritma: Sequence, Selection, Repetition

**Disusun oleh:** Muhammad Veven
**Mata Kuliah:** TRE-404 — Pemrograman Berorientasi Objek
**Program Studi:** Teknologi Rekayasa Elektronika — Politeknik Negeri Batam

---

## A. TUJUAN PEMBELAJARAN

Setelah menyelesaikan praktikum ini, mahasiswa mampu:

1. Membedakan tiga konstruksi dasar algoritma: **Sequence**, **Selection**, dan **Repetition**
2. Menuliskan algoritma dalam tiga notasi: **kalimat deskriptif**, **flowchart**, dan **pseudocode**
3. Mengimplementasikan setiap struktur algoritma ke dalam kode C#

## B. ALAT DAN BAHAN

| No | Alat/Bahan | Keterangan |
|---|---|---|
| 1 | Komputer | Spesifikasi standar lab |
| 2 | Dia / DiagramDesigner | Software untuk menggambar flowchart |
| 3 | Visual Studio 2022 | IDE untuk menulis & menjalankan kode C# |

## C. TEORI SINGKAT

### C.1 Tiga Struktur Algoritma Dasar

| Struktur | Definisi | Kata Kunci C# |
|---|---|---|
| **Sequence** | Instruksi dijalankan satu per satu secara berurutan, tanpa percabangan | — (kode berjalan dari atas ke bawah) |
| **Selection** | Alur bercabang berdasarkan satu kondisi, menghasilkan dua atau lebih kemungkinan jalur | `if`, `else`, `switch` |
| **Repetition** | Blok instruksi diulang selama suatu kondisi masih terpenuhi | `while`, `for`, `do-while` |

### C.2 Keyword dalam Kalimat Deskriptif

Kalimat deskriptif adalah cara menuliskan algoritma dengan bahasa alami (Bahasa Indonesia), lebih longgar dibanding pseudocode namun tetap punya kata kunci baku agar mudah dikenali strukturnya:

| Keyword Kalimat Deskriptif | Fungsi | Padanan di Pseudocode |
|---|---|---|
| `MULAI` / `SELESAI` | Menandai awal dan akhir algoritma | `BEGIN` / `END` |
| `Baca` | Membaca data masukan dari pengguna | `READ` / `INPUT` |
| `Tampilkan` | Menampilkan hasil ke layar | `PRINT` / `OUTPUT` |
| `←` (atau "menjadi", "diisi dengan") | Operator penugasan (assignment) | `←` / `SET` |
| `JIKA ... MAKA` | Struktur percabangan | `IF ... THEN` |
| `SEBALIKNYA JIKA ... MAKA` | Percabangan bertingkat | `ELSE IF ... THEN` |
| `SEBALIKNYA` | Kondisi terakhir (default/else) | `ELSE` |
| `SELAMA ..., ULANGI` | Perulangan dengan kondisi di awal | `WHILE ... DO` |
| `ULANGI SEBANYAK ... KALI` | Perulangan dengan jumlah iterasi tetap | `FOR ... TO ... DO` |
| `ULANGI ... SAMPAI` | Perulangan dengan kondisi di akhir | `REPEAT ... UNTIL` |
| `SISA BAGI` / `MOD` | Operator sisa bagi | `MOD` |
| `DAN` / `ATAU` / `TIDAK` | Operator logika | `AND` / `OR` / `NOT` |
| `BENAR` / `SALAH` | Nilai kebenaran | `TRUE` / `FALSE` |
| `PANGGIL` | Memanggil prosedur/fungsi lain | `CALL` |
| `KEMBALIKAN` | Mengembalikan nilai dari fungsi | `RETURN` |


### C.3 Keyword dalam Kalimat Pseudocode

Pseudocode adalah cara menuliskan algoritma menggunakan bahasa semi-formal yang mendekati bahasa pemrograman, tetapi tidak terikat pada sintaks bahasa tertentu. Berikut kata kunci (keyword) yang umum dipakai beserta fungsinya:

| Keyword | Fungsi | Contoh Penggunaan |
|---|---|---|
| `BEGIN` / `END` | Menandai awal dan akhir algoritma atau blok | `BEGIN ... END` |
| `READ` / `INPUT` | Membaca data masukan dari pengguna | `READ nilai` |
| `PRINT` / `OUTPUT` / `WRITE` | Menampilkan data ke layar | `PRINT total` |
| `←` (atau `=`, `SET`) | Operator penugasan (assignment) nilai ke variabel | `luas ← panjang * lebar` |
| `IF` / `THEN` / `ELSE` / `END IF` | Struktur percabangan (selection) | `IF nilai >= 85 THEN ... ELSE ... END IF` |
| `ELSE IF` | Percabangan bertingkat (banyak kondisi) | `ELSE IF nilai >= 70 THEN ...` |
| `WHILE` / `DO` / `END WHILE` | Perulangan dengan pengecekan kondisi di awal | `WHILE i <= N DO ... END WHILE` |
| `FOR` / `TO` / `DO` / `END FOR` | Perulangan dengan jumlah iterasi yang diketahui | `FOR i ← 1 TO N DO ... END FOR` |
| `REPEAT` / `UNTIL` | Perulangan dengan pengecekan kondisi di akhir | `REPEAT ... UNTIL i > N` |
| `MOD` | Operator sisa bagi (modulus) | `IF i MOD 2 = 0 THEN` |
| `AND` / `OR` / `NOT` | Operator logika untuk menggabungkan kondisi | `IF a > 0 AND b > 0 THEN` |
| `TRUE` / `FALSE` | Nilai boolean (kebenaran) | `flag ← TRUE` |
| `CALL` | Memanggil sebuah prosedur/fungsi | `CALL HitungLuas(p, l)` |
| `RETURN` | Mengembalikan nilai dari sebuah fungsi | `RETURN luas` |
| `FUNCTION` / `PROCEDURE` | Menandai deklarasi fungsi atau prosedur | `FUNCTION Tambah(a, b)` |
| `DECLARE` | Mendeklarasikan variabel beserta tipenya (opsional) | `DECLARE total AS INTEGER` |
| `ARRAY` | Menyatakan struktur data larik/array | `ARRAY nilai[1..10]` |
| `CASE OF` / `END CASE` | Struktur percabangan banyak kasus (mirip switch) | `CASE hari OF ... END CASE` |
| `BREAK` / `EXIT` | Menghentikan perulangan sebelum kondisi selesai | `EXIT WHILE` |
| `CONTINUE` | Melompat ke iterasi berikutnya dalam perulangan | `CONTINUE` |

> **Catatan:** Tidak ada standar tunggal untuk pseudocode — beberapa buku/dosen memakai variasi keyword (misal `INPUT` vs `READ`, atau `=` vs `←`). Yang penting adalah **konsistensi** dalam satu naskah algoritma.

**Perbedaan Kalimat Deskriptif vs Pseudocode:**

| Aspek | Kalimat Deskriptif | Pseudocode |
|---|---|---|
| Bentuk bahasa | Bahasa alami, bebas gaya | Semi-formal, terstruktur, mendekati sintaks kode |
| Keterikatan struktur | Longgar — boleh naratif | Ketat — wajib `BEGIN...END`, `IF...THEN...END IF`, indentasi konsisten |
| Keyword | Fleksibel (variasi kalimat diperbolehkan) | Baku per keyword |
| Tujuan | Memudahkan pemahaman awal & komunikasi ke orang awam | Jembatan sebelum menulis kode program sungguhan |

> Urutan pengerjaan algoritma yang disarankan: **kalimat deskriptif → pseudocode → kode program (C#)**.

---

# BAGIAN 1: SEQUENCE

## Soal Praktikum 1

Buatlah algoritma untuk **menghitung luas dan keliling persegi panjang**. Program membaca panjang dan lebar dari user, lalu menampilkan hasil luas (`panjang × lebar`) dan keliling (`2 × (panjang + lebar)`).

**Tugas:**
1. Gambarkan **flowchart**-nya
2. Tuliskan **pseudocode**-nya


---

# BAGIAN 2: SELECTION

## Soal Praktikum 2

Buatlah algoritma untuk **menentukan kategori nilai mahasiswa**. Program membaca nilai (0-100), lalu menentukan predikat:
- Nilai ≥ 85 → **A**
- Nilai ≥ 70 dan < 85 → **B**
- Nilai ≥ 55 dan < 70 → **C**
- Nilai < 55 → **D**

**Tugas:**
1. Gambarkan **flowchart**-nya
2. Tuliskan **pseudocode**-nya


---

# BAGIAN 3: REPETITION

## Soal Praktikum 3

Buatlah algoritma untuk **menghitung faktorial (N!)**. Program membaca angka N dari user, lalu menghitung hasil perkalian `1 × 2 × 3 × ... × N` menggunakan pengulangan.

**Tugas:**
1. Gambarkan **flowchart**-nya
2. Tuliskan **pseudocode**-nya


---

# BAGIAN 4: LATIHAN GABUNGAN (KOMBINASI KETIGANYA)

## Soal Praktikum 4

Buatlah program yang menampilkan **bilangan genap dari 1 sampai N**, sekaligus menghitung **jumlah totalnya**. Program ini menggunakan ketiga struktur sekaligus:
- **Sequence** — baca input, tampilkan hasil
- **Repetition** — mengulang dari 1 sampai N
- **Selection** — mengecek apakah bilangan genap

**Tugas:** 
1. Gambarkan **flowchart**-nya
2. Tuliskan **pseudocode**-nya

---
### 4 Latihan di atas masuk dalam Laporan

# D. LATIHAN MANDIRI (TUGAS PRAKTIK) Pilih Salah Satu dan masuk dalam Laporan

Kerjakan soal berikut menggunakan ketiga notasi (kalimat deskriptif, flowchart, pseudocode), lalu implementasikan dalam C#. Kumpulkan hasilnya ke dosen.

### Latihan A — Sequence
Buat program konversi suhu: baca suhu dalam Celsius, tampilkan hasil konversi ke Fahrenheit (`F = C × 9/5 + 32`) dan Kelvin (`K = C + 273.15`).

### Latihan B — Selection
Buat program yang menentukan apakah sebuah tahun adalah **tahun kabisat**. Aturan: tahun habis dibagi 4 DAN (tidak habis dibagi 100 ATAU habis dibagi 400).




---



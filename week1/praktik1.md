#  Warmup Coding C# — Pertemuan 1
### TRE-404 Pemrograman Berorientasi Objek | Teknologi Rekayasa Elektronika

> Ketik kode di **Visual Studio 2022**, jalankan dengan **Ctrl + F5**  
> Selesaikan dari Latihan 1 → 5 secara berurutan

---

##  Path Latihan

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│  Latihan 1  │────▶│  Latihan 2  │────▶│  Latihan 3 │────▶│  Latihan 4  │────▶│  Latihan 5 │
│ Hello World │     │  Variabel   │     │ Input/Output│     │    Fungsi   │     │    Class    │
│   Dasar     │     │  Mudah      │     │      Mudah  │     │ Sedang      │     │     Sedang  │
└─────────────┘     └─────────────┘     └─────────────┘     └─────────────┘     └─────────────┘
  namespace           string/int        ReadLine()          static method       class + object
  class               float/bool        Parse()             parameter           property
  Main()              interpolation     Write vs WriteLine  return value        constructor
```

---

##  Struktur Program C# (Referensi Cepat)

```
┌──────────────────────────────────────────────────┐
│  namespace Pertemuan1         ← pengelompok class │
│  {                                                │
│    class Program              ← blueprint utama   │
│    {                                              │
│      static void Main()       ← titik mulai       │
│      {                                            │
│        Console.WriteLine();   ← perintah/statement│
│      }                                            │
│    }                                              │
│  }                                                │
└──────────────────────────────────────────────────┘
  Luar ──────────────────────────────────── Dalam ▶
```

---

## Latihan 1 — Hello World

### Tujuan
Kenali struktur dasar program C# dan cara menampilkan teks ke layar.

### Konsep yang dipelajari
| Keyword | Fungsi |
|---|---|
| `namespace` | Wadah pengelompok class |
| `class` | Blueprint program |
| `static void Main()` | Titik mulai program dijalankan |
| `Console.WriteLine()` | Tampilkan teks + baris baru |
| `// komentar` | Catatan yang diabaikan compiler |

### Ilustrasi Alur

```
  Main() dipanggil
        │
        ▼
  Console.WriteLine("Halo!")  ──▶  layar: "Halo!"
        │
        ▼
  Console.WriteLine("Nama...")──▶  layar: "Nama..."
        │
        ▼
  Console.WriteLine("Prodi..")──▶  layar: "Prodi..."
        │
        ▼
  Program selesai
```

### Kode

```csharp
// Program pertama saya dalam C#
using System;

namespace Pertemuan1
{
    class Program
    {
        static void Main()
        {
            Console.WriteLine("Halo! Saya belajar C#");
            Console.WriteLine("Nama     : Muhammad Veven");
            Console.WriteLine("Prodi    : Teknologi Rekayasa Elektronika");
            Console.WriteLine("Semester : 4");
        }
    }
}
```

### Output

```
Halo! Saya belajar C#
Nama     : Muhammad Veven
Prodi    : Teknologi Rekayasa Elektronika
Semester : 4
```

### Catatan Penting
- `Console.WriteLine()` → cetak + **baris baru**
- `Console.Write()` → cetak **tanpa** baris baru
- Coba ganti beberapa `WriteLine` dengan `Write` dan amati perbedaannya!

---

## Latihan 2 — Variabel & Tipe Data

### Tujuan
Simpan data dalam variabel bertipe, tampilkan dengan string interpolation.

### Konsep yang dipelajari
| Tipe | Contoh nilai | Digunakan untuk |
|---|---|---|
| `string` | `"Indomie"` | Teks |
| `int` | `3500` | Bilangan bulat |
| `float` | `85.0f` | Bilangan desimal |
| `bool` | `true / false` | Ya atau tidak |

### Ilustrasi Tipe Data

```
  Memori Program
  ┌────────────────────────────────────────┐
  │  namaMie   │ "Indomie Goreng Spesial"  │  ◀ string
  │  harga     │ 3500                      │  ◀ int
  │  beratGram │ 85.0                      │  ◀ float
  │  tersedia  │ true                      │  ◀ bool
  └────────────────────────────────────────┘
          │
          ▼
  $"Nama: {namaMie}"  ──▶  "Nama: Indomie Goreng Spesial"
```

### Kode

```csharp
using System;

class Program
{
    static void Main()
    {
        // Deklarasi variabel
        string namaMie   = "Indomie Goreng Spesial";
        int    harga     = 3500;
        float  beratGram = 85.0f;
        bool   tersedia  = true;

        // Tampilkan dengan string interpolation
        Console.WriteLine($"Nama   : {namaMie}");
        Console.WriteLine($"Harga  : Rp {harga}");
        Console.WriteLine($"Berat  : {beratGram} gram");
        Console.WriteLine($"Stok   : {(tersedia ? "Tersedia" : "Habis")}");
    }
}
```

### Output

```
Nama   : Indomie Goreng Spesial
Harga  : Rp 3500
Berat  : 85 gram
Stok   : Tersedia
```

###  Catatan Penting
- `$"...{variabel}..."` = **string interpolation** — lebih bersih dari `"Nama: " + nama`
- `kondisi ? "ya" : "tidak"` = **ternary operator** — shortcut if-else satu baris
- Coba ubah `tersedia = false`, jalankan ulang — output berubah otomatis!

---

## Latihan 3 — Input & Output Interaktif

### Tujuan
Terima input dari user saat program berjalan menggunakan `Console.ReadLine()`.

### Konsep yang dipelajari
| Method | Fungsi |
|---|---|
| `Console.Write()` | Tampilkan teks (kursor tetap di baris sama) |
| `Console.ReadLine()` | Baca input dari keyboard → hasilnya `string` |
| `int.Parse()` | Ubah string `"3"` → int `3` |

### Ilustrasi Alur Input/Output

```
  Program                         User (keyboard)
     │                                  │
     │── Console.Write("Nama mie: ") ──▶│ layar: "Nama mie: _"
     │                                  │
     │◀── Console.ReadLine() ───────────│ user ketik "Indomie" + Enter
     │    namaMie = "Indomie"           │
     │                                  │
     │── Console.Write("Porsi: ") ─────▶│ layar: "Porsi: _"
     │                                  │
     │◀── int.Parse(ReadLine()) ────────│ user ketik "3" + Enter
     │    porsi = 3                     │
     │                                  │
     │── total = 3 × 3500 = 10500       │
     │── Console.WriteLine(struk) ─────▶│ layar: tampilkan struk
```

### Kode

```csharp
using System;

class Program
{
    static void Main()
    {
        int hargaPerPorsi = 3500;

        // Minta input dari user
        Console.Write("Nama mie     : ");
        string namaMie = Console.ReadLine();

        Console.Write("Jumlah porsi : ");
        int porsi = int.Parse(Console.ReadLine());

        // Hitung dan tampilkan struk
        int total = porsi * hargaPerPorsi;

        Console.WriteLine("\n=== Struk Pembelian ===");
        Console.WriteLine($"Mie    : {namaMie}");
        Console.WriteLine($"Porsi  : {porsi} x Rp {hargaPerPorsi}");
        Console.WriteLine($"Total  : Rp {total}");
    }
}
```

### Output (contoh sesi)

```
Nama mie     : Indomie Goreng
Jumlah porsi : 3

=== Struk Pembelian ===
Mie    : Indomie Goreng
Porsi  : 3 x Rp 3500
Total  : Rp 10500
```

###  Catatan Penting
- `Console.ReadLine()` **selalu** mengembalikan `string` → harus `int.Parse()` untuk angka
- `\n` di dalam string = baris kosong baru
- Coba ketik huruf saat diminta angka → program error! (akan dipelajari cara tanganinya nanti)

---

## Latihan 4 — Membuat Fungsi (Method)

### Tujuan
Pisahkan kode ke dalam method agar lebih terstruktur dan bisa dipanggil berulang.

### Konsep yang dipelajari
| Istilah | Penjelasan | Contoh |
|---|---|---|
| `void` | Method tidak mengembalikan nilai | `void MasakMie()` |
| `int` (return) | Method mengembalikan angka | `int HitungHarga()` |
| Parameter | Nilai yang dikirim ke method | `MasakMie("Goreng")` |
| `return` | Mengembalikan nilai dari method | `return porsi * harga` |

### Ilustrasi Alur Method

```
  Main()
    │
    ├──▶ MasakMie("Goreng Spesial")
    │         │
    │         ├── print "Memasak Goreng Spesial..."
    │         ├── print "1. Rebus air"
    │         ├── print "2. Masukkan mie"
    │         └── print "3. Tambahkan bumbu"
    │    ◀────┘ (void — tidak ada return)
    │
    ├──▶ HitungHarga(2)
    │         │
    │         └── return 2 × 3500 = 7000
    │    ◀────┘
    │
    └── print "Total 2 porsi: Rp 7000"
```

### Kode

```csharp
using System;

class Program
{
    // Method tanpa return value
    static void MasakMie(string rasa)
    {
        Console.WriteLine($"\nMemasak mie rasa {rasa}:");
        Console.WriteLine("1. Rebus air hingga mendidih");
        Console.WriteLine("2. Masukkan mie, tunggu 3 menit");
        Console.WriteLine("3. Tambahkan bumbu dan aduk");
        Console.WriteLine("4. Sajikan!");
    }

    // Method dengan return value
    static int HitungHarga(int porsi)
    {
        int hargaSatuan = 3500;
        return porsi * hargaSatuan;
    }

    static void Main()
    {
        MasakMie("Goreng Spesial");

        int total = HitungHarga(2);
        Console.WriteLine($"\nTotal 2 porsi : Rp {total}");
    }
}
```

### Output

```
Memasak mie rasa Goreng Spesial:
1. Rebus air hingga mendidih
2. Masukkan mie, tunggu 3 menit
3. Tambahkan bumbu dan aduk
4. Sajikan!

Total 2 porsi : Rp 7000
```

###  Catatan Penting
- Method bisa dipanggil **berkali-kali** dengan input berbeda: `MasakMie("Kuah Ayam")`
- `void` = tidak ada `return`. `int` sebelum nama method = wajib ada `return` angka
- Coba panggil `HitungHarga(5)` — hasilnya langsung berubah tanpa ubah kode di dalam method!

---

## Latihan 5 — Class Pertama (OOP Dasar)

### Tujuan
Buat class dengan property dan method, lalu buat object dari class tersebut.

### Konsep yang dipelajari
| Istilah | Penjelasan |
|---|---|
| `class` | Blueprint / cetakan |
| Property | Data yang dimiliki object (`Rasa`, `Harga`) |
| Constructor | Method khusus untuk inisialisasi saat `new` dipanggil |
| Method | Aksi yang bisa dilakukan object (`Masak()`, `Info()`) |
| `new` | Membuat object dari class |

### Ilustrasi Class vs Object

```
  CLASS (1 buah — cetakan)
  ┌──────────────────────────────────┐
  │  class MieInstan                 │
  │  ├── Property: Rasa              │
  │  ├── Property: Harga             │
  │  ├── Method: Info()              │
  │  └── Method: Masak()             │
  └──────────────────────────────────┘
           │                │
      new MieInstan()  new MieInstan()
           │                │
           ▼                ▼
  ┌──────────────┐  ┌──────────────────────┐
  │  mie1        │  │  mie2                │
  │  Rasa: Goreng│  │  Rasa: Kuah Ayam     │
  │  Harga: 3500 │  │  Harga: 4000         │
  │  mie1.Info() │  │  mie2.Info()         │
  │  mie1.Masak()│  │  mie2.Masak()        │
  └──────────────┘  └──────────────────────┘
   OBJECT 1          OBJECT 2
  (data sendiri)    (data sendiri)
```

### Kode

```csharp
using System;

// Definisi class
public class MieInstan
{
    // Property
    public string Rasa  { get; set; }
    public int    Harga { get; set; }

    // Constructor — dijalankan saat "new MieInstan(...)"
    public MieInstan(string rasa, int harga)
    {
        Rasa  = rasa;
        Harga = harga;
    }

    // Method — tampilkan info singkat
    public void Info()
    {
        Console.WriteLine($"[{Rasa}] — Rp {Harga}");
    }

    // Method — instruksi memasak
    public void Masak()
    {
        Console.WriteLine($"\nMemasak {Rasa}...");
        Console.WriteLine("1. Rebus air");
        Console.WriteLine("2. Masukkan mie");
        Console.WriteLine("3. Tambahkan bumbu");
        Console.WriteLine("4. Sajikan!\n");
    }
}

// Program utama
class Program
{
    static void Main()
    {
        // Buat 2 object dari class MieInstan
        MieInstan mie1 = new MieInstan("Goreng Spesial", 3500);
        MieInstan mie2 = new MieInstan("Kuah Ayam + Telur", 4000);

        Console.WriteLine("=== Daftar Mie ===");
        mie1.Info();
        mie2.Info();

        mie1.Masak();
        mie2.Masak();
    }
}
```

### Output

```
=== Daftar Mie ===
[Goreng Spesial] — Rp 3500
[Kuah Ayam + Telur] — Rp 4000

Memasak Goreng Spesial...
1. Rebus air
2. Masukkan mie
3. Tambahkan bumbu
4. Sajikan!

Memasak Kuah Ayam + Telur...
1. Rebus air
2. Masukkan mie
3. Tambahkan bumbu
4. Sajikan!
```

### Catatan Penting
- `mie1` dan `mie2` adalah **dua object berbeda** dari satu class yang sama
- Masing-masing punya data `Rasa` dan `Harga` sendiri — tidak saling mempengaruhi
- Ini adalah **inti OOP**: `class` = cetakan, `object` = hasil cetakan

---

## Ringkasan Perbandingan 5 Latihan

```
  Latihan │ Yang Baru Dipelajari             │ Baris Kode
  ────────┼──────────────────────────────────┼────────────
     1    │ namespace, class, Main, WriteLine │  ~12 baris
     2    │ string, int, float, bool, $"..."  │  ~14 baris
     3    │ ReadLine(), Write(), int.Parse()  │  ~16 baris
     4    │ method, parameter, return, void   │  ~20 baris
     5    │ class, property, constructor, new │  ~40 baris
```

---

##  Tantangan Tambahan (Bonus)

Setelah selesai semua latihan, coba:

1. **Latihan 2**: Tambah variabel `int kalori = 330` dan tampilkan
2. **Latihan 3**: Tambah diskon 10% jika porsi ≥ 5
3. **Latihan 4**: Buat method `CetakGaris()` yang mencetak `==========`
4. **Latihan 5**: Tambah property `Berat` dan method `CekStok()` yang menampilkan warning jika Harga > 5000
5. **Ekstra**: Buat class `Robot` dengan property `Nama` dan method `Gerak()` — ubah contoh mie menjadi contoh robot!

---

##  Referensi

- **Buku Wajib**: Beginning C# 6 Programming with Visual Studio — Perkins et al. (Wrox, 2016)
- **Online Gratis**: Fundamentals of Computer Programming with C# — Nakov et al.
- **Dokumentasi**: https://docs.microsoft.com/dotnet/csharp/

---

*TRE-404 | Pemrograman Berorientasi Objek | Semester 3 | Politeknik Negeri Batam*
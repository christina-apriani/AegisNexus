<div align="center">

# ▦ CacheWall

### Sub-Zero Core Isolation via Hardware-Enforced EPT & Microarchitectural Flusher

**Tidak ada data rahasia tersisa di silikon fisik untuk diintip.**

![AegisNexus](https://img.shields.io/badge/suite-AegisNexus-ff3b5c?style=flat-square)
![Category](https://img.shields.io/badge/category-Memory%20Isolation-ff7a93?style=flat-square)
![Type](https://img.shields.io/badge/type-research%20simulation-170d10?style=flat-square)

*Authored by **Christina Apriani***

</div>

---

## Realitas medan perang

Kerentanan tingkat prosesor seperti **Spectre, Meltdown**, dan varian eksekusi spekulatif terbaru memungkinkan
penyerang membaca data sensitif (master key, kredensial root) langsung dari **cache CPU fisik**, menembus batas
virtualisasi, lewat serangan **cache-timing**.

## Logika sistem

CacheWall memodifikasi hypervisor tingkat rendah dengan dua lapis pertahanan:

1. **EPT Core Isolation** — memisahkan memory page tables secara radikal menggunakan virtualisasi perangkat
   keras (Intel VT-x / AMD-V Extended Page Tables), sehingga kode pihak ketiga tidak berbagi pemetaan dengan
   modul kritis.
2. **Flush-on-Context-Switch** — pada setiap perpindahan konteks dari modul kritis ke kode pihak ketiga,
   instruksi level-assembly (WRMSR, `L1D_FLUSH`, pembersihan register mikroarsitektur) dipanggil paksa untuk
   menghapus seluruh jejak di **L1/L2 cache, Line-Fill Buffers, dan Branch Predictor** dalam hitungan siklus CPU
   terkecil. Hasilnya, ketika penyerang melakukan probe cache-timing, cache sudah kosong.

## Yang bisa Anda lakukan

- **Amati physical cache state**: L1 data cache (256 lines), Line-Fill Buffers, Branch Predictor — dengan line
  pembawa rahasia ditandai merah.
- **Jalankan serangan** (Meltdown, Spectre v1, atau MDS/RIDL) dan lihat apakah penyerang berhasil membaca secret.
- **Dengan pertahanan aktif**: flush membersihkan cache saat context switch → probe menemukan cache kosong →
  **secret aman**.
- **Matikan EPT + flush** → probe menemukan residu → **8/8 byte master key bocor** (`MasterKy`).
- Lihat **flush cost** (siklus) — biaya pertahanan yang terukur.

> Eksperimen: nyalakan kedua pertahanan → serangan **gagal**. Matikan → **secret bocor**. Trade-off keamanan vs
> performa (flush cost) terlihat langsung.

## Menjalankan

Buka `index.html`. Tanpa dependency.

## Catatan

Model konseptual / simulasi edukatif tentang cara kerja cache-timing side-channel dan mitigasinya. **Bukan** kode
serangan mikroarsitektur nyata; visualisasi menggunakan state cache tersimulasi.

---

<div align="center">
<sub>Bagian dari AegisNexus · dibangun oleh Christina Apriani</sub>
</div>

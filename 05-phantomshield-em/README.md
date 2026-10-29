<div align="center">

# φ PhantomShield

### Dynamic EM-Jacket & Clock-Jitter Randomizer vs Sub-Nanosecond EM Side-Channel Attacks

**Antena di luar gedung menangkap kebocoran EM prosesor. PhantomShield memastikan yang mereka tangkap hanyalah derau.**

![AegisNexus](https://img.shields.io/badge/suite-AegisNexus-5b8cff?style=flat-square)
![Category](https://img.shields.io/badge/category-EM%20Side--Channel-86a9ff?style=flat-square)
![Type](https://img.shields.io/badge/type-research%20simulation-0e1524?style=flat-square)

*Authored by **Christina Apriani***

</div>

---

## Realitas medan perang

Penyerang nation-state dapat mencuri kunci enkripsi (bahkan PQC) dari komputer air-gapped hanya dengan
menempatkan antena sensitif di dekat gedung untuk menangkap kebocoran gelombang **elektromagnetik** prosesor
saat komputasi kriptografi. Teknik **Differential EM Analysis (DEMA)** mengkorelasikan kebocoran ini dengan
model matematis untuk memulihkan kunci byte demi byte.

## Logika sistem

PhantomShield memanipulasi arsitektur clock di level mikroprosesor:

1. **Clock-jitter randomizer** — menyuntikkan jitter (variasi waktu) sub-nanodetik secara acak ke siklus
   instruksi CPU saat operasi kripto. Akibatnya, titik kebocoran **bergeser tak terduga** di setiap jejak,
   menghancurkan penyelarasan (alignment) yang dibutuhkan DEMA.
2. **EM-jacket chaff generator** — sirkuit FPGA eksternal membangkitkan derau EM semu (chaff) yang meniru
   frekuensi pemrosesan tetapi berisi data sampah. Sinyal bocor jadi terdistorsi total.

Hasilnya: korelasi DEMA penyerang kolaps menjadi derau acak yang mustahil didekripsi.

## Yang bisa Anda lakukan

- **Jalankan serangan DEMA** — simulasi Correlation Power/EM Analysis nyata memakai model kebocoran Hamming
  weight output S-box AES. Grafik menampilkan korelasi untuk 256 tebakan kunci.
- **Tanpa pertahanan**: puncak korelasi tajam muncul tepat di kunci sebenarnya (`0x2B`) → **kunci bocor**.
- **Aktifkan clock-jitter + EM chaff** (atur magnitude) dan jalankan lagi → puncak kolaps → **DEMA gagal**.
- Atur jumlah trace penyerang (N) untuk melihat bahwa bahkan ribuan trace tak menembus pertahanan.

> Coba sendiri: matikan kedua pertahanan → serangan **BERHASIL**. Nyalakan → serangan **GAGAL**. Itulah
> efektivitas countermeasure yang didemonstrasikan secara kuantitatif.

## Menjalankan

Buka `index.html`. Tanpa dependency.

## Catatan

Simulasi edukatif CPA/DEMA dengan model korelasi nyata atas jejak yang disimulasikan. Mendemonstrasikan
countermeasure defensif; bukan alat intersepsi nyata.

---

<div align="center">
<sub>Bagian dari AegisNexus · dibangun oleh Christina Apriani</sub>
</div>

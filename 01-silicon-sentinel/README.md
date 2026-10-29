<div align="center">

# 🔬 Silicon Sentinel

### Sub-Micron Hardware Trojan Detection via Electroluminescence & RF Side-Channel

**Detecting physical backdoors that no software can see — by watching the silicon glow and listen.**

![AegisNexus](https://img.shields.io/badge/suite-AegisNexus-1fd1a8?style=flat-square)
![Category](https://img.shields.io/badge/category-HW%20Supply%20Chain-5fe8c8?style=flat-square)
![Type](https://img.shields.io/badge/type-research%20visualization-0e151b?style=flat-square)

*Authored by **Christina Apriani***

</div>

---

## Realitas medan perang

Penyerang nation-state dapat memodifikasi silikon mikroprosesor **di pabrik fabrikasi** untuk menyuntikkan
backdoor fisik (Hardware Trojan) yang tidak terdeteksi oleh software apa pun — karena ia hidup di bawah lapisan
tempat software berjalan. Satu-satunya cara menangkapnya adalah dengan mengamati chip itu sendiri saat bekerja.

## Logika sistem

Saat chip mengeksekusi instruksi standar, Silicon Sentinel menangkap dua sinyal fisik secara bersamaan:

1. **Electroluminescence (EL)** — emisi foton inframerah-dekat dari transistor yang sedang switching, dipetakan
   ke grid transistor pada level piksel-mikro.
2. **RF side-channel** — pancaran radio dari sirkuit, dianalisis sebagai spektrum frekuensi.

Algoritma membandingkan Device-Under-Test dengan **golden reference** (signature chip bersih). Transistor
tambahan berukuran sub-mikron yang hanya aktif ketika **pola bit pemicu** tertentu dimasukkan akan muncul
sebagai: emisi EL lokal yang tidak ada di golden, puncak RF liar di luar pita normal, lonjakan konsumsi daya,
dan — bukti paling menentukan — **korelasi trigger→privilege**: sirkuit yang menyala *hanya* pada satu pola bit
adalah, menurut definisi, logika tak-terdokumentasi.

## Yang bisa Anda lakukan

- **Pilih Device-Under-Test** (golden, batch bersih, atau batch tersuspek dari fab berbeda).
- **Masukkan pola bit instruksi** (hex 16-bit) — coba pola pemicu `A5F0` pada batch tersuspek.
- **Jalankan scan** — lihat die EL map menyala, spektrum RF, dan dekomposisi skor anomali.
- **Sweep semua pola** — cara nyata menangkap trojan: ia dorman sampai pola pemicunya muncul.
- **Supply-chain map** — provenance fab global dengan node tersuspek.

> Trojan bersifat **dorman**: pada pola non-pemicu, chip tersuspek terbaca bersih. Itulah sebabnya sweep
> lintas pola adalah metodologi deteksi yang benar.

## Skor anomali

Gabungan tertimbang dari: deviasi EL vs golden, anomali spektrum RF, lonjakan daya, dan korelasi
trigger→privilege (dominan). Ambang verdict trojan: **0.60**.

## Menjalankan

Buka `index.html` di browser. Tanpa dependency, tanpa build. State di memori; peta memakai OpenStreetMap.

## Catatan

Ini **visualisasi riset / simulasi metodologi**, bukan kontrol instrumen EL/RF nyata dan bukan alat serang.
Data sinyal disimulasikan secara deterministik untuk mendemonstrasikan pipeline deteksi.

---

<div align="center">
<sub>Bagian dari AegisNexus · dibangun oleh Christina Apriani</sub>
</div>

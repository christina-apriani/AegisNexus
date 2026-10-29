<div align="center">

# 👻 GhostFlash

### Firmware Flashing Honeypot with Air-Gap Exfiltration Countermeasures

**Penyerang mengira mereka mem-flash target. Mereka sedang mem-flash bayangan — dan setiap bisikan air-gap mereka terdengar.**

![AegisNexus](https://img.shields.io/badge/suite-AegisNexus-ff9f1c?style=flat-square)
![Category](https://img.shields.io/badge/category-Deception%20%26%20Firmware-ffbf5c?style=flat-square)
![Type](https://img.shields.io/badge/type-research%20simulation-161109?style=flat-square)

*Authored by **Christina Apriani***

</div>

---

## Realitas medan perang

Kelompok APT berusaha menginfeksi firmware UEFI/BIOS dan controller penyimpanan (NVMe/SSD) agar malware tetap
bertahan **meskipun harddisk diformat ulang**. Pada target air-gapped, mereka lalu mencuri data lewat saluran
tersembunyi (covert channel) seperti getaran kipas, kedip LED, manipulasi termal, atau emanasi EM.

## Logika sistem

GhostFlash menempatkan pertahanan aktif di level firmware:

1. **Shadow firmware honeypot** — upaya flashing dialihkan ke image bayangan. Penyerang tidak sadar; mereka
   menjelajahi **decoy filesystem** berisi umpan bernilai tinggi.
2. **Air-gap covert-channel monitor** — 4 sensor (fan-vibration, LED optik, thermal, EM) mengawasi pita
   frekuensi khas exfiltrasi. Saat penyerang memodulasi salah satu kanal, carrier-nya langsung terdeteksi.
3. **Autonomous containment** — isolasi sirkuit komunikasi, peracunan stream exfil dengan data decoy (chaff),
   dan ekstraksi signature implant untuk threat-intel.

## Yang bisa Anda lakukan

- **Pilih vektor serangan** (UEFI re-flash, NVMe implant, Option-ROM) dan **metode exfiltrasi** air-gap.
- **Jalankan rantai serangan** → lihat honeypot mengalihkan ke shadow firmware, sensor menangkap carrier exfil,
  dan containment otonom bekerja langkah demi langkah di trace.
- **Air-gap covert-channel monitor** menampilkan spektrum tiap kanal; kanal yang diserang berdenyut merah.
- **Peta fasilitas** menampilkan aset air-gapped yang dilindungi beserta cakupan sensor.

## Ruang lingkup & etika

Respons "poison / counter" di platform ini bersifat **konseptual dan tersimulasi** — isolasi, penyerahan data
decoy, dan ekstraksi signature. **Tidak ada kode serang-balik fungsional** terhadap sistem pihak ketiga. Fokus
GhostFlash adalah **deteksi dan deception defensif** untuk melindungi aset air-gapped. Semua aktivitas serangan
di konsol hanya menggerakkan visualisasi, bukan operasi nyata.

## Menjalankan

Buka `index.html`. Tanpa dependency; peta memakai OpenStreetMap.

---

<div align="center">
<sub>Bagian dari AegisNexus · dibangun oleh Christina Apriani</sub>
</div>

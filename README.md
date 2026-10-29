<div align="center">

# 🛡️ AegisNexus

### Advanced Cyber Defense Research — Silicon · Kernel · Cryptographic Frontier

**Enam platform riset keamanan siber tingkat lanjut, dari backdoor fisik di dalam silikon hingga serangan kuantum pada kriptografi — semuanya interaktif, dapat diklik, dan dibuktikan secara kuantitatif.**

![Projects](https://img.shields.io/badge/platforms-6-36e0c8?style=for-the-badge)
![Stack](https://img.shields.io/badge/stack-self--contained%20·%20zero%20dependency-0c111c?style=for-the-badge)

![Red](https://img.shields.io/badge/scope-Red%20%2F%20Blue%20%2F%20Purple-6cf0dd?style=flat-square)
![Interactive](https://img.shields.io/badge/UI-interactive%20%2B%20realtime%20maps-6cf0dd?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-1a2436?style=flat-square)

*Dibangun oleh **Christina Apriani***

</div>

---

## Ringkasan

AegisNexus adalah kumpulan enam platform riset yang mendemonstrasikan metodologi deteksi dan pertahanan paling
mutakhir di lapisan terdalam sistem komputasi — tempat software tidak bisa melihat. Setiap platform adalah
dashboard interaktif dengan **logika nyata** (anomaly detection, correlation power analysis, reduksi kisi,
model cache-timing), bukan sekadar mockup.

Buka **`index.html`** untuk hub portofolio, atau masuk ke tiap platform langsung.

## Enam platform

| # | Platform | Kategori | Inti teknis |
|---|---|---|---|
| 01 | **[Silicon Sentinel](./01-silicon-sentinel)** | Hardware Supply-Chain | Deteksi hardware trojan sub-mikron via electroluminescence + RF side-channel; die heatmap, golden-reference compare |
| 02 | **[ChronoShift](./02-chronoshift-kernel)** | Kernel Defense | Hypervisor polymorphic kernel mutator; syscall table bermutasi → exploit segfault → payload trap |
| 03 | **[GhostFlash](./03-ghostflash-honeypot)** | Firmware Deception | Shadow-firmware honeypot + deteksi exfiltrasi air-gap (fan/LED/thermal/EM) + containment otonom |
| 04 | **[LatticeForge](./04-latticeforge-pqc)** | Post-Quantum | Visualizer reduksi kisi Gauss/LLL + SVP + estimator core-SVP Kyber/ML-KEM (edukatif) |
| 05 | **[PhantomShield](./05-phantomshield-em)** | EM Side-Channel | EM-jacket + clock-jitter randomizer melawan DEMA; CPA nyata, korelasi kunci kolaps ke derau |
| 06 | **[CacheWall](./06-cachewall-ept)** | Microarch Isolation | EPT core isolation + microarchitectural flusher melawan Spectre/Meltdown; flush L1/L2/LFB/BTB |

## Yang membuat ini "insane level"

- **Logika nyata, bukan animasi kosong.** CPA/DEMA memakai model Hamming-weight S-box AES; LatticeForge
  menjalankan reduksi Gauss sungguhan dan estimasi core-SVP yang selaras dokumentasi NIST; Silicon Sentinel
  memakai skor anomali multi-dimensi.
- **Buktikan sendiri secara kuantitatif.** Pada PhantomShield dan CacheWall: matikan pertahanan → serangan
  **berhasil**; nyalakan → serangan **gagal**. Trade-off keamanan terlihat langsung.
- **UI/UX ops-grade & interaktif.** Die heatmap, memory map yang bermutasi live, spektrum covert-channel,
  grafik korelasi, cache visualization, dan peta real-time (Leaflet/OpenStreetMap).

## Menjalankan

Setiap platform adalah satu halaman HTML mandiri — **tanpa build, tanpa dependency**.

```bash
# buka hub
open index.html            # atau xdg-open / start

# atau langsung sebuah platform
open 01-silicon-sentinel/index.html
```

Untuk hosting (GitHub Pages): aktifkan Pages pada branch utama, folder `/ (root)`. Seluruh platform langsung
dapat diakses dan diklik.

## Etika & ruang lingkup

Keenam platform adalah **visualisasi dan simulasi riset defensif/edukatif**. Tidak memuat exploit fungsional,
malware, kode cryptanalytic yang memecahkan sistem nyata, atau kode serang-balik terhadap pihak ketiga. Elemen
"counter/poison" bersifat **konseptual dan tersimulasi**. Ditujukan untuk pembelajaran dan penggunaan yang sah
atas sistem yang Anda miliki/uji.

---

<div align="center">

**Christina Apriani** · Cyber Security Professional
*Red Team · Blue Team · Purple Team · Hardware / Kernel / Cryptographic security*

<sub>AegisNexus · 6 platform riset · self-contained · zero dependency</sub>

</div>

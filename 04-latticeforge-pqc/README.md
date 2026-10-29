<div align="center">

# Λ LatticeForge

### Quantum-Resistant Lattice Cryptography Stress-Tester via Geometric Reduction

**Mencari retakan pada matematika murni PQC — sebelum dunia bergantung padanya.**

![AegisNexus](https://img.shields.io/badge/suite-AegisNexus-19c3c3?style=flat-square)
![Category](https://img.shields.io/badge/category-Post--Quantum-5fe3e3?style=flat-square)
![Type](https://img.shields.io/badge/type-educational-0d141b?style=flat-square)

*Authored by **Christina Apriani***

</div>

---

## Realitas medan perang

Dunia bermigrasi ke **kriptografi berbasis kisi** (lattice-based) karena dianggap tahan komputer kuantum.
Tugas pakar internasional adalah mencari retakan pada matematika ini **sebelum** diadopsi global. Keamanan PQC
seperti ML-KEM (Kyber) bersandar pada kesulitan **Shortest Vector Problem (SVP)** di kisi berdimensi tinggi.

## Logika sistem

LatticeForge bukan tentang implementasi, melainkan pembongkaran konsep:

1. **Reduksi basis** — memetakan enkripsi menjadi masalah geometris. Visualizer 2D menjalankan reduksi
   **Gauss/Lagrange** (kasus 2D dari LLL) langkah demi langkah, memperpendek vektor basis hingga menemukan SVP.
2. **SVP search** — vektor terpendek disorot beserta lingkaran normanya. Semakin pendek basis, semakin dekat ke
   solusi SVP.
3. **Core-SVP estimator** — untuk parameter NIST (ML-KEM-512/768/1024, Dilithium2), menghitung estimasi biaya
   serangan dari model core-SVP publik: klasik ≈ 2<sup>0.292·β</sup>, kuantum ≈ 2<sup>0.265·β</sup>, dengan β =
   BKZ block-size.
4. **Cost vs β chart** — menunjukkan mengapa dimensi tinggi membuat pencarian meledak eksponensial.

## Yang bisa Anda lakukan

- **Masukkan basis** 2D (atau acak), lalu **Reduksi 1 langkah** / **Auto-reduce** untuk melihat vektor memendek
  ke SVP, lengkap dengan reduction trace.
- **Pilih parameter set** PQC dan lihat estimasi keamanan klasik vs kuantum (bit).
- **Geser β** untuk mengeksplorasi hubungan eksponensial biaya-vs-blocksize.

Angka estimator selaras dengan dokumentasi NIST/literatur (mis. Kyber768 ≈ 2<sup>182</sup> klasik, Kyber1024 ≈
2<sup>255</sup>).

## Menjalankan

Buka `index.html`. Tanpa dependency.

## Catatan

**Alat edukatif.** Reduksi 2D-nya nyata dan benar; estimasi Kyber memakai model core-SVP publik. Ini **bukan**
serangan nyata terhadap kriptografi yang di-deploy, dan tidak memecahkan Kyber. Tujuannya mengajarkan mengapa
PQC aman dan bagaimana kekuatannya diukur.

---

<div align="center">
<sub>Bagian dari AegisNexus · dibangun oleh Christina Apriani</sub>
</div>

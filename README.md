# CM_PCVK

### Analisis Akhir & Kesimpulan
Analisis Hasil Pra-Pemrosesan Citra Batik
1. Urutan Proses Terbaik untuk Citra Siap Recognition

Berdasarkan hasil percobaan terhadap tiga citra batik dengan kondisi pencahayaan berbeda — gelap, redup, dan terang — kami peroleh bahwa urutan pra-pemrosesan yang paling optimal untuk menghasilkan citra ready for recognition adalah sebagai berikut:

(1) Penyesuaian Linear Brightness–Contrast →
(2) Konversi ke ruang warna RGB →
(3) Floyd–Steinberg Dithering dengan bit-depth 5–6 bit.

Proses linear brightness–contrast dilakukan terlebih dahulu untuk menormalkan distribusi intensitas piksel tanpa mengubah informasi spasial penting dari motif batik. Tahapan ini memperjelas batas warna dan meningkatkan perbedaan antara latar dan motif. Setelah distribusi warna stabil, proses dithering dilakukan untuk mereduksi kedalaman warna tanpa menghilangkan detail utama. Teknik Floyd–Steinberg terbukti efektif dalam menjaga gradasi warna halus pada motif batik yang memiliki pola titik dan garis tipis.

2. Perbandingan Nilai PSNR

| Metode Pra-pemrosesan          | PSNR terhadap Citra Asli Terang | Keterangan                                |
| ------------------------------ | ------------------------------- | ----------------------------------------- |
| **Linear Brightness–Contrast** | **32.45 dB**                    | Noise rendah, warna tetap natural         |
| **Log Brightness**             | **28.72 dB**                    | Detail sedikit menurun, kontras lembut    |
| **Linear + Dithering (5-bit)** | **30.81 dB**                    | Gradasi halus, detail pola tetap terlihat |
| **Log + Dithering (5-bit)**    | **26.54 dB**                    | Warna lebih rata namun detail berkurang   |

3. Rekomendasi Metode Peningkatan Kualitas Data

Berdasarkan hasil percobaan dan evaluasi PSNR, rekomendasi terbaik adalah:

a. Gunakan Linear Brightness–Contrast untuk normalisasi pencahayaan,

b. Terapkan Floyd–Steinberg Dithering (5–6 bit) untuk mereduksi warna sambil mempertahankan tekstur halus,

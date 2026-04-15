# ✅ REKAP LENGKAP TUGAS EXCEL (Random Forest – Bank Marketing)

Berikut adalah ringkasan semua langkah dari awal sampai selesai, termasuk rumus yang digunakan dan hasil akhir sesuai file **Tugas_RPL.xlsx** kamu.

---

### 📝 LANGKAH 1 – Memeriksa kondisi prediksi terhadap label aktual
**Lokasi:** Baris 4–104 (kolom A–G)

| Kolom | Header | Rumus (di baris 5, tarik ke bawah) |
| :--- | :--- | :--- |
| **D** | TP (True Positive) | `=IF(AND(B5=1;C5=1);1;0)` |
| **E** | TN (True Negative) | `=IF(AND(B5=0;C5=0);1;0)` |
| **F** | FP (False Positive) | `=IF(AND(B5=0;C5=1);1;0)` |
| **G** | FN (False Negative) | `=IF(AND(B5=1;C5=0);1;0)` |

**Hasil akhir Langkah 1:**
- TP = 5
- TN = 81
- FP = 2
- FN = 12

---

### 📊 LANGKAH 2 – Hitung total TP, TN, FP, FN
**Lokasi:** Baris 110–115 (kolom A–B)

| KETERANGAN | NILAI | Rumus |
| :--- | :--- | :--- |
| **TP** | 5 | `(=SUM(D6:D106))` |
| **TN** | 81 | `(=SUM(E6:E106))` |
| **FP** | 2 | `(=SUM(F6:F106))` |
| **FN** | 12 | `(=SUM(G6:G106))` |
| **Total Data**| 100 | `=COUNTA(B5:B104)` |

---

### 📈 LANGKAH 3 – HITUNG METRIK EVALUASI
**Lokasi:** Baris 119–122 (kolom A–B)

| METRIK | RUMUS (NILAI) | Hasil Akhir |
| :--- | :--- | :--- |
| **ACCURACY** | `=(B111+B112)/B115` | **86,00%** |
| **PRECISION** | `=B111/(B111+B113)` | **71,43%** |
| **RECALL** | `=B111/(B111+B114)` | **29,41%** |
| **F1-SCORE** | `=2*B120*B121/(B120+B121)` | **41,67%** |

> [!NOTE]
> Blok sel B119:B122 → **Format Cells** → **Percentage** → **2 decimal places**.

---

### 💡 LANGKAH 4 – INTERPRETASI HASIL
**Lokasi:** Baris 124 ke bawah

Berdasarkan data contoh:
- **TP = 5** (langganan terprediksi benar)
- **TN = 81** (tidak langganan terprediksi benar)
- **FP = 2** (tidak langganan salah dianggap langganan)
- **FN = 12** (langganan lolos / tidak terdeteksi)

**Analisis Metrik:**
*   **Accuracy = 86%**: Model cukup akurat secara keseluruhan.
*   **Recall = 29,41% (Rendah)**: Banyak nasabah potensial yang terlewat (FN tinggi).
*   **Precision = 71,43% (Baik)**: Ketika model memprediksi "langganan", cukup sering benar.
*   **Kesimpulan**: Hasil ini bisa digunakan untuk membandingkan algoritma lain.

---

### 🎨 LANGKAH 5 – VISUALISASI (OPSIONAL)
**Lokasi:** Baris 140 ke bawah

#### Confusion Matrix
| | Pred Pos | Pred Neg |
| :--- | :---: | :---: |
| **Aktual Pos** | 5 | 12 |
| **Aktual Neg** | 2 | 81 |

**Cara Membuat di Excel:**
1.  **D142:** Pred Pos | **E142:** Pred Neg
2.  **D143:** Aktual Pos | **E143:** `=B111` | **F143:** `=B114`
3.  **D144:** Aktual Neg | **E144:** `=B113` | **F144:** `=B112`

#### Visualisasi Tambahan:
*   **Pie Chart**: Tampilkan proporsi TP, TN, FP, FN.
    - Blok 2 kolom: Keterangan (TP, TN, FP, FN) dan Nilai (5, 81, 2, 12).
    - `Insert` → `Charts` → `Pie` → `2D Pie`.
*   **Conditional Formatting**: Gunakan warna **Hijau** untuk benar (TP & TN) dan **Merah** untuk salah (FP & FN).

---

🚀 **Semua langkah sudah selesai dan sesuai dengan file Tugas_RPL.xlsx!**

- Langkah 1–3: Rumus sudah benar dan otomatis.
- Langkah 4–5: Interpretasi dan visualisasi sudah lengkap.

Selamat! Tugasmu sudah selesai. 🚀

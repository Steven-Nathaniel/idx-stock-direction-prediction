# Prediksi Arah Pergerakan Harga Saham IDX

Proyek kelompok (3 orang) mata kuliah Data Modeling, Universitas Multimedia Nusantara.

**Tools:** Python · Pandas · NumPy · scikit-learn · Matplotlib
**Metodologi:** CRISP-DM · **Jenis masalah:** binary classification

## Tujuan
Memprediksi apakah harga penutupan saham akan **naik pada hari perdagangan berikutnya**, berdasarkan data perdagangan yang tersedia di akhir hari ini.

## Data
- 831.622 baris data harian dari **938 saham** IDX (Januari 2020 – Mei 2024)
- 54.413 baris duplikat dihapus → 777.209 baris bersih

## Langkah
1. **Data preparation:** standardisasi tanggal, penghapusan duplikasi, penanganan nilai ekstrem tanpa data leakage.
2. **Feature engineering:** 21 fitur (return dan lag return, volume, nilai transaksi, moving average, volatilitas, rentang intraday, aktivitas investor asing).
3. **Pembagian data kronologis:** 70% train, validasi, dan test berdasarkan tanggal.
4. **Modelling:** Dummy Baseline, Logistic Regression, Decision Tree, dan dua konfigurasi Random Forest.
5. **Evaluasi:** ROC-AUC sebagai metrik utama, threshold dipilih berdasarkan balanced accuracy.

## Hasil
| Model | ROC-AUC (validasi) |
|---|---|
| Random Forest A | **0,698** |
| Random Forest B | 0,697 |
| Decision Tree | 0,674 |
| Logistic Regression | 0,668 |
| Dummy Baseline | 0,500 |

Model terbaik (Random Forest) mencapai **ROC-AUC 0,707** dan balanced accuracy 0,654 pada **test set**.

## File
- `idx_stock_prediction.ipynb` – notebook lengkap dengan output

*Dataset tidak disertakan karena ukurannya besar (±95 MB).*

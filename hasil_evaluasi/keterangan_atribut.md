# Keterangan Atribut pada File CSV Hasil Evaluasi

Berikut penjelasan makna setiap kolom (atribut) pada file CSV di folder `hasil_eval`:

| Kolom              | Deskripsi                                                                                  |
|--------------------|--------------------------------------------------------------------------------------------|
| **id**             | Identifier unik skenario/pertanyaan (sesuai dengan `id` pada Ground Truth).               |
| **category**       | Kategori skenario (contoh: K-1, K-2, dst.).                                                  |
| **type**           | Tipe luaran yang diharapkan (contoh: `schedule_rows`, `lecturer_list`, `aggregation`).      |
| **tp**             | True Positives — jumlah elemen yang diprediksi benar dan sesuai dengan Ground Truth.       |
| **fp**             | False Positives — jumlah elemen yang diprediksi tetapi tidak ada atau salah.                |
| **fn**             | False Negatives — jumlah elemen yang seharusnya diprediksi tetapi terlewat.                 |
| **precision**      | Precision = tp / (tp + fp). Proporsi prediksi benar dari keseluruhan prediksi.             |
| **recall**         | Recall = tp / (tp + fn). Proporsi elemen benar yang berhasil diprediksi.                    |
| **f1**             | F1-score = 2*(precision*recall)/(precision+recall). Rata-rata harmonis precision dan recall. |
| **exact_match**    | 1 jika hasil prediksi sama persis dengan Ground Truth (semua elemen cocok), else 0.        |
| **n_ground_truth** | Jumlah elemen pada Ground Truth untuk skenario tersebut.                                   |
| **n_pred**         | Jumlah elemen yang dihasilkan (diprediksi) oleh model.                                      |
| **prompt**         | Kalimat atau instruksi yang diberikan ke model (query/pertanyaan).                         |
| **timestamp**      | Waktu eksekusi permintaan ke model (ISO-8601).                                             |
| **latency_s**      | Waktu respons model dalam detik (latensi).                                                 |
| **prompt_tokens**  | Jumlah token yang dikirim sebagai prompt.                                                  |
| **completion_tokens** | Jumlah token yang dihasilkan model sebagai jawaban (completion).                         |
| **total_tokens**   | Total token yang digunakan (prompt + completion).                                          |
| **source**         | Sumber data yang diuji: `txt_source` atau `json_source`.                                   |
| **error_notes**    | Catatan jika terjadi error saat eksekusi; kosong jika tidak ada error.                      |

> **Catatan:**
> - File CSV tertentu memisahkan hasil evaluasi berdasarkan dua sumber (`txt_source` dan `json_source`).
> - Pastikan format dan urutan kolom sesuai dengan spesifikasi agar skrip analisis dan visualisasi berjalan lancar.

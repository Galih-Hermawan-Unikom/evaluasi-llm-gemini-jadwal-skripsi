# Riset Ekstraksi dan Evaluasi LLM Jadwal Skripsi

Repositori ini berisi data, skenario, dan hasil eksperimen pada riset evaluasi model Large Language Model (LLM) untuk ekstraksi informasi jadwal seminar dan sidang skripsi dari data terstruktur dan tidak terstruktur.

## Struktur Folder

| Folder            | Deskripsi Singkat                                                                                          |
|-------------------|-----------------------------------------------------------------------------------------------------------|
| `data_konteks`    | File `.json` dan `.txt` berisi jadwal setiap pekan, dikelompokkan berdasarkan jenis kegiatan dan semester. Data ini digunakan sebagai konteks dalam prompt yang dikirim ke LLM. |
| `db`              | File database SQLite (`.db`) berisi data hasil ekstraksi, digunakan untuk membantu pembuatan ground-truth. |
| `ground-truth`    | File `ground_truth.jsonl` berisi jawaban kunci (ground truth) untuk setiap skenario uji.                  |
| `hasil_evaluasi`  | File `.csv` hasil rekapitulasi evaluasi model, mencakup metrik seperti precision, recall, F1-score, dll.  |
| `model_outputs`   | Subfolder per model (misal: `gemini-2.0-flash-lite`, `gemini-2.0-flash`, `gemini-2.5-flash-preview-05-20`), berisi file JSON hasil run LLM untuk setiap skenario (`nomor_id_skenario.json`). |
| `pdf`             | File PDF jadwal seminar/sidang asli, sebagai sumber data tidak terstruktur.                                |
| `skenario`        | File `.jsonl` berisi daftar skenario atau pertanyaan uji, termasuk metadata terkait eksperimen.           |

## Alur Umum Eksperimen

1. **Data PDF** jadwal seminar/sidang diekstraksi menjadi data terstruktur dan tidak terstruktur.
2. **Data konteks** dari `data_konteks` disisipkan dalam prompt untuk LLM.
3. **Skenario uji** dari folder `skenario` digunakan untuk menjalankan pertanyaan ke model.
4. **Model LLM** menghasilkan output yang disimpan di folder `model_outputs` (dipisah per model).
5. **Ground truth** disiapkan dalam format `.jsonl` di folder `ground-truth`.
6. **Evaluasi otomatis** dilakukan dengan membandingkan output model dan ground truth, hasilnya direkap di folder `hasil_evaluasi`.

## Catatan

- Seluruh data disusun untuk mendukung eksperimen replikasi dan evaluasi model ekstraksi LLM.
- Struktur dan format file mengikuti standar internal riset agar mudah diproses secara batch.

---

**Tim Riset:** AkaBot Research Group  
**Kontributor:** Galih Hermawan, Ednawati Rainarli  
Program Studi Teknik Informatika, Fakultas Teknik dan Ilmu Komputer  
Universitas Komputer Indonesia

**Email:** akabot.unikom@gmail.com

_Last Updated: 2 Juni 2025_

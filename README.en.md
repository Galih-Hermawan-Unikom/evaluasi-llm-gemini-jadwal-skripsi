🌐 *Baca dalam [Bahasa Indonesia](README.md)*

# LLM Thesis Schedule Extraction and Evaluation Research

This repository contains data, scenarios, and experimental results for evaluating Large Language Model (LLM) performance in extracting thesis seminar and defense schedule information from structured and unstructured data.

### Research Infographic

![LLM Thesis Schedule Infographic](infografis%20llm%20jadwal%20skripsi.png)

*Figure: Visual summary of the LLM evaluation experiment workflow for thesis schedule extraction*

## Folder Structure

| Folder            | Description                                                                                          |
|-------------------|------------------------------------------------------------------------------------------------------|
| `data_konteks`    | `.json` and `.txt` files containing weekly schedules, grouped by event type and semester. Used as context in prompts sent to LLM. |
| `db`              | SQLite database file (`.db`) containing extracted data, used to assist ground-truth creation. |
| `ground-truth`    | `ground_truth.jsonl` file containing answer keys (ground truth) for each test scenario.                  |
| `hasil_evaluasi`  | `.csv` files with evaluation results summary, including metrics such as precision, recall, F1-score, etc.  |
| `model_outputs`   | Subfolders per model (e.g., `gemini-2.0-flash-lite`, `gemini-2.0-flash`, `gemini-2.5-flash-preview-05-20`), containing JSON output files from LLM runs for each scenario (`scenario_id_number.json`). |
| `pdf`             | Original seminar/defense schedule PDF files, as unstructured data source.                                |
| `skenario`        | `.jsonl` file containing test scenarios or questions, including experiment-related metadata.           |

## General Experiment Workflow

1. **PDF Data** of seminar/defense schedules is extracted into structured and unstructured data.
2. **Context data** from `data_konteks` is inserted into prompts for the LLM.
3. **Test scenarios** from the `skenario` folder are used to run queries to the model.
4. **LLM models** generate outputs stored in the `model_outputs` folder (separated by model).
5. **Ground truth** is prepared in `.jsonl` format in the `ground-truth` folder.
6. **Automated evaluation** is performed by comparing model outputs with ground truth, results are summarized in the `hasil_evaluasi` folder.

## Notes

- All data is organized to support replication experiments and LLM extraction model evaluation.
- File structure and format follow internal research standards for easy batch processing.
- **Code Availability:** Currently, this repository focuses on presenting datasets and evaluation results. The source code used to run experiments and evaluations is being cleaned up and will be uploaded soon.

## Citation

If you use this data or refer to this research, please use the following citation format:

```bibtex
@article{Hermawan2025Evaluasi,
  author       = {Hermawan, Galih and Rainarli, Ednawati},
  title        = {Evaluasi Gemini Flash pada Ekstraksi Jadwal Skripsi Terstruktur dan Tidak Terstruktur},
  journal      = {Jurnal Informatika: Jurnal Pengembangan IT},
  volume       = {10},
  number       = {4},
  pages        = {1080--1091},
  year         = {2025},
  doi          = {10.30591/jpit.v10i4.9047},
  url          = {https://ejournal.poltekharber.ac.id/index.php/informatika/article/view/9047},
  issn         = {2477-5126},
  note         = {Open Access, CC BY 4.0}
}
```

---

**Research Team:** AkaBot Research Group  
**Contributors:** [Galih Hermawan](https://galih.eu), Ednawati Rainarli  
Department of Informatics Engineering, Faculty of Engineering and Computer Science  
Universitas Komputer Indonesia

**Email:** akabot.unikom@gmail.com

**Youtube:** [https://youtu.be/LTHHgxHS9yY](https://youtu.be/LTHHgxHS9yY)

_Last Updated: December 15, 2025_

[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112911&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** kimkhangwork@gmail.com
**Name:** Phùng Kim Khang

---

## Mo ta

Day la bai lab Data Pipeline & Data Observability. Em da hoan thanh pipeline ETL trong `solution.py` gom 4 buoc: extract du lieu tu `raw_data.json`, validate de loai record loi, transform du lieu bang cach chuan hoa category va tinh discounted_price, sau do load ket qua ra `processed_data.csv`.

Pipeline cung in log so record duoc extract, so record hop le, so record bi loai va so record da xu ly. Output co them cot `processed_at` de theo doi thoi diem du lieu duoc xu ly.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Ket qua voi `raw_data.json`:

- Extracted: 5 records
- Valid: 3 records
- Dropped/Errors: 2 records
- Loaded: 3 records vao `processed_data.csv`

Hai record bi loai vi co `price <= 0` hoac `category` rong. Cac record hop le duoc them `discounted_price = price * 0.9`, category duoc chuan hoa Title Case va them timestamp `processed_at`.

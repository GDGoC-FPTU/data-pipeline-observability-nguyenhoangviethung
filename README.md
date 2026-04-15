[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574093&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** AI20K-202600164
**Student Email:** nguyenhoangviethung@gmail.com
**Name:** Nguyen Hoang Viet Hung

---

## Mo ta

Bai lab nay xay dung ETL pipeline don gian voi 4 buoc: extract, validate, transform, load.
Pipeline doc du lieu tu JSON, loai bo record khong hop le (price <= 0 hoac category rong),
chuan hoa category sang Title Case, tinh cot discounted_price, va them timestamp processed_at.
Sau do, ket qua duoc luu ra processed_data.csv de phuc vu truy van cua agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
# Neu dung conda env theo bai lam nay
conda activate vinAssignment
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
/home/bear/miniconda3/envs/vinAssignment/bin/python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
/home/bear/miniconda3/envs/vinAssignment/bin/python generate_garbage.py
/home/bear/miniconda3/envs/vinAssignment/bin/python agent_simulation.py
```

### Chay autograder local
```bash
/home/bear/miniconda3/envs/vinAssignment/bin/python -m pytest -q
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

- ETL da doc 5 records tu raw_data.json.
- Validation giu lai 3 records hop le va drop 2 records loi.
- processed_data.csv duoc tao thanh cong voi cac cot: id, product, price, category, discounted_price, processed_at.
- Agent voi clean data tra loi hop ly (chon Laptop gia 1200.0).
- Agent voi garbage data bi danh lua boi outlier (chon Nuclear Reactor gia 999999).
- Kiem thu tu dong: 9/9 tests passed.

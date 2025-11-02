# Customer Churn Prediction - Telco

## Deskripsi
Project ini memprediksi pelanggan yang berpotensi **churn** dalam 30 hari ke depan menggunakan dataset Telco.  
Model sudah dilatih (Random Forest) dan siap pakai untuk inferensi pelanggan baru.

## Struktur Folder
```

mechine-learning/
│
├─ notebook/           # Notebook Jupyter
│   └─ churn_analysis.ipynb
├─ data/               # Dataset
│   └─ churn_cleaned.csv
├─ models/             # Model hasil training
│   └─ model.pkl
├─ requirements.txt    # Library Python
└─ README.md

````

## Install Dependencies
Buat virtual environment baru, lalu install dependencies:
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Mac/Linux
source venv/bin/activate

pip install -r requirements.txt
````

### Contoh isi `requirements.txt`

```
pandas
numpy
scikit-learn
joblib
plotly
matplotlib
```

## Cara Menjalankan Notebook

1. Pastikan folder `data/` dan `models/` ada.
2. Notebook sudah menggunakan **relative path**, jadi cukup buka di VSCode / Jupyter:

```python
df = pd.read_csv("../data/churn_cleaned.csv")
model = load("../models/model.pkl")
```

3. Jalankan semua sel notebook dari atas ke bawah tanpa error.

## Contoh Menggunakan Model untuk Prediksi

```python
from joblib import load

# Load model
model = load("../models/model.pkl")

# Data pelanggan baru
data_new = {
    "age": 30,
    "income": 35000,
    "tenure_months": 12,
    "monthly_spend": 15.0,
    "support_tickets": 1,
    "has_app": 1,
    "last_login_days": 5,
    "satisfaction_score": 4,
    "region": "B",
    "contract_type": "month-to-month",
    "payment_method": "card"
}

# Prediksi
result = predict_one(data_new)
print(result)
```

* `prediction = 0` → pelanggan **tidak churn**
* `prediction = 1` → pelanggan **churn**
* `proba` → probabilitas churn (0-1)

## Upload / Clone dari GitHub

```bash
# Clone repository
git clone https://github.com/Hmzharf/mechine-learning.git
cd mechine-learning

# Commit dan push
git add .
git commit -m "Initial commit"
git push origin main
```

## Catatan

* Notebook dan model sudah siap pakai.
* Gunakan **VSCode atau Jupyter** untuk menjalankan notebook.
* Folder `data/` dan `models/` harus ada untuk notebook berjalan lancar.
* Install library di `requirements.txt` agar tidak error.


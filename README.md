# Major Project (NLP)

This repository contains two main parts:

1. **Flask web app** for language detection (ready to run):  
   `FlaskLinguaDetect-20260110T063824Z-1-001/FlaskLinguaDetect`
2. **Backend / ML notebook code** (training + evaluation + plots):  
   `Backend code/Main.ipynb`

---

## 1) Flask Language Detection Web App (recommended)

### What it does

- Detects language from user text using `langdetect`
- Shows:
  - **Existing** (simulated) detection results
  - **Proposed** (real) detection results + top alternatives
- Dashboard + visualization pages
- Optional translation to English (best-effort) if `googletrans` is installed

### Prerequisites

- Windows 10/11
- Python **3.7+** installed and added to PATH

### Quick start (Windows script)

1. Open this folder:
   - `FlaskLinguaDetect-20260110T063824Z-1-001/FlaskLinguaDetect`
2. Run **one** of the scripts:
   - Double-click `run.bat` (CMD)
   - Or right-click `run.ps1` → **Run with PowerShell**
3. Open the app in your browser:
   - `http://localhost:5000`

What the scripts do:

- Create a virtual environment in `venv/` (if missing)
- Install dependencies from `requirements.txt`
- Start the Flask server

### Manual setup (any OS)

From inside `FlaskLinguaDetect-20260110T063824Z-1-001/FlaskLinguaDetect`:

```bash
python -m venv venv
```

Activate:

- Windows (PowerShell):

```bash
venv\Scripts\Activate.ps1
```

- Windows (CMD):

```bash
venv\Scripts\activate.bat
```

- macOS/Linux:

```bash
source venv/bin/activate
```

Install deps:

```bash
pip install -r requirements.txt
```

Run:

```bash
python app.py
```

### Routes (pages)

- `/` Home
- `/predict_existing` Existing (simulated) method
- `/predict_proposed` Proposed (real) method
- `/dashboard` Statistics dashboard
- `/visualization` Charts/visualizations

### Optional: enable translation

The proposed predictor tries to translate input text to English if `googletrans` is installed.

```bash
pip install googletrans
```

If you don’t install it, the app still runs (translation is simply skipped).

### Troubleshooting

- **PowerShell blocks `run.ps1`**: run PowerShell as admin and execute:

```bash
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

- **Port 5000 already in use**: close the other app using port 5000, or change the port in `app.py` (last line).
- **Text too short**: enter at least 3 characters for reliable detection.

---

## 2) Backend / Model Notebook (`Backend code`)

### What it contains

- `Backend code/Main.ipynb`: end-to-end notebook (data loading, preprocessing, modeling, evaluation)
- Helper modules:
  - `Backend code/metrics_calculator.py` (metrics, confusion matrix, ROC, reports)
  - `Backend code/graphs.py` (overall + per-class plots)
- Outputs typically saved under:
  - `Backend code/results/`

### Prerequisites

- Python 3.9+ recommended (TensorFlow / PyTorch / Transformers work best on newer Python)
- Jupyter (Notebook or Lab)

### Setup (recommended: separate environment)

From the repo root:

```bash
python -m venv venv-ml
```

Activate it (same commands as above), then install core packages used by the notebook (install may take time):

```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy joblib tqdm
pip install nltk wordcloud
pip install tensorflow torch transformers
```

Then start Jupyter:

```bash
pip install notebook
jupyter notebook
```

Open `Backend code/Main.ipynb` and run cells from top to bottom.

### NLTK resources (if the notebook asks for them)

If you get NLTK lookup errors (common on first run), run this in a notebook cell:

```python
import nltk
nltk.download("punkt")
nltk.download("stopwords")
nltk.download("wordnet")
nltk.download("averaged_perceptron_tagger")
```

---

## Repo structure (high level)

```
Project NLP/
├── Backend code/
│   ├── Main.ipynb
│   ├── metrics_calculator.py
│   ├── graphs.py
│   ├── Dataset/
│   ├── model/
│   └── results/
└── FlaskLinguaDetect-20260110T063824Z-1-001/
    └── FlaskLinguaDetect/
        ├── app.py
        ├── forms.py
        ├── requirements.txt
        ├── run.bat
        ├── run.ps1
        ├── static/
        └── templates/
```
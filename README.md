# DBLP Research DNA — CS Topic Drift Analysis

Analyzing the DBLP V10 dataset (AMiner) to track how CS research areas emerge, converge, and drift over time. We build TF-IDF "Research DNA" fingerprints for 6 venues and visualize how they relate and shift.

**Venues:** ICML, KDD, SIGMOD, CVPR, ACL, VLDB

**Team:** Elvin, Carlos, Kelvin

---

## Workstreams

| Notebook | Owner | Task | Depends on |
|---|---|---|---|
| `notebooks/A1_preprocessing.ipynb` | Elvin | Load & merge DBLP data, build TF-IDF matrix, PCA | nothing |
| `notebooks/A2_eda.ipynb` | Elvin | EDA: distributions, keyword heatmaps, PCA scatterplot | A1 outputs |
| `notebooks/A3_coauthor_network.ipynb` | Elvin | Co-author graph, bridge authors, venue communities | A1 outputs |
| Carlos's notebooks | Carlos | — | — |
| Kelvin's notebooks | Kelvin | — | — |

**Run A1 first.** Its outputs land in `data/processed/` and everything else reads from there.

---

## Project Structure

```
DataScienceProject/
├── data/
│   ├── raw/          # DBLP JSON files — download from Drive (gitignored)
│   └── processed/    # A1 outputs — download from Drive if you didn't run A1 (gitignored)
├── notebooks/
│   ├── A1_preprocessing.ipynb
│   ├── A2_eda.ipynb
│   ├── A3_coauthor_network.ipynb
│   └── ...           # Carlos and Kelvin's notebooks
├── requirements.txt
└── README.md
```

---

## Setup

**1. Clone the repo**
```bash
git clone <repo-url>
cd DataScienceProject
```

**2. Create a virtual environment and install dependencies**
```bash
python -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

**3. Get the data from Google Drive**

Download the shared folder: [Google Drive link — https://drive.google.com/drive/folders/1Y4yNgBS_FNa3TtDQS7rWfVbRlQYFKSl1?usp=drive_link]

- Put the 4 DBLP JSON files (`dblp-ref-0.json` through `dblp-ref-3.json`) in `data/raw/`
- If you're not running A1 yourself, also download the `processed/` folder and put it in `data/processed/`

**4. Open the notebook you're working on in Jupyter or VS Code**

---

## Data

Raw data is from the [DBLP-Citation-network V10](https://www.aminer.org/citation) dataset (~3.2M papers). We sample up to 3,000 papers per venue (~18k total) and filter to the 6 venues above.

Raw and processed files are gitignored — share via Google Drive only.

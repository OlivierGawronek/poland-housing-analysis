# poland-housing-analysis
Exploratory data analysis and price prediction of Polish real estate market based on Otodom listings data.

## Dataset

Source: [Otodom Poland Real Estate Listings](https://github.com/luminati-io/Otodom-Poland-dataset-samples) (6,252 records)

| Column | Description |
|--------|-------------|
| `price` | Asking price in PLN |
| `surface` | Living area in m² |
| `location` | Full address (street, city, voivodeship) |
| `no_of_rooms` | Number of rooms |
| `market` | Primary or secondary market |
| `form_of_property` | Property type (apartment, house, etc.) |
| `advertiser_type` | Agency or private seller |
| `description` | Full listing description |
| `title` | Listing title |
| `lighting` | Lighting features |
| `remote_support` | Remote support availability |
| `is_for_sale` | Boolean - currently for sale |
| `timestamp` | Date recorded |
| `posting_id` | Unique listing ID |

## Tech Stack

- Python 3.10+
- pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn

## Setup

```bash
git clone https://github.com/OlivierGawronek/poland-housing-analysis.git
cd poland-housing-analysis
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

## Project Structure

```
├── data/raw/              Raw Otodom data
├── data/processed/        Cleaned data
├── notebooks/             Jupyter notebooks
├── src/                   Source code modules
└── results/figures/       Charts and visualizations
```

## Notebooks

| # | Notebook | Description |
|---|----------|-------------|
| 1 | `01_data_cleaning.ipynb` | Loading, inspecting, cleaning raw data |
| 2 | `02_eda.ipynb` | Exploratory data analysis, visualizations |
| 3 | `03_feature_engineering.ipynb` | Creating new features, encoding |
| 4 | `04_modeling.ipynb` | ML models, evaluation, comparison |

## Results

Best model: **Gradient Boosting Regressor**

| Model | MAE (PLN) | RMSE (PLN) | R² |
|-------|-----------|------------|-----|
| Gradient Boosting | 173,760 | 240,165 | 0.4687 |
| Linear Regression | 189,887 | 253,638 | 0.4074 |
| Random Forest | 187,172 | 260,215 | 0.3763 |
| Decision Tree | 275,905 | 365,244 | -0.2289 |

### Key Findings
- Surface area is the strongest predictor of price
- Gradient Boosting outperforms other models with R² = 0.47
- Decision Tree overfits heavily on small dataset (502 rows)
- Location (voivodeship, city) significantly impacts price

## Progress

- [x] Load and inspect data
- [x] Data cleaning
- [x] EDA and visualizations
- [x] Feature engineering
- [x] Modeling
- [x] Document results

## License

[MIT](LICENSE)
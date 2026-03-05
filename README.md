cat > README.md << 'EOF'
# Real Estate Market EDA (Pricing Drivers + Practical Insights)

**Industry:** Real Estate  
**Project type:** Exploratory Data Analysis (EDA) + optional baseline regression  
**Goal:** Identify the strongest drivers of home sale price and translate findings into practical pricing guidance.

## Business Problem
Pricing decisions are often driven by intuition and inconsistent comps. This project analyzes residential property data to:
- identify variables most associated with sale price
- detect outliers and missingness that distort comparisons
- (optional) benchmark a simple baseline model against a naive median baseline

## Dataset
Kaggle House Prices (Ames Housing) — using `train.csv`.

Local convention:
- store the dataset at `data/ames.csv`
- **do not commit** the full dataset to GitHub

See `data/README_data_sources.md` for notes.

## Artifacts
Key visuals will be saved in `/images/`:
- `price_distribution.png`
- `price_vs_liv_area.png`
- `missingness_summary.png`

## How to Run
```bash
pip install -r requirements.txt
jupyter lab

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

 ## Key Insights (EDA)
- **Quality dominates price:** `OverallQual` shows the strongest relationship with `SalePrice` (corr ~0.79), suggesting finish/build quality is a top pricing lever.
- **Livable space is the next biggest driver:** `GrLivArea` is strongly associated with price (corr ~0.71); larger above-ground living area typically commands higher prices.
- **Garages matter more than many people expect:** both `GarageCars` (corr ~0.64) and `GarageArea` (corr ~0.62) rank among the strongest predictors.
- **Total usable square footage drives value:** `TotalBsmtSF` (corr ~0.61) and `1stFlrSF` (corr ~0.61) reinforce that overall space—not just room count—matters.
- **Newer / updated homes trend higher:** `YearBuilt` (corr ~0.52) and `YearRemodAdd` (corr ~0.51) indicate age and renovations are meaningful pricing signals.



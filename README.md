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

- # Real Estate Market EDA (Ames Housing) — Pricing Drivers + Neighborhood Effects

**Industry:** Real Estate  
**Project type:** Exploratory Data Analysis (EDA)  
**Dataset:** Kaggle House Prices (Ames Housing) — `train.csv` stored locally as `data/ames.csv`  
**Goal:** Identify the strongest pricing drivers and show how neighborhood segmentation changes pricing expectations.

## Business Problem
Pricing decisions often rely on intuition and inconsistent comps. This project analyzes residential housing data to:
- identify the highest-signal features associated with `SalePrice`
- highlight missingness patterns that affect analysis/modeling
- demonstrate neighborhood-based price separation to support better comps and investment screening

## What I Did
1) **Data audit**
- reviewed dataset structure and missingness (percent missing by column)
2) **Price distribution**
- examined `SalePrice` distribution to understand central tendency and tail behavior
3) **Driver analysis**
- ranked numeric feature relationships with `SalePrice` using correlation as a quick signal check
4) **Neighborhood segmentation**
- compared price bands across the most common neighborhoods (boxplot) to show location premiums

## Key Insights (EDA)
- **Quality dominates price:** `OverallQual` shows the strongest relationship with `SalePrice` (corr ~0.79), indicating build/finish quality is a top pricing lever.
- **Livable space is the next biggest driver:** `GrLivArea` correlates strongly with price (corr ~0.71); larger above-ground living area generally commands higher prices.
- **Garages matter:** both `GarageCars` (corr ~0.64) and `GarageArea` (corr ~0.62) rank among the strongest predictors.
- **Total usable square footage drives value:** `TotalBsmtSF` (~0.61) and `1stFlrSF` (~0.61) reinforce that overall space—not just room count—matters.
- **Newer / updated homes trend higher:** `YearBuilt` (~0.52) and `YearRemodAdd` (~0.51) show that age and renovations are meaningful pricing signals.
- **Location premium is real:** neighborhood bands show clear separation. In this sample, `NridgHt` and `Crawfor` sit among the higher price bands, while `Sawyer` is notably lower—meaning neighborhood-aware comps are essential.

## Recommendations (Decision-Ready)
- **Price with neighborhood-aware comps:** use neighborhood as the first filter, then adjust with `OverallQual` and `GrLivArea`.
- **Renovation prioritization:** prioritize changes that improve perceived quality tier (not just minor cosmetics).
- **Investor screening rule:** triage deals using a small set of high-signal variables—`OverallQual`, `GrLivArea`, garage capacity, basement area—then validate using neighborhood comps.
- **Treat extreme properties as special cases:** large-livable-area outliers can distort comps and modeling; flag before using in decision-making.

## Artifacts
Saved to `/images/`:
- `missingness_summary.png` — Top 20 columns by missingness (%)
- `price_distribution.png` — Distribution of sale prices
- `price_vs_liv_area.png` — Relationship between living area and price
- `neighborhood_price_bands.png` — Price bands across top neighborhoods (median line = typical price; box = middle 50%; whiskers = typical range)
# Real Estate Market EDA (Ames Housing) — Pricing Drivers + Neighborhood Effects

**Industry:** Real Estate  
**Project type:** Exploratory Data Analysis (EDA)  
**Dataset:** Kaggle House Prices (Ames Housing) — `train.csv` stored locally as `data/ames.csv`  
**Goal:** Identify the strongest pricing drivers and show how neighborhood segmentation changes pricing expectations.

## Business Problem
Pricing decisions often rely on intuition and inconsistent comps. This project analyzes residential housing data to:
- identify the highest-signal features associated with `SalePrice`
- highlight missingness patterns that affect analysis/modeling
- demonstrate neighborhood-based price separation to support better comps and investment screening

## What I Did
1) **Data audit**
- reviewed dataset structure and missingness (percent missing by column)
2) **Price distribution**
- examined `SalePrice` distribution to understand central tendency and tail behavior
3) **Driver analysis**
- ranked numeric feature relationships with `SalePrice` using correlation as a quick signal check
4) **Neighborhood segmentation**
- compared price bands across the most common neighborhoods (boxplot) to show location premiums

## Key Insights (EDA)
- **Quality dominates price:** `OverallQual` shows the strongest relationship with `SalePrice` (corr ~0.79), indicating build/finish quality is a top pricing lever.
- **Livable space is the next biggest driver:** `GrLivArea` correlates strongly with price (corr ~0.71); larger above-ground living area generally commands higher prices.
- **Garages matter:** both `GarageCars` (corr ~0.64) and `GarageArea` (corr ~0.62) rank among the strongest predictors.
- **Total usable square footage drives value:** `TotalBsmtSF` (~0.61) and `1stFlrSF` (~0.61) reinforce that overall space—not just room count—matters.
- **Newer / updated homes trend higher:** `YearBuilt` (~0.52) and `YearRemodAdd` (~0.51) show that age and renovations are meaningful pricing signals.
- **Location premium is real:** neighborhood bands show clear separation. In this sample, `NridgHt` and `Crawfor` sit among the higher price bands, while `Sawyer` is notably lower—meaning neighborhood-aware comps are essential.

## Recommendations (Decision-Ready)
- **Price with neighborhood-aware comps:** use neighborhood as the first filter, then adjust with `OverallQual` and `GrLivArea`.
- **Renovation prioritization:** prioritize changes that improve perceived quality tier (not just minor cosmetics).
- **Investor screening rule:** triage deals using a small set of high-signal variables—`OverallQual`, `GrLivArea`, garage capacity, basement area—then validate using neighborhood comps.
- **Treat extreme properties as special cases:** large-livable-area outliers can distort comps and modeling; flag before using in decision-making.

## Artifacts
Saved to `/images/`:
- `missingness_summary.png` — Top 20 columns by missingness (%)
- `price_distribution.png` — Distribution of sale prices
- `price_vs_liv_area.png` — Relationship between living area and price
- `neighborhood_price_bands.png` — Price bands across top neighborhoods (median line = typical price; box = middle 50%; whiskers = typical range)

## How to Run
1) Install dependencies:
```bash
pip install -r requirements.txt




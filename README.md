@"
# End-to-End Airbnb Price Prediction

## What is this project?
Pricing an Airbnb listing is harder than it looks. Set it too high and guests scroll past. Set it too low and you leave money on the table. This project builds a machine learning model that predicts the right price for an Airbnb listing based on its features — location, property type, room type, amenities, cancellation policy, and more.

The goal is simple: give hosts a data-driven starting point for pricing their listings.

---

## How it works
1. **Data** — We used a real-world Airbnb dataset with 29 features covering property details, host information, location, and guest reviews
2. **Cleaning & Transformation** — Handled missing values, encoded categorical variables, and applied log transformation on price to reduce skew
3. **Model** — Trained a CatBoost Regressor, which handles categorical features natively and performs well on tabular data
4. **Deployment** — Wrapped the model in a Flask web app where you can input listing details and get a predicted price instantly
5. **CI/CD** — Dockerized the app and set up GitHub Actions for automated deployment

---

## Model Performance

| Metric | Score |
|--------|-------|
| R² Score | 0.7092 |
| RMSE | 0.3865 |
| MAE | 0.2805 |

> Prices are predicted in log scale (log_price). An R² of 0.71 means the model explains **71% of the variance** in Airbnb listing prices — strong performance for a real-world pricing dataset with high natural variability.

---

## Key Insights

- **Location is the strongest predictor** — city and neighbourhood had the highest impact on price
- **Room type matters more than property type** — an entire home commands significantly higher prices than a private or shared room regardless of property category
- **Cancellation policy signals quality** — listings with strict cancellation policies tend to be priced higher, likely reflecting higher-end properties
- **Host trust signals add value** — verified identity and profile pictures correlated with higher listing prices
- **Accommodates and bedrooms** — unsurprisingly, larger listings that sleep more guests price higher, but the relationship is non-linear

---

## Impact

- Helps **hosts price competitively** without undervaluing their listing
- Helps **guests identify fair deals** vs overpriced listings in a given area
- Demonstrates a full **production-ready ML pipeline** from raw data to deployed web app
- The model generalizes well across 6 major US cities present in the dataset

---

## Tech Stack

| Layer | Tools |
|-------|-------|
| Data Processing | Pandas, NumPy |
| Modeling | CatBoost, Scikit-learn |
| Web App | Flask |
| Frontend | HTML, CSS |
| Containerization | Docker |
| CI/CD | GitHub Actions |
| Experiment Tracking | DVC |

---

## Installation

### Option 1: Run from GitHub

```bash
git clone https://github.com/Thorvi01/End-to-end-Airbnb-price-prediction.git
cd End-to-end-Airbnb-price-prediction
pip install -r requirements.txt
python app.py
```

### Option 2: Run with Docker

```bash
docker pull thorvi01/airbnb-app
docker run -p 5000:5000 thorvi01/airbnb-app
```

---

## Contributing
Feel free to open an issue or submit a pull request if you have ideas to improve the model or add new features.

## Acknowledgements
Dataset sourced from Kaggle's Airbnb Price Prediction competition. Thanks to the open-source community behind CatBoost, Scikit-learn, and Flask.
"@ | Set-Content README.md

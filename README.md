# Flight Price Analysis and Prediction

Analyzing the key drivers of flight ticket pricing and building a regression model to predict fares across Indian domestic routes.

---

## Problem Statement

Flight prices in India vary dramatically based on airline, route, number of stops, time of booking, and travel class. For travelers and travel platforms alike, understanding what drives price differences and predicting fares accurately has real commercial value. This project explores those pricing patterns through EDA and builds a regression model to predict ticket prices.

---

## Dataset

- **Source:** Provided by Rubixe AI Solutions as part of a structured analytics project program
- **Size:** 10,683 flight records
- **Features:** Airline, source city, destination city, departure time, arrival time, stops, travel class, duration, days left before departure
- **Target:** Flight ticket price (continuous, in INR)

---

## Repository Structure

```
flight-price-analysis-prediction/
│
├── flight_price_analysis_prediction.ipynb    # Full analysis and modeling notebook
└── dataset.csv                               # Flight price dataset
```

---

## Approach

### 1. Data Cleaning
- Parsed unstructured duration strings (e.g. "2h 30m") into numeric minutes
- Consolidated inconsistent city name labels across source and destination columns
- Handled missing values and removed duplicates

### 2. Exploratory Data Analysis (EDA)
- Identified top pricing drivers: airline class, number of stops, and route duration
- Visualized price distributions across airlines, routes, and travel classes
- Analyzed how days left before departure affects ticket price
- Compared economy vs business class pricing patterns

### 3. Feature Engineering
- Encoded categorical variables (airline, cities, time of day)
- Created duration in minutes as a clean numeric feature
- Derived stop count as an ordinal feature

### 4. Model Building
- Algorithm: Random Forest Regressor
- Validation: 5-fold cross-validation
- Evaluation metrics: R² and Mean Absolute Error (MAE)

### 5. Feature Importance
- Extracted and visualized top predictors of price
- Used findings to generate route-level pricing recommendations

---

## Results

| Metric | Score |
|---|---|
| R² | 0.84 |
| MAE | ₹1,125 |
| Validation | 5-fold cross-validation |

The model explains 84% of variance in flight prices with an average prediction error of ₹1,125.

---

## Business Insights

- Business class tickets showed non-linear price jumps on specific high-demand routes
- Flights with 1 stop were priced significantly lower than direct flights on the same route in several cases, suggesting booking opportunities
- Ticket prices rose sharply within 7 days of departure across all airlines
- Route duration was among the top 3 predictors of price, outweighing airline brand in several segments

---

## Tech Stack

- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
- **Environment:** Jupyter Notebook

---

## How to Run

1. Clone the repository
   ```bash
   git clone https://github.com/Chethans246/flight-price-analysis-prediction.git
   cd flight-price-analysis-prediction
   ```

2. Install dependencies
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn jupyter
   ```

3. Launch the notebook
   ```bash
   jupyter notebook flight_price_analysis_prediction.ipynb
   ```

---

## Key Learnings

- Raw text features like duration strings require careful parsing before they become useful model inputs
- R² alone can be misleading for regression; MAE in the actual unit (INR) gives a more honest picture of model usefulness
- Feature importance from tree-based models can directly translate into business recommendations, not just technical outputs

---

## Author

**Chethan S** — Data Analyst  
[LinkedIn](https://linkedin.com/in/chethan-s-69b71b241) • [GitHub](https://github.com/Chethans246)

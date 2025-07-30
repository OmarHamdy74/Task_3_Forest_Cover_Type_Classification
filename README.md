# Forest Cover Type Classification with Ensemble Models

## 1 · Project Overview
This notebook tackles the classic **Covertype** data‑set (581 k rows, 54 features) and builds predictive models that identify the *forest cover type* (spruce–fir, lodgepole pine, etc.) for each plot of land based purely on cartographic variables.

The end‑to‑end workflow follows five stages:

1. **Pre‑processing** – load *covtype.csv*, inspect missing values (with *missingno*), convert wilderness/soil to categorical dummies, and scale numerical columns.  
2. **EDA** – plot feature distributions, correlation heat‑maps, and hill‑shade interactions to uncover terrain patterns.  
3. **Model Building** – benchmark four algorithms out‑of‑the‑box: Logistic Regression, Decision Tree, Random Forest and XGBoost.  
4. **Hyper‑parameter Tuning** – use `GridSearchCV` to squeeze extra performance from Random Forest & XGBoost.  
5. **Evaluation & Insights** – compare accuracy, macro‑F1, and confusion matrices; analyse feature importances to see which landscape factors drive each cover type.

## 2 · Repository Structure
```

├── Forest\_Cover\_Type.ipynb  # main analysis notebook
├── covtype.csv              # raw data file (from UCI / Kaggle)
├── requirements.txt         # Python dependencies
└── README.md                # project documentation

````

## 3 · Quick Start
```bash
# 1 · clone the repo and enter it
git clone https://github.com/OmarHamdy74/Forest_Cover_Type.git
cd Forest_Cover_Type

# 2 · create a virtual environment and install requirements
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

# 3 · launch the notebook
jupyter lab Forest_Cover_Type.ipynb
````

Run the notebook cell‑by‑cell to reproduce every plot, metric and trained model.

## 4 · Results at a Glance

| Model               | Overall Accuracy | Macro‑F1 | Notes                                                        |
| ------------------- | ---------------- | -------- | ------------------------------------------------------------ |
| Logistic Regression |  ≈ 0.68          | 0.62     | linear baseline                                              |
| Decision Tree       |  ≈ 0.94          | 0.94     | perfect fit on train → overfits                              |
| **Random Forest**   |  ≈ 0.95          | **0.95** | strong balance of bias/var.                                  |
| XGBoost             |  ≈ 0.87          | 0.87     | fastest inference, top‑3 feats: Elevation, Slope, Soil\_Type |

> *Random Forest* achieved the best accuracy overall and is therefore selected as the production model, outperforming XGBoost.

> See notebook Section 5 for full confusion matrices and per‑class recall.

## 5 · Business Impact

Accurate cover‑type prediction enables forestry agencies to:

* **Prioritise conservation** of sensitive species (e.g. spruce‑fir stands at high elevation).
* **Optimise harvesting** routes by predicting terrain that favours lodgepole pine.
* **Model wildfire risk** by combining predicted cover with moisture indices.

## 6 · About the Author

**Omar Hamdy**

Email: [omarhamdy211@gmail.com](mailto:omarhamdy211@gmail.com) | [LinkedIn](https://linkedin.com/in/omar-hamdy-400961253) | [GitHub](https://github.com/OmarHamdy74)

```

---

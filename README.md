# CRO-BSI GBDT Prediction Calculator

Online calculator: https://cro-bsi.github.io/

Self-contained web calculator (`index.html` + `model.js`). No server and no external requests; all inputs are evaluated in the browser and never leave the user's device. **For research use only; not a medical device and not a substitute for clinical judgment.**

## Model
- Seven predictors: age, central venous catheter, refractory disease, COPD, cancer, B-cell count (/µl), neutrophil count.
- Gradient boosting (GBDT) classifier with Platt (sigmoid) calibration, scikit-learn 1.8.0.
- Risk strata: predicted probability < 57% = low risk; >= 57% = high risk (threshold stored in `model.js` as `risk_cutoff`).
- **Provenance:** the original server and model file were lost when the server was decommissioned. This model was **refitted** on the original training cohort with the same seven predictors; AUCs (training / internal test / external validation) are 0.912 / 0.827 / 0.900 versus 0.911 / 0.827 / 0.899 originally reported.
- Browser evaluation matches scikit-learn on all 2,254 study records (max absolute difference 2.2e-16).

## Repository contents
- `index.html`, `model.js` - the calculator. No patient-level data are included.

## Citation and license
See `CITATION.cff`. Released under the MIT License (`LICENSE`).

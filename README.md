# CRO-BSI GBDT Prediction Calculator (static build)

Self-contained web calculator: `index.html` + `model.js`. No server and no external requests; all inputs are evaluated in the browser and never leave the user's device.

- Model: seven-variable gradient boosting (GBDT) classifier with Platt calibration (scikit-learn 1.8.0), exported by `export_static.py`.
- Risk strata: predicted probability < 57% = low risk; >= 57% = high risk (threshold stored in `model.js` as `risk_cutoff`).
- Validation: probabilities evaluated in the browser match scikit-learn on all 2,254 study records (max absolute difference 2.2e-16).
- Hosting: any static host works (GitHub Pages, institutional web server, Zenodo archive). Open `index.html` directly to run it locally.

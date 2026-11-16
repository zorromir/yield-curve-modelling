# From Yield Curves to Bond Prices

*A small numerical study with the Vasicek model.*

How well can a simple stochastic interest-rate model describe an observed yield curve, and how can we use the model to price a bond option?

I use Dutch government bond yield data to fit the Vasicek model, simulate short-rate paths, and price European options on a zero-coupon bond. I then compare the fitted yield curve with a Nelson–Siegel specification. The aim is to explore what a basic model captures and where its limitations become visible.

## Results

- Vasicek yield-curve RMSE: **5.26 basis points**.
- Nelson–Siegel RMSE: **4.95 basis points**.
- Simulated bond-option call price: **0.013048**.
- Simulated bond-option put price: **0.000104**.

These are in-sample calibration results, not forecasts of future rates. The short-rate dynamics and bond-option valuation are under the risk-neutral measure.

## Files

- [`paper/From_Yield_Curves_to_Bond_Prices.pdf`](paper/From_Yield_Curves_to_Bond_Prices.pdf) — short paper.
- [`paper/main.tex`](paper/main.tex) — LaTeX source, with figures in `paper/figures/`.
- [`notebook/yield_curve_modelling.ipynb`](notebook/yield_curve_modelling.ipynb) — calculations and figures.
- [`data/dnb_yields_2022.csv`](data/dnb_yields_2022.csv) — yields used in the numerical exercises.

## Running the notebook

From the repository root:

```bash
python -m venv .venv
```

On Windows:

```powershell
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter notebook notebook/yield_curve_modelling.ipynb
```

Or open `notebook/yield_curve_modelling.ipynb` in VS Code and select a Python environment containing the packages from `requirements.txt`. Run the notebook top to bottom. The notebook expects `data/dnb_yields_2022.csv` to remain in the repository's `data` folder.

## Scope

This is a small educational numerical exploration developed from Valuation and Risk Management coursework. No historical interest-rate forecasting or out-of-sample model validation is attempted.

# Weather Prediction

A Python project comparing machine learning models for weather classification. The training script prepares tabular data, applies feature selection and generates evaluation reports. A separate Streamlit interface accepts weather measurements for prediction.

## What is included

- Data cleaning, label encoding and outlier filtering.
- Standardisation and feature selection with PCA, LDA and RFE.
- Comparisons of SVM, Random Forest, neural network and linear regression experiments.
- Confusion matrices, classification reports and saved model artefacts.

## Repository layout

- `main.py` — data preparation, model training and evaluation.
- `streamlit.py` — prediction interface.
- `requirements.txt` — existing dependency list.

## Run the training script

Use a Python virtual environment. In addition to the existing requirements, the training script needs pandas, matplotlib, seaborn and an Excel reader:

```bash
python -m pip install -r requirements.txt
python -m pip install pandas matplotlib seaborn openpyxl
python main.py
```

Before running, provide `veri_seti/traindata.xlsx` and `veri_seti/testdata.xlsx`. These datasets are not included in the repository. The last column is treated as the target label; the remaining feature columns must be suitable for numeric preprocessing.

Training writes its outputs to `results/`.

## Prediction interface

The interface expects the saved model and label encoder in `results/models/saved_models/`. It accepts temperature, dew point, humidity, wind speed and pressure.

The UI is an experimental component: its inputs are currently passed directly to the model, without the training scaler and feature selector. Align those preprocessing steps before relying on predictions. The local filename `streamlit.py` also conflicts with the package name; rename it (for example to `app.py`) before launching with `python -m streamlit run app.py`.

## Türkçe

Hava koşullarını sınıflandırmak için farklı makine öğrenmesi modellerini ve özellik seçimi yöntemlerini karşılaştırdığım bir projedir. Veri hazırlama, model eğitimi, değerlendirme raporları ve deneysel bir tahmin arayüzü içerir.

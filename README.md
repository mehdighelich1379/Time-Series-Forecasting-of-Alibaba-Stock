# Alibaba Stock Price Prediction using RNN, LSTM & GRU

This project focuses on predicting the stock price of Alibaba using Recurrent Neural Network architectures, including Simple RNN and a hybrid model combining LSTM and GRU.

---

## 📁 Dataset

- Source: Historical Alibaba stock data (includes Open, High, Low, Close, Volume)
- Format: CSV

---

## 📂 Project Structure

The project includes five Jupyter notebooks:

- Final_AliBaba_RNN_Close.ipynb
- Final_AliBaba_RNN_High.ipynb
- Final_AliBaba_RNN_Low.ipynb
- Final_AliBaba_RNN_Open.ipynb
- prediction.ipynb

---

## 🧠 Model Design

### 🔹 prediction.ipynb

- Input (X): [Low, High, Open, Close, Volume] of day *t*
- Output (y): [Low, High, Open, Close, Volume] of day *t+1*
- Window size: 60 days (i.e., the model looks back 60 days to predict the next day)
- Scaler: MinMaxScaler
- Architecture: Combined LSTM + GRU
- Loss Metric: MAE = 2.49

---

### 🔹 Other 4 Notebooks (Close, High, Low, Open)

Each notebook trains two separate models to predict one specific column, given all other features as input.

- X: All columns [Open, High, Low, Close, Volume]
- y: Only one of the columns (Close, High, Low, Open)
- Scaler: MinMaxScaler
- Window size: 60 days

#### 🔸 Architectures Compared:

| Model Type       | MAE (avg) |
|------------------|-----------|
| Simple RNN       | ~1.60     |
| LSTM + GRU Combo | ~1.40     |

> These results are consistent across all four notebooks.

---

## 🛠 Tools & Libraries

- Python
- TensorFlow / Keras
- NumPy, Pandas
- Scikit-learn
- Matplotlib

---

## 📊 Evaluation Metric

- Mean Absolute Error (MAE) was used as the primary metric to evaluate model performance.

---

## ✅ Conclusion

- The hybrid LSTM + GRU model consistently outperformed the Simple RNN in all tasks.
- Predicting a single target column yields significantly better accuracy than trying to predict all columns at once.
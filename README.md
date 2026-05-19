# Predictive Vehicle maintenance

This project develops a hybrid deep learning model for predictive vehicle maintenance using real OBD (On-Board Diagnostics) sensor data collected from commercial cars. The dataset contains over 120,000 data points with 17 features including Engine RPM, Throttle Position, Engine Load, MAF sensor, and Engine Coolant Temperature.
<p align="center">
  <img src="https://github.com/user-attachments/assets/4d4e9d7c-d724-477b-8c01-b5c3b68872a3" width="600"/>
</p>

<p align="center">
  <b>Methodology  Workflow</b>
</p>


The core approach combines LSTM (Long Short-Term Memory) neural networks with K-Means clustering to predict engine health without requiring labeled failure data. K-Means first groups sensor readings into 2 operational clusters — low throttle/low RPM and high throttle/high RPM — and these cluster labels are fed as engineered features into the LSTM pipeline. Preprocessing involved MinMax Scaling, Robust Scaling for outlier-resistant features, and 30-step sequence windowing to capture temporal patterns.
<p align="center">
  <img src"https://github.com/user-attachments/assets/d561cd95-3bf7-44d4-b1b3-01a17206e099" width="600"/>
</p>

<p align="center">
  <b>Heatmap of correlation matrix of the selected features</b>
</p>

The model architecture uses two LSTM layers with 76 units each, dropout regularization (0.2 and 0.5), and was trained over 10,000 epochs with a 70/30 train-test split. Performance was evaluated using MAE, RMSE, and R² metrics across four OBD features.
The hybrid model achieved an R² score of 97.5% on engine load prediction, significantly outperforming standalone LSTM (89.8%), GRU (89.6%), and RNN (90.1%) baselines. The final model is lightweight at just 0.31 MB with an inference time of 18–25 ms, making it suitable for real-time embedded vehicle deployment.
<p align="center">
  <img src="https://github.com/user-attachments/assets/19ac006d-db7f-4816-b3c2-bab7825c6c9e" width="600"/>
</p>

<p align="center">
  <b>True vs. Predicted values</b>
</p>




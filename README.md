# Intrusion Detection System using Machine Learning and SOAR

This project implements a basic Intrusion Detection System (IDS) using the NSL-KDD dataset and a machine learning model (Random Forest) for binary classification (Normal vs Attack). It also features an automated incident response system that sends email alerts when an attack is detected.

## 🔍 Project Overview

* **Dataset**: [NSL-KDD](https://github.com/defcom17/NSL_KDD)
* **Model**: Random Forest Classifier
* **Purpose**: Detect network intrusions (attacks) and trigger automated alerts
* **Extras**: SOAR (Security Orchestration, Automation, and Response) with email-based alerting

---

## 📁 File Structure

```text
SAC Mini Project.ipynb   # Main Colab notebook
KDDTrain+.csv            # Training dataset (auto-downloaded)
KDDTest+.csv             # Test dataset (auto-downloaded)
```

---

## ⚙️ Setup Instructions

### 1. Clone or Open the Notebook in Google Colab

[Open in Google Colab](https://colab.research.google.com/drive/1Rr1vPcSPqL9kVUSsamv_CSh8xcNS1GcC?usp=sharing)

### 2. Install Dependencies

```bash
!pip install pandas numpy scikit-learn matplotlib seaborn xgboost joblib
```

### 3. Download the Dataset

```bash
!wget https://raw.githubusercontent.com/defcom17/NSL_KDD/master/KDDTrain+.txt -O KDDTrain+.csv
!wget https://raw.githubusercontent.com/defcom17/NSL_KDD/master/KDDTest+.txt -O KDDTest+.csv
```

---

## 🚀 How It Works

1. **Load and Preprocess Data**:

   * Load NSL-KDD dataset
   * Encode categorical variables
   * Convert class labels to binary (0 = normal, 1 = attack)

2. **Train the Model**:

   * Uses `RandomForestClassifier` for prediction
   * Trained on `KDDTrain+.csv`

3. **Evaluate the Model**:

   * Predicts on `KDDTest+.csv`
   * Achieves up to **100% accuracy** on the test set

4. **Automated Incident Response**:

   * Sends email alerts for detected intrusions using `smtplib`

5. **Visualizations**:

   * Confusion Matrix for performance summary

---

## ✉️ Email Alert System

The notebook includes a simple alerting system using Gmail SMTP.

> ⚠️ Replace the placeholder credentials with **your own Gmail credentials or app password** for it to work securely.

```python
sender_email = "your_email@gmail.com"
receiver_email = "alert_receiver@gmail.com"
password = "your_app_password"
```

---

## 📊 Output Example

* **Classification Accuracy**: 100%

* **Email Alert**:

  * Subject: `🚨 Intrusion Detection Alert`
  * Body: `⚠️ ALERT: Possible intrusion detected at index X.`

* **Confusion Matrix**: Displayed with Seaborn heatmap

---

## 📌 Notes

* This project is for educational/demo purposes and is not production-grade.
* Consider using stronger models (e.g., deep learning), data balancing, and live traffic monitoring for real-world scenarios.
* Do not share your Gmail credentials. Use [App Passwords](https://support.google.com/accounts/answer/185833) for added security.

---

## 🙋‍♂️ Author

**Kruthik**
Feel free to reach out at: `kruthikwork1@gmail.com`

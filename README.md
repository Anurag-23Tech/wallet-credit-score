
# 💳 Wallet Credit Score Assignment – Aave V2 Protocol

## 📌 Overview
This project analyzes user wallet activity data from the Aave V2 Protocol to assign credit scores — **Low**, **Medium**, or **High** — based on borrowing and repayment behavior.

## 🎯 Objective
To develop a **rule-based system** that categorizes wallets using engineered features such as:
- 🏦 Total Borrowed Amount
- 💸 Repay Ratio
- ⚠️ Number of Liquidations

## 🧠 Credit Score Logic
- **High**: High borrow amount, repay ratio near 1, and **zero** liquidations.
- **Medium**: Moderate borrow, decent repay ratio, and no liquidations.
- **Low**: No borrow activity or low repay ratio and/or liquidations.



## 🏗️ Architecture
```text
user-wallet-transactions.json
            ↓
  Data Preprocessing (Pandas)
            ↓
  Feature Engineering (Borrow, Repay, Liquidation)
            ↓
  Rule-Based Credit Score Assignment
            ↓
  Save output to wallet_credit_scores.csv
            ↓
  Visualization → credit_score_chart.png

## 🔄 Processing Flow

### 1. Data Ingestion
- Load `user-wallet-transactions.json` using `pandas`.
- Parse the nested JSON structure into flat transaction tables.

### 2. Data Cleaning
- Filter only relevant transaction types: `borrow`, `repay`, and `liquidation`.
- Convert all values into USD to maintain uniform scale.

### 3. Feature Engineering
For each wallet:
- `total_borrow_usd`: Sum of all borrow transactions (in USD).
- `total_repaid_usd`: Sum of all repay transactions (in USD).
- `repay_ratio`: total_repaid_usd / total_borrow_usd.
- `num_liquidations`: Count of liquidation events.

### 4. Rule-Based Classification Logic
```python
if borrow > 5000 and repay_ratio >= 0.9 and liquidations == 0:
    score = 'High'
elif 1000 <= borrow <= 5000 and repay_ratio >= 0.5 and liquidations == 0:
    score = 'Medium'
else:
    score = 'Low'



## 📊 Sample Visualization

![Credit Score Distribution](assets/credit_score_chart.png)

*Figure: Wallets grouped by credit score.*

## 📂 Dataset
- **Source**: Aave V2 Protocol
- **Input File**: `user-wallet-transactions.json`
- **Derived Features**:
  - `total_borrow_usd`
  - `repay_ratio`
  - `num_liquidations`

## 🛠️ Tools Used
- Python 3
- Libraries: `pandas`, `matplotlib`, `seaborn`
- IDE: Google Colab

## 📤 Output Files
- `wallet_credit_scores.csv`: Wallet addresses with assigned credit scores
- `analysis.md`: Behavioral breakdown by score category
- `assets/credit_score_chart.png`: Score distribution chart

## 👨‍💻 Author
**Anurag**

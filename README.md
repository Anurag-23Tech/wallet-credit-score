
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

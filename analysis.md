
# 📈 Credit Score Behavioral Analysis – Aave V2 Wallets

This document summarizes wallet behavior grouped by their assigned credit scores using engineered features from Aave V2 transaction data.

---

## 🔍 Feature Summary by Credit Score

| Credit Score | Avg. Borrowed (USD) | Avg. Repay Ratio | Avg. Liquidations |
|--------------|---------------------|------------------|-------------------|
| **High**     | High                | ≈ 1.0            | 0                 |
| **Medium**   | Moderate            | 0.6 – 0.9        | 0                 |
| **Low**      | Low / 0             | < 0.5 or 0       | ≥ 1               |

---

## 📊 Distribution of Wallets by Credit Score

- **High Score Wallets**:  
  - Consistently repaid what they borrowed  
  - Demonstrated responsible borrowing patterns  
  - No record of liquidation  

- **Medium Score Wallets**:  
  - Borrowed moderate amounts  
  - Partial repayments made  
  - Still no liquidation history  

- **Low Score Wallets**:  
  - Either didn’t borrow or failed to repay  
  - Presence of liquidations (risk signal)  

---

## 📌 Observations

- Liquidation count is the **strongest risk indicator** — any wallet with liquidation is placed in the **Low** score category.
- Repay ratio acts as the primary behavioral feature to distinguish **High** vs **Medium** wallets.
- A considerable number of wallets had **zero borrowing** but were still active in other ways — these are typically marked **Low** due to no repayment behavior.

---

## 📁 Output Artifacts

- 📄 `wallet_credit_scores.csv`  
  Contains wallet addresses with derived features and final credit scores.
  
- 📊 `credit_score_chart.png`  
  Bar chart of wallet count by credit score (available under `/assets`).

---

## 🧠 Potential Improvements

- Apply unsupervised learning (e.g., KMeans) to discover natural groupings
- Introduce more features like collateral used, loan duration, etc.
- Track historical credit behavior over multiple time windows

---

## 📬 Author  
**Anurag**

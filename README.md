# Machine Learning on Macroeconomics: Emerging-Market Sovereign Yields
# 機器學習於總體經濟之應用：新興市場主權債券殖利率預測

This project is based on the research paper: **"Can Machine Learning Outperform Professional Consensus Forecasts in Forecasting Emerging-Market Sovereign Yields?"**
本專案基於研究論文：**「機器學習是否能系統性地超越新興市場主權債券之專業一致預期？」**

---

## 📌 Project Overview | 專案概述

[cite_start]This research examines whether machine learning models can systematically outperform professional consensus forecasts by correcting systematic biases in sovereign yield predictions[cite: 6, 876]. [cite_start]Using a panel of 3,662 observations across 16 emerging markets (2009 Q1–2025 Q2), we compare linear and non-linear models against the consensus benchmark[cite: 7, 30].

[cite_start]本研究探討機器學習模型是否能透過修正專業預期中的系統性偏差，進而超越專業機構的一致預期（Consensus Forecasts）[cite: 6, 876][cite_start]。研究採用 2009 Q1 至 2025 Q2 間，涵蓋 16 個新興市場的 3,662 筆觀測值，對比線性與非線性模型相對於共識基準的表現 [cite: 7, 30]。

---

## 🚀 Key Findings | 核心發現

* [cite_start]**Systematic Outperformance**: All three ML models statistically significantly outperform the professional consensus (Clark-West test, $p<0.01$)[cite: 8, 511].
    [cite_start]**系統性超越**：三種機器學習模型在統計上均顯著優於專業共識預期 [cite: 8, 511]。
* **Maturity-Specific Dynamics**:
    **期限特定動態**：
    * **3M Yields**: Dominated by linear overreaction; **ARX** is most effective[cite: 9, 811].
        **3M 殖利率**：受線性過度反應主導，**ARX** 效果最佳 [cite: 9, 811]。
    * **2Y Yields**: Driven by cross-period temporal dynamics; **LSTM** performs best ($OOS~R^2 = 0.794$)[cite: 9, 480].
        **2Y 殖利率**：受跨期時間動態驅動，**LSTM** 表現最優 [cite: 9, 480]。
    * **10Y Yields**: Governed by static non-linear interactions; **LightGBM** is strongest[cite: 10, 516].
        **10Y 殖利率**：受靜態非線性交互作用主導，**LightGBM** 表現最強 [cite: 10, 516]。
* **VIX-Triggered Rule**: ML gains are largest in moderate stress regimes (VIX between 17 and 23)[cite: 10, 623].
    **VIX 觸發規則**：機器學習的預測增益在中度市場壓力環境下（VIX 介於 17 至 23）最為顯著 [cite: 10, 623]。

---

## 📊 Performance Comparison | 效能對比 (Out-of-Sample $R^2$)

| Model | Overall | 10Y | 2Y | 3M |
| :--- | :---: | :---: | :---: | :---: |
| **ARX** | 0.374 | 0.245 | 0.568 | 0.485 |
| **LightGBM** | **0.490** | **0.480** | 0.496 | 0.519 |
| **LSTM** | 0.470 | 0.349 | **0.794** | **0.733** |

[cite_start]*(Note: Data sourced from Table 11 of the research paper [cite: 526])*
[cite_start]*(註：數據引用自論文表 11 [cite: 526])*

---

## 🛠 Methodology | 研究方法

[cite_start]The forecasting task is framed as **forecast error correction**[cite: 25, 189]:
預測任務被設定為「**預測誤差修正**」：
$$e_{i,m,t,h} = y_{i,m,t+h} - F_{i,m,t,h}^{Con}$$

### Predictors | [cite_start]預測變數 [cite: 138-143]:
1.  **Local Yield Variables**: Current yields and consensus revisions.
    **本地利率變數**：當前殖利率與預期修正。
2.  **U.S. Yield Forecasts**: Expectations of U.S. Treasury 2Y and 10Y yields.
    **美債預期**：美國 2 年期與 10 年期國債之共識預期。
3.  **Global Macro & Financials**: VIX, S&P 500, Brent Crude, and Exchange Rates.
    **全球宏觀與金融**：VIX 指數、標普 500 指數、布蘭特原油及匯率。

---

## 📂 Project Structure | 專案結構

* `/src`: Source code for ARX, LightGBM, and LSTM implementations.
* `/data`: Data cleaning and panel construction scripts (R/Python).
* [cite_start]`Project.pdf`: The full research paper[cite: 3].

---

## 📝 Citation | 引用

```bibtex
@article{tsai2026mlmacro,
  title={Can Machine Learning Outperform Professional Consensus Forecasts in Forecasting Emerging-Market Sovereign Yields?},
  author={Tsai, Yuze},
  year={2026}
}

# Lab 2 – Anomaly Detection

## Model Comparison

| Metric | Isolation Forest | Autoencoder + Embeddings |
|--------|-----------------:|-------------------------:|
| Detected Anomalies | 33 | 40 |
| Precision | **0.97** | 0.80 |
| Recall | **1.00** | **1.00** |
| F1 Score | **0.985** | 0.889 |
| False Positives | **1** | 8 |
| False Negatives | **0** | **0** |

---

## Model Agreement

- Agreement Rate: **99.12%**
- Detected by both models: **33**
- Isolation Forest only: **0**
- Autoencoder only: **7**

---

# Discussion Questions

## 1. Which model performed better overall and why?

Isolation Forest achieved the best overall performance. It reached higher Precision (0.97), higher F1 Score (0.985), and produced only one False Positive while maintaining perfect Recall. This makes it the more accurate model for this dataset.

---

## 2. Which model produced fewer False Positives?

Isolation Forest produced only **1 False Positive**, while the Autoencoder produced **8 False Positives**. Therefore, Isolation Forest generated fewer false alerts.

---

## 3. What types of anomalies were unique to each model?

Isolation Forest did not detect any unique anomalies.

The Autoencoder detected seven additional behavioral anomalies that were actually legitimate events. These cases represented subtle deviations from normal behavior rather than true attacks, resulting in False Positives.

---

## 4. Did embeddings improve behavioral separation?

Yes. The embeddings allowed the Autoencoder to learn relationships between categorical features such as users, devices, countries, and protocols. This enabled the model to detect subtle behavioral deviations that Isolation Forest did not identify. However, the increased sensitivity also produced more False Positives.

---

## 5. Why should a SOC analyst not rely on only one model?

Different anomaly detection models have different strengths.

Isolation Forest is more conservative and produces fewer False Positives, while the Autoencoder is more sensitive to unusual behavioral patterns. Using both models together provides better visibility, reduces the chance of missing attacks, and helps analysts make more informed decisions before taking action.

---

# Disagreement Analysis

All disagreement cases were legitimate login events (`is_attack = 0`).

- Isolation Forest classified all of them as normal.
- Autoencoder classified them as anomalies.
- The additional detections were caused by unusual behavioral combinations rather than malicious activity.

These disagreements demonstrate that behavioral models are more sensitive but may generate additional False Positives, requiring analyst validation.

---

# Conclusion

Both models successfully detected all attacks (Recall = 1.0).

Isolation Forest delivered the best overall performance because it achieved higher Precision, a higher F1 Score, and significantly fewer False Positives.

The Autoencoder demonstrated stronger sensitivity to behavioral deviations but generated additional false alerts.

A practical SOC environment benefits from combining both approaches: Isolation Forest provides reliable anomaly detection with low false alarm rates, while the Autoencoder helps identify subtle behavioral changes that may warrant further investigation.

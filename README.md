# 🎵 A/B Testing: Spotify Targeted Campaign Strategy

A data-driven A/B testing analysis project evaluating the effectiveness of personalized promotional campaigns on increasing the **Payment Conversion Rate (CVR)** of Spotify Free users, as well as their impact on **User Engagement (Duration Played)**.

---

## 📌 Executive Summary

- **Core Problem**: High drop-off rate in the Control group (30.3% of Free users exited without completing a payment conversion).
- **Experimental Initiative**: Evaluated a personalized promotional campaign (targeted discount/trial banners + relevant content recommendations) on the Target group.
- **Key Findings**:
  * **Success Metric (Payment CVR)**: Increased significantly by **+10.1%** (from 69.7% to 79.8%, p-value = 0.0000 < 0.05).
  * **Guardrail Metric (Duration Played)**: Average user listening duration increased by **+39.84 minutes** (from 120.07 minutes to 159.91 minutes, p-value = 0.0000 < 0.05).
- **Business Decision**: **Full Rollout (100%)** of the personalized campaign to all Free tier users.

---

## 🎯 Objectives & Assignment Scope

1. **A/B Testing Experiment & Design**: Designing the experiment flow, defining Success and Guardrail metrics, and performing precise statistical hypothesis testing.
2. **Monitoring & Evaluation**: Analyzing Before vs. After conditions and ensuring no cannibalization occurs on user engagement metrics.
3. **Business Recommendations**: Providing strategic decision recommendations backed by quantitative conclusions.
4. **Reflective Questions**: Explaining the urgency of detailed sample design, handling current vs. innovation conditions, and post-implementation steps.

---

## 📁 Repository Structure

```text
.
├── Assignment - spotify_campaign_data.csv    # A/B Testing Dataset (100,000 samples)
├── AB_Testing_Spotify_Campaign.ipynb         # Python Colab Notebook (Data Cleaning & Hypothesis Testing)
├── A_B Testing Spotify Campaign.pptx         # Presentation Slides & Storytelling Visualizations
└── README.md                                 # Data Analyst Portfolio Documentation
```

## 🛠️ Tools & Technologies Used

- **Python (Google Colaboratory)**: Data Manipulation (`pandas`, `numpy`) & Statistical Testing (`statsmodels`, `scipy`).
- **Power BI / Slide Visuals**: Comparative chart generation and campaign performance funnel visualization.
- **Applied Statistics**: Two-Sample Proportion Z-Test & Independent Two-Sample T-Test.

---

## 📐 Experiment Design & Metrics Definition

### 1. Identify Change
- **Current Condition (Control / Group A)**: Free users see standard audio ads and generic promotional banners without special offers.
- **Proposed Change (Target / Group B)**: Free users receive personalized discount/trial offers along with customized content recommendations.

### 2. Hypothesis Definition
> *"Implementing targeted promotional campaigns and personalized recommendations will increase the payment conversion rate of Free users to Premium because relevant offers can drive engagement and reduce user drop-off rates."*

### 3. Key Metrics & Statistical Formulation

| Metric Category | Metric Name | Operational Definition | Statistical Test | Hypothesis Formulation |
| :--- | :--- | :--- | :--- | :--- |
| **Success Metric** | **Payment Conversion Rate (CVR)** | Percentage of users who made a payment (`Payment = Yes`) | Two-Sample Proportion Z-Test | `H0: CVR_Target <= CVR_Control`<br>`H1: CVR_Target > CVR_Control` |
| **Guardrail Metric** | **Average Session Duration** | Average listening time duration (`Duration Played` in minutes) | Independent T-Test | `H0: Avg_Target <= Avg_Control`<br>`H1: Avg_Target > Avg_Control` |

---

## 📊 Statistical Analysis & Results

Statistical tests were conducted on a total population sample of 100,000 ($N = 50,000$ per Control and Target group).

### 1. Success Metric: Payment Conversion Rate (CVR)
- **Control CVR**: 69.7% (34,844 converted / 50,000 users)
- **Target CVR**: 79.8% (39,907 converted / 50,000 users)
- **Absolute Uplift**: +10.1% (+1,010 bps)
- **Z-Statistic**: 36.8534
- **P-value**: 0.0000 (p < 0.05)
- **Conclusion**: **Reject H0**. There is a statistically significant increase in the Payment Conversion Rate for the Target group.

### 2. Guardrail Metric: Session Duration Played
- **Control Mean Duration**: 120.07 minutes
- **Target Mean Duration**: 159.91 minutes
- **Absolute Uplift**: +39.84 minutes (+33.2%)
- **P-value**: 0.0000 (p < 0.05)
- **Conclusion**: **Reject H0**. The payment conversion increase **did not compromise user session duration**. Instead, user engagement increased significantly.

---

## 💡 Strategic Recommendations & Monitoring

1. **Full Rollout Strategy**: Deploying and rolling out the personalized promotional campaign and recommendation system to 100% of Spotify Free users.
2. **Monitoring Before vs. After**:
   - Conducting weekly post-full rollout CVR monitoring to ensure performance does not degrade due to novelty effects.
   - Monitoring long-term retention indicators (**30-day Retention Rate**) for newly converted Premium users.
3. **Further Optimization**: Segmenting audiences based on music genre preferences to tailor more specific discount offers to low-converting cohorts.

---

## 💭 Reflection Questions

### 1. Why is detailed experiment design (duration, sample selection, etc.) crucial?
Detailed design is critical to maintaining the scientific validity of the experiment:
- **Sampling**: Random assignment is mandatory to eliminate background bias from confounding variables.
- **Sample Size**: Ensuring a sufficient sample size guarantees adequate statistical power to detect real differences (Minimum Detectable Effect).
- **Experiment Duration**: Running experiments for an appropriate duration prevents seasonal bias and novelty effects (user curiosity spikes at the initial introduction of a new feature).

### 2. What should be done if the current condition outperforms the innovation?
If the innovation results in poorer performance (*Failed Experiment*):
- **Fail to Reject H0 / Rollback**: Cancel the rollout of the new variation and maintain the current condition (Control).
- **Root Cause Analysis**: Conduct a deep-dive post-mortem analysis to understand why the innovation failed (e.g., promotional messages felt intrusive, UI/UX friction, or trial pricing lacked appeal).
- **Hypothesis Iteration**: Refine the campaign design based on data feedback, then formulate a new hypothesis before re-testing.

### 3. Once recommendations are implemented, what are the next steps?
Following implementation (*post-implementation steps*):
- **Continuous Guardrail Monitoring**: Monitor long-term impacts on server capacity, Premium churn rates, and Customer Lifetime Value (CLV).
- **Guard Against Cannibalization**: Ensure discount promotions do not cause users who were otherwise willing to pay full price to shift to cheaper discounted plans (*margin erosion*).
- **Initiate New A/B Test Cycles**: Explore the next optimization areas (e.g., testing variations in offer copywriting or Call-to-Action button placement).

---

## 👤 Author

- **Name**: Muhammad Rizky Ginanjar
- **Role**: Data Analyst
- **LinkedIn**: [Muhammad Rizky Ginanjar](https://www.linkedin.com/in/rizkyginan/)

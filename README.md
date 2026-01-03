# H1N1 Vaccination Analysis: Identifying Key Drivers for Public Health

**Project Contributor:** Valary Kones  
**Technical Stack:** Python, Scikit-Learn, Pandas, Matplotlib, NumPy

---

## Overview
<p align="center">
  <img src="Images/H1N1_Vaccine.jpg" width="95%"/>
</p>
The goal of this project is to provide the **National Public Health Department** with actionable insights into the factors that influence H1N1 vaccination uptake. By building a predictive model, we identify the behavioral, clinical, and demographic drivers that can be used to design targeted public health campaigns and increase vaccination rates.

## Business Understanding
Public health officials need to understand the "why" behind vaccine hesitancy and uptake. Our objectives include:
* **Determining key features** that predict whether an individual will receive the H1N1 vaccine.
* **Comparing the impact** of professional clinical recommendations versus personal beliefs and perceived risks.
* **Providing data-driven recommendations** for resource allocation in future outreach strategies.

## Data & Methodology
The dataset is derived from the **National 2009 H1N1 Flu Survey**.
* **Target:** Binary classification (Vaccinated vs. Not Vaccinated).
* **Baseline:** Logistic Regression using `liblinear` solver.
* **Preprocessing:** Utilized `StandardScaler` within a `Pipeline` to normalize numerical features and handled categorical variables via encoding.
* **Tuning:** Performed `GridSearchCV` to optimize regularization strength ($C$) and penalty types ($L1$ vs $L2$).

## EDA
Our exploratory analysis revealed several critical insights:
* **Doctor Recommendations:** A preliminary look showed a massive gap; patients with a recommendation were significantly more likely to be vaccinated.
* **Risk Perception:** There is a direct correlation between perceived personal risk of the virus and the likelihood of seeking vaccination.
* **Safety Barriers:** Concerns about side effects and "getting sick from the vaccine" were identified as primary deterrents.

## Models
We prioritized **interpretability** and **AUC-ROC** to ensure our model not only predicts accurately but also provides explainable evidence for stakeholders.

### Final Model
Our final **Tuned Logistic Regression** model significantly outperformed the baseline by optimizing the $C$ parameter and using a balanced class weight.
* **Key Metric:** Final Model achieved a **ROC-AUC of [Insert Score]**.
* **Feature Impact:** The model revealed that a doctor's recommendation is the strongest predictor, followed by the perceived effectiveness of the vaccine.



## Conclusion
To increase H1N1 vaccination rates, the National Public Health Department should:
* **Empower Clinicians:** Develop "Provider Prompt" programs, as a doctor's recommendation more than doubles the odds of vaccination.
* **Address Safety Fears:** Create targeted messaging to debunk the myth that the vaccine causes the flu (addressing the `opinion_seas_sick_from_vacc` factor).
* **Highlight Effectiveness:** Shift the narrative toward the vaccine’s proven efficacy to boost public confidence.

## Next Steps
* **Advanced Modeling:** Explore Random Forest or XGBoost to capture non-linear interactions between demographic features.
* **Interaction Terms:** Investigate if the impact of doctor recommendations varies significantly across different age groups or education levels.
* **Deployment:** Build a simplified risk-assessment dashboard for clinics to identify "low-probability" patients for proactive outreach.

## For More Information
See the full analysis in the [Jupyter Notebook](./Your_Notebook_Name.ipynb) or review the [Presentation](./Your_Presentation.pdf).

**Contact:** [Your Name] | [Your Email] | [Your LinkedIn]

---

## Project Structure
```text
├── README.md
├── Data/
│   ├── training_set_features.csv
│   └── training_set_labels.csv
├── Notebooks/
│   ├── Vaccination_EDA.ipynb
│   └── Vaccination_Modeling.ipynb
├── Vaccination_Presentation.pdf
└── .gitignore

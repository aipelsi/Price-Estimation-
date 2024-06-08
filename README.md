# Car Loan Price Estimation

## Purpose and Situation
In this project, we examine e-car's business model and past data to determine if e-cars could generate higher profits through auto car loans. Our analysis revealed that e-cars were offering considerably higher interest rates to customers deemed risky, potentially overpricing its loans. This project aims to competitively price e-car offerings while also mitigating risk and minimizing losses.

## Objectives
- **Increase Acceptance Rates:** Aim to achieve an acceptance rate of over 50%.
- **Optimize Pricing Strategy:** Implement both value-based and cost-based pricing strategies to find the optimal price point that balances profit margins with transaction volume.
- **Enhance Customer Segmentation:** Increase the number of customer segments to better tailor prices and risk factors.

## Methods
### Data Collection
The dataset consists of 208,077 loan offers from e-car, with only 45,785 accepted, indicating a 22% acceptance rate. Variables include gender, age, dietary habits, physical activity, and genetic factors.

### Modeling Techniques
- **Logistic Regression:** Initially used to predict loan outcomes with 82% accuracy, but adjustments were needed due to multicollinearity and endogeneity issues.
- **Causal Inference:** Employed to understand the causal impact of interest rates on loan acceptance decisions, using season as an instrumental variable to account for variations in rates due to seasonal buying trends.

## Experiment
Divided the dataset into three equal parts for analysis:
- **Training:** Used one part to train the IVSLS model.
- **Control and Treatment Groups:** The other two parts were used to analyze the effects of matching competitor rates on loan acceptance.

### Key Actions
- **Lower APR:** To match the competitor’s general market rate.
- **Extend Loan Terms:** Offer longer terms on loans to make them more attractive.
- **Promote New Car Loans:** Since these were the least accepted loan type.
- **Increase Advertisements:** Utilize online and billboard ads to retain customers.

## Results
- **Increased Acceptance Rate:** From 22% to 66%, significantly improving total profit margins.
- **Net Profit Optimization:** In a specific tier (Segment 4), the profit increased from $9.5 million to an adjusted $12.7 million after accounting for expected losses.

## Appendixes
### Profit and Risk Formulas Used
- **Interest Earned:** `Interest Earned = (Rate/100) × Amount × (Term/12)`
- **Total Cost:** `Total Cost = (Cost of Funds/100) × Amount`
- **Expected Loss:** `Expected Loss = PD × Amount/(Term/24) * (assuming customers forfeit around half time of the term)`
- **Net Profit:** `Profit = Interest Earned − Total Cost − Expected Loss`
- **Probability of Default (PD):** `PD= 1- Acceptance probability`

## Conclusion
This study recommends e-car to continuously monitor market rates and adjust loan offerings accordingly. By refining loan terms and segmentation strategies, e-car can enhance its profitability while managing the risks associated with loan defaults. Continuous evaluation, prediction, and estimation are crucial for the efficacy of marketing and pricing models.


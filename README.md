Purpose and Situation: 
We will review and examine the business model and past data to determine if e-cars could potentially generate higher profits through auto car loans. According to the case study, e-car has encountered difficulties in obtaining loan acceptance from potential customers. Upon reviewing the case data, it became apparent that e-cars were offering considerably higher interest rates to customers deemed risky, placing them in a higher risk tier. We believe that e-car may have been overpricing its loans, significantly exceeding market rates for car loans. In today's competitive business landscape, e-cars must competitively price their offerings while also mitigating risk and minimizing losses.
Upon brief data exploration, it became evident that the acceptance rate of e-car loans was unusually low. Out of the 208,077 loans offered, only 45,785 were accepted, resulting in a 22% acceptance rate (Fig.1). We propose that e-car's objective should be to achieve an acceptance rate of over 50%. Several areas for improvement have been identified:
1.	Increasing the number of customer segments to better tailor prices and risk factors.
2.	Optimizing the term by observing trends and preference of accepted loans
3.	Establishing an optimal price point those balances profit margins with transaction volume.
We have decided to address this issue using both value-based and cost-based pricing strategies. Value-based pricing entails quoting fair prices and providing seamless service from start to finish. Cost-based pricing will enable us to determine the best pricing strategy, ensuring that we neither miss opportunities by overpricing nor undercut potential profits by underpricing the loans.
Task: 
After exploring the data further, we were able to gain more insight in the possible areas of improvement. With so many factors to consider, e-car needs to identify what are the important factors in decision making while customers are shopping for car loans.
1.	Considering lowering APR to match competitor’s rate, general market rate fig.6
2.	Offer Longer terms on loans fig.3 
3.	Make “new” car loans attractive since that was the least accepted loan type fig.2
4.	Offer more online and billboard ads to retain customers.  
Out of all these factors, rate and loan terms are something that e-care can control directly and by changing the parameters we were able to get insight, predict and estimate possible revenue for e-car.  After estimating and predicting the acceptance of each loan we can attempt to optimize the pricing by using parameters from our preferred model. In seeking to validate our hypothesis that the "Interest rate has a causal effect on the decision made by customers," we propose employing causal inference and estimating the effect of manipulating the rate (APR) 
We are proposing to use the methods below to predict loan outcomes and optimize the pricing better to maximize returns. Models we attempted are below. 
a.	Logistic Regression:
The model was executed and had about 82% accuracy. However, there was multicollinearity in the price, car types, term, and Fico score. After conducting further literature research, we concluded that the model doesn’t account for endogeneity and can result in significant underestimation in price. We consider the role of endogeneity in customized pricing in which a seller gains information out a potential buyer before quoting a price. If there is more data gained between the buyer and seller prior to the final price being set, then buyer characteristics such as FICO score, income, risk observed by the seller but clearly identified in the data may be an additional source of endogeneity. Logistic regression phyton based code will be submitted with the solution package.
b.	Casual Inference
Utilizing the exploratory data, our analysis indicates that the Interest rate plays a pivotal role in customers' loan acceptance or rejection decisions. Based on empirical evidence and the presented data, we posit that the interest rate holds a causal influence on loan decisions within the provided dataset. To further investigate this claim, we define our variables as follows:
Dependent variable: Loan decision (Accept=1 or Deny=0)
Independent Variable: Interest ('rate')
Instrumental (IV) variable: Season
Control Variables: equal amount of e-care customers randomly assigned but will not receive any treatment. 
Given the constraints of the limited shared data in this case, we faced challenges in identifying a suitable IV variable. However, upon closer examination, Nomis we decided to use season as IV variable. We noticed that the rate was higher in spring, and summer and it’s known that Auto buying is higher in these seasons. Leveraging this seasonal data, we opted to consider it as a factor influencing the interest rate offered, though not directly impacting the ultimate decision made by customers. To mitigate confounding variables, our control group will comprise individuals from the same city of residence in theory for this assignment purpose we can’t use city as criteria as it is not available in the dataset. 
Action: 
Cleaning Data set and Training Causal Model:
The dataset contains 208077 data sets. After cleaning the data and observing trends (see the code submitted for data cleaning and observed insights), we divided the dataset to three equal parts n= 69363 per group. Partition1 was utilized to train the IVSLS model using the factors we mentioned above. Partition3 and partition2 were used as treatment and control sets respectively. We choose to consider tier, Car Type, Amount, Competition Rate and IV variable [Rate ~ Season] to train our model. The model yielded R^2 value of 0.81 and Accuracy was 88.8%. Once the model was trained, we moved on to our experiment section. Code base will be submitted with the package. 
Experiment: 
Based on the Nomis solution case suggestion we decided to segment our data further to 8 (using the median as the breaking point) Tiers then treat each loan in the tier with varying rates. The baseline acceptance rate was 26.10% and 23.3% for our experimental (treatment) and control groups respectively. The samples were assigned randomly, and we decided to not manipulate the data further to avoid biases. We decided to start by matching the competitor’s rate (general market rate) form tier 3- 8 initially and vary the rate to optimize it better. We found that matching the competitors rate yielded ~75% acceptance rate and thus we had room to quote a bit higher to minimize risk and still meet our goal of >50% acceptance rate. Finally, we decided to match the market rate for new cars but add two value +2% for the other cars (refinance and used). The final acceptance rate was 66%. 
Net Profit Optimization: 
Per the project instructions we calculated profit in one segment, segment 4, for demonostration. We simulated treatment as mentioned above by segmenting the tiers into eight segments, setting the price at the market rate for new cars, price for used and refinance was set at competitor rate +2 and normalized term 45-70months (most accepted loans were in that range). Regarding term, we suggest that customers will be given term options in that range, with more options for customers in lower tier. For this experiment’s purpose, we just normalized the initial value. Following that calculated expected interest earning, Total cost, expected loss, probability of default (Risk) and the final net profit. See Appendix for formulas used. 

Results 
The findings of our analysis revealed a substantial increase in the overall acceptance rate from 22% to 66%, consequently leading to a notable improvement in the total profit margin. The logistic regression model resulted in ~32% increase with the same treatment. Our strategy primarily targeted securing acceptance of quotes, thereby amplifying our net profitability. Focusing on a specific tier, namely Segment 4 (n=7704), initially yielded a profit of $9.5 million, exclusive of any projected losses or forfeitures. Following adjustments to the interest rates and loan durations, Segment 4 witnessed a surge in profitability to $41.1 million, prior to factoring in expected losses. Accounting for expected losses, the net profit estimate settled at $12.7 million.
In summary, our consultancy recommends e-car to vigilantly monitor prevailing market rates and strive to align their loan offerings accordingly. Additionally, optimizing the duration of loan terms and refining segmentation strategies could further boost the acceptance rate. Despite the inherent risks of default that come with lowering rate price, our analysis demonstrates a significant increase in net profit as acceptance rates improve with even when factoring the probability of default. Prioritizing the acquisition of potential customers not only elevates acceptance rates but also augments revenue per accepted quotation.
To conclude, it is critical to acknowledge that the dataset utilized comprises one year of sales records. Access to a more extensive historical data set could provide deeper insights. Therefore, continuous evaluation, prediction, and estimation are essential for the efficacy of marketing and pricing models. Furthermore, it is crucial to replicate this experiment multiple times to ascertain its validity and applicability.
 


Appendixes 

1.	Profit and Risk Formulas used. 
a.	Interest Earned: This represents the total interest earned on the loans granted by the lender.
 Interest Earned = (Rate/100) × Amount × (Term/12)
b.	Total Cost: This includes all costs associated with funding the loans, such as the cost of funds. 
Total Cost = (Cost of Funds/100) × Amount Total Cost
c.	Expected Loss: This is the expected amount of loss due to defaults on the loans, based on the probability of default (PD).
 Expected Loss = PD × Amount/(Term/24) 
* we assumed that customers forfeit around half time of the term
d.	Net Profit: This is the difference between the interest earned and the total cost, adjusted for the expected loss. 
Profit = Interest Earned − Total Cost − Expected Loss 
e.	Probability of default: The probability that a loan may default.
PD= 1- Acceptance probability

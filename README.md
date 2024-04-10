# Dynamic Ride Fare Optimization

## Problem Statement
Developing an effective dynamic pricing strategy for rides to optimize revenue while considering factors like rider count, driver count, location category, customer loyalty status, past rides, average ratings, time of booking, vehicle type, expected ride duration, and historical cost of rides.

## Goal
The goal of this project is to implement a dynamic pricing strategy that maximizes profitability by adjusting ride costs based on real-time demand and supply factors. The objective is to improve revenue and customer satisfaction by aligning pricing with market conditions and user preferences.

## Dataset
The dataset includes various features:
- `Number_of_Riders`: Total number of riders for a particular ride.
- `Number_of_Drivers`: Total number of drivers available for a particular ride.
- `Location_Category`: Category of the location where the ride is initiated (Rural, Semiurban, Urban).
- `Customer_Loyalty_Status`: Loyalty status of the customer (Regular, Silver, Gold).
- `Number_of_Past_Rides`: Number of rides the customer has taken in the past.
- `Average_Ratings`: Average rating given by customers for previous rides.
- `Time_of_Booking`: Time of day when the ride is booked (Morning, Afternoon, Evening, Night).
- `Vehicle_Type`: Type of vehicle used for the ride (Premium, Economy).
- `Expected_Ride_Duration`: Expected duration of the ride in minutes.
- `Historical_Cost_of_Ride`: Historical cost of the ride based on previous rides.

## Feature Engineering
- Calculated demand and supply multipliers based on rider and driver counts relative to high and low percentiles.
- Adjusted ride cost for dynamic pricing by considering demand and supply multipliers with specified thresholds.

**Variables created**

- `demand_multiplier`: A multiplier reflecting the demand for rides, calculated based on the number of riders. It indicates how much the demand deviates from the median demand, influencing the adjusted riding cost.
- `driver_supply_multiplier`: A multiplier reflecting the supply of drivers, calculated based on the number of drivers. It indicates how much the supply deviates from the median supply, influencing the adjusted riding cost.
- `adjusted_riding_cost`: Definition: The dynamically adjusted cost of a ride, considering factors such as demand patterns and supply availability. It incorporates the historical cost of the ride, demand_multiplier, and driver_supply_multiplier.
- `profit_percentage`: The percentage of profit or loss for a ride, calculated as the percentage difference between the adjusted riding cost and the historical cost of the ride. Positive values indicate profit, while negative values indicate a loss.

## EDA & Visualization

### Key Insights:

- **Cost Distribution:** Adjusted ride costs typically range between 250 to 800, occasionally exhibiting spikes that may indicate outliers or specific influencing factors.

- **Profitability:** Profit percentages fluctuate from 25% to 150%, with intermittent negative percentages, signaling losses on specific rides despite dynamic pricing, Profitability is variable, with location, loyalty status, and time influencing profit percentages..

- **Location Impact on Profitability:** Rural and suburban locations tend to yield higher profit percentages compared to urban areas.

- **Time of Booking:** No significant variation in adjusted ride costs is observed based on the time of booking.

- **Loyalty Status Influence:** Silver loyalty status holders exhibit slightly higher profit percentages, closely followed by gold members.

- **Linear Relationships:** A robust linear relationship is observed between historical cost and ride duration, while a moderate linear relationship exists between adjusted ride cost and expected duration.

- **Consistent Ratings:** Ratings remain consistently high across all loyalty programs.

- **Vehicle Type Preference:** Users consistently prefer premium vehicle types over economy options.

- **Membership Distribution:** Surprisingly, there is a distribution of Gold membership holders in rural areas.

- **Profitable vs. Loss-Making Rides:** Approximately 82.7% of rides are profitable, while around 17.3% incur losses.
  
-   **Customer satisfaction indicators include consistent high ratings and vehicle type preferences**.
  
## Modelling

### Linear Regression, Ridge Regression & Lasso Regression
- After testing linear, ridge, and lasso regression models, the Random Forest Regressor outperformed, achieving exceptional accuracy without hyperparameter tuning. The model captures intricate patterns with a training score of 98%, testing score of 89%, and R2 score of 88%.
- Upon evaluating the training and testing scores of **linear Regression**, **Ridge Regression**, and **Lasso regression** models, it's evident that these approaches fall short for our dataset.Our exploration of linear, ridge, and lasso regression revealed their limitations.

### Random Forest Regressor
- Shifting gears, we turn to the **Random Forest Regressor** for its known versatility in handling complex data relationships. Surprisingly, the default Random Forest Regressor stood out, showcasing its inherent strength in managing the intricacies of our ride data. Even without hyperparameter tuning, the model demonstrated exceptional accuracy.
Fine-tuning attempts aligned with the default settings, reinforcing the robustness of the initial configuration. With a **training score of 98%, testing score of 89%, and R2 score of 88%**, the model not only captures intricate patterns but also attains an impressive level of precision. This highlights the Random Forest's effectiveness in optimizing our dynamic pricing strategy, offering a reliable solution for our evolving fare adjustment

## Final Conclusion

The Random Forest Regressor emerged as the ideal model for our dynamic pricing strategy, showcasing its ability to navigate complex patterns and deliver outstanding accuracy. The default configuration, without hyperparameter tuning, demonstrated robust performance, making it a reliable solution for optimizing fare adjustments.

## Key Findings
- Adjusted Riding Costs Distribution: Ranges from 250 to 800 with occasional spikes, suggesting potential outliers.
- Profitability Variability: Rural and suburban locations prove more lucrative than urban areas. Loyalty status influences profit percentages.
- Linear Relationships Insights: Strong linear relationship between historical cost and ride duration. Moderate linear relationship between adjusted ride cost and expected duration.
- Customer Satisfaction Indicators: Consistently high ratings across loyalty programs. Preference for premium vehicle types indicates customer satisfaction and preferences.

## Suggestions for Further Improvement
1. Loss-Making Ride Analysis
2. Cost Dynamics Exploration
3. Customer Feedback Integration
4. Feature Expansion

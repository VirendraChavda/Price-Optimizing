# Price Optimization for CPU Coolers
### Author: Virendrasinh Chavda

<p align="justify">
This repository contains the code and analysis for optimizing prices of various CPU cooler products using **Generalized Additive Models (GAMs)**. The project explores the relationship between price and demand, incorporating event-driven pricing strategies and modeling complex, non-linear relationships using GAM. The analysis identifies optimal price points that maximize revenue across different market conditions and promotional events.
</p>

## Table of Contents
1. [Overview](#Overview)
2. [Data](#Data)
3. [Methodology](#Methodology)
4. [Results](#Results)
5. [Future Work](#Future-Work)
6. [Contributing](#Contributing)
7. [License](#License)

## Overview
<p align="justify">
Price optimization is a critical aspect of maximizing revenue in competitive markets. In this project, we leverage **Generalized Additive Models (GAMs)** to optimize the prices of CPU coolers, accounting for seasonality and promotional events. GAMs allow us to capture non-linear relationships between price and demand, providing flexibility that traditional linear models lack. This model identifies optimal prices for each product, maximizing expected revenue by taking into account event-driven price sensitivities and the seasonal decay of demand.
</p>

## Data
The dataset used in this project is a simulated set of daily sales data for six different CPU cooler products, spanning two years and covering multiple promotional events. Key features include:

* **price**: Adjusted daily product price considering discounts and seasonal decay.
* **quantity_sold**: Units sold, adjusted based on price elasticity and event-driven demand shifts.
* **event**: Promotional event, e.g., Black Friday, Amazon Prime Day.
* **profit**: Calculated based on price and base profit margin.
* **profit_margin**: Product-specific profit margin.

<p align="justify">
The data was carefully designed to reflect realistic sales patterns and allow for price optimization under varied event conditions. Each product's demand responds to price elasticity and event-specific price sensitivities, making this dataset suitable for GAM modeling.
</p>

## Methodology

### 1. Preprocessing
<p align="justify">
The data was cleaned and prepared by creating additional columns to calculate revenue and profit based on adjusted prices. Various events and seasonal trends were incorporated to simulate real-world sales patterns.
</p>

### 2. Modeling with Generalized Additive Models (GAM)
<p align="justify">
GAMs were chosen for their ability to model non-linear relationships in data, particularly the non-linear price-demand relationship. This method enables flexible modeling, allowing for smooth adjustments based on predictors like price while avoiding overfitting. GAMs were fit for each product to estimate optimal prices at different confidence intervals.
</p>

### 3. Revenue Optimization
To find the optimal prices, we calculated predicted revenue for each price point based on different quantiles:
* **Median Prediction (50th Percentile)**: Identifies the price that maximizes expected revenue under average conditions.
* **Lower and Upper Bounds (2.5th and 97.5th Percentiles)**: Provides a conservative and optimistic revenue range to help manage risks associated with pricing decisions.

### 4. Visualization
Visualizations include:
* **Revenue vs. Price by Product**: Line and ribbon plots showing the predicted revenue and its confidence intervals at various price points.
* **Optimal Price Points**: Scatter plots highlighting optimal price points across different confidence intervals.

## Results
* **Optimal Price Identification**: The GAM models provided optimal prices for each product across different revenue prediction intervals.
* **Event-Driven Price Sensitivity**: Promotional events such as Black Friday and Amazon Prime Day showed significant effects on sales, validating the need for dynamic, event-based pricing strategies.
* **Revenue Ranges**: Predicted revenue ranges provided a conservative-to-optimistic pricing strategy for revenue maximization.

| Product                     | Optimal Price (50th) | Revenue (50th) | Revenue (2.5th) | Revenue (97.5th) |
|-----------------------------|----------------------|----------------|-----------------|-------------------|
| Corsair H100i               | 130.90              | 129,942       | 128,459         | 130,336           |
| Dark Rock Pro 4             | 80.23               | 94,717        | 93,435          | 96,792            |
| EKWB EK-KIT P240            | 241.24              | 156,423       | 154,979         | 159,184           |
| NZXT Kraken X63             | 141.12              | 125,527       | 123,005         | 126,851           |
| Noctua NH-D15               | 90.16               | 115,631       | 114,076         | 117,999           |
| Thermaltake Pacific CL360   | 302.14              | 311,335       | 308,351         | 313,099           |

## Future Work
* **Additional Feature Integration**: Including demographic and competitor data could improve model accuracy and relevancy.
* **Seasonal Analysis**: Extending the model to include seasonal trends for better long-term predictions.
* **Advanced Optimization Techniques**: Incorporating machine learning methods to dynamically adjust prices based on real-time data.

## Contributing
<p align="justify">
Contributions are welcome! If you would like to suggest improvements, report issues, or contribute to the project, feel free to open a pull request or submit an issue.
</p>

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

For a full explanation of the analysis, please refer to the [project report](https://github.com/VirendraChavda/Price-Optimizing/blob/main/Price%20Optimization.ipynb).

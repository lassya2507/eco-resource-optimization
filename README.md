# Eco-Resource Optimization using EAs and SHAP

This project presents a novel approach to optimizing renewable energy resource allocation using **Evolutionary Algorithms (EA)** enhanced with **SHAP (SHapley Additive exPlanations)** analysis. The research combines multiple global energy datasets to develop a comprehensive model that balances electricity generation with environmental impact. Through iterative improvement and sophisticated fitness functions, the model achieves significant optimization results while providing interpretable insights into feature importance in sustainable energy systems.  

**Key observations**: The evolutionary algorithm for optimizing global energy distribution, achieved a best fitness score of **12821.54**. Through SHAP analysis, critical features such as **Electricity Generation (TWh)** (with a SHAP value of **498.38**) and **Solar PV (TWh)** (SHAP value of **0.45**) were identified as key contributors to the decision-making process.
![shap analysis](shap_analysis.png)

## Requirements

1. **Datasets:**

Three major dataset collections from Kaggle have been utilized:

   a) https://www.kaggle.com/datasets/jamesvandenberg/renewable-power-generation  
   b) https://www.kaggle.com/datasets/iannjuguna/energy-data-since-1990  
   c) https://www.kaggle.com/datasets/anshtanwar/global-data-on-sustainable-energy

After going through each datasets, they were first cleaned and standardized. Then after handled missing values they were merged on common attributes such as year, country, energy production, CO2 emissions, etc. This resulted in a comprehensive, unified dataset **(scaled_merged_dataset.csv)** containing all key features, which provided a holistic view of global energy generation, environmental impact, and renewable energy capacities for optimization.

2. **Tools:** Python, Jupyter Notebook, Evolutionary Algorithm module, SHAP.
3. **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Plotly, Scikit-learn.
   
## Results
All the results and visualizing observations graph can be fount at main.ipynb

#### 1. Optimization Performance

Initial Implementation:
- Base EA Implementation: Best Fitness = **12813.68**
- Grid Search Implementation: Best Fitness = 12813.681259087005
- Local Search Implementation: Best Fitness ≈ 12813

Parameter Tuning Results:
- Mutation rates tested: [0.1, 0.2, 0.3]
- Population size variations: Various ranges around 70
- Consistent convergence around 12813 fitness score

Final Improved Implementation:
- Best Fitness Score: **12821.54**
- Demonstrated robust convergence across different configurations

#### 2. SHAP Analysis Results
a. Electricity Generation: Increased significantly from **223.59 TWh** to **498.38 TWh (+123%)**

b. Renewables (all positive new additions):
**Solar:** 0 → 0.45 TWh, **Geothermal:** 0 → 0.33 TWh and **Hydro:** 0 → 0.29 TWh 

c. CO2 Emissions: Increased from **0.19 GT** to **0.40 GT (+107%)** - but grew slower than generation
This shows a major expansion in power generation with new renewable sources, demonstrating improved energy mix diversity while maintaining better carbon efficiency.
## Future Work
Potential areas for future research include:
- Integration of more granular temporal data
- Incorporation of economic factors
- Extension to regional optimization scenarios
- Dynamic adaptation of fitness functions based on policy goals

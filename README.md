# Appliance_diffusion_model
This repository contains a model for estimating appliance adoption over 20 years, based on the Faza mini-grid case study in Kenya.
The contents of the model consist of three modules (I–III), and an example Excel dataset is provided to illustrate the data structure used in the analysis


## Model Description

- Module I implements the diffusion model to obtain the logistic curve variables for each customer cluster to obtain each cluster's average annual tier.  
- Module II applies SLSQP optimization to obtain the annual tier distributions.  
- Module III aggregates all customer cohorts by tier and year to produce the final appliance diffusion outputs.  


## Module Integration  

The modules are soft-linked:  
- Outputs from Module I are passed as inputs to Module II.  
- Outputs from Module II are then passed to Module III.  


[Module I: Logistic Diffusion] → [Module II: SLSQP optimization] → [Module III: Aggregation → Final outputs]

## Example Dataset (Excel file)  
The provided Excel file contains an example dataset illustrating the structure used in the analysis. Each row corresponds to a household and contains the following information:
- HHindex — unique household identifier.  
- ClusterLabel — cluster membership assigned to the household (e.g., 0 or 1).  
- **Year1 … Year5** — appliance tier for the household in each year of observation (from baseline *Year1* to *Year5*).  

## Run Online
You can run the notebooks directly in Google Colab:
- Module I: https://colab.research.google.com/github/leticiatf/Appliance_diffusion_model/blob/main/Module%20I_Logistic%20difussion.ipynb
- Module II: https://colab.research.google.com/github/leticiatf/Appliance_diffusion_model/blob/main/Module%20II_SLSQP%20Optimization.ipynb
- Module III: https://colab.research.google.com/github/leticiatf/Appliance_diffusion_model/blob/main/Module%20III_Aggregation%20of%20customer%20cohorts.ipynb

📄 **Citation**  
If you use this code or data in your research, please cite it using the DOI below:

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15196889.svg)](https://doi.org/10.5281/zenodo.15196889)  
https://doi.org/10.5281/zenodo.15196889

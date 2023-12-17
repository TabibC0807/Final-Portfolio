# Final Project Portfolio

This repository contains all 3 of the final versions of the projects for PHP 2550. Both the pdf report and .rmd R markdown files are included. In the following sections I will summarize the three projects as a whole


## Project 1

### Overview:

In this report, we conducted missing and exploratory data analysis of the data provided. We found that the data is MAR(missing at random). We showed this thru visuals, examples and tables. We also found significant relationships between SDP and adolescent self-regulation, substance use, and externalizing. This relationship was not as easily visible for ETS, however we did find some relationships between ETS and adolescent substance use. 
The main set back of the study was the low number of observations. This could lead to high bias among our results. More importantly, the low number of observations decreased the statistical power of the study. Another set back of the study is having more observations than variables. Often this leads to high data sparsity, which ddidn't allow us to deal with missing data through imputaions. 


## Project 2

### Overview:

In this collaborative project with Dr. Chris Schmid, we attempt to address the challenges of determining indication criteria and timing for tracheostomy placement in neonates with severe bronchopulmonary dyspla- sia (sBPD). Leveraging a national dataset comprising demographic, diagnostic, and respiratory parameters of infants from collaborative NICUs, we conducted an extensive analysis that involved Exploratory Data Analysis (EDA), missing data analysis, leading to the implementation of multiple imputation techniques. Imputation was performed for both the complete dataset and a targeted subset at 44 weeks, because we wanted to address the non-proportionate missing data between 36 and 44 weeks.
To develop a robust predictive model for the composite outcome of tracheostomy/death, various model selection approaches were explored. We performed Lasso regularization based on Akaike Information Crite- rion (AIC) and Bayesian Information Criterion (BIC), and backward stepwise selection based on AIC. We consider 4 different logistic mixed effects models and their performance was rigorously compared using predic- tion, discrimination, and calibration metrics. Additionally, to find the optimal timeframe for tracheostomy, predictions were stratified across diverse subsets of the data.

We found that a full mixed effect model is best for prediction for the outcome of death and trachoestomy. Additionally, implementing a full model with both the 36 week and 44 week data allowed us to compare the coefficeints between 36 and 44 week data. We found that the variables describing the fraction of inspired Oxygen, medication for Pulmonary Hypertension(PH) and Peak Inspiratory Pressure (cmH2O) has opposite effects on the log odds of death/tracheostomy. We also found that the influence andom effects of the centers on the log odds of the outcome accurately depict what we discussed in the EDA section.

Some of the setbacks of our work here is that we don’t take into account some of the outliers in the data, although we did remove outliers heavily affecting the data we predicted on. There are many missing values that are indiscriminate between 36 weeks and 44 weeks which can sway the bias of the models. The model is difficult to generalize outside of centers included in the data. Another set back is that we don't implement interaction terms into the model because we want interpretation in the clinical setting to be simple, easy and efficient. One could try and implement interaction terms to attempt to see if the model prediction improves.

## Project 3


### Overview:

In this collaborative project with Dr. Jon Steingrimsson we evaluate the performance of a model when applied to a different external dataset. Often time prediction models are trained on randomized controlled trials or observational study data which may not represent the demographics of the target population. The Framingham ATP III model has been trained on predominantly white participants and has shown to be limited in terms of its generalization to multiethnic populations.
In this project, we conduct a simulation study where we focus on a risk score model built from the Fram- ingham Heart Study data, and the evaluation will be conducted in the population underlying the National Health and Nutrition Examination Survey (NHANES). To evaluate the NHANES data, we estimate the mean squared error for binary outcome data(i.e brier score) on a target population. This procedure is called transportability analysis. We found that the model evaluates well on the NHANES data achieving an MSE score of around 0.075 for males and 0.042 for femlaes. Comparatively, the MSE on the framingham data is lower at 0.157 for males and 0.155 for females. After doing this, I simulated new individual level data using the summary statistics of the the NHANES data and proceeded to perform transportability analysis to the simulated data as well. We found that the model performs better on the simulated data compared to the actual NHANES data.
We simulated data considering both associations and no associations and also under different threshold values. Model performance and evaluations were then visualized with the tables and plots above. Overall the simulated data resulted in similar MSE scores however we found that as associations got stronger, the MSE increased and standard error decreased.

Some limitations of my study is that I only considered one metric to evaluate the performance of the model evaluation on the target population. One metric I could have used is the AUC performance metric in transportability analysis(from the paper "Estimating the area under the ROC curve when transporting a prediction model to a target population"), however it has been proven difficult to implement. 

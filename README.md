# Final Project Portfolio

This reposatory contains all 3 of the final versions of the projects for PHP 2550. Both the pdf report and .rmd R markdown files are included. In the following sections I will summarize the three projects as a whole

## Project 1

### Overview(from Dr. Alice Paul's canvas site):
This project is a collaboration with Dr. Lauren Micalizzi from the Department Behavioral and Social Sciences. Exposure to smoking during pregnancy (SDP) and environmental tobacco smoke (ETS) are two of the most ubiquitous and hazardous of children’s environmental exposures. Seven to 15% of infants born per year are exposed to SDP and more than 25% of children are exposed to household ETS. SDP alone imposes a $4 billion annual economic burden due to health-care costs. Early smoke-exposure increases rates of externalizing behaviors in children, including Attention-Deficit/Hyperactivity Disorder, and rates of substance use problems, all of which have clear public health implications. Early smoke exposure is also linked to self-regulation problems (i.e., the maintenance of physiological, emotional, behavioral, and cognitive control).

### Objective
The purpose of Dr. Micalizzi’s research is to examine the association between smoking during pregnancy (SDP) and environmental tobacco smoke (ETS) exposure and self-regulation, externalizing behavior, and substance use. The women in this study were recruited from a previous study on smoke avoidance intervention to reduce low-income women’s (N=738) smoking and ETS exposure during pregnancy and children’s exposure to ETS in the immediate postpartum period. A subset of adolescents (N=100) and their mothers are randomly selected for recruitment into this study. The data we analyze are two longitudinal follow up assessments occur at 6- and 12-months post-baseline. My main objective was to examine effects of SDP/ETS on adolescent self-regulation, substance use, and externalizing.

### Methods
I worked on doing missing and exploratory data analysis. I used R software to construct tables and plots comparing groups of SDP/ETS to variables describing adolescent self-regulation, substance use, and externalizin. These tables include p-values to determine if the relationships I found were statistically significant. 
I recieved cleaned and preprocessed data. I simply had to preprocess some minor details relating to the missing values. I worked on doing missing and exploratory data analysis. I used R software to construct tables and plots comparing groups of SDP/ETS to variables describing adolescent self-regulation, substance use, and externalizin. These tables include p-values to determine if the relationships I found were statistically significant. 

### Conclusion

In this report, we conducted missing and exploratory data analysis of the data provided. We found that the data is MAR(missing at random). We showed this thru visuals, examples and tables. We also found significant relationships between SDP and adolescent self-regulation, substance use, and externalizing. This relationship was not as easily visible for ETS, however we did find some relationships between ETS and adolescent substance use. 
The main set back of the study was the low number of observations. This could lead to high bias among our results. More importantly, the low number of observations decreased the statistical power of the study. Another set back of the study is having more observations than variables. Often this leads to high data sparsity, which ddidn't allow us to deal with missing data through imputaions. 


## Project 2

### Overview(from Dr. Alice Paul's canvas site):
This project is a collaboration with Dr. Chris Schmid in the Biostatistics Department. The exact indication criteria and timing of tracheostomy placement in neonates with severe bronchopulmonary dysplasia (sBPD) remains unclear. Studies suggest that earlier tracheostomy placement may be beneficial for growth. Previous analyses of large databases have shown that likelihood of tracheostomy placement or death can be accurately predicted based on baseline demographics and clinical diagnoses, but these analyses have not used detailed respiratory parameters and have not provided prediction at different postmenstrual ages (PMA). Accurate prediction of need for tracheostomy at early PMA would have implications for counseling families and timing of tracheostomy placement, which is an active area of debate in sBPD. 

My goal is to develop a regression model to predict the composite outcome of tracheostomy/death to guide the indication criteria and timing of tracheostomy placement. In the report, I fit a mixed effect regression model and interpret key variables as it relates to the composite outcome of tracheostomy placement and death. The data is a national data set of demographic, diagnostic, and respiratory parameters of infants with sBPD admitted to collaborative NICUs and with known respiratory support parameters at 36 weeks PMA.


### Objective
Although many studies suggests that early tracheostomy placement for babies with severe bronchopulmonary dysplasia (sBPD) has benefits, the work around the criteria and timing of the precedure is still incomplete. In this research project, we will attempt to address this issue by developing a regression model to predict the composite outcome of tracheostomy/death to guide the indication criteria and timing of tracheostomy placement. In our model we will include birth variables, respiratory support variables, and infant data at 36 and 44 weeks corrected gestational age(CGA). We estimate an ideal time frame to refer a patient for tracheostomy by providing predictions across different postmenstrual ages. 

### Methods
We first perform multiple data imputation(m = 5) using the MICE package in R and split the data into training and testing sets with a 70-30 split. From our exploratory data analysis we know that the composite outcome of tracheostomy and death of the neonatal infants are not evenly distributed throughout the centers. This is due to the fact that the patient’s severity with sBPD is correlated with which center they are placed in. Another point to consider with the centers is that once we fit a model, it will be difficult to get accurate predictions from said models since we cannot extrapolate outside the centers given in the data. Because of this we were either left with the option of leaving out the center variable and fit a logistic generalized linear model or fit a generalized mixed effects model with the center variable as a random intercept. We chose the latter as we believe that the random intercept will capture the variability between centers for each patient based on their differing levels of severity. In our fixed effect model we consider the composite outcome of tracheostomy and death as the binary outcome variable and the patients birth variables, respiratory support variables, and infant data at 36 and 44 weeks corrected gestational age(CGA) as predictors.

### Conclusion

In conclusion, we found that a full mixed effect model is best for prediction for the outcome of death and trachoestomy. Additionally, implementing a full model with both the 36 week and 44 week data allowed us to compare the coefficeints between 36 and 44 week data. We found that the variables describing the fraction of inspired Oxygen, medication for Pulmonary Hypertension(PH) and Peak Inspiratory Pressure (cmH2O) has opposite effects on the log odds of death/tracheostomy. We also found that the influence andom effects of the centers on the log odds of the outcome accurately depict what we discussed in the EDA section.

Some of the setbacks of our work here is that we don’t take into account some of the outliers in the data, although we did remove outliers heavily affecting the data we predicted on. There are many missing values that are indiscriminate between 36 weeks and 44 weeks which can sway the bias of the models. The model is difficult to generalize outside of centers included in the data. Another set back is that we don't implement interaction terms into the model because we want interpretation in the clinical setting to be simple, easy and efficient. One could try and implement interaction terms to attempt to see if the model prediction improves.

# Project 3


## Overview(from Dr. Alice Paul's canvas site):
This project is a collaboration with Dr. Jon Steingrimsson in the Biostatistics Department and focuses on evaluating a performance of a prediction model in a different population than it was originally developed and/or evaluated in. 

Users of prediction models are usually interested in using model-derived predictions in some target population. For example, a healthcare system may want to deploy a risk prediction model to identify individuals at high risk for cardiovascular events among all patients receiving care. The data used for prediction model development, referred to as the source study data, are often data from randomized trials, large observational databases, or prospective cohort studies. Such datasets are typically not a random sample from the target population. As a result, the target population and the population underlying the source study data differ. As an example, the Framingham ATP-III model is often used to predict 10-year risk of cardiovascular events. This model was built using source data that had predominantly white participants and the models have been shown to generalize poorly to multi-ethnic populations. 

In recent years, several methods have been developed to evaluate the performance of prediction models in a target population (or transporting measures of model performance from the source population to the target population). My goal is to apply these methods to a risk score model built using data from the Framingham heart study data and then estimate performance of that model in a population underlying the NHANES (National Health and Nutrition Examination Survey) survey data using a simulation study. As NHANES does not include long term outcome information, this involves using data from both NHANES and the Framingham Heart Study. In this project, I have used recent transport performance methods to evaluate the NHANES dataset in different settings. In addition, I conducted further simulation studies to compare how a simulated data might perform against an actual external dataset. 

## Objective
The main objective of this project is to perform transportability analysis on the NHANES dataset, and a simulated dataset to see how the framingham model performs outside the source data. Transportability analysis is required for our specific setting because we are attempting to address the critical challenges of assessing the performance of prediction models when applied to populations distinct from those in which they were originally developed. The source data here is the framingham data orginates from a 1948 study where the original goal of the Framingham Heart Study (FHS) was to identify common factors or characteristics that contribute to cardiovascular disease and it's been collected over generations from the city of Framingham, Massachussetts. The issue with this setting is that the city of Framingham, MA is predominantly white and thus it would be hard to generalize this study to a different setting. 

## Methods

In our project, we first perform Exploratory Data Analysis to observe patterns and differences between the source and target data. We find that there are significant differences between the two sets of data along with the problem of missing values in the target dataset. To solve this issue, we do multiple imputation and then perform transportability analysis using the mean squared error as the main metric of performance. The next part of the project involves simulating a second dataset which reqiured us to analyze the summary statistics, association and distributions of the common covariates between the framingham and the NHANES data. We then also performed transportability analysis on the simulated data and compared how the model performs on the actual NHANES data and the simulated NHANES data. 

## Conclusion
In conclusion, in this project we have first evaluated the model on the target population using the MSE as the main performance metric. We found that the model evaluates well on the framingham data achieving an MSE score of around 0.105. We then studied the associations and distributions of the common variables in the framingham data and used this to simulate a second dataset in the hope of mirroring the NHANES data. To inform the parameters of the distribution we used a summary table from the NHANES dataset that provided us with useful information such as the mean, standard deviation and proportions of the covariates. Using this datagenerating process, we simulated data considering both associations and no associations and also under different threshold values. We found that the model evaluates well on the NHANES data achieving an optimal MSE score of around 0.105, however it performs better on the simulated data.

Some limitations of my study is that I only considered one metric to evaluate the performance of the model evaluation on the target population. One metric I could have used is the AUC performance metric in transportability analysis(from the paper "Estimating the area under the ROC curve when transporting a prediction model to a target population"), however it has been proven difficult to implement. 



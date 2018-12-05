---
layout: default
---

Linear regression is a simple but very helpful model to help us conduct data analysis. I applied this method to conduct the data analysis project on air pollution. Through my analysis, I find out what factors influence the air condition. Also, we can use this model to forcast the air condition of a city.

### Data Clean
Before, I begin to analyze the dataset, I delete those records with missing values. Then, I change scale of two variables by diveded 10000 because their mean values are much larger than the dependent variable.

### Choosing Predictors
Not all variables are highly related with the dependent variable, which is Nitrous Oxide. Therefore, I calculated the correlation coeffients between them and the dependent. Here is the scatter plot of those variables. I choose these variables with correlation coeffients greater than 0.3 as predictors in my linear model.
<img src = "/figures/regressionAnalysis/ScatterPlot.png" alt = "Scatter Plot" width = "500">

### Detecting Outliers
Detecting outliers is very important for linear regression. Because outliers may badly affect the result of our regression result.
I used boxplot and histogram to detect outliers. The graphs shows there are five outliers in the dataset.
<img src = "/figures/regressionAnalysis/boxPlot.png" alt = "Box Plot" style="width:400px;height:300px;">

<img src = "/figures/regressionAnalysis/histogram_density.png" alt = "Histogram" style="width:400px;height:300px;">

### Checking Collinear Problem
I use pearson correlation coeffients to check if there exists Collinear probrem. From these matrix, we see that some variables have this problem. Therefore, I delete this variables, which have collinearity problem.
<img src = "/figures/regressionAnalysis/PearsonCorrelation.png" alt = "Pearson Correlation" width = "500">

### Checking Heteroscedasticity Problem
I use residual plot to check this problem. As the graph show, the residuals are randomly distributed with predictors. So, there is no Heteroscedasticity problem in the dataset.
<img src = "/figures/regressionAnalysis/residualPlot.png" alt = "residual plot" width = "500">

### Checking Autocorrelation Problem.
I also use residual plot to check this problem. But at this time, I use residual-index plot. Also, residuals are randomly distributed with index. Therefore, there is no such problem.

### Model Fitting
After deleting the collinear data, I can do regression analysis now. The fowllowing graph is the scatter plot of dependent variable and predictors. There are linear relationships between them. 

<img src = "/figures/regressionAnalysis/scatterplot.png" alt = "scatter plot" width = "500">

Finnaly, I find the best model to fit this dataset and give forcasting of air pollution condition of a city.


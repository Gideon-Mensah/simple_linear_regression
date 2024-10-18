# Simple linear regression
## Objective of the project
Objective: The primary objective of this analysis is to demonstrate the application of regression analysis using Python and Jupyter Notebook to explore the relationship between SAT scores and GPA. Specifically, this study aims to:

Utilize Python’s robust data analysis libraries (such as Pandas, NumPy, and Statsmodels) to perform and interpret a regression analysis, demonstrating the effect of SAT scores on GPA.
Showcase how Jupyter Notebook provides an interactive environment for performing regression analysis, including data manipulation, statistical calculations, and result interpretation.
Visualize the relationship between SAT scores and GPA using Python’s visualization tools (such as Matplotlib), and explain the regression results in a clear, step-by-step manner.
Highlight the use of Python and Jupyter as effective tools for academic research and data analysis, making the process transparent, reproducible, and easy to follow.
This demonstration will serve as an educational example of how Python and Jupyter can be employed to perform and present regression analysis in a clear and accessible format.
## Procedure
I have included the CSV data necessary for running this regression analysis. https://github.com/Gideon-Mensah/simple_linear_regression/blob/main/1.01.%2BSimple%2Blinear%2Bregression.csv
First, download the CSV data file. Next, download and install Anaconda, and run Jupyter Notebook from Anaconda. After opening a new notebook in Jupyter, follow the procedure outlined below:
### Import the relevant libraries
This can be achieved by writing the following code in Jupyter
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import statsmodels.api as sm
```
### Load the data and run the data (run the data by pressing shift + enter)
```
pd.set_option('display.max_rows', None)
file_path = r"C:\Users\Lenovo\Desktop\Projects\Data Analysis\data\1.01.+Simple+linear+regression.csv"
data = pd.read_csv(file_path)
data
```
<img src="https://github.com/Gideon-Mensah/simple_linear_regression/blob/main/data.png">
Run this code to describe the data
```
data.describe()
```
<img src="https://github.com/Gideon-Mensah/simple_linear_regression/blob/main/data_description.png">

### Create regression analysis

#### Define dependant and independant variable
```
y = data['GPA']
x1 = data ['SAT']

```
#### Explore the data by plotting it on a scatter diagram
```
plt.scatter(x1,y)
plt.xlabel('SAT', fontsize=20)
plt.ylabel('GPA', fontsize=20)
plt.show()

```
<img src="https://github.com/Gideon-Mensah/simple_linear_regression/blob/main/Scatter_diagram.png">

#### Run the regression itself
```
x = sm.add_constant(x1)
results = sm.OLS(y,x).fit()
results.summary()

```
<img src="https://github.com/Gideon-Mensah/simple_linear_regression/blob/main/regression_result.png">

## Discussion of result 
R-squared in simple regression indicates the proportion of the variance in the dependent variable (the variable being predicted) that is explained by the independent variable.
The R-squared value ranges from 0 to 1:

R-squared = 0: This indicates that the independent variable does not explain any of the variation in the dependent variable.
R-squared = 1: This indicates that the independent variable explains all of the variation in the dependent variable.

NB: A higher R-squared value indicates a better fit of the model to the data, as it suggests that a greater proportion of the variance in the dependent variable is explained by the independent variable
## Conclusion


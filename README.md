# Data-science Challenge - IC Innovations
## Challenge for candidates to the Junior Data Scientist position at IC Innovations 

In this challenge you will analyze datasets that contain the time evolution of the physiological variable SmO2 in a group of subjects. We are interested in determining the time instant where the evolution shows a break in linear trend, i.e., the breakpoints, as illustrated in the following image:


![challenge.pdf](https://github.com/dehurtado/data-science-challenge-01/files/7538892/challenge.pdf)

General instructions:
* All code developments must be written in Python language using Jupyter Notebooks. 
* Datasets provided should be treated as confidential,and should not be distributed.
* When you are done with the challenge, please send your results by e-mail - do not commit your results to this repository. 

## Tasks

1. Dataset cleanup and reformatting 
* Time reformatting: Raw data comes with time stamps. Transform them to seconds. Also, we are only interested in SmO2 measurements in this project.
* Remove outliers: Some datasets contain abnormal data points (outliers) that are due to errors in the signal acqusition. No abrupt changes are expected to occur during the time evolution. Filter data to remove outliers. 
* Slice dataset: For the purpose of this challenge we are only interested in decaying signals. For all datasets, detect the minimum value in SmO2 and consider data up until that point


2. Regression analysis
* Implement a segmented regression function: datasets are expected to follow a piecewise-linear (2-segment) trend. Create a function that solves the 2-segment regression as detailed in this [link](https://en.wikipedia.org/wiki/Segmented_regression) 
* The function should return the fitted model constants ($A_1,K_1,A_2,K_2,BP$) and the two correlation coefficients $R_1^2,R_2^2$. Validate your function using a synthetic problem where model constants are known a priori, and a synthetic dataset is created from this regression plus noise (Gaussian)   
* Analyze datasets: using the 2-segment regression function, determine the breakpoints (BP) and correlation coefficients $R_1^2,R_2^2$ for each of the datasets provided.

3. Results presentation
* Plot SmO2 vs time for both data and model, for the two best and two worst cases
* Generate a histogram for the BP distribution, indicating in the plot the mean, median, and standard devation for the sample group 
* Report in a plot the $R_1^2,R_2^2$ for each subject (x-data: subject number, y-data: correlation coefficients)
* Be thoughful about visual aspects of the plots such as choice of colors, font size, title and axis lables, legends, etc. Do not include redundant information, be clear and concise. 
* Comment on your results



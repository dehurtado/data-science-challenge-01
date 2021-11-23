# Data-science Challenge - IC Innovations

## Context

In this challenge you will analyze datasets that contain the time evolution of the physiological variable SmO2 in a group of subjects. We are interested in determining the time instant where the evolution shows a break in linear trend, i.e., the breakpoints, as illustrated in the following image:

![alt text](https://github.com/dehurtado/data-science-challenge-01/blob/main/SmO2.png)

Note that for this trend analysis, we neglect the recovery part of the dataset.



## Tasks

1. Dataset cleanup and reformatting 
* Datasets can be found [here](https://github.com/dehurtado/data-science-challenge-01/blob/main/SmO2-datasets-ICI.zip). Datasets provided should be treated as confidential, and should not be distributed.
* Time reformatting: Raw data comes with time stamps. Transform them to seconds and only consider the column with SmO2 data.
* Remove outliers: Some datasets contain abnormal data points (outliers) that are due to errors in the signal acqusition. No abrupt changes are expected to occur during the time evolution. Filter data to remove outliers. 
* Slice dataset: For the purpose of this challenge we are only interested in decaying signals, and we neglect the datapoints in the recovery stage (noted in gray shadow in the figure). For all datasets, detect the minimum value in SmO2 and only consider data up until that point for the analysis


2. Regression analysis
* Implement a segmented regression function: datasets are expected to follow a piecewise-linear (2-segment) trend. To this end, you have to write a function that solves the 2-segment regression. For more info baout segmented regression, see this [link](https://en.wikipedia.org/wiki/Segmented_regression) 
* The function should return the fitted model constants ($A_1,K_1,A_2,K_2,BP$) and the two correlation coefficients $R_1^2,R_2^2$. Validate your function using a synthetic problem where model constants are known a priori, and a synthetic dataset is created from this regression plus noise (Gaussian)   
* Analyze datasets: using the 2-segment regression function, determine the breakpoints (BP) and correlation coefficients $R_1^2,R_2^2$ for each of the datasets provided.

3. Results presentation
* Plot SmO2 vs time for both data and model, for the two best and two worst cases
* Generate a histogram for the BP distribution, indicating in the plot the mean, median, and standard devation for the sample group 
* Report in a plot the $R_1^2,R_2^2$ for each subject (x-data: subject number, y-data: correlation coefficients)
* Be thoughful about visual aspects of the plots such as choice of colors, font size, title and axis lables, legends, etc. Do not include redundant information, be clear and concise. 
* Comment on your results


## Deliverables
* Codes: all code developments must be written in Python language using Jupyter Notebooks, with the requested results clearly reported. you can use a separate .py file for libraries, if you consider it necessary, but the main code should be in a Jupyter notebook. Please send your Jupyter notebook and .py files by e-mail - do not commit them to this repo. Don't forget to comment your codes/notebook
* Presentation: Prepare a PowerPoint/Google Slides presentation that briefly presents the methods for analysis, results, and conclusions. Your audience is the Chief Science Officer of the company. The presentation should contain at most 6 slides, should be written in English (you can present in Spanish), and should be sent by e-mail when you are done with the challenge


# Report-Resturant-Location-Prediction

Hi, there!
**This is a typical 101 case study for leverging Regression to understand the casuality of busiess.**
To be more detail, This a coding script &amp; report using Stepwise regression model to predict for a restaurant location choice based on both model performance and economical meaning behind parameters. 

<h1 align="center">Where is the Next Croq' Pain?</h1>
<img src="Pics/cover_pic.png",class="center">

## Part 1. Case Overview
### Background
Croq'Pain is a chain of French-style fast food restaurants that has wide branches in Paris. According to the store revenue report, seven out of ten new stores opened in last 10 years did not perform well. Thus, an improving system on location selection of new stores need to be constructed to help stakeholders in Croq'Pain identify the right locations for future store openings.
### Objectives
•	Identify the most significant explanatory variables that affect operating earnings;
•	Develop a regression model on operating earnings based on the most impactful variables from historical data;
•	Select the optimal locations for new stores based on prediction.

## Part 2. Data Processing
### Data Cleaning
Firstly, we explored data by reading the description and viewing its histogram, scatterplot and correlation plots to check if abnormality exists. Two problems were found as shown below:
•	There are five duplicate values in dataset;
•	There is an extreme value in earning in store 1. 
After cross checking all data, we believe that the outlier (see in Exhibit 1) is caused by a mistake of data entry. Since the unit of earning is $1000 and all other store earnings are ranged from -40 to 399 thousand dollars, it's highly possible that the original earning of store 1 was inputted in a raw format instead of being divided by 1000.
Thus, we removed all duplicates and divided the earning value in store 1 by 1000 for further processing.

<img src="Pics/"correlation.png",class="center">
### Data Exploration
#### Histogram plot
After cleansing, we plotted the most variables' distribution, all of which look acceptable.
 (See in Exhibit 2)
#### Scatterplots and correlation plots on total and P15 - P55 variables
By drawing scatterplots and correlation plots, high correlation is found among the population in each age group with ‘total’ population within 3 km of the restaurant, which indicates the high potential of multi-collinearity.  (see Table 1 and Figure 1 and more details in Exhibit 3)

## Part 3. Model Building
Firstly, we normalized variables ‘EARN’, ‘COMP’, ‘NCOMP’, ‘NREST’ and all age group variables (i.e. P15-P55) by total amount of residents. By comparing the dashboard of regression using un-normalized and normalized variables, we prefer to normalize data for further analysis based on more accountable variables (i.e., earnings per person and population proportion in each age group) to eliminate the impact of total population on other variables (see Exhibit 4-5). 
Moreover, we used “stepwise” approach to select variables in regression model based on significance (see Exhibit 6-7) and made further adjustment by removing P15 and P25 (i.e. age groups from 15 to 34) and adding back P35 (i.e. age group from 35-44), as people aged from 35 to 44 are the target customers of Croq'Pain. (see following Table 2)

<img src="Pics/"Regression.png",class="center">
                                               
## Part 4. Model Validation
To validate the model, we split the dataset into two parts: ‘50 historical restaurants before 1994’ and ‘10 restaurants after 1994’. Then we applied data of first 50 restaurants to amend regression model (result seen in Table 3) and to predict which restaurant opened after 1994 would reach the performance ratio target of Croq'Pain (i.e., 26%).

<img src="Pics/"validation.png",class="center">
                                               
## Part 5. Model Prediction
Based on the model, we predicted the potential earning of 10 restaurants opened after 1994 and calculated their performance ratios accordingly. It turned out that only "Toulouse" and "Montpellier" (see in Table 6) exceeded 26% level of performance ratio.

## Part 6. Conclusion and Advice in Location Choice
According to the model and prediction result, we highly recommend that Craq'pain should take the following factors into consideration when selecting location for new stores: **capital investment, regional income level, restaurant size, the proportion of residents aging from 35-44 in the region and the number of non-restaurant business per person in the region.**

To reach performance ratio goal and achieve future success for new restaurants, we recommend choosing **‘Toulouse’** and **‘Montpellier’** to invest.

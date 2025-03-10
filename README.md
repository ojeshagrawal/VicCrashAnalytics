# VicCrashAnalytics

# Executive Summary:
VicCrashAnalytics, a reputable data consulting company, an authority which provides complete analytics services to a range of governmental entities and organisations in Australia, is focussed on getting information about the given dataset and predicting whether some features of the surroundings make a place a blackspot or not. The dataset contains many variables like demographic attributes, road type, surrounding information etc with detailed data. 
This report has been drafted based on BACCM framework to make it understandable.
Blackspots are the places where accidents are most likely to occur. To reduce these government plans to act accordingly, for which this report and findings can be helpful.
This report addresses the questions asked and provides some analytical insights regarding the same.
To complete this report, the data analysis was done, along with building of different machine learning model building was done, for which the data was required, all thanks to the management team of VicCrashAnalytic for supplying the dataset which was up to the mark. 

# Business and understandings (Need, Value and Stakeholder):
Having name as one of the most trusted organisations in the world VicCrashAnalytics has always been able to supply the accurate analytical services to multiple departments of the government of Victoria. This project is aimed to help governmental Department of Transport.
The main aim of the project is to identify which all factors contribute to make a place to be labelled as Blackspot. To define, the blackspots are the places where accidents are reported more frequently in comparison to other places in an area.
Life of a human being is very important as accidents can cause severe injuries and if a person dies not only he dies but all other dependencies suffer.
In order to bring down the number of accidents happening the government plans to understand the most crucial factors for the same and accordingly plans to execute the interventions, like educational or legislative reforms.
The stakeholders for this project are Michael Howards, who is the Manager in charge for this project, the government and the governmental officials who will be using the analyses and models to bring reforms to reduce the number of blackspots

# Data Preparation and Machine Learning in Business
The dataset provided is properly supplied with all the information needed to perform the analysis and model building.
We followed and observed the following steps for the preparation of the data:
The dimensions of the dataset was (5326, 36) initially. There were missing data points in some of the following variables:
1.	AGE_65YRS_OVER_PCNT variable had 9 missing data points, which denotes % of people with 65+ of age.
2.	Lq_Licenses variable which had 6 missing data points, which denotes number of liquor license venues in a particular region.
Then using the dataset.describe() function we analysed the statistics like mean, mode, minimum and maximum value, etc. of the numerical variables in the dataset.
As noted above, in order to fill the missing data points, we used mean as the best substitute value, this is because:
1.	Both the variables had very fewer missing data points, so ignoring whole of the variables was not a good idea.
2.	The variables mentioned above had numerical values, had it been categorical variable we would have used mode as the best substitute.
Then we figured out different categories that were present in the variables and visually represented it. The two of these kinds of variables are ROAD_TYPE and Intersection.
The ROAD_TYPE variable gives us description of the road, as if it was a street, a road or so on. The category with ROAD_TYPE as Road was the highest with fewer Way and Freeways.
The Intersection variable gives us description of the whether the road segment had intersection or not. It was noted that the maximum number of road segments hadn’t had intersection.
As noted above, the ROAD_TYPE variable had categories in the alphabetical forms, hence, we converted it into numerical form by assigning dummy values using LabelEncoder. Similarly, dummy values were assigned to the variable Intersection.
Now, since, the regression classification model does not work on the alphabetical data, hence, we converted the variable Blackspot to BLACKSPOTS which had values:
a.	1 representing non-Blackspot.
b.	0 representing Blackspot.
Now, we remove all the non-essential variables which we won’t be using in the model building.
After filtering through the variables, the dimension of the dataset was (5326, 24).

# Model Development and Evaluation
In this process of the predictive modelling, we did split the data into two parts:
a.	80% of the data was kept for training the model. (X_train, y_train)
b.	20% of the data has been kept for testing the model. (X_test, y_test)
After the above-mentioned process, the data has been inspected.
Using the logreg = LogisticRegression(max_iter=100) function we created Logistic Regression model.
After running the model, we again inspect the values whether the model predicted the values that were already there and whether the model is predicting maximum value right or not.
In our case, the model is found to be working effectively.

# Evaluating the model:
Using various parameters our stats of the model are as follows:
a.	Accuracy: 91.9%
b.	Precision: 93.5%
c.	Recall: 97.8%
d.	F1: 95.6%
Hence, we are confident in our model.

The confusion matrix is as follows:
![image](https://github.com/user-attachments/assets/fa23ab41-74ff-4b2f-ab38-cd8a2cad150a)


# Solution and recommendations
It is evident from the analysis that:
1.	Blackspots were more in the areas which:
a.	 don’t have a traffic signal - This can be sorted out by installing the traffic signals at the places required and proper investigation of the spot should be done, if required the zebra-crossing should be installed or the pedestrian-crossing sign must be installed.
b.	Have an intersection, a supermarket, school, post– This problem can be solved by installing the reduce speed sign boards and educating the children about these while in school so that when they start to drive they have the knowledge of the same.
The model has been made in order to predict whether the next spot will be a blackspot or not a blackspot, given the variables’ values.
Hence, the model has been trained and tested accordingly.

# References
1. Apte, C. (2010). The role of machine learning in business optimization. In Proceedings of the 27th International Conference on Machine Learning (ICML-10) (pp. 1-2).
2. Apte, C. (2010). The role of machine learning in business optimization. In Proceedings of the 27th International Conference on Machine Learning (ICML-10) (pp. 1-2).
3. Raschka, S. (2015). Python machine learning. Packt publishing ltd.

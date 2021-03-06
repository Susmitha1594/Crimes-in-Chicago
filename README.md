# Data Analysis of Crimes in Chicago
### Aim of Project:
Crime has been a major issue in the current world. Crime rate has been increasing rapidly since past few years and especially in the United States. Classifying the crime rates that occurred in different locations and sending this data can be helpful for the police department to protect the public by identifying the underlying areas to protect people and provide safety. Chicago is one of those states where crime rate has been more. By using dataset from Kaggle ‘Chicago Crime from 01JAN2001 to 22JUL2020’(https://www.kaggle.com/n3v375/chicago-crime-from-01jan2001-to-22jul2020) we perform data analysis and check the different types of crimes occurring and give the information to the police department and take necessary steps based on the type of crime. The main aim of the project is to plot various Data Visualization graphs and implement different Machine Learning algorithms and finally evaluate the model that gives better accuracy in predicting the crimes which will help the police department to identify the serious crimes and take necessary actions to provide safety of the people.

### Dataset 
The dataset consists of reported incidents of crimes which have occurred in Chicago from 01 Jan 2001 to 22 Jul 2020. This data has been extracted from Chicago Police Department's CLEAR (Citizen Law Enforcement Analysis and Reporting). This dataset consists of 22 columns and 1048567 records. The dataset consists of columns as below:
ID - Unique identifier for the record.

Case Number - The Chicago Police Department RD Number (Records Division Number), which is unique to the incident.

Date - Date when the incident occurred. this is sometimes a best estimate.

Block - The partially redacted address where the incident occurred, placing it on the same block as the actual address.

IUCR - The Illinois Uniform Crime Reporting code.

Primary Type - The primary description of the IUCR code.

Description - The secondary description of the IUCR code, a subcategory of the primary description.

Location Description - Description of the location where the incident occurred.

Arrest - Indicates whether an arrest was made.

Domestic - Indicates whether the incident was domestic-related as defined by the Illinois Domestic Violence Act.
Beat - Indicates the beat where the incident occurred. A beat is the smallest police geographic area – each beat has dedicated police beat car. Three to five beats make up a police sector, and three sectors make up a police district.

District - Indicates the police district where the incident occurred. 

Ward - The ward (City Council district) where the incident occurred. 

Community Area - Indicates the community area where the incident occurred. Chicago has 77 community areas. 

FBI Code - Indicates the crime classification as outlined in the FBI's National Incident-Based Reporting System (NIBRS).

X Coordinate - The x coordinate of the location where the incident occurred.

Y Coordinate - The y coordinate of the location where the incident occurred. 

Year - Year the incident occurred.

Updated On - Date and time the record was last updated.

Latitude - The latitude of the location where the incident occurred. 

Longitude - The longitude of the location where the incident occurred. 

Location - The location where the incident occurred in a format that allows for creation of maps and other geographic operations on this data portal. 

### Steps performed for analysis
* Data Collection
* Data Pre-processing
* Data Visualization
* Feature selection and Correlation matrix
* Data Modeling
* Evaluation of the results

### Data Collection
The dataset that we have collected is from Kaggle source (https://www.kaggle.com/n3v375/chicago-crime-from-01jan2001-to-22jul2020)
It has 22 columns and 1048567 values in the table. We have imported the dataset and converted it into a pandas dataframe.

### Data Preprocessing
 Based on the columns we will firstly perform Data Pre-processing steps that can help us in getting a clean data for our analysis. We will take a sample of 900000 data and perform our analysis. First we have checked if the dataset consists of any null values and dropped them as there are few null values in the dataset and dropping them will not make much difference to the analysis. Then we converted the datetime column into individual month, date , time columns that will be used for our data visulization graphs.We have few columns like Ward, District and Community Area that have a datatype float and must be converted to string for further analysis. In columns Description and Location Description we have huge classes, so we have taken the classes that have occurred less than 20 and changed them to Others.
 
### Data Visualization
 #### Occurrence of Crimes
<img width="363" alt="Word cloud 1" src="https://user-images.githubusercontent.com/60418159/110204482-761bde80-7e30-11eb-966e-c3911828b32b.PNG">
<img width="586" alt="bar graph word cloud" src="https://user-images.githubusercontent.com/60418159/110204542-cf840d80-7e30-11eb-81f2-93931993f532.PNG">

We have plotted a word cloud and bar graph to check what the most frequently crimes are and displayed them in the decreasing order. We can see that from the bar graph the top five crimes are Theft, Battery, Criminal damage, Narcotics and Assault. We can see similar findings in word cloud as well where Theft, Battery, Criminal damage, Narcotics and Assault are displayed in bigger font. Therefore, from these plots we can find out the crimes that have occurred maximum number of times.

#### Plotting time series graph to check the top 5 crimes that have occurred in 24hrs in an day
<img width="562" alt="timeseries 24hrs" src="https://user-images.githubusercontent.com/60418159/110204836-71f0c080-7e32-11eb-9e24-adb5c4ed2cbe.PNG">

We can see the top 5 crimes that have been committed in Chicago are Theft, Battery, Criminal damage, Narcotics and Assault. By looking at the crimes that were committed in 24 hours we can understand the characteristics and behaviors of each crimes. From the graph we can see that a greater number of thefts have taken place around 12 in the afternoon, battery around 3pm, narcotics and criminal damage around night and assault around afternoon time. We can conclude that the top crimes have mostly occurred around 11am to 1pm where this is at the peak afternoon office working hours and the lowest was around morning time. Narcotics was shown high around two times 11am and 7pm.

#### Plotting time series graph for all the years and monthly.
<img width="567" alt="time-series monthly" src="https://user-images.githubusercontent.com/60418159/110204908-cac05900-7e32-11eb-94f4-2d0e54c24ebb.PNG">

While looking the graph, we can notice crime rate according to seasons. Crime rate has reduced around February, the reason could be due to the weather being bad inn winters. Crime looks more around summers as many people would be going for holidays due to good weather conditions.

#### Year that has maximum crimes
<img width="553" alt="year crimes" src="https://user-images.githubusercontent.com/60418159/110204963-31de0d80-7e33-11eb-9f11-2456eaa0514e.PNG">

From the bar plot, we can see that maximum number of crimes have occurred in 2003. We can notice that the crimes have been reducing as years pass. By the year 2020 the crime rate has drastically reduced as compared to 2003.

#### Correct number of arrests
<img width="403" alt="pie chart" src="https://user-images.githubusercontent.com/60418159/110204996-53d79000-7e33-11eb-97bb-31a093cd769e.PNG">
<img width="467" alt="bar plot piechart" src="https://user-images.githubusercontent.com/60418159/110205032-7cf82080-7e33-11eb-851e-803076ce3a58.PNG">

For all the crimes, arrests were not made. Percentage of people arrested are 27% and 72% are not arrested. From the line plot we have maximum arrests made in the year 2005 and the least in 2020. Number of arrests have gradually reduced since 2009 could be due to having a good number of people getting employed.
#### Choropleth map of wards and number of crimes
<img width="630" alt="wards" src="https://user-images.githubusercontent.com/60418159/110205303-82a23600-7e34-11eb-982c-320e151aa8f9.PNG">

#### Choropleth map of district and number of crimes for the Chicago coordinates for the year 2020
<img width="661" alt="district" src="https://user-images.githubusercontent.com/60418159/110205347-b4b39800-7e34-11eb-9c64-68dcfe6d507f.PNG">

#### Feature selection and Correlation matrix

Before proceeding with feature selection, we will remove few unwanted classes in primary_type. By using group_by for the primary_type column we will remove the least 12 classes. 
![bargraph](https://user-images.githubusercontent.com/60418159/110206316-27734200-7e3a-11eb-954b-736c6e27cc1c.png)

The above graph shows the primary_type classes we will consider.
We have converted few columns to numeric values and plotted a heatmap.
![correation matrix](https://user-images.githubusercontent.com/60418159/110206348-58ec0d80-7e3a-11eb-962f-dee434e049cd.png)

After plotting the heatmap, we will print the correlation values with which we will select the features that will be used for train and test data.

<img width="281" alt="corr values" src="https://user-images.githubusercontent.com/60418159/110206378-7a4cf980-7e3a-11eb-8fe0-8c2414fdeee3.PNG">

We have made feature selection by taking the correlation values above 0.1. From the results we can see that Description, Arrest and Domestic have been more correlated for the model which we will use in train and test data.
### Data Modeling
We will be using supervised machine learning algorithms. We have performed Neural Network model, Random Forest model and KNN model to check for the accuracy each model performs. Finally we will use Ensemble model which is uses

#### Neural Network
We build a model by using neural network algorithm by importing MLPClassifier. Assigning solver as 'adam' which is stochastic gradient based optimizer , activation function as 'relu' which is the rectified linear unit function, 'hidden_layer_sizes' refers to the number of neurons, 'random_state' determines random number generation for weights and bias initialization, 'max_iter' is the number of iterations. 


<img width="273" alt="nn" src="https://user-images.githubusercontent.com/60418159/110207394-8045d900-7e40-11eb-873a-70c6577924a7.PNG">

![nn mod](https://user-images.githubusercontent.com/60418159/110207401-8471f680-7e40-11eb-907f-c2f92a3030e6.png)

We have an Accuracy score of 0.90, Recall of 0.90, Precision of 0.89 and F1 score of 0.90. Overall, the Accuracy score is 90% for a Neural Network model.

#### Random Forest 
Using Random Forest Classifier by import RandomForestClassifier method. Assigning 'n_estimators' as 100 which is the number of trees in the forest , 'min_samples_split' as 40 which is the minimum number of samples required, setting 'bootstrap' to true which will select the features randomly , 'max_depth' is the maximum height of the tree.

<img width="314" alt="rf-1" src="https://user-images.githubusercontent.com/60418159/110207920-3f02f880-7e43-11eb-9916-e91901ffccd7.PNG">


![rf-2](https://user-images.githubusercontent.com/60418159/110207923-41655280-7e43-11eb-90a7-f9476a3ab448.png)

We have an Accuracy score of 0.94, Recall of 0.94, Precision of 0.93 and F1 score of 0.94. Overall, the Accuracy score is 94% for a Neural Network model.

#### KNN Model
Using KNN model by selecting the n_neighbours as 4 to find the accuracy.


<img width="208" alt="knn" src="https://user-images.githubusercontent.com/60418159/110207961-8be6cf00-7e43-11eb-956c-4967b2285a1d.PNG">


![knn-2](https://user-images.githubusercontent.com/60418159/110207963-8db09280-7e43-11eb-8c1a-46ca86fb255b.png)


We have an Accuracy score of 0.93, Recall of 0.93, Precision of 0.93 and F1 score of 0.93. Overall, the Accuracy score is 93% for a KNN model.


#### Ensemble model
Ensemble model gives us a good raise in machine learning results by combining different models to give a better accuracy. Ensemble model consists of different individual trained supervised learning methods and are merged to provide a better predictive performance as compared to individual trained model. 
For our Ensemble model we have combined Neural Network, Random Forest Classifier and KNN model. By using Voting Classifier, we will build an ensemble model. After looking at the accuracy we have 94.1%.


<img width="236" alt="ensem" src="https://user-images.githubusercontent.com/60418159/110207971-9dc87200-7e43-11eb-952c-d7a99ccb7e0f.PNG">


![ensm-2](https://user-images.githubusercontent.com/60418159/110207972-9f923580-7e43-11eb-98a5-f2c23ff1e70b.png)

### Evaluation of result
The models that we performed were Neural Network using MLPClassifier, Random Forest, KNN model. From all the models Neural Network using MLPClassifier has an accuracy of 90%, but the execution speed is very slow compared to other models. Random Forest Classifier has an accuracy of 94% and the execution time was also little faster than other models. KNN model has an accuracy of 93%. Finally, in ensemble model even thought if it has less execution speed it combines all the models together to give a little better accuracy of 94.1% which is almost close to Random Forest Classifiers accuracy. 

### Conclusion 
All the models have given a good accuracy with different execution times. Out of all the models KNN has a better accuracy with less execution time, but whereas Ensemble model has a little better accuracy than KNN model.

#### References:
*	Kaggle dataset. Chicago Crime from 01Jan2001 to 22JUL2020.Retrieved from     
  https://www.kaggle.com/n3v375/chicago-crime-from-01jan2001-to-22jul2020
* kaggle. Classification with ML: Predict Crime Type. Retrieved from  
  https://www.kaggle.com/heng8835/classification-with-ml-predict-crime-type
*	Project pro. How to split DateTime Data to create multiple feature in python? Retrieved from
  https://www.dezyre.com/recipes/split-datetime-data-create-multiple-feature-in-python
*	Tutorials point. Machine Learning with Python. Retrieved from   
  https://www.tutorialspoint.com/machine_learning_with_python/machine_learning_improving_performance_of_ml_model.htm
* Towards Data Science. Accuracy, Precision, Recall or F1?. Retrieved from  
  https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9
* AditModi. Machine Learning Projects. Retrieved from  
  https://github.com/My-Machine-Learning-Projects-2020/chicago-crime-data-analysis/blob/master/Chicago-Crime-Data-Analysis.ipynb








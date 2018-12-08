

# Introduction and Project Background
For our final project we performed machine learning on JMU IT Help Desk support tickets. We used a dataset of tickets that were extracted from the JMU IT Help desk from August 16, 2018 to October 31, 2018. The datatype of our dataset is categorical data. The datafields we used from our extracted data are Troubleshooting Notes and Service Grouping. Troubleshooting Notes is a brief description of what was done during an IT support session. From the contents of the troubleshooting notes, a help desk employee then will determine the customers problem from a selection of already existing service categories. In our initaial data we included Service Categories and Troubleshooting Notes, below are examples of what that data looked like. With our dataset we predicted the Service Categories for customer support tickets based off of keywords in the Troubleshooting Notes section. These predictions could potentially assist the Help Desk by improving the accuracy of how well their support tickets are categorized. Correct ticket categorization is important because if a ticket is grouped with an incorrect service category, the intended department might not recieve the ticket in a timely manner which would lead to a slower response rate and a potentially unsatisfied customer. 

We used the Naive Bayes machine learning model to form predictions. We preformed all of our data analysis, machine learning model processing, data testing, and data training with the RapidMiner Software. We then used Microsoft Excel to visualize our data along with https://voyant-tools.org to perform text visualization and analysis. 

### Introduction and data description visualizations 
Each service grouping as a percentage of the total amount of service tickets in dataset 
![Before data](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/total_real.JPG)
Word Cloud of words with the highest frequency in trouble shooting notes in the original dataset
![WordCloud](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/wordcloud)

Word Link that links words with high frequency's in troubleshooting notes, with keywords
![WordLink](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Wordlink.png)

Highest Frequency words in Troubleshooting notes 

![wordoccurance](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Occurances%20of%20words.PNG)

[Link to More Visualizations] https://voyant-tools.org/?corpus=92c24d4c36952fc089ac79378305ba61&view=Summary
## Constraints of Project and Project Setup
There were a few constraints with our dataset for this project. Some service categories were not included in the dataset because they were categories that were used by another department outside of the help desk. Along with this, tickets that included personally identifiable information were discarded from the dataset. Aside from these two constraints our data quality is really good. We had no tickets with the same Troubleshooting Notes, no zero-value data, and no irrelevant data in our dataset. During data cleaning we only had to remove one Service Category because it only had one ticket associated with it. The dataset we received from the JMU IT Help Desk had all tickets categorized by date, so we had to shuffle our dataset randomly. We also gave each ticket in our dataset an ID number so we would be able to identify the correct Service Category for its associated Troubleshooting Notes. After cleaning our data we split it 90-10 (90% for testing, 10% for training). We then removed the Service Category for our testing data. The remaining 10% was used for training. Our training data included a Service Category associated with the correct Troubleshooting Notes. After splitting our data we applied the Naive Bayes machine learning model to our testing data. Within RapidMiner we tokenized the Troubleshooting Notes datafield for all of our datasets. After doing this we were able to count the occurances of every word within all ticket's Troubleshooting Notes in order to allow the model to predict its Service Category. From this we applied the model and exported the result to Microsoft Excel. Shown below are our RapidMiner processes that we used for data cleaning, splitting, training, testing, and Naive Bayes model application.

### RapidMiner Processes used in project
1st Process Used in Rapid Miner 
![1st Process](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/1st_Process.JPG)

2nd Process Used in Rapid Miner
![2nd Process](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/2nd_Process.JPG)
3rd Process Used in Rapid Miner
![3rd Process](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/3rd_Process.JPG)
      
## Machine Learning Model and Parameters
We chose to use Naive Bayes to classify service groupings for our dataset of support ticket Troubleshooting Notes. Naive Bayes is a good model to use when analyzing categorical data. It also performs well when trying to predict classifications. Using Naive Bayes in RapidMiner requires a datafield to be set to label. We were able to apply this in our project because support ticket service groupings are also a label. The data that was being analyzed to make the service grouping prediction was the troubleshooting notes field which is considered as regular data in RapidMiner. Since we had the correct parameters to apply Naive Bayes in RapidMiner we decided it was the best choice for us. Naive Bayes also performed well when attempting to predict positive and negative tweets based on the contents of the tweet. Our project uses Naive Bayes in a similar way.  

### Training data Visualization
Percentage of tickets grouped by each service grouping in our training data
![trainVisual](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Training_Data_Pie_Chart.JPG)

### Model Application Results
Naive Bayes Model Accuracy
![modelAcc](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Accuracy.JPG)
Naive Bayes Model Kappa
![modelK](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Kappa.JPG)
Each predicted service grouping as a percentage of the total amount of service tickets in dataset 
![theResult](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/total%20predicted.JPG)
Accuracy of our predictions compared to original data service groupings 
![realAccuracy](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/of_total_accuracy.JPG)
Accuracy of our predictions by individual service grouping
![1](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Accounts_Pie_chart.JPG)
![2](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/IT_pie_chart.JPG)
![3](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Software_pie_chart.JPG)
![4](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/academic_pie_chart.JPG)
![5](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/admin_pie_chart.JPG)
![6](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/email_pie_chart.JPG)
![7](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/internet_pie_chart.JPG)

## Conclusion, limitations, and suggestions
After analyzing result data and applying the Naive Bayes Model we came to the conclusion that our model performed well. Since the original dataset had all of the service groupings we were able to compare that predicted service grouping for our training data against correct service grouping. When we compared our testing data predications to the correct service groupings from our original data set, our testing data predicted the correct service grouping 59% of the time. Also the percentage of each individual service grouping predicted is very similar to the percentage of our starting dataset where every ticket was labeled correctly. Based off of our results and analysis of our data we were able to conclude that service groupings can be predicted by analyzing keywords within the troubleshooting notes of a JMU IT Help Desk Support Ticket. This could help improve the quality of troubleshooting tickets at the IT Help desk. From these results employees could be trained to document support sessions better in by including more relevant keywords in the troubleshooting notes field of a ticket. This would further help increase the percentage of tickets that are labeled correctly which could help the IT Help Desk's Troubleshooting support process. After using Voyant-Tools.org, we discovered that the word "customer" was used 7,515 time in all 5,939 support tickets. We believe that this had a major impact on RapidMiner predicting the service categories and that by removing the word, it could potentially increase the accuracy of our predictions. This is because the word "customer" is completely irrelevant to the IT customer service department and should be neglected.

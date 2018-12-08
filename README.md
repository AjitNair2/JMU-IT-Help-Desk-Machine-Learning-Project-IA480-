# Introduction and Project Background
In this project we performed machine learning on JMU IT Help Desk Support Tickets. We used a dataset of tickets that was extracted from the JMU IT Help desk from August 16, 2018 to October 31,2018. The datatype of our dataset is categorical data. The datafields we used from our extracted data are the troubleshooting notes and service grouping. Troubleshooting notes is a brief description of what was done during a IT support session. From the contents of the description a Help Desk Employee choose a service category from the list of existing service categories. Below are examples of what data for these two datafields look like. With our dataset we predicted the service categories for Support tickets in our dataset based off of keywords in the troubleshooting notes section. These prediction could help the Help Desk improve the accuracy of how well tickets are categorized. Correct ticket categorization is important because if a ticket is grouped with an incorrect service grouping, the intended department might not recieve the ticket which could lead to slower response rate and potentially unsatisfied customers. 

We used the Naive Bayes Machine learning model to form predictions. We did all of our data analysis, machine learning model processing, data testing, data training with the RapidMiner Software. We used Microsoft Excel to visualize our data along with https://voyant-tools.org to perform some visualization and text analysis. 

### Introduction and data description visualizations 
Each service grouping as a percentage of the total amount of service tickets in dataset 
![Before data](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/total_real.JPG)
Word Cloud of words with the highest frequency in trouble shooting notes in the original dataset
![WordCloud](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/wordcloud)

Word Link that links words with high frequency's in troubleshooting notes, with keywords
![WordLink](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Wordlink.png)

Highest Frequency words in Troubleshooting notes 

![wordoccurance](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Occurances%20of%20words.PNG)

## Constraints of Project and Project Setup
There were a few constraints with our dataset for this project. Some service categories were not included in the dataset because they were categories that were used by another department outside of the help desk. Along with this, tickets that included personally identifiable information were discarded from the dataset. Aside from these two constraints our data quality is really good. We had no tickets with the same troubleshooting notes, no zero value data, and no irrelevant data in our dataset. During data cleaning we only had to remove one service category because it only had one ticket associated with it. The dataset we received from the JMU IT Help Desk had all tickets categorized so we had to shuffle our dataset randomly since they were in order by date. We also gave each ticket in our dataset an ID number to help with identification. After data cleansing we trained our data by splitting 90% of the data into a testing dataset, where troubleshooting notes did not have an associated service grouping because we removed them before applying the machine learning model. The remaining 10% of our data was our machine learning model training set, which included troubleshooting notes that were labeled with a service grouping. Before we split our data we randomized the order of the tickets in our dataset by shuffling the tickets into a random order. After splitting our data we began to apply the Naive Bayes machine learning model. Within RapidMiner we tokenized the troubleshooting notes datafield for all of our dataset. After doing this we were able to count the occurance of every word within all ticket's troubleshooting notes in order to allow the model to make service category predictions. From this we applied the model and exported the result to Microsoft excel. Shown Below are our RapidMiner processes that we used in data cleaning, splitting, training, testing, and Naive Bayes model application.

### RapidMiner Processes used in project
1st Process Used in Rapid Miner 
![1st Process](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/1st_Process.JPG)
2nd Process Used in Rapid Miner
![2nd Process](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/2nd_Process.JPG)
3rd Process Used in Rapid Miner
![3rd Process](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/3rd_Process.JPG)
      
## Machine Learning Model and Parameters
We chose to use Naive Bayes to classify service groupings for our dataset of support ticket troubleshooting notes. Naive Bayes is a good model to use when analyzing categorical data. It also performs well when trying to predict a classification. Using Naive Bayes in RapidMiner requires a datafield to be a label. We were able to apply this in our project because support ticket service groupings are also a label. The data that was being analyzed to make the service grouping prediction was the troubleshooting notes field which is considered as regular data in RapidMiner. Since we had the correct parameters to apply Naive Bayes in RapidMiner we decided it was the best choice for us. Naive Bayes also performed well when attempting to predict positive and negative tweets based on the contents of the tweet. Our project uses Naive Bayes in a similar way.  

### Training data Visualization
Percentage of tickets grouped by each service grouping in our training data
![trainVisual](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Training_Data_Pie_Chart.JPG)

### Model Application Results
Naive Bayes Model Accuracy
![modelAcc](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Accuracy.JPG)
Naive Bayes Model Kappa
![modelK](https://github.com/dalto2wk/JMU-IT-Help-Desk-Machine-Learning-Project-IA480-/blob/master/ProjectImages/Kappa.JPG)

## Conclusion, limitations, and suggestions
After analyzing result data and applying the Naive Bayes Model we came to the conclusion that our model performed well. Since the original dataset had all of the service groupings we were able to compare that predicted service grouping for our training data against correct service grouping. When we compared our testing data predications to the correct service groupings from our original data set, our testing data predicted the correct service grouping 59% of the time. Also the percentage of each individual service grouping predicted is very similar to the percentage of our starting dataset where every ticket was labeled correctly. Based off of our results and analysis of our data we were able to conclude that service groupings can be predicted by analyzing keywords within the troubleshooting notes of a JMU IT Help Desk Support Ticket. This could help improve the quality of troubleshooting tickets at the IT Help desk. From these results employees could be trained to document support sessions better in by including more relevant keywords in the troubleshooting notes field of a ticket. This would further help increase the percentage of tickets that are labeled correctly which could help the IT Help Desk's Troubleshooting support process. After using Voyant-Tools.org, we discovered that the word "customer" was used 7,515 time in all 5,939 support tickets. We believe that this had a major impact on RapidMiner predicting the service categories and that by removing the word, it could potentially increase the accuracy of our predictions. This is because the word "customer" is completely irrelevant to the IT customer service department and should be neglected.

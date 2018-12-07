# Introduction and Project Background
In this project we performed machine learning on JMU IT Help Desk Support Tickets. We used a dataset of tickets that was extracted from the JMU IT Help desk from August 16, 2018 to October 31,2018. The datatype of our dataset is categorical data. The datafields we used from our extracted data are the troubleshooting notes and service grouping. Troubleshooting notes is a brief description of what was done during a IT support session. From the contents of the description a Help Desk Employee choose a service category from the list of existing service categories. Below are examples of what data for these two datafields look like. With our dataset we predicted the service categories for Support tickets in our dataset based off of keywords in the troubleshooting notes section. 

We used the Naive Bayes Machine learning model to form predictions. We did all of our data analysis, machine learning model processing, data testing, data training with the RapidMiner Software. We used Microsoft Excel to visualize our data along with https://voyant-tools.org to perform some visualization and text analysis. 

### Introduction and data description visualizations 


## Constraints of Project and Project Setup
There were a few constraints with our dataset for this project. Some service categories were not included in the dataset because they were categories that were used by another department outside of the help desk. Along with this, tickets that included personally identifiable information were discarded from the dataset. Aside from these two constraints our data quality is really good. We had no tickets with the same troubleshooting notes, no zero value data, and no irrelevant data in our dataset. During data cleaning we only had to remove one service category because it only had one ticket associated with it. The dataset we received from the JMU IT Help Desk had all tickets categorized so we had to shuffle our dataset randomly since they were in order by date. We also gave each ticket in our dataset an ID number to help with identification. After data cleansing we trained our data by splitting 90% of the data into a testing dataset, where troubleshooting notes did not have an associated service grouping because we removed them before applying the machine learning model. The remaining 10% of our data was our machine learning model training set, which included troubleshooting notes that were labeled with a service grouping. Before we split our data we randomized the order of the tickets in our dataset by shuffling the tickets into a random order. After splitting our data we began to apply the Naive Bayes machine learning model. Within RapidMiner we tokenized the troubleshooting notes datafield for all of our dataset. After doing this we were able to count the occurance of every word within all ticket's troubleshooting notes in order to allow the model to make service category predictions. From this we applied the model and exported the result to Microsoft excel. Shown Below are our RapidMiner processes that we used in data cleaning, splitting, training, testing, and Naive Bayes model application.

### RapidMiner Processes used in project

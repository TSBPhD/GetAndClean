---
title: "README.md"
author: "TSBrownPhD"
date: "May 12, 2016"
output: html_document
---

# Getting and Cleaning Data - Week 4 Assignment
## Generating a Tidy Data Set
This assignment utilizes the data files made publically available from a study
named "Human Activity Recognition Using Smartphones Dataset - Version 1.0" by
Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto and Xavier
Parra and provided as part of the course via https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

The objectives of this project were to create one R script called run_analysis.R that does the following :

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names.
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

To achieve this, my run_anaylsis.R takes the following steps:

### 1. Merges the training and the test sets to create one data set.
#### Read in data files.
a. Set the working directory

b. Create objects to hold the file locations; makes code for reading easier

c. Read the data into dataframes

#### Merge the training and the test sets to create one data set.
d. Combine the complet test and train sets

e. Add names to columns in combined dataset from features.txt


### 2. Extracts only the measurements on the mean and standard deviation for each measurement.
a. Find all columns with "mean()" in the name

b. Find all columns with "std()" in the name

c. Column combine the corresponding columns into a new object named "meanstd"


### 3. Uses descriptive activity names to name the activities in the data set
a. Combine the subject numbers and activity labels

b. Name the subject label columns

c. Add human-readable activity from lable

d. Add combined subject numbers, activity labels, and human readable activity to the combined dataset as a complete, named dataset as well as the subset from 2.


### 4. Appropriately labels the data set with descriptive variable names. 

Note that I had already labeled the features above in 1, but renamed "subject" and "label" to "study_subject" and "activity_code", respectively, at this point for clarity.


### 5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

a. Use the aggregate function to group columns 4 through 82 of the data frame meanstddesc by study_subject and activity and calculate the mean

b. Finally, use dput to put the contents of the data frame tidy into a file named "tidy.txt"



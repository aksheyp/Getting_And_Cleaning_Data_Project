Getting and Cleaning Data Course Project CodeBook

This file discusses the variables, the data, and any transformations or work that I have performed to clean up the data.

    The data was obtained from the following site:
    http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
    
	The data for the project is as follows:
    https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
    
	The run_analysis.R script performs the following steps to clean the data:
    1)  Read X_train.txt, y_train.txt and subject_train.txt from the "C:/Users/user/Desktop/coursera/gacd/data/train" folder and 
		store them in trainData, trainLabel and trainSubject variables respectively.
    2)	Read X_test.txt, y_test.txt and subject_test.txt from the "C:/Users/user/Desktop/coursera/gacd/data/test" folder and 
		store them in testData, testLabel and testsubject variables respectively.
	3)	Concatenate testData to trainData to generate a 10299 x 561 data frame, joinData, then concatenate testLabel to 
		trainLabel to generate a 10299 x 1 data frame, joinLabel, then concatenate testSubject to trainSubject to generate
		a 10299 x 1 data frame, joinSubject.
	4)  Read the features.txt file from the "C:/Users/user/Desktop/coursera/gacd/data" folder and store the data in a variable called
	    features. Only the measurements on the mean and Standard Deviation are extracted. This results in a 66 indices list. 
	    So the subset of joinData has 66 corresponding columns.
    5)  Clean the column names of the subset. The "()" and "-" symbols in the names are removed, as well as capitalising the first letter 
	    of "mean" and "std" respectively.
    6)  Read the activity_labels.txt file from the "C:/Users/user/Desktop/coursera/gacd/data" folder and store the data
		in a variable called activity.
    7)  Clean the activity names in the second column of activity. All names are converted to lower cases. 
		If the name has an underscore between letters, the underscore is removed the letter immediately after the underscore is capitalised.
    8)  Transform the values of joinLabel according to the activity data frame.
    9)  Combine the joinSubject, joinLabel and joinData by column to get a new cleaned 10299 x 68 data frame called cleanedData. 
		The first two columns, "subject" and "activity" are properly named and the "subject" column contains integers that range from
		1 to 30 inclusive; the "activity" column contains 6 kinds of activity names; the last 66 columns contain measurements 
		that range from -1 to 1 exclusive.
    10) Write the cleanedData out to "merged_data.txt" file in the current working directory.
    11) Lastly, generate a second independent tidy data set with the average of each measurement for each activity and 
		each subject. This has 30 unique subjects and 6 unique activities, which result in a 180 combinations of the two. 
		Then, for each combination, we mean of each measurement with the corresponding combination is calculated. So, after initialising
		the result data frame and performing the two for-loops, we get a 180 x 68 data frame.
    12) Write the result out to "data_with_means.txt" file in current working directory.

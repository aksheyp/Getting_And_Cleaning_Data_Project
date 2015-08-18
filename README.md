Getting and Cleaning Data - Course Project

This file describes how run_analysis.R script works.

    1) First, unzip the data from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip and rename the folder as "data".
    2) Put both the folder "data" and the run_analysis.R script in the current working directory.
    3) Second, use source("run_analysis.R") command in RStudio.
    4) Third, two output files are generated in the current working directory, namely, "merged_data.txt" (7.9 Mb), which contains a data frame called 
	   "cleanedData" with a 10299 * 68 dimension. Then "data_with_means.txt" (220 Kb) which contains a data frame called "result" with 180 * 68 dimension.
    5) Finally, use data <- read.table("data_with_means.txt") command in RStudio to read the file. 
	   As we are required to get the average of each variable for each activity and each subject, and there are 6 activities in total and 30 subjects in total, 
	   we have 180 rows with all combinations for each of the 66 features.

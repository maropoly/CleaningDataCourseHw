##This is a CodeBook for Cleaning Data Assignment to help merge two data sets into one unified dataset


####Source of the original data AS fileURL:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

This is where the full description at the site where the data was obtained:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

####Process

The script run_analysis.R performs the following process to clean up the data and create tiny data sets:

Merge the training and test sets to create one data set.

Reads features.txt and uses only the measurements on the mean and standard deviation for each measurement.

Reads activity_labels.txt and applies human readable activity names to name the activities in the data set.

Labels the data set with descriptive names. (Names are converted to lower case; underscores and brackets are removed.)

Merges the features with activity labels and subject IDs. The result is saved as tidy-UCI-HAR-dataset.txt.

The average of each measurement for each activity and each subject is merged to a second data set. The result is saved as tidy-UCI-HAR-dataset-AVG.txt.

####Variables
The variables for both files start out with Subject Id in first column, followed by activity name and finally with the measurement aatributes in the next corresponding columns in dataframe.
Subject ID is from 1-30.
x <- rbind(x_train, X_test)
y <- rbind(y_train, y_test)
s <- rbind(subject_train, subject_test)

x_train <- read.table("./UCI HAR Dataset/train/X_train.txt", header = FALSE)
X_test <- read.table("./UCI HAR Dataset/test/X_test.txt", header = FALSE)
y_train <- read.table("./UCI HAR Dataset/train/y_train.txt", header = FALSE)
y_test <- read.table("./UCI HAR Dataset/test/y_test.txt", header = FALSE)
subject_train <- read.table("./UCI HAR Dataset/train/subject_train.txt", header = FALSE)
subject_test <- read.table("./UCI HAR Dataset/test/subject_test.txt", header = FALSE)

####Output

tidy-UCI-HAR-dataset.txt

tidy-UCI-HAR-dataset.txt is data frame.

The first column contains subject IDs.
The second column contains activity names.
The last 66 columns are measurements.
Subject IDs are integers between 1 and 30.


tidy-UCI-HAR-dataset-AVG.txt

tidy-UCI-HAR-dataset-AVG.txt is data frame.

The first column contains subject IDs.
The second column contains activity names.
Averages for each of the 66 attributes are in columns 3-68.

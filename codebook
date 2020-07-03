This is the code book for run_analysis.R script,It explains what the code does in the chronological order
1)dataset downloaded and extracted

2)Assign each data to variables
features <- features.txt : 561 rows, 2 columns(in the environment tab it is described as 561 obs or 2 variables)
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
the code for that looks like
features <- read.table("UCI HAR Dataset/features.txt", col.names = c("n","functions"))

activities <- activity_labels.txt : 6 rows, 2 columns
List of activities performed when the corresponding measurements were taken and its codes (labels)
activities <- read.table("UCI HAR Dataset/activity_labels.txt", col.names = c("code", "activity"))


subject_test <- test/subject_test.txt : 2947 rows, 1 column
contains test data of 9/30 volunteer test subjects being observed
subject_test <- read.table("UCI HAR Dataset/test/subject_test.txt", col.names = "subject")

x_test <- test/X_test.txt : 2947 rows, 561 columns
contains recorded features test data
x_test <- read.table("UCI HAR Dataset/test/X_test.txt", col.names = features$functions)

y_test <- test/y_test.txt : 2947 rows, 1 columns
contains test data of activities’code labels
y_test <- read.table("UCI HAR Dataset/test/y_test.txt", col.names = "code")


subject_train <- test/subject_train.txt : 7352 rows, 1 column
contains train data of 21/30 volunteer subjects being observed
subject_train <- read.table("UCI HAR Dataset/train/subject_train.txt", col.names = "subject")

x_train <- test/X_train.txt : 7352 rows, 561 columns
contains recorded features train data
x_train <- read.table("UCI HAR Dataset/train/X_train.txt", col.names = features$functions)

y_train <- test/y_train.txt : 7352 rows, 1 columns
contains train data of activities’code labels
y_train <- read.table("UCI HAR Dataset/train/y_train.txt", col.names = "code")


3)Merges the training and the test sets to create one data set
X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function
Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function
Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function
Merged_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function

4)Extracts only the measurements on the mean and standard deviation for each measurement
TidyData (10299 rows, 88 columns) is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

5)Uses descriptive activity names to name the activities in the data set
Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable

6)Appropriately labels the data set with descriptive variable names
code column in TidyData renamed into activities
All Acc in column’s name replaced by Accelerometer
All Gyro in column’s name replaced by Gyroscope
All BodyBody in column’s name replaced by Body
All Mag in column’s name replaced by Magnitude
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time

7)From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
FinalData (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Export FinalData into FinalData.txt file.

Data Location:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
Script File:

run_analysis.R
Environment:

RStudio Version 1.0.153
OS - OSX El Capitan, V. 10.11.6
Input Files:

test/Y_test.txt -- This file contains accelerometer activity code info

1 column, 2,947 rows
V1 - Column contains the accelerometer activity code
Activity codes:
Walking
Walking_upstairs
Walking_downstairs
Siting
Standing
Laying
train/Y_train.txt -- This file contains accelerometer activity code info

1 column, 7,352 rows
V1 - Column contains the accelerometer activity code
Activity codes:
Walking
Walking_upstairs
Walking_downstairs
Siting
Standing
Laying
test/subject_test.txt -- This file contains accelerometer subject/ user ID info

1 column, 2,947 rows
V1 - Column contains the accelerometer subject ID code
train/subject_train.txt -- This file contains accelerometer subject/ user ID info

1 column, 7,352 rows
V1 - Column contains the accelerometer subject ID code
test/X_test.txt -- This file contains accelerometer measurements/ observations info

561 columns, 2,947 rows
V1 to V561 - Columns contains the accelerometer measurements
train/subject_train.txt -- This file contains accelerometer measurements/ observations info

561 columns, 7,352 rows
V1 to V561 - Columns contains the accelerometer measurements
features.txt -- This file contains the accelerometer column names

2 columns, 561 rows
V1 - Feature Code
V2 - Feature Name
activity_labels.txt -- This files contains the activity codes and descriptions

2 columns, 6 rows
V1 - Activity Code
V2 - Activity Name
Processing Approach:

Download the data files using the above link

Load the required data files

ActivityTest will load the Y_test.txt data
ActivityTrain will load the Y_train.txt data
SubjectTest will load the subject_test.txt data
SubjectTrain will load the subject_train.txt data
FeaturesTest will load the x_test.txt data
FeaturesTrain will load the x_train.txt data
Bind the Activity, Subject and Features (measurements) data

Bind the ActivityTest and ActivityTrain into the Activity data frame
1 column, 10,299 rows
V1 - Column contains the accelerometer activity code
Activity codes:
Walking
Walking_upstairs
Walking_downstairs
Siting
Standing
Laying
Bind the SubjectTest and SubjectTrain into the Subject data frame
1 column, 10,299 rows
V1 - Column contains the accelerometer subject ID code
Bind the FeaturesTest and the FeaturesTrain into the Features data frame
561 columns, 10,299 rows
V1 to V561 - Columns contains the accelerometer measurements
Name the Activity, Subject and Features columns with descriptive names

Use the features.txt file to lable the column names for the Features data frame
Columns too numerous to list
Label the Subject data frame V1 column to subject
Label the Activity data frames V1 column to activity
Merge all data into the MergeInfo data frame

Bind the Features (measurements), subject and activity data frames into MergeInfo
Extract only the columns with std() and mean() measurements/ observations

Compacts the MergeInfo data frame to 68 columns

Here is the selected/ extracted column list:

tBodyAcc-mean()-X: Number - measurement
tBodyAcc-mean()-Y: Number - measurement
tBodyAcc-mean()-Z: Number - measurement
tBodyAcc-std()-X: Number - measurement
tBodyAcc-std()-Y: Number - measurement
tBodyAcc-std()-Z: Number - measurement
tGravityAcc-mean()-X: Number - measurement
tGravityAcc-mean()-Y: Number - measurement
tGravityAcc-mean()-Z: Number - measurement
tGravityAcc-std()-X: Number - measurement
tGravityAcc-std()-Y: Number - measurement
tGravityAcc-std()-Z: Number - measurement
tBodyAccJerk-mean()-X: Number - measurement
tBodyAccJerk-mean()-Y: Number - measurement
tBodyAccJerk-mean()-Z: Number - measurement
tBodyAccJerk-std()-X: Number - measurement
tBodyAccJerk-std()-Y: Number - measurement
tBodyAccJerk-std()-Z: Number - measurement
tBodyGyro-mean()-X: Number - measurement
tBodyGyro-mean()-Y: Number - measurement
tBodyGyro-mean()-Z: Number - measurement
tBodyGyro-std()-X: Number - measurement
tBodyGyro-std()-Y: Number - measurement
tBodyGyro-std()-Z: Number - measurement
tBodyGyroJerk-mean()-X: Number - measurement
tBodyGyroJerk-mean()-Y: Number - measurement
tBodyGyroJerk-mean()-Z: Number - measurement
tBodyGyroJerk-std()-X: Number - measurement
tBodyGyroJerk-std()-Y: Number - measurement
tBodyGyroJerk-std()-Z: Number - measurement
tBodyAccMag-mean(): Number - measurement
tBodyAccMag-std(): Number - measurement
tGravityAccMag-mean(): Number - measurement
tGravityAccMag-std(): Number - measurement
tBodyAccJerkMag-mean(): Number - measurement
tBodyAccJerkMag-std(): Number - measurement
tBodyGyroMag-mean(): Number - measurement
tBodyGyroMag-std(): Number - measurement
tBodyGyroJerkMag-mean(): Number - measurement
tBodyGyroJerkMag-std(): Number - measurement
fBodyAcc-mean()-X: Number - measurement
fBodyAcc-mean()-Y: Number - measurement
fBodyAcc-mean()-Z: Number - measurement
fBodyAcc-std()-X: Number - measurement
fBodyAcc-std()-Y: Number - measurement
fBodyAcc-std()-Z: Number - measurement
fBodyAccJerk-mean()-X: Number - measurement
fBodyAccJerk-mean()-Y: Number - measurement
fBodyAccJerk-mean()-Z: Number - measurement
fBodyAccJerk-std()-X: Number - measurement
fBodyAccJerk-std()-Y: Number - measurement
fBodyAccJerk-std()-Z: Number - measurement
fBodyGyro-mean()-X: Number - measurement
fBodyGyro-mean()-Y: Number - measurement
fBodyGyro-mean()-Z: Number - measurement
fBodyGyro-std()-X: Number - measurement
fBodyGyro-std()-Y: Number - measurement
fBodyGyro-std()-Z: Number - measurement
fBodyAccMag-mean(): Number - measurement
fBodyAccMag-std(): Number - measurement
fBodyBodyAccJerkMag-mean(): Number - measurement
fBodyBodyAccJerkMag-std(): Number - measurement
fBodyBodyGyroMag-mean(): Number - measurement
fBodyBodyGyroMag-std(): Number - measurement
fBodyBodyGyroJerkMag-mean(): Number - measurement
fBodyBodyGyroJerkMag-std(): Number - measurement
subject: Number - subject ID
activity: Number - activity code
Convert activity codes to decriptive activities in the MergeInfo data frame

Activity description and codes:
Walking = 1
Walking_upstairs = 2
Walking_downstairs = 3
Siting = 4
Standing = 5
Laying = 6
Relable column names in the MergeInfo data frame with better descriptions

Here is a list of the more descriptive column names:

timeBodyAccelerometer-mean()-X
timeBodyAccelerometer-mean()-Y
timeBodyAccelerometer-mean()-Z
timeBodyAccelerometer-std()-X
timeBodyAccelerometer-std()-Y
timeBodyAccelerometer-std()-Z
timeGravityAccelerometer-mean()-X
timeGravityAccelerometer-mean()-Y
timeGravityAccelerometer-mean()-Z
timeGravityAccelerometer-std()-X
timeGravityAccelerometer-std()-Y
timeGravityAccelerometer-std()-Z
timeBodyAccelerometerJerk-mean()-X
timeBodyAccelerometerJerk-mean()-Y
timeBodyAccelerometerJerk-mean()-Z
timeBodyAccelerometerJerk-std()-X
timeBodyAccelerometerJerk-std()-Y
timeBodyAccelerometerJerk-std()-Z
timeBodyGyroscope-mean()-X
timeBodyGyroscope-mean()-Y
timeBodyGyroscope-mean()-Z
timeBodyGyroscope-std()-X
timeBodyGyroscope-std()-Y
timeBodyGyroscope-std()-Z
timeBodyGyroscopeJerk-mean()-X
timeBodyGyroscopeJerk-mean()-Y
timeBodyGyroscopeJerk-mean()-Z
timeBodyGyroscopeJerk-std()-X
timeBodyGyroscopeJerk-std()-Y
timeBodyGyroscopeJerk-std()-Z
timeBodyAccelerometerMagnitude-mean()
timeBodyAccelerometerMagnitude-std()
timeGravityAccelerometerMagnitude-mean()
timeGravityAccelerometerMagnitude-std()
timeBodyAccelerometerJerkMagnitude-mean()
timeBodyAccelerometerJerkMagnitude-std()
timeBodyGyroscopeMagnitude-mean()
timeBodyGyroscopeMagnitude-std()
timeBodyGyroscopeJerkMagnitude-mean()
timeBodyGyroscopeJerkMagnitude-std()
frequencyBodyAccelerometer-mean()-X
frequencyBodyAccelerometer-mean()-Y
frequencyBodyAccelerometer-mean()-Z
frequencyBodyAccelerometer-std()-X
frequencyBodyAccelerometer-std()-Y
frequencyBodyAccelerometer-std()-Z
frequencyBodyAccelerometerJerk-mean()-X
frequencyBodyAccelerometerJerk-mean()-Y
frequencyBodyAccelerometerJerk-mean()-Z
frequencyBodyAccelerometerJerk-std()-X
frequencyBodyAccelerometerJerk-std()-Y
frequencyBodyAccelerometerJerk-std()-Z
frequencyBodyGyroscope-mean()-X
frequencyBodyGyroscope-mean()-Y
frequencyBodyGyroscope-mean()-Z
frequencyBodyGyroscope-std()-X
frequencyBodyGyroscope-std()-Y
frequencyBodyGyroscope-std()-Z
frequencyBodyAccelerometerMagnitude-mean()
frequencyBodyAccelerometerMagnitude-std()
frequencyBodyAccelerometerJerkMagnitude-mean()
frequencyBodyAccelerometerJerkMagnitude-std()
frequencyBodyGyroscopeMagnitude-mean()
frequencyBodyGyroscopeMagnitude-std()
frequencyBodyGyroscopeJerkMagnitude-mean()
frequencyBodyGyroscopeJerkMagnitude-std()
subject
activity
Write the MergeInfo data frame to MergeInfo.csv

Aggregate data from MergeInfo into the MergeInfo2 data frame with the average of all variables

Sort MergeInfo2 by Subject and Activity columns

Write the MergeInfo2 file to a text file called MergeInfoTidyData.txt

Output Files:

MergeInfo.csv -- contains merged accelerometer information
MergeInfo2.txt -- contains tidy accelerometer information

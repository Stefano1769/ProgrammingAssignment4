# Codebook
# Variables
Variable                                   | Comments
-------------------------------------------|-----------
Subject                                    |  subject identifier of volunteer (1-24)
ActivityName                               |  name of activity subject performed (LAYING,SITTING,STANDING,WALKING,WALKING_DOWNSTAIRS,WALKING_UPSTAIRS)
timeBodyAccelerometerMeanX                 |  mean of tBodyAcc-mean()-X
timeBodyAccelerometerMeanY                 |  mean of tBodyAcc-mean()-Y
timeBodyAccelerometerMeanZ                 |  mean of tBodyAcc-mean()-Z
timeBodyAccelerometerStdX                  |  mean of tBodyAcc-std()-X
timeBodyAccelerometerStdY                  |  mean of tBodyAcc-std()-Y
timeBodyAccelerometerStdZ                  |  mean of tBodyAcc-std()-Z
timeGravityAccelerometerMeanX              |  mean of tGravityAcc-mean()-X
timeGravityAccelerometerMeanY              |  mean of tGravityAcc-mean()-Y
timeGravityAccelerometerMeanZ              |  mean of tGravityAcc-mean()-Z
timeGravityAccelerometerStdX               |  mean of tGravityAcc-std()-X
timeGravityAccelerometerStdY               |  mean of tGravityAcc-std()-Y
timeGravityAccelerometerStdZ               |  mean of tGravityAcc-std()-Z
timeBodyAccelerometerJerkMeanX             |  mean of tBodyAccJerk-mean()-X
timeBodyAccelerometerJerkMeanY             |  mean of tBodyAccJerk-mean()-Y
timeBodyAccelerometerJerkMeanZ             |  mean of tBodyAccJerk-mean()-Z
timeBodyAccelerometerJerkStdX              |  mean of tBodyAccJerk-std()-X
timeBodyAccelerometerJerkStdY              |  mean of tBodyAccJerk-std()-Y
timeBodyAccelerometerJerkStdZ              |  mean of tBodyAccJerk-std()-Z
timeBodyGyroscopeMeanX                     |  mean of tBodyGyro-mean()-X
timeBodyGyroscopeMeanY                     |  mean of tBodyGyro-mean()-Y
timeBodyGyroscopeMeanZ                     |  mean of tBodyGyro-mean()-Z
timeBodyGyroscopeStdX                      |  mean of tBodyGyro-std()-X
timeBodyGyroscopeStdY                      |  mean of tBodyGyro-std()-Y
timeBodyGyroscopeStdZ                      |  mean of tBodyGyro-std()-Z
timeBodyGyroscopeJerkMeanX                 |  mean of tBodyGyroJerk-mean()-X
timeBodyGyroscopeJerkMeanY                 |  mean of tBodyGyroJerk-mean()-Y
timeBodyGyroscopeJerkMeanZ                 |  mean of tBodyGyroJerk-mean()-Z
timeBodyGyroscopeJerkStdX                  |  mean of tBodyGyroJerk-std()-X
timeBodyGyroscopeJerkStdY                  |  mean of tBodyGyroJerk-std()-Y
timeBodyGyroscopeJerkStdZ                  |  mean of tBodyGyroJerk-std()-Z
timeBodyAccelerometerMagMean               |  mean of tBodyAccMag-mean()
timeBodyAccelerometerMagStd                |  mean of tBodyAccMag-std()
timeGravityAccelerometerMagMean            |  mean of tGravityAccMag-mean()
timeGravityAccelerometerMagStd             |  mean of tGravityAccMag-std()
timeBodyAccelerometerJerkMagMean           |  mean of tBodyAccJerkMag-mean()
timeBodyAccelerometerJerkMagStd            |  mean of tBodyAccJerkMag-std()
timeBodyGyroscopeMagMean                   |  mean of tBodyGyroMag-mean()
timeBodyGyroscopeMagStd                    |  mean of tBodyGyroMag-std()
timeBodyGyroscopeJerkMagMean               |  mean of tBodyGyroJerkMag-mean()
timeBodyGyroscopeJerkMagStd                |  mean of tBodyGyroJerkMag-std()
frequencyBodyAccelerometerMeanX            |  mean of fBodyAcc-mean()-X
frequencyBodyAccelerometerMeanY            |  mean of fBodyAcc-mean()-Y
frequencyBodyAccelerometerMeanZ            |  mean of fBodyAcc-mean()-Z
frequencyBodyAccelerometerStdX             |  mean of fBodyAcc-std()-X
frequencyBodyAccelerometerStdY             |  mean of fBodyAcc-std()-Y
frequencyBodyAccelerometerStdZ             |  mean of fBodyAcc-std()-Z
frequencyBodyAccelerometerJerkMeanX        |  mean of fBodyAccJerk-mean()-X
frequencyBodyAccelerometerJerkMeanY        |  mean of fBodyAccJerk-mean()-Y
frequencyBodyAccelerometerJerkMeanZ        |  mean of fBodyAccJerk-mean()-Z
frequencyBodyAccelerometerJerkStdX         |  mean of fBodyAccJerk-std()-X
frequencyBodyAccelerometerJerkStdY         |  mean of fBodyAccJerk-std()-Y
frequencyBodyAccelerometerJerkStdZ         |  mean of fBodyAccJerk-std()-Z
frequencyBodyGyroscopeMeanX                |  mean of fBodyGyro-mean()-X
frequencyBodyGyroscopeMeanY                |  mean of fBodyGyro-mean()-Y
frequencyBodyGyroscopeMeanZ                |  mean of fBodyGyro-mean()-Z
frequencyBodyGyroscopeStdX                 |  mean of fBodyGyro-std()-X
frequencyBodyGyroscopeStdY                 |  mean of fBodyGyro-std()-Y
frequencyBodyGyroscopeStdZ                 |  mean of fBodyGyro-std()-Z
frequencyBodyAccelerometerMagMean          |  mean of fBodyAccMag-mean()
frequencyBodyAccelerometerMagStd           |  mean of fBodyAccMag-std()
frequencyBodyBodyAccelerometerJerkMagMean  |  mean of fBodyBodyAccJerkMag-mean()
frequencyBodyBodyAccelerometerJerkMagStd   |  mean of fBodyBodyAccJerkMag-std()
frequencyBodyBodyGyroscopeMagMean          |  mean of fBodyBodyGyroMag-mean()
frequencyBodyBodyGyroscopeMagStd           |  mean of fBodyBodyGyroMag-std()
frequencyBodyBodyGyroscopeJerkMagMean      |  mean of fBodyBodyGyroJerkMag-mean()
frequencyBodyBodyGyroscopeJerkMagStd       |  mean of fBodyBodyGyroJerkMag-std()

# Trasformation

1. First of all the dataset was split into features, subject and activity. Each of these were split into test and train sets and then they were all merged to get a single dataset called data.all
2. The second step imports the variable names for measurement data.It finds the only the columns that contain variables that are the mean and standard deviation of measurements and subsequently subsets the combined data to only these variables.
 - mean_std.select Finds the positions in features that only contains variables that are for mean and standard deviation for measurements
 - data.sub subset of data.all with only the columns of variables that mean and standard deviations of measurements
 3. The activity labels dataset is imported which contains the descriptive names of the activities linked with the numeric code for the activity. This is joined with the combine_labels dataset and the output is a single variable dataset with descriptive activity labels for each row of the dataset.
 - activity.labels imported dataset that links numeric coded activity with descriptive name
 4. The measurement variable names for the mean and standard deviation variables are extracted from the features dataset. The names are modified a bit for readbility, in the tables it's possible to see how name were changed.
 5. The data.all dataset is sorted by subject and activity for readability in a dataframe called:
  - data.tidy Outputs a dataset sorted by subject and activity with the mean for measurement variable for each combination of subject+activity.

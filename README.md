## Readme for "Getting and Cleaning Data" course project

### Description of experiment and dataset
(taken from [1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012)

"The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain."

### Step-by-step description of run_analysis.R script

* Read subject IDs/activity labels/561-feature vector data for training and test sets into R
* Name "subjects" and "activity" columns accordingly
* cbind subject/activity/561-feature vector from respective training and test set data to form complete training and test sets
* rbind complete training and test sets to form complete set of all data
* Name variables from 561-feature vector to be extracted (mean and standard deviations of measurements) accordingly
* Extract subject, activity, and measurement mean and standard deviation variables (as above) to first tidy data set
* Set "subjects" and "activity" column classes as factors
* Name levels in "activity" column according to activity labels given in 'activity_labels.txt' file
* Aggregate means (sorted by subject ID and activity) into second, independent, final dataset
* Write final dataset to space seperated .txt file, 'tidydataset.txt'

### Variables chosen to be extracted

* Subject IDs
* Activity labels
* tBodyAcc-mean()-XYZ
* tBodyAcc-std()-XYZ
* tGravityAcc-mean()-XYZ
* tGravityAcc-std()-XYZ
* tBodyGyro-mean()-XYZ
* tBodyGyro-std()-XYZ
* fBodyAcc-mean()-XYZ
* fBodyAcc-std()-XYZ
* fBodyGyro-mean()-XYZ
* fBodyGyro-std()-XYZ

### Reasoning behind chosen variables

* Subject IDs and activity labels required for describing feature variables
* Mean and stand deviations of only raw measurements
* Features that could be derived from raw measurements were excluded
* Time and frequency domain signals included as both are mutually exclusive
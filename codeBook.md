The following steps were followed to create FinalData.txt

1. Download
Data was downloaded from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip.
using file.download()

2. assignment
The following data tables were created in my R workspace to make it easy to work with the given data
- features <- features.txt : 561 rows, 2 columns 
- activities <- activity_labels.txt : 6 rows, 2 columns 
- subject_test <- test/subject_test.txt : 2947 rows, 1 column 
- x_test <- test/X_test.txt : 2947 rows, 561 columns
- y_test <- test/y_test.txt : 2947 rows, 1 columns 
- subject_train <- test/subject_train.txt : 7352 rows, 1 column
- x_train <- test/X_train.txt : 7352 rows, 561 columns
- y_train <- test/y_train.txt : 7352 rows, 1 columns

3. run_analysis.R was run on the above variables
  run_analysis.R did the following tasks
  - merge x_train and x_test into X (rbind)
  - merge y_train and y_test into Y (rbind)
  - merge subject_train and subject_test into Subject (rbind)
  - merge Subject, X and Y into Merged_Data (cbind) 
  - extracted measurements on only the mean and the standard deviation from Merged_Data (select from dplyr)
  - changed the names on the final data base so that it is more descriptive("acc" -> "acceleration") (gsub)
  - write the final data into a text file "FinalData.txt" (write.table)


following are the name changes that were implemented:
- code column in TidyData renamed into activities
- All Acc in column’s name replaced by Accelerometer
- All Gyro in column’s name replaced by Gyroscope
- All BodyBody in column’s name replaced by Body
- All Mag in column’s name replaced by Magnitude
- All start with character f in column’s name replaced by Frequency
- All start with character t in column’s name replaced by Time

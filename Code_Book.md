## CodeBook


The run_analysis.R script include getting and preparation data (got nessesary libraries) and 
then the 5 steps required as described in the course project’s definition.
## 1. Dataset downloaded, checked if alredy exists and extracted.
## 2. Assigned each data to variables
    features 
    activities 
    subject_test 
    x_test
    y_test 
    subject_train
    x_train 
    y_train

## 3.Merged the training and the test sets to create one data set
      X <- rbind(x_train, x_test 
      Y <- rbind(y_train, y_test)
      Subject <- rbind(subject_train, subject_test)
      Merged_Data <- cbind(Subject, Y, X)

## 4.Extracted only the measurements on the mean and standard deviation for each measurement
    TidyData <- Merged_Data %>% select(subject, code, contains("mean"), contains("std"))
    TidyData (10299 obs., 88 variables) is created by subsetting Merged_Data, 
    selected columnsare: subject, code and the measurements on the mean and standard deviation for each measurement

## 5.Created another tidy dataset from the data set in step 4,
    FinalData (180 obs., 88 variables) is created by summarizing TidyData 
    where the means of each variable for each activity and
    each subject, groupped by subject and activity 
    WALKING
    WALKING_UPSTAIRS
    WALKING_DOWNSTAIRS
    SITTING
    STANDING
    LAYING.
    Export FinalData into FinalData.txt file.
    

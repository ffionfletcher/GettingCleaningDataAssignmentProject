GETTING AND CLEANING DATA ASSIGNMENT PROJECT
by Ffion Fletcher

This assignment project was to take a set of data and transform then to one tidy dataset. Included are:
1. The script used to do the transformation and analysis of the data
2. A codebook describing the contents of the tidy dataset

The run_analysis script was used to download and transform the data into tidy data and then later
created a second tidy dataset with the averages.

The following were done in the run_analysis script:
1. The libraries to be used were loaded

2. The file was downloaded and unzipped to a folder on my local drive

3. Only the files that were needed to create a tidy dataset were read into R - subject_test, 
X_test, y_test, subject_train, X_train, y_train, activity_labels and features.
 
4. Two datasets were then created using the cbind commands. The datasets were combined
using the datasets that had "test" in their names to create a new dataset called test; and combined
the datasets that had "train" in their names to create a new dataset called train.

5. The test and train datasets were then combined using rbind to create one dataset - test_train.
rbind was used and both the test and train datasets created from step four have the same variables.

6. The columns in the new dataset test_train were then given labels using the names I chose as well as
the names in the features dataset.

7. The select command was then used to extract only the columns with mean() and std() in their names.
Note: When the select command was first run, an error was received citing duplicated column names. I 
decided to include a command to remove duplicated names since those names did not include any with 
mean() or std().

8. In tidying the data, the following were done:
- The activities were labeled with the activities' names as opposed to the code that was initially read into R
- I then gathered the variables that had mean() in the name which created two variables - MeanFeatures and MeanValue.
The same thing was done for the variables with std() in the name, creating STDFeatures and STDValue. This created a long
dataset which for me was easier to work with especially in being able to give the variables meaningful names.
- Since MeanFeatures and STDFeatures had the same values, I decided to create only one variable called Features. 
This was done by removing the the mean() and std () from the values in the MeanFeatures column, which I then renamed Features.
- I then selected on the columns needed for the final tidy dataset: Subject_ID, Activities, Features, Mean and Standard_Deviation.

9. In creating the second tidy dataset to show the average of each variable for each activity and each subject, the followig was done:
- The dataset from step 8 above was grouped by Subject_ID, then Activities and then Features.
- Then summarised the data creating two new variables called MeanAverage and STDAverage.
- This new dataset contains only the average values with the following variables: Subject_ID, Activities, Features, MeanAverage and
STDAverage.

10. The dataset was then exported to a .txt file - avgdata.txt. This can be read back into R using the read.table(header=TRUE) command.

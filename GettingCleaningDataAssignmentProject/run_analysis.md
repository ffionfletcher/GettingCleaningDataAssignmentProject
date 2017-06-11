##Load Libraries to be used
library(dplyr)
library(tidyr)

##Download the file
fileurl <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"

temp <- tempfile()
download.file(fileurl, temp)
unzip(temp, exdir = "~/Data_Science_Files/week4")
rm(temp)

##Read the files into R
subject_test <- read.table("~/Data_Science_Files/week4/UCI HAR Dataset/test/subject_test.txt",
                           header = FALSE)
X_test <- read.table("~/Data_Science_Files/week4/UCI HAR Dataset/test/X_test.txt",
                     header = FALSE)
y_test <- read.table("~/Data_Science_Files/week4/UCI HAR Dataset/test/y_test.txt",
                     header = FALSE)
subject_train <- read.table("~/Data_Science_Files/week4/UCI HAR Dataset/train/subject_train.txt",
                            header = FALSE)
X_train <- read.table("~/Data_Science_Files/week4/UCI HAR Dataset/train/X_train.txt",
                      header = FALSE)
y_train <- read.table("~/Data_Science_Files/week4/UCI HAR Dataset/train/y_train.txt",
                      header = FALSE)
activity_labels <- read.table("~/Data_Science_Files/week4/UCI HAR Dataset/activity_labels.txt",
                              header = FALSE)
features <- read.table("~/Data_Science_Files/week4/UCI HAR Dataset/features.txt",
                       header = FALSE)

##Create two datasets with the test and train datasets
test <- cbind(subject_test, y_test, X_test)
train <- cbind(subject_train, y_train, X_train)

##Create one dataset
test_train <- rbind(test, train)

##Label the columns with descriptive names
featureslabels <- as.character(features[,2])
colnames(test_train) <- c("subjectID","activities", featureslabels)

##Extract only the variables with mean and standard deviation measurements
##Selecting only the variables with mean() or std()
test_train <- test_train[ , !duplicated(colnames(test_train))]
ttms <- test_train %>% select(subject, activities, contains("mean()"), contains("std()"))

##Tidying the Data
#First - label the types of activities
activity_labels <- as.character(activity_labels[,2])
ttms$activities <- factor(test_train$activities, levels = c(1,2,3,4,5,6), 
                     labels = activity_labels)

#Second - gather mean variables and standard deviation variables
ttms2 <- ttms %>% gather(MeanFeatures, MeanValue, 3:35)
ttms2 <- ttms2 %>% gather(STDFeatures, STDValue, 3:35)

#Third - remove duplicate feature variables to have one variable with features
ttms2$MeanFeatures <- sub("\\-mean\\(\\)", "", ttms2$MeanFeatures)
ttms2$MeanFeatures <- sub("\\-std\\(\\)", "", ttms2$MeanFeatures)

#Fourth - rename the columns and keep the variables required
colnames(ttms2) <- c("Subject_ID","Activities", "Features", "Mean", "STDFeatures", "Standard_Deviation")
finalttms <- ttms2 %>% select(Subject_ID, Activities, Features, Mean, Standard_Deviation)

finalttms

##Create second independent tidy dataset with the average of each variable 
##for each activity and each subject.

avgdata <- finalttms %>% group_by(Subject_ID, Activities, Features) %>%
            summarise(AverageMean = mean(Mean), AverageSTD = mean(Standard_Deviation))
                    
##Export the data to a .txt file
write.table(avgdata, file = "avgdata.txt", row.name = FALSE)









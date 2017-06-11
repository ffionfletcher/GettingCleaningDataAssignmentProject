CODE BOOK FOR AVGDATA.TXT

Subject_ID - column 1
 - Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 
 
Activities - column 2
 - The name of the activity done for each observation. Values are WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING,
STANDING and LAYING

Features - column 3
 - The features come from the accelerometer and gyroscope 3-axial raw signals as explained in the README file accompanying this submission. Values are: 
   - tBodyAcc-X - Body Acceleration in the X direction denoted in time (t)
   - tBodyAcc-Y - Body Acceleration in the Y direction denoted in time (t)
   - tBodyAcc-Z - Body Acceleration in the Z direction denoted in time (t)
   - tGravityAcc-X - Gravity Acceleration in the X direction denoted in time (t)
   - tGravityAcc-Y - Gravity Acceleration in the Y direction denoted in time (t)
   - tGravityAcc-Z - Gravity Acceleration in the Z direction denoted in time (t)
   - tBodyAccJerk-X - Jerk of the Body Acceleration in the X direction denoted in time (t)
   - tBodyAccJerk-Y - Jerk of the Body Acceleration in the Y direction denoted in time (t)
   - tBodyAccJerk-Z - Jerk of the Body Acceleration in the Z direction denoted in time (t)
   -tBodyGyro-X - Gyroscopic Body movement in the X direction denoted in time (t)
   -tBodyGyro-Y - Gyroscopic Body movement in the Y direction denoted in time (t)
   -tBodyGyro-Z - Gyroscopic Body movement in the Z direction denoted in time (t)
   -tBodyGyroJerk-X - Gyroscopic Jerk of the Body movement in the X direction denoted in time (t)
   -tBodyGyroJerk-Y - Gyroscopic Jerk of the Body movement in the Y direction denoted in time (t)
   -tBodyGyroJerk-Z - Gyroscopic Jerk of the Body movement in the Z direction denoted in time (t)
   -tBodyAccMag - Magnitude of the Body Acceleration in all three directions: X,Y and Z, denoted in time (t)
   -tGravityAccMag - Magnitude of the Gravity Acceleration in all three directions: X,Y and Z, denoted in time (t)
   -tBodyAccJerkMag - Magnitude of the Jerk of the Body Acceleration in all three directions: X,Y and Z, denoted in time (t)
   -tBodyGyroMag - Magnitude of the Gyroscopic Body movement in all three directions: X,Y and Z, denoted in time (t)
   -tBodyGyroJerkMag - Magnitude of the Gyroscopic Jerk of the Body movement in all three directions: X,Y and Z, denoted in time (t)
   -fBodyAcc-X - Body Acceleration in the X direction denoted in frequency (f)
   -fBodyAcc-Y - Body Acceleration in the Y direction denoted in frequency (f)
   -fBodyAcc-Z - Body Acceleration in the Z direction denoted in frequency (f)
   -fBodyAccJerk-X - Jerk of the Body Acceleration in the X direction denoted in frequency (f)
   -fBodyAccJerk-Y - Jerk of the Body Acceleration in the Y direction denoted in frequency (f)
   -fBodyAccJerk-Z - Jerk of the Body Acceleration in the Z direction denoted in frequency (f)
   -fBodyGyro-X - Gyroscopic Body movement in the X direction denoted in frequency (f)
   -fBodyGyro-Y - Gyroscopic Body movement in the Y direction denoted in frequency (f)
   -fBodyGyro-Z - Gyroscopic Body movement in the Z direction denoted in frequency (f)
   -fBodyAccMag - Magnitude of the Body Acceleration in all three directions: X,Y and Z, denoted in frequency (f)
   -fBodyAccJerkMag - Magnitude of the Jerk of the Body Acceleration in all three directions: X,Y and Z, denoted in frequency (f)
   -fBodyGyroMag - Magnitude of the Gyroscopic Body movement in all three directions: X,Y and Z, denoted in frequency (f)
   -fBodyGyroJerkMag - Magnitude of the Gyroscopic Jerk of the Body movement in all three directions: X,Y and Z, denoted in frequency (f)
 
AverageMean - column 4
 - contains the average of the mean values collected for each subject, activity and feature combination
 
AverageSTD - column 5
 - contains the average of the standard deviation values collected for each subject, activity and feature combination

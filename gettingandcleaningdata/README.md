Getting and Cleaning Data Project

run_analysis.R

The cleanup script (run_analysis.R) does the following:

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive activity names.
5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Running the script:

To run the script, source run_analysis.R
If no such file or directory error occurs, set the working directory to folder containing the files.
e.g. if the files are under "UCI HAR Dataset" directory of "d:/coursera/datascience/getting-and-cleaning-data/assignment"
then run setwd("d:/coursera/datascience/getting-and-cleaning-data/assignment")

Process:
1. For both the test and train datasets, produce an interim dataset:
	a. Extract the mean and standard deviation features (listed in CodeBook.md, section 'Extracted Features'). This is the values table.
	b. Get the list of activities.
	c. Put the activity labels (not numbers) into the values table.
	d. Get the list of subjects.
	e. Put the subject IDs into the values table.
2. Join the test and train interim datasets.
3. Put each variable on its own row.
4. Rejoin the entire table, keying on subject/acitivity pairs, applying the mean function to each vector of values in each subject/activity pair. This is the clean dataset.
5. Write the clean dataset "tidy_movement_data.txt" to disk.

Cleaned Data
The cleaned output data is in "UCI HAR Dataset/tidy_movement_data.txt"
It contains one row for each subject/activity pair and columns for subject, activity, and each feature that was a mean or standard deviation from the original dataset.
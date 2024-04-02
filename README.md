# Human Activity Recognition Using Smart Phone Data 📱

The Human Activity Recognition database was built from the recordings of 30 study participants performing activities of daily living (ADL) while carrying a waist-mounted smartphone with embedded inertial sensors. The objective is to classify activities into one of the six activities performed.

# Description of experiment
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKINGUPSTAIRS, WALKINGDOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

# Data Exploration
**1.** Initial exploration reveals that accelerometer and gyroscope readings are crucial for activity recognition.Density plots help differentiate between static and dynamic activities based on the **tBodyAccMag-mean() feature**
<br>
<p align="center">
  <img src="Images/Different Activities based on Acc.png" alt="Density-like plot for the distribution of 'tBodyAccMag-mean()' values across different activities" /><br>
  <em>Caption: Density-like plot for the distribution of 'tBodyAccMag-mean()' values across different activities</em>
</p>
<br>
Using the above density plot we can easily come with a condition to seperate static activities from dynamic activities.

if(tBodyAccMag-mean()<=-0.5):
    
    Activity = "static"
else:

    Activity = "dynamic"

**2** Another Important feature for Activity recognition is Angle of the Activity. Box plots help differentiate between static and dynamic activities by Analysing **Angle between X-axis and gravityMean** and **Y-axis and gravityMean** features.
<br>
<p align="center">
  <img src="Images/X Angle based Activities.png" alt="Box plot illustrating the distribution of 'Angle between X-axis and gravityMean' values across different activities" /><br>
  <em>Caption: Box plot illustrating the distribution of 'Angle between X-axis and gravityMean' values across different activities</em>
</p>
<br>

# School_District_Analysis

## Project Overview
After a school board found evidence of academic dishonesty among the grades of one of the district schools, a chief data scientist for the city school district has given us the following tasks to complete the school district data analysis.

1. Replace the math and reading scores for Thomas High School with NaNs while keeping the rest of the data intact.
2. Repeat the school district analysis and recreate the following metrics:
    - The district summary
    - The school summary
    - The top 5 and bottom 5 performing schools, based on the overall passing rate
    - The average math score for each grade level from each school
    - The average reading score for each grade level from each school
    - The scores by school spending per student, by school size, and by school type.
3. Describe how these changes affect the overall analysis.

## Resources
- Data Source: schools_complete.csv, students_complete.csv
- Software: Python 3.7.7, Anaconda Navigator 1.9.12, Conda 4.8.4, Jupyter Notebook 6.0.3

## Results

### Replace Ninth-Grade Reading and Math Scores at Thomas High School with NaN
```
# Install numpy using conda install numpy or pip install numpy. 
# Step 1. Import numpy as np.
import numpy as np

# Step 2. Use the loc method on the student_data_df to select all the reading scores from the 9th grade at Thomas High School and replace them with NaN.
student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School"),"reading_score"] = np.nan

#  Step 3. Refactor the code in Step 2 to replace the math scores with NaN.
student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School"),"math_score"] = np.nan

#  Step 4. Check the student data for NaN's. 
student_data_df.tail(10)
```
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90834754-9959c300-e310-11ea-9104-5b9fc311df42.png">
</p>

### Repeat the School District Analysis

- The district summary
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90918895-1cc7f280-e3ab-11ea-86dc-11e3d5a0d1fd.png">Pre correction
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90834746-98c12c80-e310-11ea-9bb1-90c5b80a0cfa.png">After correction
</p>
The district summary was barely affected by the correction made:<br/>
- The average Math Score decreased by 0.1 point to 78.9.<br/>
- The % Passing Math decreased by 0.2% to 74.8%.<br/>
- The % Overall Passing decreased by 0.3% to 64.9%.<br/><br/>

- The school summary
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90918905-1e91b600-e3ab-11ea-8287-04cc30205d2c.png">Pre correction
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90918909-1f2a4c80-e3ab-11ea-90b7-3296810ec63b.png">After correction
</p>
The school summary was slightly affected by the correction made:<br/>
- The average Reading Score increased by 0.1 point to 83.9.<br/>
- The % Passing Math decreased by 0.1% to 93.2%.<br/>
- The % Passing Math decreased by 0.3% to 97.0%.<br/>
- The % Overall Passing decreased by 0.3% to 90.6%.<br/><br/>

- High and Low performing schools based on the overall passing rate
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90834767-9bbc1d00-e310-11ea-8bbf-aac572055b80.png">
  Top 5 schools
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90836950-4551dd00-e316-11ea-82e8-8dc7fbc9b609.png">
  Bottom 5 schools
</p>
The 5 highest and 5 lowest performing schools ranking in the district was not affected by the correction.<br/><br/>

- Math and Reading Scores by Grade
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90834748-98c12c80-e310-11ea-8e79-5471f2832077.png">
  <img src="https://user-images.githubusercontent.com/68669675/90834752-9959c300-e310-11ea-921d-dbe0afd02c4d.png"> 
</p>
<p align="center">Math scores (left) and Reading scores (right)</p>
As expected, the average math and reading scores for Thomas High School ninth graders show as NaN on the math and reading scores by grade summary. <br/><br/>

- Scores by School Spending
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90918914-1f2a4c80-e3ab-11ea-93a7-53600aeb0cce.png"><br/>Pre correction
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90918915-1fc2e300-e3ab-11ea-8c84-b62876291a1a.png">After correction
</p>
The only changes are on the $630-644 range where the % Passing Reading and the % Overall Passing both dropped by 0.1% to respectively 84.3% and 62.8%.<br/><br/>

- Scores by School Size
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90918911-1f2a4c80-e3ab-11ea-87c0-c538166d07de.png"><br/>Pre correction
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90918912-1f2a4c80-e3ab-11ea-9445-edd9b20feaa6.png"><br/>After correction
</p>
The only change is on the Medium size school range where the % Passing Reading dropped by 0.1% to 96.7%.<br/><br/>

- Scores by School Type
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90918919-205b7980-e3ab-11ea-9c0c-cd1ead21a6ca.png">
</p>
There is no noticeable change to the scores by school type summary after correction.<br/><br/>

## Summary
Replacing the math and reading scores did not imply any major change to the school district analysis.\
The following metrics were slightly affected by the correction: the district summary, the school summary for Thomas High School, the scores by school spending and the scores by school size summaries.
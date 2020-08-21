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
  <img src="https://user-images.githubusercontent.com/68669675/90834746-98c12c80-e310-11ea-9bb1-90c5b80a0cfa.png">
</p>

- The school summary
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90834757-99f25980-e310-11ea-824a-15157afc96a4.png">
</p>

- High and Low performing schools based on the overall passing rate
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90834767-9bbc1d00-e310-11ea-8bbf-aac572055b80.png">
  Top 5 schools
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90836950-4551dd00-e316-11ea-82e8-8dc7fbc9b609.png">
  Bottom 5 schools
</p>

- Math and Reading Scores by Grade
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/90834748-98c12c80-e310-11ea-8e79-5471f2832077.png">math

  <img src="https://user-images.githubusercontent.com/68669675/90834752-9959c300-e310-11ea-921d-dbe0afd02c4d.png">reading
</p>

## Summary


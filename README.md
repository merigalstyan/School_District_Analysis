# School District Analysis

Maria, the chief data scientist for a city school district, needs to analyze all data regarding each school, the students, the grades, and the scores. This analysis also includes the types of schools and the budget for each school. This analysis is to help the data scientist make sense of school performance trends and patterns.

### Purpose

The purpose of this analysis is to check all the data about a school district, to find performance patterns and trends. These insights will be used to make important decisions about each school, their budgeting, students and student performances to improve outcomes.

## Section 1: Data Collection

In the initial step of this analysis, it's essential to collect the correct data and create paths to the file. Maria has a CSV file that includes all the school data in this case. We first need to import **pandas** and **os** to the *read_csv* file and assign the path to the file to a variable. Here's how it's done:

<img width="658" alt="Screen Shot 2022-09-21 at 4 37 39 PM" src="https://user-images.githubusercontent.com/111609994/191628298-0fc4b351-8dec-4b05-8575-2026e6c0ff4e.png">

## Section 2: Data Preparation

It's always extremely important to check the data for missing, incorrect, or duplicated data. Luckily, pandas allow us to check for them and drop or even replace them. In this next step, we check for empty and duplicated data using **isna** and **duplicated** functions. Then we can drop the incorrect data using **dropna** and **drop__duplicated** functions. Here's a quick peek:

<img width="385" alt="Screen Shot 2022-09-21 at 5 40 36 PM" src="https://user-images.githubusercontent.com/111609994/191633969-0f2166b7-d5b9-4553-876b-9b06b9f4bd83.png">
<img width="346" alt="Screen Shot 2022-09-21 at 5 40 51 PM" src="https://user-images.githubusercontent.com/111609994/191633972-89cfb804-0efa-492c-8f93-1c5340d83d1e.png">

Additionally, the dataset included the wrong datatype **str**. Originally, ***grade*** series should be integer since it indicates the grade of each student. Since we might need to use that data for calculations, later on, we need to make sure the data type is an integer instead of a string. Using **student_df.loc[:, "grade"] = student_df.loc[:, "grade"].str.replace("th","")** code allows us to replace that *str* with *int* by removing the **th** from the grades.

## Section 3: Summarizing the data

This part of the analysis is very simple and is focused on describing the data, seeing the average math and reading scores for the whole district:

<img width="580" alt="Screen Shot 2022-09-21 at 5 54 35 PM" src="https://user-images.githubusercontent.com/111609994/191635188-67419aa4-f24b-4822-9db1-535942f2c925.png">

Here we can see the average scores for the district, the number of all students in the district, and average school budgets and much more. 

## Section 4: Targeted Analysis

After the collection and preparation steps, we drill down into the data by finding the areas of interest. In this section, we focus on the grade of students. First, if we select 9th graders and look at their scores, we can see their average math and reading scores. We do this my using **loc** function to select the specific grade we want and looking at its description. This part is especially useful since we can change the grade and see the average scores for each grade in different schools or the district as a whole:

<img width="793" alt="Screen Shot 2022-09-21 at 5 56 34 PM" src="https://user-images.githubusercontent.com/111609994/191635477-31ada3bb-d056-42b3-890c-545578fb8855.png">

In addition, we can use conditional to filter grades and schools to look at average scores. The following script is useful in filtering to see any information we need from schools and grades.

<img width="813" alt="Screen Shot 2022-09-21 at 6 04 09 PM" src="https://user-images.githubusercontent.com/111609994/191636172-9466c096-c209-4325-94af-232375fdad2a.png">

Both of these codes can be used to access targeted analysis. We can use 10th graders from Sullivan High School or 11th graders from Bowers High School, compare their average math and reading scores, compare budgets for different schools and etc. 

## Section 5: Data Comparisons

Finally, another amazing function in pandas is **groupby** function. This allows the users to draw comparisons within data, which we'll see first hand. 

An important part of this data is the budget available for each school and each type of school. We can use ***groupby*** to see how the budgets are spread out between schools. 

<img width="698" alt="Screen Shot 2022-09-21 at 6 10 06 PM" src="https://user-images.githubusercontent.com/111609994/191636687-5341552b-f4f0-4c8f-a338-d6641daf264d.png">

We can use the same code later to group by school_name to see budgets for each school.

# Summary

We used many functions to find specific insights about the school district. Each part of this analysis was important to get the targeted information we need for schools, and the important part was that we can reuse the code and the functions by filtering them or by changing the columns. This analysis allowed us to look at vital points in the school district, including:

* Number of students in the district and each school
* Average scores for math and reading for each school, type of school, and grades
* Budgeting by school type and name
* Lowest and Highest scores
* Number of students in each grade for each school

We can further filter the code to our preferences and use it to get more data to make decisions. We can use the lowest average scores by school, focus on improving performance, and find out what causes these schools to underperform.




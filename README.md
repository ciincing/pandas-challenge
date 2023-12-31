# pandas-challenge

I used Pandas and Jupyter Notebook to create a report that included the following data. My report had a written description of at least two observable trends based on the data.

For the District Summary, I performed the necessary calculations and then created a high-level snapshot of the district's key metrics in a DataFrame. The District Summary included the total number of unique schools, total students, total budget, average math score, average reading score, % passing math, % passing reading, and % overall passing.

For the School Summary, I performed the necessary calculations and then created a DataFrame that summarized key metrics about each school. The School Summary included the school name, school type, total students, total school budget, per student budget, average math score, average reading score, % passing math, % passing reading, and % overall passing.

To find the Highest-Performing Schools by % Overall Passing, I sorted the schools by % Overall Passing in descending order and displayed the top 5 rows. I saved the results in a DataFrame called "top_schools".

Similarly, to find the Lowest-Performing Schools by % Overall Passing, I sorted the schools by % Overall Passing in ascending order and displayed the top 5 rows. I saved the results in a DataFrame called "bottom_schools".

I also created a DataFrame that listed the average math score for students of each grade level (9th, 10th, 11th, 12th) at each school, called "Math Scores by Grade". Additionally, I created another DataFrame that listed the average reading score for students of each grade level (9th, 10th, 11th, 12th) at each school, called "Reading Scores by Grade".

Finally, I created a table called "Scores by School Spending" that broke down school performance based on average spending ranges per student. I used provided code to create four bins with reasonable cutoff values to group school spending.

    spending_bins = [0, 585, 630, 645, 680]
    labels = ["<$585", "$585-630", "$630-645", "$645-680"]

I used the pd.cut function to categorize spending based on the bins. Then, I used the provided code to calculate the mean scores per spending range.

    spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Math Score"].mean()
    spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Reading Score"].mean()
    spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Math"].mean()
    spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Reading"].mean()
    overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Overall Passing"].mean()

I used the scores above to create a DataFrame called "spending_summary". In this table, I included the following metrics: average math score, average reading score, % passing math (the percentage of students who passed math), % passing reading (the percentage of students who passed reading), and % overall passing (the percentage of students who passed math AND reading).

To bin the "per_school_summary" DataFrame based on school size, I used the provided code.

    size_bins = [0, 1000, 2000, 5000]
    labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]

I used the pd.cut function on the "Total Students" column of the per_school_summary DataFrame to categorize school performance based on school size. I created a DataFrame called "size_summary" that breaks down school performance into three categories: small, medium, and large.

To analyze school performance based on school type, I used the per_school_summary DataFrame from the previous step. I created a new DataFrame called "type_summary" that displayed school performance based on the "School Type".

Conclusions: 
  Turns out, Charter schools have a higher overall passing rate at 90.43% compared to District schools which is only 53.67%. 
  Bailey High School has the most amount of students at 4,976 students and has the highest school budget at $3,124,928. 

Summary Analysis: 
  To make strategic decisions regarding future school budgets and priorities, we had to analyze the district-wide standardized test results which includes information of every student's math and reading scores, and the school that they attend. Amongst 15 schools and 39,170 total students, the total budget was $24,649,428.00, the average math score was about 78.99% and the average reading score was 81.88%. The average passing rate for math was 74.98% and the average passing rate for reading was 85.81%, therefore, the overall passing rate comes to around 65.17%. 
  Then, I created a summary of all 15 schools and their information on school type (charter/district), total students, total school budget, per student budget, average math/reading score, average rate of passing for math/reading, and overall passing rate. I found that the top 5 highest preforming schools by overall passing rate were all charter schools: Cabrera High School, Thomas High School, Griffin High School, Wilson High School, and Pena High School. However, the top worst preforming schools we all district schools. 
  I also found math and reading scores by age and I can confidently say that reading scores have a higher average than math scores because they were all in their 80s. 
  Next, we looked at the spending for each student and their average scores for both math and reading subjects. There is an odd correlation that I did not expect. The spending ranges are: "<$585", "$585-630", "$630-645", "$645-680". What I've noticed is that, students who have a budget of $585 and less have the highest average scores amongst the other classes. For example, the overall passing rate for a student with the budget of $585 and less is 90.37% and for a student with the highest budget of $645-680 have a 53.53% passing rate. It may be because charter schools have less students than district schools, meaning they have a smaller sample size, allowing them to have higher scores. 
  Essentially, we conclude that charter schools have higher passing rates and scores, but smaller school sizes and budget. While district schools have slightly lower passing rates and scores, but larger school sizes and budgets. 
  

## Religious Private Schools Top the Ranking of Cafeteria Hygiene Violations - Methodology Post ##

By Charlene Lin & Renata Daou

In this post, we will explain how we have used the data:
How did we find the story?
For the information on the number of schools and violations, we explored the DOHMH School Cafeteria Inspections (2020-Present) dataset. Initially, we began by examining the school cafeteria dataset to identify schools with the highest number of violations and their geographical distribution. Since we had the longitude and latitude data available for each school, we easily mapped them using Datawrapper, creating a preliminary visual representation for our investigation, which we then refined and added to the main article.

Upon further analysis, we observed a significant concentration of schools in two particular neighborhoods in Brooklyn: Williamsburg and Borough Park. This observation prompted us to explore common characteristics among these schools, such as their public or private status, religious affiliations, and other relevant factors. This exploration formed the basis of our story.

Percentages and calculations

To make calculations easier, we created multiple pivot tables where we could filter information such as the location of the schools, the number and type of violations, and others.

The tables can be seen in the link here:
NYC School Cafeteria Violation Sep 2021-April 2024

To help in understanding the article, we have provided a breakdown of all the percentages and calculations performed to determine the percentage of violations per school, type of school, and type of violations.

1. Percentage of Schools with Violations:
   - Out of 2059 schools, 799 have zero violations.
   - So, the number of schools with violations is 1260 schools.
   - Percentage of schools with violations = (1260 / 2059) * 100% ≈ 61.17%

2. Percentage of Religious Schools among Schools with Violations:
   - Out of 32 schools with 6 or more violations, 23 are religious.
   - Percentage of religious schools among schools with violations = (23 / 32) * 100% ≈ 71.88%

3. Percentage of Jewish Schools among Religious Schools with Violations:
   - Out of 23 religious schools with violations, 19 are Jewish.
   - Percentage of Jewish schools among religious schools with violations = (19 / 23) * 100% ≈ 82.61%

4. Percentage of Private Schools with Critical Violations:
Out of 680 private schools, 328 had critical violations.
Percentage of private schools with critical violations = (328 / 680) * 100% ≈ 48.24%


5. Percentage of Public Schools with Critical Violations:
Out of 1379 public schools, 398 had critical violations.
Percentage of public schools with critical violations = (398 / 1379) * 100% ≈ 28.85%


6. Schools with General Violations:
For private schools:
Total number of general violations = 777
Total number of private schools = 680
Average number of general violations per private school = 777 / 680 ≈ 1.14
For public schools:	
Total number of general violations = 990
Total number of public schools = 1,379
Average number of general violations per public school = 990 / 1,379 ≈ 0.72
Multivariable regression analysis 

Statistical analyses reveal a significant gap between private and public schools, with private schools consistently showing more food violations in school cafeterias. This divide is particularly stark in Jewish schools. The information on which religious denomination the schools belong to was obtained from this website add website

Multivariable regression analysis indicates that Jewish schools tend to have higher counts of food violations compared to other schools. This suggests an association between being a Jewish school and having more food violations. Interestingly, factors such as student population and student-to-teacher ratio do not consistently affect food violations. This implies that school size and teacher-student ratio may not play a significant role in determining food violations.

Regression analysis is a methodical way of exploring the relationships between different factors to understand why something happens. In this case, we're investigating why there are issues with food in school cafeterias. We're looking at various factors that might be linked to these problems.

First, we consider the financial background of students' families. Then, we examine how students are performing academically. Are they achieving high scores on tests? We also evaluate the resources available in schools, such as whether there are enough teachers to supervise students properly. Additionally, we analyze the type of school – whether it's public or private, religiously affiliated or secular. We also look at the diversity of the student body. Finally, we consider the overall size of the student population.

Here’s the original analysis breakdown: 

Y ~ X1 + X2 + X3 + X4 + X5 + X6
Y = Food violation counts (from 9/17/2021, when public schools re-opened since COVID)
X1 = Student socioeconomic status (family income, poverty rate, eligible for free lunch programs or not)
X2 = Educational attainment (SAT/ACT score, college admission rate)
X3 = Resources (student-teacher ratio)
X4 = School Type (Public/Private, Religious or not, Jewish/Catholic)
X5 = Minority (percentage of students being minorities)
X6 = Student body size (hypothesis is that if there are more people to cook for, the kitchen can be more messy)

The Welch Two Sample t-test suggests significant differences in food violation counts between schools categorized by these variables. In the Multivariable Regression Analysis, the presence of Jewish schools significantly increases the expected food violation count, independent of other factors. Private schools tend to have slightly higher food violation counts than public schools. "Students" and "Student-Teacher Ratio” don’t show a significant effect on food violations.


When it comes to test results, we explored the dataset from this article here. To match the schools in the DOHMH dataset, and the test results dataset, we used a method in Python called fuzzy match. In Python, the fuzzy-wuzzy library allowed us to perform fuzzy matching between strings, and link the schools with their cafeteria violations as well as their test results. 


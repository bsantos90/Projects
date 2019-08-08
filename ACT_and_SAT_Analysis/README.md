# SAT & ACT - An Analytical Look at States and Their Numbers

#### Project by: Bruno Santos

### Contents

- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Dictionary](#Data-Dictionary)
- [Conclusion and Recommendations](#Conclusion-and-Recommendations)

## Problem Statement

"The new format for the SAT was released in March 2016. As an employee of the College Board - the organization that administers the SAT - you are a part of a team that tracks statewide participation and recommends where money is best spent to improve SAT participation rates. Your presentation and report should be geared toward non-technical executives with the College Board and you will use the provided data and outside research to make recommendations about how the College Board might work to increase the participation rate in a state of your choice."

We will look over our data and inspect how a state's participation in a given test impacts their average test scores. Do states that require a particular test score higher on that test? How can we increase participation on the SAT, and where is money best spent to improve SAT participation rates?

## Executive Summary

The ACT and SAT are standardized tests used to gauge high school students' understanding of certain subjects, including Math, Reading/Writing, English, and Science. The tests do not test on all of the same subject matters, but their goal is the same: to test each student's understanding of the material and assess their college readiness.

If you're a high school student in the United States, the odds are that at some point you will be expected to take a standardized test prior to your admission to college. Nearly every four-year college or university in the country will require either an ACT or SAT test score to be submitted, with most having a certain minimum threshold that all applicants must meet in order to be considered for admission. In some cases, states may require students to take either the ACT or SAT regardless of whether or not they plan to continue their educational career in college or university.

Throughout this project, we obtained additional necessary data, cleaned our existing data as well as our new data using the `pandas` Python library, consolidated it into one `pandas` DataFrame to make it easier to work with, and applied several `pandas` methods to show tables of different sections of our data. Additionally, we used several plotting libraries within Python, such as `matplotlib` and `seaborn` to plot the data.

## Data Dictionary

### Dataset Sources:

- [2017 SAT Data](./data/sat_2017.csv)
- [2018 SAT Data](./data/sat_2018.csv)
- [2017 ACT Data](./data/act_2017.csv)
- [2018 ACT Data](./data/act_2018.csv)
- [Final Data - 2017 and 2018 Combined](./data/final.csv)

### Data Sources:

- [2017 SAT Data](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/)
- [2017 ACT Data](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)
- [2018 SAT Data](https://reports.collegeboard.org/sat-suite-program-results/state-results)
- [2018 ACT Data](http://www.act.org/content/dam/act/unsecured/documents/cccr2018/Average-Scores-by-State.pdf)
- [Further 2018 ACT Data](https://magoosh.com/hs/act/2016/average-act-score-by-state/)
- [States that Require the ACT or SAT](https://magoosh.com/hs/act/2017/states-that-require-the-act-or-sat/)
- [State Spending on Education](https://www.the74million.org/the-states-that-spend-the-most-and-least-on-education-and-how-their-students-perform-compared-to-their-neighbors/)

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|SAT/ACT|The state our row refers to| 
|sat_participation|integer|SAT|The percentage of students in the given state that took the SAT in 2017|
|sat_participation_2018|integer|SAT|The percentage of students in the given state that took the SAT in 2018|
|act_participation|integer|ACT|The percentage of students in the given state that took the SAT in 2017|
|act_participation_2018|integer|ACT|The percentage of students in the given state that took the SAT in 2018|
|sat_eb_reading_and_writing|integer|SAT|The average score per state on the 'Evidence-Based Reading and Writing' portion of the SAT exam in 2017|
|sat_eb_reading_and_writing_2018|integer|SAT|The average score per state on the 'Evidence-Based Reading and Writing' portion of the SAT exam|
|sat_math|integer|SAT|The average score per state on the 'Math' portion of the SAT exam in 2017|
|sat_math_2018|integer|SAT|The average score per state on the 'Math' portion of the SAT exam in 2018|
|sat_total|integer|SAT|The total combined average score per state of the 'Evidence-Based Reading and Writing' and 'Math' portions of the SAT exam in 2017|
|sat_total_2018|integer|SAT|The total combined average score per state of the 'Evidence-Based Reading and Writing' and 'Math' portions of the SAT exam in 2018|
|act_english|float|ACT|The average score per state on the 'English' portion of the ACT exam in 2017|
|act_english_2018|float|ACT|The average score per state on the 'English' portion of the ACT exam in 2018|
|act_math|float|ACT|The average score per state on the 'Math' portion of the ACT exam in 2017|
|act_math_2018|float|ACT|The average score per state on the 'Math' portion of the ACT exam in 2018|
|act_reading|float|ACT|The average score per state on the 'Reading' portion of the ACT exam in 2017|
|act_reading_2018|float|ACT|The average score per state on the 'Reading' portion of the ACT exam in 2018|
|act_science|float|ACT|The average score per state on the 'Science' portion of the ACT exam in 2017|
|act_science_2018|float|ACT|The average score per state on the 'Science' portion of the ACT exam in 2018|
|act_composite|float|ACT|The average score per state of the combined 'English', 'Math', 'Reading', and 'Science' portions of the ACT exam in 2017|
|act_composite|float|ACT|The average score per state of the combined 'English', 'Math', 'Reading', and 'Science' portions of the ACT exam in 2018|


## Conclusion and Recommendations

Based on our observations, we can conclude that participation levels and average total/composite scores are negatively correlated. That is, as the participation levels on a given test increases, we can expect the average total/composite test score will also decrease. Similarly, as participation levels decrease, the average total/composite score will increase. 

This can be primarily observed in the states of Colorado and Illinois, where the SAT participation rates jumped from 11% in 2017 to 100% in 2018 for Colorado, and 9% in 2017 to 99% in 2018 for Illinois. Conversely, the average total SAT scores dropped from 1201 to 1025 for Colorado, and 1115 in 2017 to 2019 in 2018 for Illinois. Florida, on the other hand, saw their SAT participation drop from 83% in 2017 to 56% in 2018. As expected, their average total SAT score rose from 1017 in 2017 to 1099 in 2018.

Given our observations, our goal is to increase participation on the SAT. We are not concerned with the overall average scores. Due to this, my recommendation is that we avoid states where the ACT is mandatory and focus on states that do not have mandatory testing one way or another. It will be beneficial to focus on states that are in close proximity to those that have successfully transitioned to the SAT - such as Colorado or Illinois. Looking at the surrounding states, we should focus on states such as New Mexico, which had an 11% participation in 2017 and a 16% participation in 2018, or Iowa, which had a 2% participation rate in 2017 and a 3% participation rate in 2018.
# Job-Recommendation-System

This is a repository for career job recommendation system

#### Fields
======
Given that;

1. id - The unique identifier for the profile
2. careerjunction_za_primary_jobtitle - The most recent job title of the profile
3. careerjunction_za_recent_jobtitles - The next job titles after the most recent one (max 2)
4. careerjunction_za_historical_jobtitles - All other job titles after recent ones (from the 4th job title)
5. careerjunction_za_future_jobtitles - Job titles the seeker would like to have as their next job (ambitions)
6. careerjunction_za_employer_names - All employers worked for
7. careerjunction_za_skills - All the skills
8. careerjunction_za_courses - Titles for education/courses
 
What we want is:-

- Any insight into the data that can be extrapolated
- If given a profile id, find similar profiles like that one. A combination of similar skills, courses and/or job titles.
- If given a profile id, recommend what their next job title(s) could be

#### Data Analysis Exploration

As the amount of data captured increases, structure of data in the database become unstructured data. From the JSON file, there are 2000 separate profiles listed within the file, with 8 different columns. Each profile has different fields, and some of the fields are nested datasets. 

Furthermore, this type of data is very hard to store in a regular SQL database. Since this unstructured data was stored in a format called JavaScript Object Notation (JSON). JSON is a way to encode data structures like lists and dictionaries to strings that ensures that they are easily readable by machines. Even though JSON starts with the word Javascript, 
it's actually just a format, and can be read by any language. Ref: (https://en.wikipedia.org/wiki/JSON)

To tackle this kind of challenges, this project used Python Programming language (i.e. a scripting Language) with Pandas libraries. Python has great JSON support, with the json library. 

#### Data Structure

I convert the JSON lists and dictionaries to command separate version (CSV). And then convert strings to lists and dictionaries. Although, the JSON data looks much like a dictionary that allow me to process the data using the keys and values and stored in memory via the use of Pandas libraries. 

##### file structure in repository

1. Dataset : The folder contain the two input files: JSON and CSV. The CSV makes easier to viualize the dataset in columns and rows.

2. career_recommendation.ipynb: This file is a Jupyter notebook that explain in detail the methods and functions used in solving the challenge. The project used profile similarity measure, a simple approach implementation.

3. career_dataAnalysis.ipynb: This is file is a Jupyter notebook that show how the data were extrapolated.

#### Data Exploration

Given the time and in this task, I explored the JSON file using Jupyter notebook, and then import it into Python and work with it using Pandas. Furthermore, I attempt at solving all three questions of the data analysis challenge. The following information show my approach in solving the challenge:

1. I iterate over the data, by finding and counting words that are similar between descriptions and those that share more words, for example, I used the closest ones.

2. For the recommendation, after finding the similar ones, I checked the current job title of source and compare with the corresponding job titles of the similar targets and then find the job title that is next.

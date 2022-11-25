# Programming for Data Analysis - Project 1

###  ***Requirement:*** 
The task was to synthesize a dataset, based upon research of a real-world phenomenon.

### ***Overview***  
A synthesize dataset was created to compare the usage of electronic cigarettes to tobacco cigarettes over time and to understand if any correlation exists between smoking and key social demographics such as age, gender, residency; as well as variables associated with finances such as cost and salary.

### ***Method***
Within Jupyter Notebook, using packages pandas and NumPy, a dataframe of unique responses was created. The first variable created was Response ID, assigning a random integer using ``Random.randint`` that represents to size of the study, within the range of 1-1,000. 

The second variable labelled Type was generated to examine if a person used tobacco cigarettes or electronic cigarettes, this variable was split based on a study of usage among Irish teenagers with 69.5% identifying as regular smokers and 30.4% as e-smokers. *Random.choice()* function in *NumPy* was used to generate this categorical variable and the variables based on social demographics. *Random.randint* was used again to create numeric based variables such as Frequency, ranging from 1 to 10 times per day and Age, ranging from 18 to 70. *head()* was used repeatedly to ensure the correct data layout was being generated.

The variable Cost was created based on a dependency to frequency since the more frequently a respondent smoked, the higher the financial burden. An empty array was created and based on frequency; a random number was generated within a range using an *If* statement. A second numeric column, Salary based again on frequency was created. Although both variables are numeric and based on a respondent’s smoking frequency, different methods were used. The function *loc*  was used to select frequency and generate a new variable based on conditions.

*Type* function was then used to give a summary of the columns created, Cost and Salary were changed from a 64 to a 32 float to reduce memory usage. Using the *lambda* function, a variable x, rounded to two decimal places was created. This expression was applied to the numeric columns of the dataframe and returned a modified copy of the dataframe.   

### ***Summary***

A further description of the dataset created, and the results generated can be found within the Jupyter Notebook along with references.

# Programming for Data Analysis - Project 1

###  ***Requirement:*** 
The task is to synthesize a dataset, based upon research of a real-world phenomena.

### ***Overview***  
A synthesize dataset was created to track the usage of electronic cigarettes over time and to understand if any correlation exists between smoking and key social demographics such as age, gender, education residency and employment.

### ***Method***
Using Jupyter Notebook, a synthesize dataset of unique responses was created. Using packages pandas and numpy random a dataframe of unique responses was created. The first varible created was Response ID, assigning a random intger using ``np.random.randint`` that represents to size of the study, within the range of 1-1,000. 

```` 
dataset = 1000 
response_id = np.random.randint(1, 1000, dataset)
````

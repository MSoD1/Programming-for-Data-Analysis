# Programming for Data Analysis - Project 1

###  ***Requirement:*** 
The task is to synthesize a dataset, based upon research of a real-world phenomena.

### ***Overview***  
A synthesize dataset was created to track the usage of electronic cigarettes over time and to understand if any correlation exists between smoking and key social demographics such as age, gender, education residency and employment.

### ***Method***
Using Jupyter Notebook, a synthesize dataset of unique responses was created. Using packages pandas and numpy random a dataframe of unique responses was created. The first varible created was Response ID, assigning a random intger using ``Random.randint`` that represents to size of the study, within the range of 1-1,000. 

```` 
dataset = 1000 
response_id = np.random.randint(1, 1000, dataset)
````

The second variable *Type* was generated to examine if a person used tabacco cigarettes or electronic cigarettes, this variable was split based on a study[1 https://www.drugsandalcohol.ie/24024/] of usage amoung Irish teenagers with 69.5% identifing as regular smokers and 30.4% as e-smokers. ``Random.choice()`` function in Numpy was used to generate this cateigorical varaible and also the variables based on social demographics. ``Random.randint`` was used again to create numeric based variables such as frequency, ranging from 1 to 10 times per day and age, ranging from 18 to 70. The final synthesize data column to be created was based on the financial cost, this was generated using ``random.uniform()``.
``head()`` was used repeatedly to ensure the correct data layout was being generated 

````
df['Type'] = np.random.choice(["Tobacco","e-Cigarettes"], size=dataset, p=[.695,.305])
df['Gender'] = np.random.choice(["Male","Female", "Other"], size=dataset, p=[.45,.45,.1])
df['Residence'] = np.random.choice(["City","Town", "Rural"], size=dataset, p=[.37,.42,.21])
df['Year'] = np.random.choice(["2022","2019"], size=dataset)
df.head()
````

````
df['Frequency'] = np.random.randint(1,10 , dataset)
df['Age'] = np.random.randint(18,70 , dataset)
df.head()
````
The final variable is *Cost*, which was dependant on *frequency* since the more frequently a respondent smoked the higher the cost. Based on frequency, a random number was generated within a range created within an If statement. Although the Cost variables appears as a float, using ``append`` has created a list variable. 

# Programming for Data Analysis - Project 1

###  ***Requirement:*** 
The task was to synthesize a dataset, based upon research of a real-world phenomenon.

### ***Overview***  
A synthesize dataset was created to compare the usage of electronic cigarettes to tobacco cigarettes over time and to understand if any correlation exists between smoking and key social demographics such as age, gender, education residency and employment.

### ***Method***
Within Jupyter Notebook, using packages pandas and NumPy, a dataframe of unique responses was created. The first variable created was Response ID, assigning a random integer using ``Random.randint`` that represents to size of the study, within the range of 1-1,000. 

```` 
dataset = 1000 
response_id = np.random.randint(1, 1000, dataset)
````

The second variable labelled Type was generated to examine if a person used tobacco cigarettes or electronic cigarettes, this variable was split based on a study [1 https://www.drugsandalcohol.ie/24024/] of usage among Irish teenagers with 69.5% identifying as regular smokers and 30.4% as e-smokers. *Random.choice()* function in *NumPy* was used to generate this categorical variable and the variables based on social demographics. *Random.randint* was used again to create numeric based variables such as Frequency, ranging from 1 to 10 times per day and Age, ranging from 18 to 70. *head()* was used repeatedly to ensure the correct data layout was being generated.

````
df['Type'] = np.random.choice(["Tobacco", "e-Cigarettes"], size=dataset, p=[.695,.305])
df['Gender'] = np.random.choice(["Male", "Female", "Other"], size=dataset, p=[.45,.45,.1])
df['Residence'] = np.random.choice(["City", "Town", "Rural"], size=dataset, p=[.37,.42,.21])
df['Year'] = np.random.choice(["2022","2019"], size=dataset)
df['Frequency'] = np.random.randint(1,10 , dataset)
df['Age'] = np.random.randint(18,70 , dataset)
````

The variable Cost, was created based on a dependency to frequency since the more frequently a respondent smoked, the higher the financial burden. An empty array was created and based on frequency, a random number was generated within a range using an *If* statement. A second numeric column, Salary based again on frequency was created. Although both variables are numeric and based on a respondents smoking frequency, different methods were used. The function *loc*  was used to select frequency and generate a new variable based on conditions.

````
cost = []
for row in df['Frequency']:
        if row < 2 :    cost.append(float(np.random.uniform(10,20,1)))
        elif row < 4  : cost.append(float(np.random.uniform(21,40,1)))
        elif row < 6 : cost.append(float(np.random.uniform(41,60,1)))
        elif row < 8 :  cost.append(float(np.random.uniform(61,80,1)))        
        else:          cost.append(float(np.random.uniform(81,110,1)))
````

````
df.loc[df['Frequency'] <= 5, 'Salary'] = df['Frequency']*df['Age']*100 
df.loc[df['Frequency'] > 5, 'Salary'] = df['Frequency']*df['Age']*100 + df['Cost']*15
````

*Type* function was then used to give a summary of the columns created, Cost and Salary were changed from a 64 to a 32 float to reduce memory usage. Using the *lambda* function, a variable x, rounded to two decimal places was created. This expression was applied to the numeric columns of the dataframe and returned a modified copy of the dataframe.   

````
print(df.dtypes)

df['Cost'] =np.float32(df['Cost'])
df['Salary'] = np.float32(df['Salary'])

df['Cost']= df['Cost'].apply(lambda x:round(x,2))
df['Salary']= df['Salary'].apply(lambda x:round(x,2))

````

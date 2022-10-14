# Pandas-in-Python
import pandas as pd
# create data frame
c = ["ch",'usman', 'python']
e = pd.DataFrame(c)
print(e)

# adding new column or changing the column name
column = ['Usman','Ali','Rizwan']
title_columns = {"name": column,
                "height": [5.6,4.5,5.1],
                "weight": [80,45,55]} # title_column varible dictionary is used to create the new column, changing column name etc.
data = pd.DataFrame(title_columns)
print(data)

# select column in DataFrame
select_column = data["weight"]
print(select_column)

# select value in data Frame:  This shows the single value in Data Frame
select_value = data["weight"][1]
print(select_value)

# Select row in Data Frame: iloc method is used to show the all values related index
select_row = data.iloc[0]
#OR
select_row = data.iloc[0]['weight']
print(select_row)

# Manupolate the data Frame values
bmi = [] # bmi is empty list but the formula is weight[i]/height[i]**2
for i in range(len(data)):
    bmi_score = data['weight'][i]/data['height'][i]**2
    bmi.append(bmi_score)
data['bmi'] = bmi
print(data)


# manupolate data store into your file
data.to_csv("usman.csv", index = False) # now the file created in you pc as loction where the notebook open
#  This is the your choice you want to create file in csv or txt. 

# read usman.csv file in jupyter notebook
pd.read_csv('usman.csv') # now the file load in notebook as excel form


# head and tail methods: Head method show the first rows and columns and tail method show the last rows and columns
print(data.head(2)) #show first two elements
print(data.tail(2)) # shows the last two method

# replace method
data1 = data.replace("Ali", "Ahmad")
print(data1)

# remove column
data2 = data.drop("height", axis = 1)  # now the height column deleted
data2 = data.iloc[2:] # removing row
print(data2)


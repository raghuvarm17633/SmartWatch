# **SmartWatch Price Prediction**


 # **Defining the Problem**


 ![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/f93a0704-3c55-4775-bdd5-1b750e464d15)


# **Dataset Generation**

#Import the Required libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
#Generating the Dataset using Pandas
data = { 'S.No': pd.Series([1,2,3,4,5,6,7,8,9,10]),
         'Brand': pd.Series(['Apple','Noise','Fossil','Titan','Wrogn','Samsung','Google','Fastrack','Amazefit','Rolex']),
         'Min_Price': pd.Series([90,9,20,12,10,35,50,20,5,500]),
         'Max_Price': pd.Series([900,40,600,330,200,250,700,150,60,1000]),
         'Avg_Price': pd.Series([200,20,300,125,75,100,300,70,30,600]),
         'Sold_in_2020': pd.Series([100,350,150,400,200,100,50,300,250,30]),
         'Sold_in_2021': pd.Series([150,450,175,500,250,75,50,250,300,25]),
         'Sold_in_2022': pd.Series([130,400,150,450,230,80,60,275,275,25]),
         'Sold_in_2023': pd.Series([160,425,200,475,250,100,65,290,325,35]),
         'Best_Selling_Model':pd.Series(['Apple Watch Series 7','Noise Pulse 2 Max Smartwatch',"Fossil Fenmore Analog Black Dial Men's Watch",'Titan Smart','Wrogn fitness smart band','Galaxy Watch 6 Classic hands-on','Google Pixel Watch (GPS)','Fastrack Reflex Vox','Amazfit T Rex Pro','Rolex Daytona'])}

Data = pd.DataFrame(data)

print(Data)



 ![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/fe453980-9abd-42ed-a18d-a221ff97e1d6)


 ![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/13840553-dcca-4cfd-939a-35e95b0dac56)


 # **Copy the DataSet**

 # Copy the Data to make operations without any effect of original data

print('----------------------Copied Data----------------------')


copy = Data.copy(deep=False)

print(copy)

# Accessing Panda Series Elements

print('----------Access with Position----------')

print(copy[0::2])



![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/976c1dce-579a-4c49-89bf-deee4a137ffd)

![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/c1b36d74-6ea2-4121-8b55-475d38bf3eec)


## Row Operations

# Performing the Row Operations

print('-----Row Operations-----')

# selecting a row and print the selected row

print(copy.loc[9])

![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/65fbd0e9-d2f9-444f-8d01-a719715e6523)


# Adding a Row and print the DataFrame with including added row

copy.loc[10] = [11,'DanielKhan',10,100,30,150,170,165,170,'Danielkhan series 1']

print(copy)


![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/2991607a-182e-4c1b-982a-adc5414ed000)

![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/7781f880-de2f-4c6b-9f13-57592bfaf1cf)


# Deleting a selected row and print the DataFrame
cop = copy.drop(10)

print(cop)

![image](https://github.com/raghuvarm17633/SmartWatch/assets/137690672/896e1005-0f48-4f7a-9b21-bd8c49943672)




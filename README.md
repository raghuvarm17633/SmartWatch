# SmartWatch
# **SmartWatch Price Prediction**



  # **Defining the Problem**

                          
   The global smartwatch market is expected to grow at a significant rate in the coming years, driven by factors such as increasing health awareness, growing demand for wearable devices, and 
          rising disposable incomes. This growth is expected to lead to a decrease in smart watch prices, as manufacturers compete to gain market share.
 According to a report by Statista, the average price of a smartwatch is expected to decrease from $213.70 in 2023 to $198.30 by 2027. This represents a CAGR of -2.68%.
 However, it is important to note that the price of a smartwatch can vary significantly depending on the brand, features, and design.

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



   S.No     Brand  Min_Price  Max_Price  Avg_Price  Sold_in_2020  \
0     1     Apple         90        900        200           100   
1     2     Noise          9         40         20           350   
2     3    Fossil         20        600        300           150   
3     4     Titan         12        330        125           400   
4     5     Wrogn         10        200         75           200   
5     6   Samsung         35        250        100           100   
6     7    Google         50        700        300            50   
7     8  Fastrack         20        150         70           300   
8     9  Amazefit          5         60         30           250   
9    10     Rolex        500       1000        600            30   

   Sold_in_2021  Sold_in_2022  Sold_in_2023  \
0           150           130           160   
1           450           400           425   
2           175           150           200   
3           500           450           475   
4           250           230           250   
5            75            80           100   
6            50            60            65   
7           250           275           290   
8           300           275           325   
9            25            25            35   

                             Best_Selling_Model  
0                          Apple Watch Series 7  
1                  Noise Pulse 2 Max Smartwatch  
2  Fossil Fenmore Analog Black Dial Men's Watch  
3                                   Titan Smart  
4                      Wrogn fitness smart band  
5               Galaxy Watch 6 Classic hands-on  
6                      Google Pixel Watch (GPS)  
7                           Fastrack Reflex Vox  
8                             Amazfit T Rex Pro  
9                                 Rolex Daytona  




# **Copy the DataSet**

 # Copy the Data to make operations without any effect of original data
print('----------------------Copied Data----------------------')

copy = Data.copy(deep=False)
print(copy)

# Accessing Panda Series Elements
print('----------Access with Position----------')
print(copy[0::2])


# ---------------------Copied Data----------------------
   S.No     Brand  Min_Price  Max_Price  Avg_Price  Sold_in_2020  \
0     1     Apple         90        900        200           100   
1     2     Noise          9         40         20           350   
2     3    Fossil         20        600        300           150   
3     4     Titan         12        330        125           400   
4     5     Wrogn         10        200         75           200   
5     6   Samsung         35        250        100           100   
6     7    Google         50        700        300            50   
7     8  Fastrack         20        150         70           300   
8     9  Amazefit          5         60         30           250   
9    10     Rolex        500       1000        600            30   

   Sold_in_2021  Sold_in_2022  Sold_in_2023  \
0           150           130           160   
1           450           400           425   
2           175           150           200   
3           500           450           475   
4           250           230           250   
5            75            80           100   
6            50            60            65   
7           250           275           290   
8           300           275           325   
9            25            25            35   

                             Best_Selling_Model  
0                          Apple Watch Series 7  
1                  Noise Pulse 2 Max Smartwatch  
2  Fossil Fenmore Analog Black Dial Men's Watch  
3                                   Titan Smart  
4                      Wrogn fitness smart band  
5               Galaxy Watch 6 Classic hands-on  
6                      Google Pixel Watch (GPS)  
7                           Fastrack Reflex Vox  
8                             Amazfit T Rex Pro  
9                                 Rolex Daytona  
# ----------Access with Position----------
   S.No     Brand  Min_Price  Max_Price  Avg_Price  Sold_in_2020  \
0     1     Apple         90        900        200           100   
2     3    Fossil         20        600        300           150   
4     5     Wrogn         10        200         75           200   
6     7    Google         50        700        300            50   
8     9  Amazefit          5         60         30           250   

   Sold_in_2021  Sold_in_2022  Sold_in_2023  \
0           150           130           160   
2           175           150           200   
4           250           230           250   
6            50            60            65   
8           300           275           325   

                             Best_Selling_Model  
0                          Apple Watch Series 7  
2  Fossil Fenmore Analog Black Dial Men's Watch  
4                      Wrogn fitness smart band  
6                      Google Pixel Watch (GPS)  
8                             Amazfit T Rex Pro  
Row Operations

[ ]
# Performing the Row Operations
print('-----Row Operations-----')
# selecting a row and print the selected row
print(copy.loc[9])
# -----Row Operations-----
S.No                             10
Brand                         Rolex
Min_Price                       500
Max_Price                      1000
Avg_Price                       600
Sold_in_2020                     30
Sold_in_2021                     25
Sold_in_2022                     25
Sold_in_2023                     35
Best_Selling_Model    Rolex Daytona
Name: 9, dtype: object





# Adding a Row and print the DataFrame with including added row
copy.loc[10] = [11,'DanielKhan',10,100,30,150,170,165,170,'Danielkhan series 1']
print(copy)


    S.No       Brand  Min_Price  Max_Price  Avg_Price  Sold_in_2020  \
0      1       Apple         90        900        200           100   
1      2       Noise          9         40         20           350   
2      3      Fossil         20        600        300           150   
3      4       Titan         12        330        125           400   
4      5       Wrogn         10        200         75           200   
5      6     Samsung         35        250        100           100   
6      7      Google         50        700        300            50   
7      8    Fastrack         20        150         70           300   
8      9    Amazefit          5         60         30           250   
9     10       Rolex        500       1000        600            30   
10    11  DanielKhan         10        100         30           150   

    Sold_in_2021  Sold_in_2022  Sold_in_2023  \
0            150           130           160   
1            450           400           425   
2            175           150           200   
3            500           450           475   
4            250           230           250   
5             75            80           100   
6             50            60            65   
7            250           275           290   
8            300           275           325   
9             25            25            35   
10           170           165           170   

                              Best_Selling_Model  
0                           Apple Watch Series 7  
1                   Noise Pulse 2 Max Smartwatch  
2   Fossil Fenmore Analog Black Dial Men's Watch  
3                                    Titan Smart  
4                       Wrogn fitness smart band  
5                Galaxy Watch 6 Classic hands-on  
6                       Google Pixel Watch (GPS)  
7                            Fastrack Reflex Vox  
8                              Amazfit T Rex Pro  
9                                  Rolex Daytona  
10                           Danielkhan series 1  



# Deleting a selected row and print the DataFrame
cop = copy.drop(10)
print(cop)



   S.No     Brand  Min_Price  Max_Price  Avg_Price  Sold_in_2020  \
0     1     Apple         90        900        200           100   
1     2     Noise          9         40         20           350   
2     3    Fossil         20        600        300           150   
3     4     Titan         12        330        125           400   
4     5     Wrogn         10        200         75           200   
5     6   Samsung         35        250        100           100   
6     7    Google         50        700        300            50   
7     8  Fastrack         20        150         70           300   
8     9  Amazefit          5         60         30           250   
9    10     Rolex        500       1000        600            30   

   Sold_in_2021  Sold_in_2022  Sold_in_2023  \
0           150           130           160   
1           450           400           425   
2           175           150           200   
3           500           450           475   
4           250           230           250   
5            75            80           100   
6            50            60            65   
7           250           275           290   
8           300           275           325   
9            25            25            35   

                             Best_Selling_Model  
0                          Apple Watch Series 7  
1                  Noise Pulse 2 Max Smartwatch  
2  Fossil Fenmore Analog Black Dial Men's Watch  
3                                   Titan Smart  
4                      Wrogn fitness smart band  
5               Galaxy Watch 6 Classic hands-on  
6                      Google Pixel Watch (GPS)  
7                           Fastrack Reflex Vox  
8                             Amazfit T Rex Pro  
9                                 Rolex Daytona  




# **Column Operations**


# Adding a Column and print the DataFrame with newly added Column also
cop['Total Sold Watches'] = cop['Sold_in_2020']+cop['Sold_in_2021']+cop['Sold_in_2022']+cop['Sold_in_2023']
print(cop)



S.No     Brand  Min_Price  Max_Price  Avg_Price  Sold_in_2020  \
0     1     Apple         90        900        200           100   
1     2     Noise          9         40         20           350   
2     3    Fossil         20        600        300           150   
3     4     Titan         12        330        125           400   
4     5     Wrogn         10        200         75           200   
5     6   Samsung         35        250        100           100   
6     7    Google         50        700        300            50   
7     8  Fastrack         20        150         70           300   
8     9  Amazefit          5         60         30           250   
9    10     Rolex        500       1000        600            30   

   Sold_in_2021  Sold_in_2022  Sold_in_2023  \
0           150           130           160   
1           450           400           425   
2           175           150           200   
3           500           450           475   
4           250           230           250   
5            75            80           100   
6            50            60            65   
7           250           275           290   
8           300           275           325   
9            25            25            35   

                             Best_Selling_Model  Total Sold Watches  
0                          Apple Watch Series 7                 540  
1                  Noise Pulse 2 Max Smartwatch                1625  
2  Fossil Fenmore Analog Black Dial Men's Watch                 675  
3                                   Titan Smart                1825  
4                      Wrogn fitness smart band                 930  
5               Galaxy Watch 6 Classic hands-on                 355  
6                      Google Pixel Watch (GPS)                 225  
7                           Fastrack Reflex Vox                1115  
8                             Amazfit T Rex Pro                1150  
9                                 Rolex Daytona                 115  




# Deleting a column and print the DataFrame
del cop['Total Sold Watches']
print(cop)




   S.No     Brand  Min_Price  Max_Price  Avg_Price  Sold_in_2020  \
0     1     Apple         90        900        200           100   
1     2     Noise          9         40         20           350   
2     3    Fossil         20        600        300           150   
3     4     Titan         12        330        125           400   
4     5     Wrogn         10        200         75           200   
5     6   Samsung         35        250        100           100   
6     7    Google         50        700        300            50   
7     8  Fastrack         20        150         70           300   
8     9  Amazefit          5         60         30           250   
9    10     Rolex        500       1000        600            30   

   Sold_in_2021  Sold_in_2022  Sold_in_2023  \
0           150           130           160   
1           450           400           425   
2           175           150           200   
3           500           450           475   
4           250           230           250   
5            75            80           100   
6            50            60            65   
7           250           275           290   
8           300           275           325   
9            25            25            35   

                             Best_Selling_Model  
0                          Apple Watch Series 7  
1                  Noise Pulse 2 Max Smartwatch  
2  Fossil Fenmore Analog Black Dial Men's Watch  
3                                   Titan Smart  
4                      Wrogn fitness smart band  
5               Galaxy Watch 6 Classic hands-on  
6                      Google Pixel Watch (GPS)  
7                           Fastrack Reflex Vox  
8                             Amazfit T Rex Pro  
9                                 Rolex Daytona  



# **Scrutinizing the Data**

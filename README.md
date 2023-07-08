# vehiclegasmileage
Data Cleaning, understand the data first, and rename columns.  Summary statistics, and filtering data for a specific type of vehicle
<br>
<br>
import pandas as pd
import matplotlib as plt
<br>
<br>
df=pd.read_csv('https://raw.githubusercontent.com/CunyLaguardiaDataAnalytics/datasets/master/mtcars.csv')
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/94b61e4f-31d2-4058-870b-b293107ff818)
<br>
<br>
df.head()
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/def49326-b87a-4e82-8274-13bec9d01954)
<br>
<br>
df.describe()
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/ab2a78c6-f0b5-4fe3-a8a1-69a86acd9576)
<br>
<br>
df1=df.rename(columns={'Unnamed: 0':'Make'})
<br>
<br>
df1
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/7e83ff21-50b5-43f6-be63-f271e6796061)
<br>
<br>
df.rename(columns={'Unnamed: 0':'Make'},inplace=True)
<br>
<br>
df
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/be6d9d64-ca24-4dce-8a61-680f5f09d1d8)
<br>
<br>
dfnew=df[['mpg','hp','wt','cyl']]      create a new dataframe only for mpg, hp, wt and cyl
<br>
<br>
dfnew
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/80453057-6cf3-49ca-93bd-01b3dd4dcb48)
<br>
<br>
dfnew.columns
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/b6c31809-4fbd-4c65-b2fd-7b56b8257009)
<br>
<br>
dfnew=dfnew.rename(columns={'mpg':'milespergallon','hp':'horsepower','wt':'weight','cyl':'cylinders'})      rename the 4 columns 
<br>
<br>
dfnew.describe()      summary statistics for the above mentioned columns
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/de34d538-c95e-40e4-8f2c-b36cb51f9579)
<br>
<br>
dfnew
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/f094b409-dada-4331-87db-dbc1d6654241)
<br>
<br>
If we want to use a specific code to get the average miles per gallon we can use the below code too.
<br>
<br>
average = dfnew.mean().milespergallon
<br>
<br>
average
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/9473f2a8-7cfb-4225-acd6-d3cc08eff0af)
<br>
<br>
I'll filter the date and find a summary statistic for only one type of vehicle.  In this case I Chose the "Valiant" Make, and we found tha the average miles per gallon for it is 18.1 mpg
<br>
<br>
filtered_datavaliantx = df1[df1["Make"] == "Valiant"].describe()
<br>
<br>
filtered_datavaliantx
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/cd59a4e8-f851-4b07-9522-4a40aa849f1c)
<br>
<br>
We can also get to the same average mileage per gallon for Valiant if we use the .loc method, once we know which row belongs to the Valiant type.
<br>
<br>
dfnew.loc[5]
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/3d8f978b-ce92-43b1-89ce-94ed612562c0)
<br>
<br>
Even another way is to look if the Make columns contain a string with 'valiant' in it.
<br>
<br>
df3=df[df['Make'].str.contains('Valiant')]
<br>
<br>
df3
<br>
<br>
![image](https://github.com/marcosalinas777/vehiclegasmileage/assets/95108103/c2480501-481b-445e-a7e0-6416282833a4)





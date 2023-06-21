# Combat_Python

the python version for the Combat batch effect remove method 

##  use the demo data
# example
# import libraries
import pandas as pd
import matplotlib.pyplot as plt

# Read data CSV file
data = pd.read_csv('mydata.csv',index_col=0)

# Display the contents of the DataFrame
# plt.boxplot(data)
# plt.show()
#type(data)
#print(data.shape)

# Read batch and mod1 CSV file
batch = pd.read_csv('batch.csv')
mod = pd.read_csv('mod1.csv')
# Extract batch values as a list
batch = batch['x'].tolist()
mod = mod['x'].tolist()
# Display the batch list
print(batch)
type(batch)
print(mod)
type(mod)
#print(data.shape)

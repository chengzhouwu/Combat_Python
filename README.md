# Combat_Python

the python version for the Combat batch effect remove method 

##  use the demo data
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('mydata.csv',index_col=0)
batch = pd.read_csv('batch.csv')
mod = pd.read_csv('mod1.csv')

batch = batch['x'].tolist()
mod = mod['x'].tolist()

#### Test the code line by line

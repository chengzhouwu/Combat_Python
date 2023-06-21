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
# prior parameters in the function 
data = data
batch = batch 
mod=mod 
mod=[] 
par_prior=True
prior_plots=False
mean_only=False 
ref_batch= 5
precision=None


# details
data = data
list_samples = data.columns
list_samples
list_genes = data.index
list_genes
dat = data.values
dat
check_mean_only(mean_only)
mean_only
batchmod = define_batchmod(batch)
batchmod
ref, batchmod = check_ref_batch(ref_batch, batch, batchmod)
ref
batchmod
ref
treat_batches(batch)
n_batch, batches, n_batches, n_array = treat_batches(batch)
n_batch
batches
n_array
design = treat_covariates(batchmod, mod, ref, n_batch)
design
NAs = check_NAs(dat)
NAs
B_hat, grand_mean, var_pooled = calculate_mean_var(
           design, batches, ref, dat, NAs, n_batches, n_batch, n_array)
B_hat
grand_mean
var_pooled
stand_mean = calculate_stand_mean(
           grand_mean, n_array, design, n_batch, B_hat)
stand_mean

s_data = standardise_data(dat, stand_mean, var_pooled, n_array)
s_data

gamma_star, delta_star, batch_design = fit_model(
           design, n_batch, s_data, batches, mean_only, par_prior, precision, ref, NAs)
gamma_star
delta_star
batch_design

adjust_data(s_data, gamma_star, delta_star, batch_design,
                               n_batches, var_pooled, stand_mean, n_array, ref, batches, dat)
bayes_data = adjust_data(s_data, gamma_star, delta_star, batch_design,
                               n_batches, var_pooled, stand_mean, n_array, ref, batches, dat)
bayes_data
bayes_data_df = pd.DataFrame(bayes_data,
                   columns = list_samples,
                  index = list_genes)
bayes_data_df
bayes_data

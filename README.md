# Data-Science
Write python code to import “data.csv” file and perform following task:
a)	Select random sample from the file
b)	Compare the population mean and sample mean
c)	And display message that the selected sample is representing population or not.

import pandas as pd
file = pd.read_csv("Covid-19.csv")

random_sample = file.sample(10)
file_filled = file.fillna(0)

numeric_columns = file_filled.select_dtypes(include=[int, float]).columns

population_mean = file_filled[numeric_columns].mean()
sample_mean = random_sample[numeric_columns].mean()

if population_mean.equals(sample_mean):
    message = "The sample mean is equal to the population mean."
else:
    message = "The sample mean is not equal to the population mean."

print("\n1. Selecting random sample from the file")
print("\nPrinting Random 10 rows\n")
print(random_sample)

print("\n2. Comparing population mean and sample mean")
print("Population Mean is:")
print(population_mean)
print("\nSample Mean is:")

print(sample_mean)
print("\n3. Displaying result whether sample mean represent the data or not")
print("\nComparison Result:")
print(message)

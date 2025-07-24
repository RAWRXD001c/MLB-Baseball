# MLB-Baseball

import pandas as pd
from google.colab import files
uploaded = files.upload()
df = pd.read_csv('/content/archive.zip', encoding="latin-1")
import matplotlib.pyplot as plt

#Some fixes

renaming = {'G': 'Games', 'AB': 'At Plate', 'R': 'Runs', 'H': 'Hits', '2B': 'Doubles', '3B': 'Triples',
            'RBI': 'Runs Batted In'}
df = df.rename(columns=renaming)
df['HOF'][160]=1

#graph 1

label = df['HOF']
plt.scatter(df['Hits'], df['Runs'], c=label)
plt.xlabel("Hits")
plt.ylabel("Home Runs")
plt.title("Hits to Home Runs")

#graph 2

plt.scatter(df['Runs'], df['HOF'])
plt.xlabel("Home Runs")
plt.ylabel("Hall of Fame")
plt.title("Home Runs to Hall of Fame")

#graph 3

plt.scatter(df['Runs'], df['HOF'])
plt.xlabel("Home Runs")
plt.ylabel("Hall of Fame")
plt.title("Home Runs to Hall of Fame")

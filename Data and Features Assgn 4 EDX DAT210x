# DATA210X-EDX-assgn

#SOLUTION TO ASSIGNMENT 4 OF DAT210x Programming with Python for Data Science
#Lab Assignment 4
#Navigate over to ESPN's website for NHL Historic Player Points Statistics, for the years 2014-2015. This page has a table on it with a few stats we're interested in obtaining. But it's a bit messy! Clean it up for us, using the appropriate commands to:
#Load up the table on this page into a Pandas dataframe

import pandas as pd
df_NHL = pd.read_html('http://www.espn.com/nhl/statistics/player/_/stat/points/sort/points/year/2015/seasontype/2')[0]
df_NHL = df_NHL.rename(index=str,columns=df_NHL.loc[1])
df_NHL = df_NHL.dropna(axis=0,thresh=4)
df_NHL = df_NHL.drop(labels=['RK'],axis=1)  
df_NHL = df_NHL.reset_index(drop=True) 
df_NHL = df_NHL[1:]
df_NHL = df_NHL.drop(labels=['A','G'],axis=1)
df_NHL = df_NHL.drop_duplicates(keep=False)
df_NHL = df_NHL.reset_index(drop=True) 
for col in df_NHL.columns[2:]:
    df_NHL[col] = pd.to_numeric(df_NHL[col],errors='coerce')


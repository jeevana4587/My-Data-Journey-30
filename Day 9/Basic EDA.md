```python
import pandas as pd
df = pd.read_csv("C:\\Users\\jeeva\\OneDrive\\My Data Journey 30\\ds_salaries.csv")
```


```python
print(df.isnull().sum())
```

    work_year             0
    experience_level      0
    employment_type       0
    job_title             0
    salary                0
    salary_currency       0
    salary_in_usd         0
    employee_residence    0
    remote_ratio          0
    company_location      0
    company_size          0
    dtype: int64
    


```python
df.columns
```




    Index(['work_year', 'experience_level', 'employment_type', 'job_title',
           'salary', 'salary_currency', 'salary_in_usd', 'employee_residence',
           'remote_ratio', 'company_location', 'company_size'],
          dtype='object')




```python
df['job_title'] = df['job_title'].str.strip().str.lower()
df['company_location'] = df['company_location'].str.strip().str.upper()
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>work_year</th>
      <th>experience_level</th>
      <th>employment_type</th>
      <th>job_title</th>
      <th>salary</th>
      <th>salary_currency</th>
      <th>salary_in_usd</th>
      <th>employee_residence</th>
      <th>remote_ratio</th>
      <th>company_location</th>
      <th>company_size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2023</td>
      <td>SE</td>
      <td>FT</td>
      <td>principal data scientist</td>
      <td>80000</td>
      <td>EUR</td>
      <td>85847</td>
      <td>ES</td>
      <td>100</td>
      <td>ES</td>
      <td>L</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2023</td>
      <td>MI</td>
      <td>CT</td>
      <td>ml engineer</td>
      <td>30000</td>
      <td>USD</td>
      <td>30000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>S</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2023</td>
      <td>MI</td>
      <td>CT</td>
      <td>ml engineer</td>
      <td>25500</td>
      <td>USD</td>
      <td>25500</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>S</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2023</td>
      <td>SE</td>
      <td>FT</td>
      <td>data scientist</td>
      <td>175000</td>
      <td>USD</td>
      <td>175000</td>
      <td>CA</td>
      <td>100</td>
      <td>CA</td>
      <td>M</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2023</td>
      <td>SE</td>
      <td>FT</td>
      <td>data scientist</td>
      <td>120000</td>
      <td>USD</td>
      <td>120000</td>
      <td>CA</td>
      <td>100</td>
      <td>CA</td>
      <td>M</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['experience_level']= df['experience_level'].replace({'EN': 'Entry-level',
    'MI': 'Mid-level',
    'SE': 'Senior-level',
    'EX': 'Executive-level'})
```


```python
df['employment_type'] = df['employment_type'].replace({
    'FT': 'Full-time',
    'PT': 'Part-time',
    'CT': 'Contract',
    'FL': 'Freelance'
})
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>work_year</th>
      <th>experience_level</th>
      <th>employment_type</th>
      <th>job_title</th>
      <th>salary</th>
      <th>salary_currency</th>
      <th>salary_in_usd</th>
      <th>employee_residence</th>
      <th>remote_ratio</th>
      <th>company_location</th>
      <th>company_size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2023</td>
      <td>Senior-level</td>
      <td>Full-time</td>
      <td>principal data scientist</td>
      <td>80000</td>
      <td>EUR</td>
      <td>85847</td>
      <td>ES</td>
      <td>100</td>
      <td>ES</td>
      <td>L</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2023</td>
      <td>Mid-level</td>
      <td>Contract</td>
      <td>ml engineer</td>
      <td>30000</td>
      <td>USD</td>
      <td>30000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>S</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2023</td>
      <td>Mid-level</td>
      <td>Contract</td>
      <td>ml engineer</td>
      <td>25500</td>
      <td>USD</td>
      <td>25500</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>S</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2023</td>
      <td>Senior-level</td>
      <td>Full-time</td>
      <td>data scientist</td>
      <td>175000</td>
      <td>USD</td>
      <td>175000</td>
      <td>CA</td>
      <td>100</td>
      <td>CA</td>
      <td>M</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2023</td>
      <td>Senior-level</td>
      <td>Full-time</td>
      <td>data scientist</td>
      <td>120000</td>
      <td>USD</td>
      <td>120000</td>
      <td>CA</td>
      <td>100</td>
      <td>CA</td>
      <td>M</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.drop(columns=['salary_currency', 'salary'],inplace=True)
```


```python
df.head(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>work_year</th>
      <th>experience_level</th>
      <th>employment_type</th>
      <th>job_title</th>
      <th>salary_in_usd</th>
      <th>employee_residence</th>
      <th>remote_ratio</th>
      <th>company_location</th>
      <th>company_size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2023</td>
      <td>Senior-level</td>
      <td>Full-time</td>
      <td>principal data scientist</td>
      <td>85847</td>
      <td>ES</td>
      <td>100</td>
      <td>ES</td>
      <td>L</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2023</td>
      <td>Mid-level</td>
      <td>Contract</td>
      <td>ml engineer</td>
      <td>30000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>S</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2023</td>
      <td>Mid-level</td>
      <td>Contract</td>
      <td>ml engineer</td>
      <td>25500</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>S</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2023</td>
      <td>Senior-level</td>
      <td>Full-time</td>
      <td>data scientist</td>
      <td>175000</td>
      <td>CA</td>
      <td>100</td>
      <td>CA</td>
      <td>M</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2023</td>
      <td>Senior-level</td>
      <td>Full-time</td>
      <td>data scientist</td>
      <td>120000</td>
      <td>CA</td>
      <td>100</td>
      <td>CA</td>
      <td>M</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['company_size'] = df['company_size'].replace({
    'S': 'Small',
    'M': 'Medium',
    'L': 'Large'
})
```


```python
df['employee_residence'] = df['employee_residence'].str.upper()
df = df.rename(columns={'salary_in_usd': 'salary_usd'})
```


```python
df.to_csv('cleaned_dataset.csv', index=False)
```


```python
df.shape
```




    (3755, 9)




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 3755 entries, 0 to 3754
    Data columns (total 9 columns):
     #   Column              Non-Null Count  Dtype 
    ---  ------              --------------  ----- 
     0   work_year           3755 non-null   int64 
     1   experience_level    3755 non-null   object
     2   employment_type     3755 non-null   object
     3   job_title           3755 non-null   object
     4   salary_usd          3755 non-null   int64 
     5   employee_residence  3755 non-null   object
     6   remote_ratio        3755 non-null   int64 
     7   company_location    3755 non-null   object
     8   company_size        3755 non-null   object
    dtypes: int64(3), object(6)
    memory usage: 264.2+ KB
    


```python
df.describe(include='all')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>work_year</th>
      <th>experience_level</th>
      <th>employment_type</th>
      <th>job_title</th>
      <th>salary_usd</th>
      <th>employee_residence</th>
      <th>remote_ratio</th>
      <th>company_location</th>
      <th>company_size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>3755.000000</td>
      <td>3755</td>
      <td>3755</td>
      <td>3755</td>
      <td>3755.000000</td>
      <td>3755</td>
      <td>3755.000000</td>
      <td>3755</td>
      <td>3755</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>NaN</td>
      <td>4</td>
      <td>4</td>
      <td>93</td>
      <td>NaN</td>
      <td>78</td>
      <td>NaN</td>
      <td>72</td>
      <td>3</td>
    </tr>
    <tr>
      <th>top</th>
      <td>NaN</td>
      <td>Senior-level</td>
      <td>Full-time</td>
      <td>data engineer</td>
      <td>NaN</td>
      <td>US</td>
      <td>NaN</td>
      <td>US</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>NaN</td>
      <td>2516</td>
      <td>3718</td>
      <td>1040</td>
      <td>NaN</td>
      <td>3004</td>
      <td>NaN</td>
      <td>3040</td>
      <td>3153</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2022.373635</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>137570.389880</td>
      <td>NaN</td>
      <td>46.271638</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.691448</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>63055.625278</td>
      <td>NaN</td>
      <td>48.589050</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>2020.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5132.000000</td>
      <td>NaN</td>
      <td>0.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2022.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>95000.000000</td>
      <td>NaN</td>
      <td>0.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2022.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>135000.000000</td>
      <td>NaN</td>
      <td>0.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2023.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>175000.000000</td>
      <td>NaN</td>
      <td>100.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2023.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>450000.000000</td>
      <td>NaN</td>
      <td>100.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(df['experience_level'].value_counts())
print(df['employment_type'].value_counts())
print(df['job_title'].value_counts().head(10))  # Top 10 job titles
print(df['company_size'].value_counts())
```

    experience_level
    Senior-level       2516
    Mid-level           805
    Entry-level         320
    Executive-level     114
    Name: count, dtype: int64
    employment_type
    Full-time    3718
    Part-time      17
    Contract       10
    Freelance      10
    Name: count, dtype: int64
    job_title
    data engineer                1040
    data scientist                840
    data analyst                  612
    machine learning engineer     289
    analytics engineer            103
    data architect                101
    research scientist             82
    data science manager           58
    applied scientist              58
    research engineer              37
    Name: count, dtype: int64
    company_size
    Medium    3153
    Large      454
    Small      148
    Name: count, dtype: int64
    


```python
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(8, 4))
sns.histplot(df['salary_usd'], kde=True)
plt.title("Salary Distribution (USD)")
plt.xlabel("Salary")
plt.ylabel("Frequency")
plt.show()
```


    
![png](output_17_0.png)
    



```python
sns.countplot(data=df, x='experience_level')
plt.title("Experience Level Distribution")
plt.show()
```


    
![png](output_18_0.png)
    



```python
plt.figure(figsize=(8, 4))
sns.boxplot(data=df, x='experience_level', y='salary_usd')
plt.title("Salary by Experience Level")
plt.show()
```


    
![png](output_19_0.png)
    



```python
sns.boxplot(data=df, x='employment_type', y='salary_usd')
plt.title("Salary by Employment Type")
plt.show()
```


    
![png](output_20_0.png)
    



```python
sns.scatterplot(data=df, x='remote_ratio', y='salary_usd')
plt.title("Remote Ratio vs Salary")
plt.show()
```


    
![png](output_21_0.png)
    



```python
top_jobs = df.groupby('job_title')['salary_usd'].mean().sort_values(ascending=False).head(10)
print(top_jobs)
top_jobs.plot(kind='barh', figsize=(8, 5), title="Top 10 Highest Paying Job Titles")
plt.xlabel("Average Salary (USD)")
plt.show()
```

    job_title
    data science tech lead                375000.000000
    cloud data architect                  250000.000000
    data lead                             212500.000000
    data analytics lead                   211254.500000
    principal data scientist              198171.125000
    director of data science              195140.727273
    principal data engineer               192500.000000
    machine learning software engineer    192420.000000
    data science manager                  191278.775862
    applied scientist                     190264.482759
    Name: salary_usd, dtype: float64
    


    
![png](output_22_1.png)
    



```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.boxplot(x=df['salary_usd'])
plt.title("Boxplot of Salary (USD)")
plt.show()
sns.scatterplot(x=df['experience_level'], y=df['salary_usd'])
```


    
![png](output_23_0.png)
    





    <Axes: xlabel='experience_level', ylabel='salary_usd'>




    
![png](output_23_2.png)
    



```python

```

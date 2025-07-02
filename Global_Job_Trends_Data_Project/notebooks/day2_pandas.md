```python
import pandas as pd
df = pd.read_csv("C:\\Users\\jeeva\\Downloads\\archive (14)\\ds_salaries.csv")
```


```python
print(df)
```

          work_year experience_level employment_type                 job_title  \
    0          2023               SE              FT  Principal Data Scientist   
    1          2023               MI              CT               ML Engineer   
    2          2023               MI              CT               ML Engineer   
    3          2023               SE              FT            Data Scientist   
    4          2023               SE              FT            Data Scientist   
    ...         ...              ...             ...                       ...   
    3750       2020               SE              FT            Data Scientist   
    3751       2021               MI              FT  Principal Data Scientist   
    3752       2020               EN              FT            Data Scientist   
    3753       2020               EN              CT     Business Data Analyst   
    3754       2021               SE              FT      Data Science Manager   
    
           salary salary_currency  salary_in_usd employee_residence  remote_ratio  \
    0       80000             EUR          85847                 ES           100   
    1       30000             USD          30000                 US           100   
    2       25500             USD          25500                 US           100   
    3      175000             USD         175000                 CA           100   
    4      120000             USD         120000                 CA           100   
    ...       ...             ...            ...                ...           ...   
    3750   412000             USD         412000                 US           100   
    3751   151000             USD         151000                 US           100   
    3752   105000             USD         105000                 US           100   
    3753   100000             USD         100000                 US           100   
    3754  7000000             INR          94665                 IN            50   
    
         company_location company_size  
    0                  ES            L  
    1                  US            S  
    2                  US            S  
    3                  CA            M  
    4                  CA            M  
    ...               ...          ...  
    3750               US            L  
    3751               US            L  
    3752               US            S  
    3753               US            L  
    3754               IN            L  
    
    [3755 rows x 11 columns]
    


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
      <td>Principal Data Scientist</td>
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
      <td>ML Engineer</td>
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
      <td>ML Engineer</td>
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
      <td>Data Scientist</td>
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
      <td>Data Scientist</td>
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
df.tail(5)
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
      <th>3750</th>
      <td>2020</td>
      <td>SE</td>
      <td>FT</td>
      <td>Data Scientist</td>
      <td>412000</td>
      <td>USD</td>
      <td>412000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>L</td>
    </tr>
    <tr>
      <th>3751</th>
      <td>2021</td>
      <td>MI</td>
      <td>FT</td>
      <td>Principal Data Scientist</td>
      <td>151000</td>
      <td>USD</td>
      <td>151000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>L</td>
    </tr>
    <tr>
      <th>3752</th>
      <td>2020</td>
      <td>EN</td>
      <td>FT</td>
      <td>Data Scientist</td>
      <td>105000</td>
      <td>USD</td>
      <td>105000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>S</td>
    </tr>
    <tr>
      <th>3753</th>
      <td>2020</td>
      <td>EN</td>
      <td>CT</td>
      <td>Business Data Analyst</td>
      <td>100000</td>
      <td>USD</td>
      <td>100000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>L</td>
    </tr>
    <tr>
      <th>3754</th>
      <td>2021</td>
      <td>SE</td>
      <td>FT</td>
      <td>Data Science Manager</td>
      <td>7000000</td>
      <td>INR</td>
      <td>94665</td>
      <td>IN</td>
      <td>50</td>
      <td>IN</td>
      <td>L</td>
    </tr>
  </tbody>
</table>
</div>




```python
#to read headers
df.columns
```




    Index(['work_year', 'experience_level', 'employment_type', 'job_title',
           'salary', 'salary_currency', 'salary_in_usd', 'employee_residence',
           'remote_ratio', 'company_location', 'company_size'],
          dtype='object')




```python
print(df.iloc[0:4])
df.iloc[0,4]
```

       work_year experience_level employment_type                 job_title  \
    0       2023               SE              FT  Principal Data Scientist   
    1       2023               MI              CT               ML Engineer   
    2       2023               MI              CT               ML Engineer   
    3       2023               SE              FT            Data Scientist   
    
       salary salary_currency  salary_in_usd employee_residence  remote_ratio  \
    0   80000             EUR          85847                 ES           100   
    1   30000             USD          30000                 US           100   
    2   25500             USD          25500                 US           100   
    3  175000             USD         175000                 CA           100   
    
      company_location company_size  
    0               ES            L  
    1               US            S  
    2               US            S  
    3               CA            M  
    




    80000





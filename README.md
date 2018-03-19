

```python
#dependencies
import pandas as pd
import numpy as np
```


```python
#import csv path
csv_path_schools = "schools_complete.csv"
csv_path_students = "students_complete.csv"
```


```python
#read in csv files
schools_df = pd.read_csv(csv_path_schools)
students_df = pd.read_csv(csv_path_students)
```


```python
schools_df.head()
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
      <th>School ID</th>
      <th>name</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
  </tbody>
</table>
</div>




```python
students_df.head()
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
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>school</th>
      <th>reading_score</th>
      <th>math_score</th>
      <th>read_pass</th>
      <th>math_pass</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>1</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
#make count for passing scores in new column
students_df['read_pass'] = np.where(students_df['reading_score']>=70, 1, 0)
students_df['math_pass'] = np.where(students_df['math_score']>=70, 1, 0)
students_df.head()
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
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>school</th>
      <th>reading_score</th>
      <th>math_score</th>
      <th>read_pass</th>
      <th>math_pass</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>1</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
students_df.columns
```




    Index(['Student ID', 'name', 'gender', 'grade', 'school', 'reading_score',
           'math_score', 'read_pass', 'math_pass'],
          dtype='object')




```python
#group student data by school & apply sum method
groupbyschool_students_sum = students_df.groupby('school', as_index=False).sum()
groupbyschool_students_sum[['school','read_pass', 'math_pass']].head()
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
      <th>school</th>
      <th>read_pass</th>
      <th>math_pass</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>4077</td>
      <td>3318</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cabrera High School</td>
      <td>1803</td>
      <td>1749</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Figueroa High School</td>
      <td>2381</td>
      <td>1946</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford High School</td>
      <td>2172</td>
      <td>1871</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>1426</td>
      <td>1371</td>
    </tr>
  </tbody>
</table>
</div>




```python
groupbyschool_students_sum.columns
```




    Index(['school', 'Student ID', 'reading_score', 'math_score'], dtype='object')




```python
#group student data by school & apply mean method
groupbyschool_students_mean = students_df.groupby('school', as_index=False).mean()
average_scores = groupbyschool_students_mean[['school', 'reading_score', 'math_score']]

#rename columns
average_scores.rename(columns = {'reading_score':'Average Reading Score', 'math_score':'Average Math Score'}, inplace = True)
average_scores.head()
```

    /Users/stefanirobnett/anaconda3/lib/python3.6/site-packages/pandas/core/frame.py:3027: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame
    
    See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy
      return super(DataFrame, self).rename(**kwargs)





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
      <th>school</th>
      <th>Average Reading Score</th>
      <th>Average Math Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>81.033963</td>
      <td>77.048432</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cabrera High School</td>
      <td>83.975780</td>
      <td>83.061895</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Figueroa High School</td>
      <td>81.158020</td>
      <td>76.711767</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford High School</td>
      <td>80.746258</td>
      <td>77.102592</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>83.816757</td>
      <td>83.351499</td>
    </tr>
  </tbody>
</table>
</div>




```python
#merge student_mean & student_sum data 
merged_students_sum_average = groupbyschool_students_sum.merge(average_scores, on='school')
#Re-assign groupby to df
#Omit unnecessary columns(reading_score, math_score, student id)
students_sum_average = merged_students_sum_average[['school', 'Average Reading Score', 'Average Math Score', 'read_pass', 'math_pass']]
students_sum_average.head()
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
      <th>school</th>
      <th>Average Reading Score</th>
      <th>Average Math Score</th>
      <th>read_pass</th>
      <th>math_pass</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>81.033963</td>
      <td>77.048432</td>
      <td>4077</td>
      <td>3318</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cabrera High School</td>
      <td>83.975780</td>
      <td>83.061895</td>
      <td>1803</td>
      <td>1749</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Figueroa High School</td>
      <td>81.158020</td>
      <td>76.711767</td>
      <td>2381</td>
      <td>1946</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford High School</td>
      <td>80.746258</td>
      <td>77.102592</td>
      <td>2172</td>
      <td>1871</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>83.816757</td>
      <td>83.351499</td>
      <td>1426</td>
      <td>1371</td>
    </tr>
  </tbody>
</table>
</div>




```python
#merge groubyschool_student_df with school_df
#re-assign chart name as "School Summary"
school_summary = pd.merge(schools_df, students_sum_average, left_on='name', right_on='school')
#Rename columns
school_summary.rename(columns = {'school':'School Name', 'type':'School Type','size':'Total Students', 'budget': 'Total School Budget'}, inplace = True)
```


```python
#divide read_pass by size to get percent passed
school_summary['% Passing Reading'] = school_summary['read_pass']/school_summary['Total Students']*100
#divide math_pass by size to get percent passed
school_summary['% Passing Math'] = school_summary['math_pass']/school_summary['Total Students']*100
#divide budget by size for budget per student
school_summary['Per Student Budget'] = school_summary['Total School Budget']/school_summary['Total Students']
#average of read_pass and Math_pass overall passing
school_summary['Overall Passing Rate'] = school_summary[['% Passing Reading', '% Passing Math']].mean(axis=1)
```


```python
#Omit un. columns
school_summary= school_summary[['School Name', 'School Type', 
                                'Total Students', 'Total School Budget', 
                                'Per Student Budget', 'Average Math Score', 
                                'Average Reading Score', '% Passing Math', 
                                '% Passing Reading', 'Overall Passing Rate']]
school_summary
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
      <th>School Name</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>65.683922</td>
      <td>81.316421</td>
      <td>73.500171</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>65.988471</td>
      <td>80.739234</td>
      <td>73.363852</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
      <td>600.0</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>93.867121</td>
      <td>95.854628</td>
      <td>94.860875</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
      <td>652.0</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>66.752967</td>
      <td>80.862999</td>
      <td>73.807983</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
      <td>625.0</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>93.392371</td>
      <td>97.138965</td>
      <td>95.265668</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
      <td>578.0</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>93.867718</td>
      <td>96.539641</td>
      <td>95.203679</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>94.133477</td>
      <td>97.039828</td>
      <td>95.586652</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Bailey High School</td>
      <td>District</td>
      <td>4976</td>
      <td>3124928</td>
      <td>628.0</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>66.680064</td>
      <td>81.933280</td>
      <td>74.306672</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Holden High School</td>
      <td>Charter</td>
      <td>427</td>
      <td>248087</td>
      <td>581.0</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>92.505855</td>
      <td>96.252927</td>
      <td>94.379391</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
      <td>609.0</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>94.594595</td>
      <td>95.945946</td>
      <td>95.270270</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
      <td>583.0</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>93.333333</td>
      <td>96.611111</td>
      <td>94.972222</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>66.366592</td>
      <td>80.220055</td>
      <td>73.293323</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>66.057551</td>
      <td>81.222432</td>
      <td>73.639992</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>68.309602</td>
      <td>79.299014</td>
      <td>73.804308</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>638.0</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>93.272171</td>
      <td>97.308869</td>
      <td>95.290520</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Top Performing Schools (by passing rate)
#Get top 5 schools
top_five_schools = school_summary.nlargest(5, 'Overall Passing Rate')
top_five_schools
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
      <th>School Name</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6</th>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>94.133477</td>
      <td>97.039828</td>
      <td>95.586652</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>638.0</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>93.272171</td>
      <td>97.308869</td>
      <td>95.290520</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
      <td>609.0</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>94.594595</td>
      <td>95.945946</td>
      <td>95.270270</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
      <td>625.0</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>93.392371</td>
      <td>97.138965</td>
      <td>95.265668</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
      <td>578.0</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>93.867718</td>
      <td>96.539641</td>
      <td>95.203679</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Top Performing Schools (by passing rate)
#Get bottom 5 schools
bottom_five_schools = school_summary.nsmallest(5, 'Overall Passing Rate')
bottom_five_schools
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
      <th>School Name</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>66.366592</td>
      <td>80.220055</td>
      <td>73.293323</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>65.988471</td>
      <td>80.739234</td>
      <td>73.363852</td>
    </tr>
    <tr>
      <th>0</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>65.683922</td>
      <td>81.316421</td>
      <td>73.500171</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>66.057551</td>
      <td>81.222432</td>
      <td>73.639992</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>68.309602</td>
      <td>79.299014</td>
      <td>73.804308</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Group by schools and Grade
# Apply mean function for reading & math scores
students_df_grade_mean = students_df.groupby(['school','grade'], as_index=False).mean()
#rename columns
students_df_grade_mean.rename(columns= {'school':'School Name', 'grade': 'Grade','reading_score':'Average Reading Score', 'math_score':'Average Math Score'}, inplace = True)

```


```python
#Create Reading Scores By Grade
reading_scores_by_grade = students_df_grade_mean[['School Name', 'Grade', 'Average Reading Score']]
reading_scores_by_grade
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
      <th>School Name</th>
      <th>Grade</th>
      <th>Average Reading Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>10th</td>
      <td>80.907183</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Bailey High School</td>
      <td>11th</td>
      <td>80.945643</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Bailey High School</td>
      <td>12th</td>
      <td>80.912451</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Bailey High School</td>
      <td>9th</td>
      <td>81.303155</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Cabrera High School</td>
      <td>10th</td>
      <td>84.253219</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Cabrera High School</td>
      <td>11th</td>
      <td>83.788382</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Cabrera High School</td>
      <td>12th</td>
      <td>84.287958</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Cabrera High School</td>
      <td>9th</td>
      <td>83.676136</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Figueroa High School</td>
      <td>10th</td>
      <td>81.408912</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Figueroa High School</td>
      <td>11th</td>
      <td>80.640339</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Figueroa High School</td>
      <td>12th</td>
      <td>81.384863</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Figueroa High School</td>
      <td>9th</td>
      <td>81.198598</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Ford High School</td>
      <td>10th</td>
      <td>81.262712</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Ford High School</td>
      <td>11th</td>
      <td>80.403642</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Ford High School</td>
      <td>12th</td>
      <td>80.662338</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Ford High School</td>
      <td>9th</td>
      <td>80.632653</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Griffin High School</td>
      <td>10th</td>
      <td>83.706897</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Griffin High School</td>
      <td>11th</td>
      <td>84.288089</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Griffin High School</td>
      <td>12th</td>
      <td>84.013699</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Griffin High School</td>
      <td>9th</td>
      <td>83.369193</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Hernandez High School</td>
      <td>10th</td>
      <td>80.660147</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Hernandez High School</td>
      <td>11th</td>
      <td>81.396140</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Hernandez High School</td>
      <td>12th</td>
      <td>80.857143</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Hernandez High School</td>
      <td>9th</td>
      <td>80.866860</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Holden High School</td>
      <td>10th</td>
      <td>83.324561</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Holden High School</td>
      <td>11th</td>
      <td>83.815534</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Holden High School</td>
      <td>12th</td>
      <td>84.698795</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Holden High School</td>
      <td>9th</td>
      <td>83.677165</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Huang High School</td>
      <td>10th</td>
      <td>81.512386</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Huang High School</td>
      <td>11th</td>
      <td>81.417476</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Huang High School</td>
      <td>12th</td>
      <td>80.305983</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Huang High School</td>
      <td>9th</td>
      <td>81.290284</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Johnson High School</td>
      <td>10th</td>
      <td>80.773431</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Johnson High School</td>
      <td>11th</td>
      <td>80.616027</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Johnson High School</td>
      <td>12th</td>
      <td>81.227564</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Johnson High School</td>
      <td>9th</td>
      <td>81.260714</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Pena High School</td>
      <td>10th</td>
      <td>83.612000</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Pena High School</td>
      <td>11th</td>
      <td>84.335938</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Pena High School</td>
      <td>12th</td>
      <td>84.591160</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Pena High School</td>
      <td>9th</td>
      <td>83.807273</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Rodriguez High School</td>
      <td>10th</td>
      <td>80.629808</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Rodriguez High School</td>
      <td>11th</td>
      <td>80.864811</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Rodriguez High School</td>
      <td>12th</td>
      <td>80.376426</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Rodriguez High School</td>
      <td>9th</td>
      <td>80.993127</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Shelton High School</td>
      <td>10th</td>
      <td>83.441964</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Shelton High School</td>
      <td>11th</td>
      <td>84.373786</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Shelton High School</td>
      <td>12th</td>
      <td>82.781671</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Shelton High School</td>
      <td>9th</td>
      <td>84.122642</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Thomas High School</td>
      <td>10th</td>
      <td>84.254157</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Thomas High School</td>
      <td>11th</td>
      <td>83.585542</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Thomas High School</td>
      <td>12th</td>
      <td>83.831361</td>
    </tr>
    <tr>
      <th>51</th>
      <td>Thomas High School</td>
      <td>9th</td>
      <td>83.728850</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Wilson High School</td>
      <td>10th</td>
      <td>84.021452</td>
    </tr>
    <tr>
      <th>53</th>
      <td>Wilson High School</td>
      <td>11th</td>
      <td>83.764608</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Wilson High School</td>
      <td>12th</td>
      <td>84.317673</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Wilson High School</td>
      <td>9th</td>
      <td>83.939778</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Wright High School</td>
      <td>10th</td>
      <td>83.812757</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Wright High School</td>
      <td>11th</td>
      <td>84.156322</td>
    </tr>
    <tr>
      <th>58</th>
      <td>Wright High School</td>
      <td>12th</td>
      <td>84.073171</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Wright High School</td>
      <td>9th</td>
      <td>83.833333</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Create Math Scores By Grade
math_scores_by_grade = students_df_grade_mean[['School Name', 'Grade', 'Average Math Score']]
math_scores_by_grade
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
      <th>School Name</th>
      <th>Grade</th>
      <th>Average Math Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>10th</td>
      <td>76.996772</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Bailey High School</td>
      <td>11th</td>
      <td>77.515588</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Bailey High School</td>
      <td>12th</td>
      <td>76.492218</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Bailey High School</td>
      <td>9th</td>
      <td>77.083676</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Cabrera High School</td>
      <td>10th</td>
      <td>83.154506</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Cabrera High School</td>
      <td>11th</td>
      <td>82.765560</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Cabrera High School</td>
      <td>12th</td>
      <td>83.277487</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Cabrera High School</td>
      <td>9th</td>
      <td>83.094697</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Figueroa High School</td>
      <td>10th</td>
      <td>76.539974</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Figueroa High School</td>
      <td>11th</td>
      <td>76.884344</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Figueroa High School</td>
      <td>12th</td>
      <td>77.151369</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Figueroa High School</td>
      <td>9th</td>
      <td>76.403037</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Ford High School</td>
      <td>10th</td>
      <td>77.672316</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Ford High School</td>
      <td>11th</td>
      <td>76.918058</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Ford High School</td>
      <td>12th</td>
      <td>76.179963</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Ford High School</td>
      <td>9th</td>
      <td>77.361345</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Griffin High School</td>
      <td>10th</td>
      <td>84.229064</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Griffin High School</td>
      <td>11th</td>
      <td>83.842105</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Griffin High School</td>
      <td>12th</td>
      <td>83.356164</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Griffin High School</td>
      <td>9th</td>
      <td>82.044010</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Hernandez High School</td>
      <td>10th</td>
      <td>77.337408</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Hernandez High School</td>
      <td>11th</td>
      <td>77.136029</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Hernandez High School</td>
      <td>12th</td>
      <td>77.186567</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Hernandez High School</td>
      <td>9th</td>
      <td>77.438495</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Holden High School</td>
      <td>10th</td>
      <td>83.429825</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Holden High School</td>
      <td>11th</td>
      <td>85.000000</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Holden High School</td>
      <td>12th</td>
      <td>82.855422</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Holden High School</td>
      <td>9th</td>
      <td>83.787402</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Huang High School</td>
      <td>10th</td>
      <td>75.908735</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Huang High School</td>
      <td>11th</td>
      <td>76.446602</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Huang High School</td>
      <td>12th</td>
      <td>77.225641</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Huang High School</td>
      <td>9th</td>
      <td>77.027251</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Johnson High School</td>
      <td>10th</td>
      <td>76.691117</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Johnson High School</td>
      <td>11th</td>
      <td>77.491653</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Johnson High School</td>
      <td>12th</td>
      <td>76.863248</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Johnson High School</td>
      <td>9th</td>
      <td>77.187857</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Pena High School</td>
      <td>10th</td>
      <td>83.372000</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Pena High School</td>
      <td>11th</td>
      <td>84.328125</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Pena High School</td>
      <td>12th</td>
      <td>84.121547</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Pena High School</td>
      <td>9th</td>
      <td>83.625455</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Rodriguez High School</td>
      <td>10th</td>
      <td>76.612500</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Rodriguez High School</td>
      <td>11th</td>
      <td>76.395626</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Rodriguez High School</td>
      <td>12th</td>
      <td>77.690748</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Rodriguez High School</td>
      <td>9th</td>
      <td>76.859966</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Shelton High School</td>
      <td>10th</td>
      <td>82.917411</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Shelton High School</td>
      <td>11th</td>
      <td>83.383495</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Shelton High School</td>
      <td>12th</td>
      <td>83.778976</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Shelton High School</td>
      <td>9th</td>
      <td>83.420755</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Thomas High School</td>
      <td>10th</td>
      <td>83.087886</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Thomas High School</td>
      <td>11th</td>
      <td>83.498795</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Thomas High School</td>
      <td>12th</td>
      <td>83.497041</td>
    </tr>
    <tr>
      <th>51</th>
      <td>Thomas High School</td>
      <td>9th</td>
      <td>83.590022</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Wilson High School</td>
      <td>10th</td>
      <td>83.724422</td>
    </tr>
    <tr>
      <th>53</th>
      <td>Wilson High School</td>
      <td>11th</td>
      <td>83.195326</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Wilson High School</td>
      <td>12th</td>
      <td>83.035794</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Wilson High School</td>
      <td>9th</td>
      <td>83.085578</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Wright High School</td>
      <td>10th</td>
      <td>84.010288</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Wright High School</td>
      <td>11th</td>
      <td>83.836782</td>
    </tr>
    <tr>
      <th>58</th>
      <td>Wright High School</td>
      <td>12th</td>
      <td>83.644986</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Wright High School</td>
      <td>9th</td>
      <td>83.264706</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Groupby spending ranges (per student):
#Create copy of school_summary for spending ranges
school_summary_spending_ranges = school_summary
#Create bins and bin labels Average Spending Ranges per student to school_summary
school_summary_spending_ranges["Spending Ranges (Per Student)"] = pd.qcut(school_summary_spending_ranges['Per Student Budget'], 4, labels=["High", "Medium-high", "Medium-low", "Low"])
#Omit unnecessary columns
school_summary_spending_ranges = school_summary_spending_ranges[['Spending Ranges (Per Student)', 'School Name', 'Average Math Score', 'Average Reading Score', '% Passing Math', '% Passing Reading', 'Overall Passing Rate']]
#Groupby School Name and Spending Ranges (per student)
school_summary_spending_ranges_grouped = school_summary_spending_ranges.groupby(['Spending Ranges (Per Student)'], as_index=False).mean()
school_summary_spending_ranges_grouped
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
      <th>Spending Ranges (Per Student)</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>High</td>
      <td>83.455399</td>
      <td>83.933814</td>
      <td>93.460096</td>
      <td>96.610877</td>
      <td>95.035486</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Medium-high</td>
      <td>81.899826</td>
      <td>83.155286</td>
      <td>87.133538</td>
      <td>92.718205</td>
      <td>89.925871</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Medium-low</td>
      <td>78.990942</td>
      <td>81.917212</td>
      <td>75.209078</td>
      <td>86.089386</td>
      <td>80.649232</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Low</td>
      <td>77.023555</td>
      <td>80.957446</td>
      <td>66.701010</td>
      <td>80.675217</td>
      <td>73.688113</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Groupby school size:
#Create copy of school_summary for school size
school_summary_size_ranges = school_summary
#Create bins and bin labels Average Spending Ranges per student to school_summary
school_summary_size_ranges["School Size"] = pd.qcut(school_summary_size_ranges['Total Students'], 3, labels=["Large", "Medium", "Small"])
#Omit unnecessary columns
school_summary_size_ranges = school_summary_size_ranges[['School Size', 'School Name', 'Average Math Score', 'Average Reading Score', '% Passing Math', '% Passing Reading', 'Overall Passing Rate']]
#Group by school size
school_summary_size_ranges_grouped = school_summary_size_ranges.groupby(['School Size'], as_index=False).mean()
school_summary_size_ranges_grouped
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
      <th>School Size</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Large</td>
      <td>83.554500</td>
      <td>83.850220</td>
      <td>93.526422</td>
      <td>96.500267</td>
      <td>95.013345</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Medium</td>
      <td>80.750065</td>
      <td>82.769850</td>
      <td>83.065610</td>
      <td>90.161203</td>
      <td>86.613407</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Small</td>
      <td>76.993025</td>
      <td>80.967495</td>
      <td>66.369129</td>
      <td>80.995600</td>
      <td>73.682364</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Groupby school type: 
#Create copy of school_summary for school type
school_summary_type = school_summary
#Create bins and bin labels Average Spending Ranges per student to school_summary
#school_summary_type["School Size"] = pd.qcut(school_summary_type['Total Students'], 3, labels=["Large", "Medium", "Small"])
#Omit unnecessary columns
school_summary_type = school_summary_type[['School Type', 'Average Math Score', 'Average Reading Score', '% Passing Math', '% Passing Reading', 'Overall Passing Rate']]
#Groupby Type
school_summary_type_grouped = school_summary_type.groupby(['School Type'], as_index=False).mean()
school_summary_type_grouped
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
      <th>School Type</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Charter</td>
      <td>83.473852</td>
      <td>83.896421</td>
      <td>93.620830</td>
      <td>96.586489</td>
      <td>95.103660</td>
    </tr>
    <tr>
      <th>1</th>
      <td>District</td>
      <td>76.956733</td>
      <td>80.966636</td>
      <td>66.548453</td>
      <td>80.799062</td>
      <td>73.673757</td>
    </tr>
  </tbody>
</table>
</div>




```python
#District Summary:
#Find total number of schools
school_count = len(school_summary.index)

#apply sum function
district_school_summary_sum = school_summary[['Total Students', 'Total School Budget']].sum()
district_school_summary_sum.head()
#apply mean function
district_school_summary_mean = school_summary[['Average Math Score', 'Average Reading Score','% Passing Math', '% Passing Reading', 'Overall Passing Rate']].mean()
district_school_summary_mean.head()
#combine series 
district_summary = pd.concat([district_school_summary_mean, district_school_summary_sum, pd.Series({'Total Schools': school_count})])
district_summary
```




    Average Math Score       8.043253e+01
    Average Reading Score    8.252919e+01
    % Passing Math           8.098705e+01
    % Passing Reading        8.921902e+01
    Overall Passing Rate     8.510304e+01
    Total Students           3.917000e+04
    Total School Budget      2.464943e+07
    Total Schools            1.500000e+01
    dtype: float64



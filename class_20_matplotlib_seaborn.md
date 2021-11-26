#  Group by


```python
import pandas as pd
```


```python
df = pd.read_csv('datasets/weather_by_cities_group_by.csv')
df
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
      <th>day</th>
      <th>city</th>
      <th>temperature</th>
      <th>windspeed</th>
      <th>event</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1/1/2017</td>
      <td>new york</td>
      <td>32</td>
      <td>6</td>
      <td>Rain</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1/2/2017</td>
      <td>new york</td>
      <td>36</td>
      <td>7</td>
      <td>Sunny</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1/3/2017</td>
      <td>new york</td>
      <td>28</td>
      <td>12</td>
      <td>Snow</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1/4/2017</td>
      <td>new york</td>
      <td>33</td>
      <td>7</td>
      <td>Sunny</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1/1/2017</td>
      <td>mumbai</td>
      <td>90</td>
      <td>5</td>
      <td>Sunny</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1/2/2017</td>
      <td>mumbai</td>
      <td>85</td>
      <td>12</td>
      <td>Fog</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1/3/2017</td>
      <td>mumbai</td>
      <td>87</td>
      <td>15</td>
      <td>Fog</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1/4/2017</td>
      <td>mumbai</td>
      <td>92</td>
      <td>5</td>
      <td>Rain</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1/1/2017</td>
      <td>paris</td>
      <td>45</td>
      <td>20</td>
      <td>Sunny</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1/2/2017</td>
      <td>paris</td>
      <td>50</td>
      <td>13</td>
      <td>Cloudy</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1/3/2017</td>
      <td>paris</td>
      <td>54</td>
      <td>8</td>
      <td>Cloudy</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1/4/2017</td>
      <td>paris</td>
      <td>42</td>
      <td>10</td>
      <td>Cloudy</td>
    </tr>
  </tbody>
</table>
</div>



What was the max temp in each of the 3 citites


```python
g = df.groupby("city")
```


```python
for data in g:
    print(data)
```

    ('mumbai',         day    city  temperature  windspeed  event
    4  1/1/2017  mumbai           90          5  Sunny
    5  1/2/2017  mumbai           85         12    Fog
    6  1/3/2017  mumbai           87         15    Fog
    7  1/4/2017  mumbai           92          5   Rain)
    ('new york',         day      city  temperature  windspeed  event
    0  1/1/2017  new york           32          6   Rain
    1  1/2/2017  new york           36          7  Sunny
    2  1/3/2017  new york           28         12   Snow
    3  1/4/2017  new york           33          7  Sunny)
    ('paris',          day   city  temperature  windspeed   event
    8   1/1/2017  paris           45         20   Sunny
    9   1/2/2017  paris           50         13  Cloudy
    10  1/3/2017  paris           54          8  Cloudy
    11  1/4/2017  paris           42         10  Cloudy)
    


```python
g.get_group('mumbai')
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
      <th>day</th>
      <th>city</th>
      <th>temperature</th>
      <th>windspeed</th>
      <th>event</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>1/1/2017</td>
      <td>mumbai</td>
      <td>90</td>
      <td>5</td>
      <td>Sunny</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1/2/2017</td>
      <td>mumbai</td>
      <td>85</td>
      <td>12</td>
      <td>Fog</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1/3/2017</td>
      <td>mumbai</td>
      <td>87</td>
      <td>15</td>
      <td>Fog</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1/4/2017</td>
      <td>mumbai</td>
      <td>92</td>
      <td>5</td>
      <td>Rain</td>
    </tr>
  </tbody>
</table>
</div>




```python
g.get_group('paris')
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
      <th>day</th>
      <th>city</th>
      <th>temperature</th>
      <th>windspeed</th>
      <th>event</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8</th>
      <td>1/1/2017</td>
      <td>paris</td>
      <td>45</td>
      <td>20</td>
      <td>Sunny</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1/2/2017</td>
      <td>paris</td>
      <td>50</td>
      <td>13</td>
      <td>Cloudy</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1/3/2017</td>
      <td>paris</td>
      <td>54</td>
      <td>8</td>
      <td>Cloudy</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1/4/2017</td>
      <td>paris</td>
      <td>42</td>
      <td>10</td>
      <td>Cloudy</td>
    </tr>
  </tbody>
</table>
</div>




```python
g.max()
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
      <th>day</th>
      <th>temperature</th>
      <th>windspeed</th>
      <th>event</th>
    </tr>
    <tr>
      <th>city</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>mumbai</th>
      <td>1/4/2017</td>
      <td>92</td>
      <td>15</td>
      <td>Sunny</td>
    </tr>
    <tr>
      <th>new york</th>
      <td>1/4/2017</td>
      <td>36</td>
      <td>12</td>
      <td>Sunny</td>
    </tr>
    <tr>
      <th>paris</th>
      <td>1/4/2017</td>
      <td>54</td>
      <td>20</td>
      <td>Sunny</td>
    </tr>
  </tbody>
</table>
</div>




```python
g.mean()
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
      <th>temperature</th>
      <th>windspeed</th>
    </tr>
    <tr>
      <th>city</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>mumbai</th>
      <td>88.50</td>
      <td>9.25</td>
    </tr>
    <tr>
      <th>new york</th>
      <td>32.25</td>
      <td>8.00</td>
    </tr>
    <tr>
      <th>paris</th>
      <td>47.75</td>
      <td>12.75</td>
    </tr>
  </tbody>
</table>
</div>




```python
automobile_df = pd.DataFrame({'car_name' : ["Toyota Corolla Mark ii",
                                            "Chevrolet Chevelle Malibu",
                                            "Audi 100 LS",
                                            "BMW 2002",
                                            "Datsun PL510"],
                                   'mpg' : [24, 18, 24, 26, 27],
                            'horsepower' : [95, 130, 90, 113, 88],
                        'origin_country' : ["Japan", "US", "Germany", 
                                            "Germany", "Japan"]
    
                            })
```

#automobile_df


```python
automobile_df.to_csv('new_data.csv')
```


```python
ls
```

     append_mode.txt
     append_read_mode.py
     Assignment.txt
     class_10_map_reduce_filter_enumerate_iterator.ipynb
     class_11_module_filehandling.ipynb
     class_12_file_handling.ipynb
     class_13_exception_handling.ipynb
    'class_14_regular expression.ipynb'
     class_15_numpy_part_1.ipynb
     class_16_numpy_part_2.ipynb
     class_17_numpy_part_3_pandas.ipynb
     class_18_pandas_part_2.ipynb
     class_19_pandas_part_3.ipynb
     class_20_matplotlib_seaborn.ipynb
     class_4_string_part2_list.ipynb
     class_5_list_tuple.ipynb
     class_6_tuple_set_dic.ipynb
    'class_7_dict_conditional statments.ipynb'
     class_8_for_while_break_continue_range.ipynb
     class_9_functions_and_global_local_varibales.ipynb
     [0m[01;34mdatasets[0m/
    'Data Types.ipynb'
     float_complex_None_Bool_String.ipynb
     my_module.py
     new_data.csv
     [01;34m__pycache__[0m/
     read_mode.txt
     read_write_mode.py
    'string methods.ipynb'
     text.py
     Untitled1.ipynb
     Untitled.ipynb
     write_mode_op.py
     write_mode.txt
     write_read_mode.py



```python
# matpotlib

import matplotlib.pyplot as plt
```


```python
week_day=[1,2,3,4,5,6,7]
temp=[50,51,52,48,47,49,46]
```


```python
plt.plot(week_day , temp)
```




    [<matplotlib.lines.Line2D at 0x7f0e6717f310>]




    
![png](output_16_1.png)
    



```python
plt.plot(week_day , temp , marker = 'p' , linestyle = ':' , color = 'g')
plt.title('temperature vs weekday')
plt.ylabel('temp')
plt.xlabel('weekday')
```




    Text(0.5, 0, 'weekday')




    
![png](output_17_1.png)
    


https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html


```python
# format string

fmt = '[marker][line][color]'

plt.plot(week_day , temp , 'o--b')
plt.title('temperature vs weekday')
plt.ylabel('temp')
plt.xlabel('weekday')
```




    Text(0.5, 0, 'weekday')




    
![png](output_19_1.png)
    



```python
plt.plot(week_day , temp , 'k>--')
plt.title('temperature vs weekday')
plt.ylabel('temp')
plt.xlabel('weekday')
```




    Text(0.5, 0, 'weekday')




    
![png](output_20_1.png)
    



```python
days=[1,2,3,4,5,6,7] # weekdays
max_t=[50,51,52,48,47,49,46] # max temp recorder at that day
min_t=[43,42,40,44,33,35,37] # min temp
avg_t=[45,48,48,46,40,42,41] # avg temp
```


```python
plt.plot(days , max_t)
plt.plot(days , min_t)
plt.plot(days , avg_t)
```




    [<matplotlib.lines.Line2D at 0x7f0e65fe8460>]




    
![png](output_22_1.png)
    



```python
plt.plot(days , max_t , label ='max')
plt.plot(days , min_t, label ='min')
plt.plot(days , avg_t, label ='avg')
plt.title('temperature vs weekday')
plt.ylabel('temp')
plt.xlabel('weekday')
plt.legend()
```




    <matplotlib.legend.Legend at 0x7f0e6640ff70>




    
![png](output_23_1.png)
    



```python
plt.plot(days , max_t , label ='max')
plt.plot(days , min_t, label ='min')
plt.plot(days , avg_t, label ='avg')
plt.title('temperature vs weekday')
plt.ylabel('temp')
plt.xlabel('weekday')
plt.legend()
plt.grid()
plt.savefig('abc.jpg')
```


    
![png](output_24_0.png)
    



```python
1. barchart
2. histogram
3. scatterplot
4. piechart
```


```python
# barchart

company=['GOOGL','AMZN','MSFT','FB']
revenue=[90,136,89,27]
```


```python
plt.bar(company, revenue , label = 'Revenue')
plt.title('revenue')
plt.ylabel('revenue')
plt.xlabel('company')
plt.legend()
```




    <matplotlib.legend.Legend at 0x7f0e65cb4f10>




    
![png](output_27_1.png)
    



```python
plt.barh(company, revenue , label = 'Revenue')
plt.title('revenue')
plt.ylabel('revenue')
plt.xlabel('company')
plt.legend()
```




    <matplotlib.legend.Legend at 0x7f0e65c6ed30>




    
![png](output_28_1.png)
    



```python
plt.bar(company, revenue , label = 'Revenue')
plt.bar(company, [10,20,30,40] , label = 'profit')

plt.title('revenue')
plt.ylabel('revenue')
plt.xlabel('company')
plt.legend()
```




    <matplotlib.legend.Legend at 0x7f0e65bbfeb0>




    
![png](output_29_1.png)
    



```python
# Histogram - one axis - x aixs
```


```python
blood_sugar = [113, 85, 90, 150, 149, 88, 93, 115, 135, 80, 77, 82, 129]

80-100 normal
100 -125 pre
125+ dibatic
```


```python
blood_sugar = [113, 85, 90, 150, 149, 88, 93, 115, 135, 80, 77, 82, 129]
plt.hist(blood_sugar , bins = 10)
```




    (array([3., 3., 1., 0., 1., 1., 0., 2., 0., 2.]),
     array([ 77. ,  84.3,  91.6,  98.9, 106.2, 113.5, 120.8, 128.1, 135.4,
            142.7, 150. ]),
     <BarContainer object of 10 artists>)




    
![png](output_32_1.png)
    



```python
77   ---   150
```


```python
blood_sugar = [113, 85, 90, 150, 149, 88, 93, 115, 135, 80, 77, 82, 129]
plt.hist(blood_sugar , bins = [70 ,100,125,150])
```




    (array([7., 2., 4.]),
     array([ 70, 100, 125, 150]),
     <BarContainer object of 3 artists>)




    
![png](output_34_1.png)
    



```python
blood_sugar_men = [113, 85, 90, 150, 149, 88, 93, 115, 135, 80, 77, 82, 129]
blood_sugar_women = [67, 98, 89, 120, 133, 150, 84, 69, 89, 79, 120, 112, 100]

plt.hist([blood_sugar_men , blood_sugar_women] , bins = 10 , color = ['green' , 'orange'],
        label = ['men' , 'woman'])
plt.legend()
```




    <matplotlib.legend.Legend at 0x7f0e65886f70>




    
![png](output_35_1.png)
    



```python
# piechart

exp_vals = [1400,600,300,410,250]
exp_labels = ["Home Rent","Food","Phone/Internet Bill","Car ","Other Utilities"]
plt.pie(exp_vals , labels = exp_labels)
```




    ([<matplotlib.patches.Wedge at 0x7f0e65a27c10>,
      <matplotlib.patches.Wedge at 0x7f0e65a39ee0>,
      <matplotlib.patches.Wedge at 0x7f0e65a398e0>,
      <matplotlib.patches.Wedge at 0x7f0e65a395b0>,
      <matplotlib.patches.Wedge at 0x7f0e65a37eb0>],
     [Text(0.09328656407206024, 1.0960372333838069, 'Home Rent'),
      Text(-0.9822184890776084, -0.4952240298229684, 'Food'),
      Text(-0.16284704617934698, -1.0878790555712807, 'Phone/Internet Bill'),
      Text(0.6256100334857941, -0.9047718419590123, 'Car '),
      Text(1.0615045230766318, -0.28845822485734873, 'Other Utilities')])




    
![png](output_36_1.png)
    



```python
exp_vals = [1400,600,300,410,250]
exp_labels = ["Home Rent","Food","Phone/Internet Bill","Car ","Other Utilities"]
plt.pie(exp_vals , labels = exp_labels, radius = 2)
```




    ([<matplotlib.patches.Wedge at 0x7f0e659ff340>,
      <matplotlib.patches.Wedge at 0x7f0e659ff5e0>,
      <matplotlib.patches.Wedge at 0x7f0e659ff520>,
      <matplotlib.patches.Wedge at 0x7f0e659ffa30>,
      <matplotlib.patches.Wedge at 0x7f0e664c9c40>],
     [Text(0.18657312814412047, 2.1920744667676137, 'Home Rent'),
      Text(-1.964436978155217, -0.9904480596459369, 'Food'),
      Text(-0.32569409235869395, -2.1757581111425615, 'Phone/Internet Bill'),
      Text(1.2512200669715883, -1.8095436839180246, 'Car '),
      Text(2.1230090461532636, -0.5769164497146975, 'Other Utilities')])




    
![png](output_37_1.png)
    



```python
exp_vals = [1400,600,300,410,250]
exp_labels = ["Home Rent","Food","Phone/Internet Bill","Car ","Other Utilities"]
plt.pie(exp_vals , labels = exp_labels, radius = 2 , autopct = '%0.0f%%')
```




    ([<matplotlib.patches.Wedge at 0x7f0e6590ddf0>,
      <matplotlib.patches.Wedge at 0x7f0e6589b520>,
      <matplotlib.patches.Wedge at 0x7f0e6589bbb0>,
      <matplotlib.patches.Wedge at 0x7f0e658a8280>,
      <matplotlib.patches.Wedge at 0x7f0e658a8910>],
     [Text(0.18657312814412047, 2.1920744667676137, 'Home Rent'),
      Text(-1.964436978155217, -0.9904480596459369, 'Food'),
      Text(-0.32569409235869395, -2.1757581111425615, 'Phone/Internet Bill'),
      Text(1.2512200669715883, -1.8095436839180246, 'Car '),
      Text(2.1230090461532636, -0.5769164497146975, 'Other Utilities')],
     [Text(0.10176716080588388, 1.1956769818732438, '47%'),
      Text(-1.0715110789937545, -0.5402443961705109, '20%'),
      Text(-0.17765132310474216, -1.1867771515323062, '10%'),
      Text(0.6824836728935935, -0.9870238275916496, '14%'),
      Text(1.1580049342654164, -0.31468169984438044, '8%')])




    
![png](output_38_1.png)
    



```python
exp_vals = [1400,600,300,410,250]
exp_labels = ["Home Rent","Food","Phone/Internet Bill","Car ","Other Utilities"]
plt.pie(exp_vals , labels = exp_labels, radius = 2 , autopct = '%0.0f%%', explode = [0.05,0,0,0,0.07])
```




    ([<matplotlib.patches.Wedge at 0x7f0e65736460>,
      <matplotlib.patches.Wedge at 0x7f0e65736b50>,
      <matplotlib.patches.Wedge at 0x7f0e65743160>,
      <matplotlib.patches.Wedge at 0x7f0e65743760>,
      <matplotlib.patches.Wedge at 0x7f0e65743cd0>],
     [Text(0.1908134265110323, 2.2418943410123324, 'Home Rent'),
      Text(-1.964436978155217, -0.9904480596459369, 'Food'),
      Text(-0.32569409235869395, -2.1757581111425615, 'Phone/Internet Bill'),
      Text(1.2512200669715883, -1.8095436839180246, 'Car '),
      Text(2.190559333985413, -0.5952728822056197, 'Other Utilities')],
     [Text(0.1060074591727957, 1.2454968561179622, '47%'),
      Text(-1.0715110789937545, -0.5402443961705109, '20%'),
      Text(-0.17765132310474216, -1.1867771515323062, '10%'),
      Text(0.6824836728935935, -0.9870238275916496, '14%'),
      Text(1.2255552220975656, -0.3330381323353026, '8%')])




    
![png](output_39_1.png)
    



```python
# Scatter plot

# - gives the relation between the two variable
```


```python
x = [1,2,3,4,5,6,7,8]
y = [5,2,5,7,8,4,2,5]
plt.xticks([1,2,3,4,5,6,7,8] , ['a' , 'b' , 'c' , 'd' , 'e' , 'f' , 'g' , 'h'])
plt.scatter(x,y , color = 'g')
```




    <matplotlib.collections.PathCollection at 0x7f0e6553c310>




    
![png](output_41_1.png)
    



```python
# subplot

year=[2014,2015,2016,2017]
income=[4000,4500,5300,4600]
expense=[2800,3000,2800,3400]

plt.subplot(1,2,1)
plt.bar(year,income)

plt.subplot(1,2,2)
plt.bar(year,expense)
```




    <BarContainer object of 4 artists>




    
![png](output_42_1.png)
    


# seaborn


```python
import seaborn as sns
```


```python
tips = sns.load_dataset('tips')
tips
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
      <th>total_bill</th>
      <th>tip</th>
      <th>sex</th>
      <th>smoker</th>
      <th>day</th>
      <th>time</th>
      <th>size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>16.99</td>
      <td>1.01</td>
      <td>Female</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10.34</td>
      <td>1.66</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>21.01</td>
      <td>3.50</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>23.68</td>
      <td>3.31</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>24.59</td>
      <td>3.61</td>
      <td>Female</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>4</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>239</th>
      <td>29.03</td>
      <td>5.92</td>
      <td>Male</td>
      <td>No</td>
      <td>Sat</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>240</th>
      <td>27.18</td>
      <td>2.00</td>
      <td>Female</td>
      <td>Yes</td>
      <td>Sat</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>241</th>
      <td>22.67</td>
      <td>2.00</td>
      <td>Male</td>
      <td>Yes</td>
      <td>Sat</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>242</th>
      <td>17.82</td>
      <td>1.75</td>
      <td>Male</td>
      <td>No</td>
      <td>Sat</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>243</th>
      <td>18.78</td>
      <td>3.00</td>
      <td>Female</td>
      <td>No</td>
      <td>Thur</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>244 rows × 7 columns</p>
</div>




```python
sns.relplot(x = 'total_bill', y = 'tip', data = tips)
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e65245970>




    
![png](output_46_1.png)
    



```python
sns.relplot(x = 'total_bill', y = 'tip', data = tips, hue = 'smoker')
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e660bae20>




    
![png](output_47_1.png)
    



```python
sns.relplot(x = 'total_bill', y = 'tip', data = tips, hue = 'smoker', style = 'time')
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e60006760>




    
![png](output_48_1.png)
    



```python
sns.relplot(x = 'total_bill', y = 'tip', data = tips, hue = 'smoker', style = 'time', size = 'size')
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e661b3760>




    
![png](output_49_1.png)
    



```python
sns.relplot(x = 'total_bill', y = 'tip', data = tips, hue = 'time', col = 'day', size = 'size')
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e5fe10bb0>




    
![png](output_50_1.png)
    



```python
# barplot
titanic = sns.load_dataset('titanic')
titanic
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
      <th>survived</th>
      <th>pclass</th>
      <th>sex</th>
      <th>age</th>
      <th>sibsp</th>
      <th>parch</th>
      <th>fare</th>
      <th>embarked</th>
      <th>class</th>
      <th>who</th>
      <th>adult_male</th>
      <th>deck</th>
      <th>embark_town</th>
      <th>alive</th>
      <th>alone</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>7.2500</td>
      <td>S</td>
      <td>Third</td>
      <td>man</td>
      <td>True</td>
      <td>NaN</td>
      <td>Southampton</td>
      <td>no</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>71.2833</td>
      <td>C</td>
      <td>First</td>
      <td>woman</td>
      <td>False</td>
      <td>C</td>
      <td>Cherbourg</td>
      <td>yes</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>3</td>
      <td>female</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>7.9250</td>
      <td>S</td>
      <td>Third</td>
      <td>woman</td>
      <td>False</td>
      <td>NaN</td>
      <td>Southampton</td>
      <td>yes</td>
      <td>True</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>53.1000</td>
      <td>S</td>
      <td>First</td>
      <td>woman</td>
      <td>False</td>
      <td>C</td>
      <td>Southampton</td>
      <td>yes</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>8.0500</td>
      <td>S</td>
      <td>Third</td>
      <td>man</td>
      <td>True</td>
      <td>NaN</td>
      <td>Southampton</td>
      <td>no</td>
      <td>True</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>886</th>
      <td>0</td>
      <td>2</td>
      <td>male</td>
      <td>27.0</td>
      <td>0</td>
      <td>0</td>
      <td>13.0000</td>
      <td>S</td>
      <td>Second</td>
      <td>man</td>
      <td>True</td>
      <td>NaN</td>
      <td>Southampton</td>
      <td>no</td>
      <td>True</td>
    </tr>
    <tr>
      <th>887</th>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>19.0</td>
      <td>0</td>
      <td>0</td>
      <td>30.0000</td>
      <td>S</td>
      <td>First</td>
      <td>woman</td>
      <td>False</td>
      <td>B</td>
      <td>Southampton</td>
      <td>yes</td>
      <td>True</td>
    </tr>
    <tr>
      <th>888</th>
      <td>0</td>
      <td>3</td>
      <td>female</td>
      <td>NaN</td>
      <td>1</td>
      <td>2</td>
      <td>23.4500</td>
      <td>S</td>
      <td>Third</td>
      <td>woman</td>
      <td>False</td>
      <td>NaN</td>
      <td>Southampton</td>
      <td>no</td>
      <td>False</td>
    </tr>
    <tr>
      <th>889</th>
      <td>1</td>
      <td>1</td>
      <td>male</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>30.0000</td>
      <td>C</td>
      <td>First</td>
      <td>man</td>
      <td>True</td>
      <td>C</td>
      <td>Cherbourg</td>
      <td>yes</td>
      <td>True</td>
    </tr>
    <tr>
      <th>890</th>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>32.0</td>
      <td>0</td>
      <td>0</td>
      <td>7.7500</td>
      <td>Q</td>
      <td>Third</td>
      <td>man</td>
      <td>True</td>
      <td>NaN</td>
      <td>Queenstown</td>
      <td>no</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
<p>891 rows × 15 columns</p>
</div>




```python
sns.barplot('class' , 'survived' , data= titanic)
```

    /home/hulk/anaconda3/lib/python3.8/site-packages/seaborn/_decorators.py:36: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
      warnings.warn(
    




    <AxesSubplot:xlabel='class', ylabel='survived'>




    
![png](output_52_2.png)
    



```python
sns.catplot(x = 'day', y = 'total_bill', data = tips)
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e5fe1cf10>




    
![png](output_53_1.png)
    



```python
sns.catplot(x = 'day', y = 'total_bill', data = tips , jitter = False)
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e5f8344c0>




    
![png](output_54_1.png)
    



```python
sns.catplot(x = 'day', y = 'total_bill', data = tips, kind = 'swarm')
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e5f7c4d60>




    
![png](output_55_1.png)
    



```python
sns.catplot(x = 'day', y = 'total_bill', data = tips, kind = 'box')
```




    <seaborn.axisgrid.FacetGrid at 0x7f0e5f648e80>




    
![png](output_56_1.png)
    


# dist plot


```python
import numpy as np
x = np.random.randn(100)
x
```




    array([ 1.20895122e+00, -3.61654260e-01, -8.56853015e-02, -1.80143552e+00,
           -1.43471882e+00, -8.76126422e-01,  5.68828313e-02, -1.42702998e+00,
           -6.76190322e-01,  9.10473800e-01,  8.57903348e-01,  6.63026888e-01,
            1.29653461e+00,  1.79994532e-01, -3.96637754e-01,  5.70411031e-01,
            1.11308962e+00, -1.17778935e-01, -3.52804676e-01,  2.11839652e+00,
            1.22798719e+00, -1.76368839e+00, -1.26409100e+00,  1.51044439e+00,
           -4.42388697e-01,  1.25995734e+00, -8.21535810e-01, -7.67369174e-01,
            7.88685250e-01, -7.44380768e-01,  1.12259208e+00, -1.15564655e+00,
           -7.40668781e-02,  3.06903557e-01, -4.85264199e-02, -1.30832854e+00,
            1.08268735e+00, -4.43940985e-01,  8.36561631e-01, -1.05571179e+00,
            5.94675970e-01,  7.88414707e-02, -5.49860318e-01, -1.12310396e-01,
            1.29502916e+00, -4.88071914e-01,  3.17891705e-01,  6.68758589e-01,
           -4.82899870e-01,  1.09765044e+00,  1.31126898e+00, -7.33118190e-02,
            1.53413397e+00, -2.77952413e-01,  8.61308736e-02, -9.99182679e-01,
            8.68086463e-02, -1.13335084e+00, -1.09656862e+00,  4.03188305e-01,
            1.37229884e+00, -8.92676314e-01, -2.50639426e+00,  1.37087991e+00,
           -4.27399123e-01,  1.04940531e+00, -1.50680156e+00, -5.33722115e-02,
            4.27843663e-01,  2.42039611e-01, -1.87616278e+00,  1.84510351e+00,
            6.02392892e-01,  2.09802848e+00,  9.14298274e-01,  5.75221065e-01,
            2.67026169e-01, -1.11025211e+00, -2.71384389e+00, -2.72022487e-01,
           -2.42280821e-02, -1.78043855e+00,  2.20840475e+00,  2.00137780e+00,
            1.00994250e+00,  2.04426213e-01, -1.48321816e+00,  5.56690082e-01,
            1.49549006e+00, -1.16053498e-01, -4.26685636e-01,  4.97923395e-01,
            1.02571632e-01, -8.65353792e-04, -3.04887561e-01, -8.09851273e-01,
           -1.27114395e+00,  3.00051006e-01, -1.47509469e+00, -4.88772729e-02])




```python
sns.distplot(x)
```

    /home/hulk/anaconda3/lib/python3.8/site-packages/seaborn/distributions.py:2551: FutureWarning: `distplot` is a deprecated function and will be removed in a future version. Please adapt your code to use either `displot` (a figure-level function with similar flexibility) or `histplot` (an axes-level function for histograms).
      warnings.warn(msg, FutureWarning)
    




    <AxesSubplot:ylabel='Density'>




    
![png](output_59_2.png)
    



```python
x = tips['total_bill']
y = tips['tip']
sns.jointplot(x = x, y=y)
```




    <seaborn.axisgrid.JointGrid at 0x7f0e5da4ab50>




    
![png](output_60_1.png)
    



```python
sns.pairplot(tips)
```




    <seaborn.axisgrid.PairGrid at 0x7f0e5da4e070>




    
![png](output_61_1.png)
    



```python

```

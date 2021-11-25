# local and global varibale

- global varibale is a varibale which you an use in entire code
- local varibale is a varibale where you can you in only in a particular function


```python
a = 15  # Global varibale
b = 10  # global varibale

def add():
    c = a + b  # c is a local varibale
    print(c)
    
add()
print(a)
print(b)
print(c)
```

    25
    15
    10
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-1-18cdd8d94993> in <module>
          9 print(a)
         10 print(b)
    ---> 11 print(c)
    

    NameError: name 'c' is not defined



```python
# write a function to check if a number is prime or not

def is_prime(num):
    for n in range(2 , num//2):
        if num %n ==0:
            print('not a prime')
            break
    else:
        print('prime')
```


```python
13 - 1, 2,3,4,5,6,7,8,9,10,11,12
13 - 2,3,4,5,6
```


```python
is_prime(3)
```

    prime
    

# For else

# the else keyword in the for loop specifiers a block of code to be executed when the loop is finished


```python
for x in range(6):
    print(x)
else:
    print('finally done')
```

    0
    1
    2
    3
    4
    5
    finally done
    


```python
map()

map function takes 2 args

1. function
2. iterable

synatx = map(function , iterable)
```


```python
def fahrenheit(T):
    return ((9/5)*T + 32)


def celsius(T):
    return ((5/9)*T - 32)
```


```python
temp_cel = [0 , 22.5 , 40, 100]
temp_fah = [fahrenheit(i) for i in temp_cel]
```


```python
temp_fah
```




    [32.0, 72.5, 104.0, 212.0]




```python
# working of map function

list(map(fahrenheit , temp_cel))
```




    [32.0, 72.5, 104.0, 212.0]




```python
list(map(lambda x :((9/5)*x + 32)  , temp_cel))
```




    [32.0, 72.5, 104.0, 212.0]




```python
a  = [1,2,3,4,5]
b = [2,3,4,5,6]
c = [6,7,8,9,10]

add_all = [9,12 , ]

list(map(lambda x,y,z : x+y+z , a , b , c))
```




    [9, 12, 15, 18, 21]




```python
#reduce

2 args

1. fucntion
2. iterable

syntax reduce(function , iterable)

agg , prod , sum , max , min

#Note - reducr fucntion alwasy takes 2 parameter only
```


```python
from functools import reduce

reduce(lambda a,b : a+b , [9,10,11,12,13])
```




    55




```python
from IPython.display import Image
Image('https://www.python-course.eu/images/reduce_diagram.png')
```




    
![png](output_16_0.png)
    




```python
reduce(lambda a,b : a>b , [9,10,11,12,13])
```




    False




```python
# fint the maximum of a seq (reduce)

reduce(lambda a,b: a if a>b else b , [5,2,7,9,2])
```




    9



# Filter

the filter function is the conviient way to filter out the lements from a literable

2 args

1. func
2. iterable

synatx - filter(func , iterbale)

the filter fucn need as funct as the first args . the function alwasy need to return Bool value .
this function willbe applied to every element of iterbale , only if the fucn return True for a 
element then that element will be considered as a part of new lits




```python
def even_check(num):
    if num%2 == 0:
        return True
    else:
        return False
```


```python
lst = [1,2,3,4,5,6,7,8,9]

list(filter(even_check , lst))
```




    [2, 4, 6, 8]




```python
def even_check(num):
    if num%2 == 0:
        return False
    else:
        return True
    
lst = [1,2,3,4,5,6,7,8,9]

list(filter(even_check , lst))
```




    [1, 3, 5, 7, 9]




```python
list(filter(lambda x : x%2!=0 , lst))
```




    [1, 3, 5, 7, 9]




```python
lst = ['akzelxw@hotmail.com',
'elum@gmail.com',
'akbar.caakaterasu@gmail.com',
'akarui.kibuno@gmail.com',
'ajsparkchick@hotmail.com',
'ajmeia@yahoo.com',
'ajhnstn87@gmail.com',
'ailuvzhoko4@hotmail.com',
'ailuvzhoko3@hotmail.com',
'ailuvzhoko2@hotmail.com',
'ailuvzhoko@hotmail.com',
'aillensiquioco@aol.com',
'ahmovic_ines@hotmail.com',
'ahmed_g300@yahoo.com',
'ahmadjazlan@gmail.com',
'ahmad_ridho19@yahoo.com']

# 1. get only those emails where the ending part is @gmail.com
# 2. a seq of all username of all email id - anything wriiten before @
```


```python
list(filter(lambda x : '@gmail.com' in  x , lst))
```




    ['elum@gmail.com',
     'akbar.caakaterasu@gmail.com',
     'akarui.kibuno@gmail.com',
     'ajhnstn87@gmail.com',
     'ahmadjazlan@gmail.com']




```python
a = list(map(lambda x : x.split('@')[0], lst))
```


```python
a.sort()
```


```python
a
```




    ['ahmad_ridho19',
     'ahmadjazlan',
     'ahmed_g300',
     'ahmovic_ines',
     'aillensiquioco',
     'ailuvzhoko',
     'ailuvzhoko2',
     'ailuvzhoko3',
     'ailuvzhoko4',
     'ajhnstn87',
     'ajmeia',
     'ajsparkchick',
     'akarui.kibuno',
     'akbar.caakaterasu',
     'akzelxw',
     'elum']




```python
# Enumerate

list(enumerate([10,20,30,40] , start=5))
```




    [(5, 10), (6, 20), (7, 30), (8, 40)]




```python
for i , j  in enumerate([1,2,3,4,5]):
    print(i)
    print(j)
```

    0
    1
    1
    2
    2
    3
    3
    4
    4
    5
    


```python
# find the key of value 'PYTHON'

my_dict = {"a": "PHP", "b":"JAVA", "c":"PYTHON", "d":"NODEJS"}

for i,j in enumerate(my_dict):
    if my_dict[j] == 'PYTHON':
        print(j)
```

    c
    


```python
for i,j in my_dict.items():
    if j == 'PYTHON':
        print(i)
```

    c
    

# iterables , Iterator


```python
1 . iterables

- list , tuple , string , dict

how to identify

- len
- dir(dataype) --> __iter__
- for loop should work
```


```python
2. Iterator

from the iterable objects we can create the iterator object

concept is used in for loop
```


```python
lst = [1,2,3,4,5,6]

# to create an iterator from iterable
my_iter = iter(lst)

print(type(my_iter))



```

    <class 'list_iterator'>
    


```python
# every iterator has something call as next function
next(my_iter)
```


    ---------------------------------------------------------------------------

    StopIteration                             Traceback (most recent call last)

    <ipython-input-74-e542bc5d2ec8> in <module>
          1 # every iterator has something call as next function
    ----> 2 next(my_iter)
    

    StopIteration: 



```python
lst = [0,1,2,3,4,5,6]

# to create an iterator from iterable
my_iter = iter(lst)

print(type(my_iter))

# print(next(my_iter))
# print(next(my_iter))
# print(next(my_iter))
# print(next(my_iter))
# print(next(my_iter))
# print(next(my_iter))
# print(next(my_iter))
```

    <class 'list_iterator'>
    


```python
for i in range(7):
    print(i)
```

    0
    1
    2
    3
    4
    5
    6
    


```python
try:
    print(next(my_iter))
except:
    pass
```


```python

```


```python

```

# SPINLAN
Spinlan, the declarative programming language 

## Example #1

```python 
#records_csv.h

def __SCOPE__ {
  fn as file('r');
}
#dict{SYMBOL,STOCK_PRICE,VOLUME,CLOSE} as DRECORD 
'AAPL',180.59,'20.9M','2019-7-16T16:29:59'
'AAPL',189.49,'19.6M','2019-7-17T16:29:59'
  .
  .
'AAPL',202.99,'21.3M','2019-7-31T16:29:59'
```


```python  
#!/usr/bin/spinlan

from fn import DRECORD
print '''${DRECORD.STOCK_PRICE[0]}'''

```

## Example #2

```python
#data_csv.h

def __SCOPE__ {
  fn as file('r');
}
#MyGrades is sorted(reverse=True) in [round(float,2) in fn.readlines()]
75.0
80.5
100.0
 .
 .
89.0
```

```python
#!/usr/bin/spinlan

from fn import MyGrades
print '''My highest grade is ${MyGrades[0]}'''
```

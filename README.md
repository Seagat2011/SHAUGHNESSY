# SPINLAN
Spinlan is a shell-based declarative programming language 

## Example #1

```python 
#records_csv.h

#dict{SYMBOL,STOCK_PRICE,VOLUME,CLOSE} as DRECORD;
'AAPL',180.59,'20.9M','2019-7-16T16:29:59'
'AAPL',189.49,'19.6M','2019-7-17T16:29:59'
  .
  .
'AAPL',202.99,'21.3M','2019-7-31T16:29:59'
```


```python  
#!/usr/bin/spinlan

from records_csv import DRECORD
print '''${DRECORD[0].STOCK_PRICE}'''

```

```python  
#!/usr/bin/spinlan

import records_csv as fn
from fn import DRECORD
print '''${DRECORD[0].STOCK_PRICE}'''

```

## Example #2

```python
#data_csv.h

#sorted(reverse=True) as MyGrades;
75.0
80.5
100.0
 .
 .
89.0
```

```python
#!/usr/bin/spinlan

from data_csv import MyGrades
print '''My highest grade is ${MyGrades[0]}'''
```

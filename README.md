# SPINLAN
Spinlan is a general purpose declarative programming language 

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

Also 

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

Spinlan also generates code to satisfy test-cases

## Example 3

```python
#x_csv.h

#dict{SYMBOL,PRICE,VOLUME,CLOSE} as x;
'AAPL',180.59,'20.9M','2019-7-16T16:29:59'
'AAPL',189.49,'19.6M','2019-7-17T16:29:59'
  .
  .
'AAPL',202.99,'21.3M','2019-7-31T16:29:59'
```

```python
#y_csv.h

#dict{SYMBOL,RANGE,AVGVOLUME,PERIOD} as y;
'AAPL',22.40,'20.4M','2019-7-16T16:29:59 - 2019-7-31T16:29:59'
```

```python
#!/usr/bin/spinlan

from x_csv import x
from y_csv import y
exec(from=[x],to=[y]) as z
print '''${z}'''
```

```
dict{SYMBOL,RANGE,AVGVOLUME,PERIOD} as y;
x[0].SYMBOL as y.SYMBOL;
len(x)-1 as _000_;
abs(x[0].PRICE-x[_000_].PRICE) as y.RANGE;
x[len].VOLUME as y.AVGVOLUME;
'''${x[0].CLOSE} - ${x[len].CLOSE}''' as y.PERIOD;
```

If Spinlan is unable to satisfy test-cases, test-cases may be submitted incrementally

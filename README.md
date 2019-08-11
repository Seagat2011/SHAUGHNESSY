# SHAUGHNESSY 
Shaughnessy is a general purpose declarative programming language 

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
#!/usr/bin/Shaughnessy

from records_csv import DRECORD
print '''${DRECORD[0].STOCK_PRICE}'''

```

Also 

```python  
#!/usr/bin/Shaughnessy

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
#!/usr/bin/Shaughnessy

from data_csv import MyGrades
print '''My top grade is ${MyGrades[0]}'''
```

Shaughnessy also generates intermediate code from provided test-cases

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

#dict{SYMBOL,PRICE_TO_VOLUME} as y;
'AAPL',9.0000E-6
'AAPL',9.6429E-6
 .
 .
'AAPL',9.6301E-6
```

```python
#!/usr/bin/Shaughnessy

from x_csv import x
from y_csv import y
exec(from=[x],to=[y]) as z
print '''${z}'''
```

```
dict{SYMBOL,PRICE,VOLUME,PERIOD} as x;
dict{SYMBOL,PRICE_TO_VOLUME} as y;
each x.SYMBOL as y.SYMBOL;
each ( x.PRICE / x.VOLUME ) as y.PRICE_TO_VOLUME
```

When Shaughnessy is unable to satisfy test-cases, test-cases may be submitted incrementally

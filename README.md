# SPINLAN
Spinlan, the declarative programming language 

## Example

```python 
#!/usr/bin/spinlan

import fn
import DRECORD from fn
import STOCK_PRICE from DRECORD as dict{SYMBOL,STOCK_PRICE,VOLUME,CLOSE}
print '''${STOCK_PRICE}'''

def __SCOPE__ {
  file('r') as fn from 'records.csv'
  DRECORD is str.split(',') in line from lines in fn.readlines()
  STOCK_PRICE isa str
}

```

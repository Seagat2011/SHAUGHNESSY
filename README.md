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
  fn as file('r') from 'records.csv'
  DRECORD as str.split(',') from fn.readlines()
  STOCK_PRICE as str
}

```

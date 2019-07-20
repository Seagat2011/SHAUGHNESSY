# SPINLAN
Spinlan, the declarative programming language 

## Example

```python 
#!/usr/bin/spinlan

import fn
import DRECORD from fn
import STOCK_PRICE from DRECORD
print '''${STOCK_PRICE}'''

def __SCOPE__ {
  fn as file('r') from 'records.csv'
  DRECORD is str.split(',') as dict{SYMBOL,STOCK_PRICE,VOLUME,CLOSE} from fn.readlines()
  STOCK_PRICE is str
}

```

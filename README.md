# SPINLAN
Spinlan, the declarative programming language 

## Example

```python 
#records_csv.h

def __SCOPE__ {
  fn as file('r');
  DRECORD is dict{SYMBOL,STOCK_PRICE,VOLUME,CLOSE} from str.split(',') in fn.readlines():
    SYMBOL is str;
    STOCK_PRICE is float(2);
    VOLUME is str;
    CLOSE is str;
}
'AAPL',180.59,'20.9M','2019-7-16T16:29:59'
'AAPL',189.49,'19.6M','2019-7-17T16:29:59'
  .
  .
'AAPL',202.99,'21.3M','2019-7-31T16:29:59'
```


```python  
#!/usr/bin/spinlan

import fn
import DRECORD from fn
print '''${DRECORD.STOCK_PRICE[0]}'''

```

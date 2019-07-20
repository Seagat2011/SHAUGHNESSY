# SPINLAN
Spinlan, the declarative programming language 

## Example

```python 
import fn
import DRECORD from fn
import STOCK_PRICE from DRECORD 

def {
  fn isa file from 'records.csv'
  DRECORD isa dict{SYMBOL,STOCK_PRICE,VOLUME,CLOSE} of str.split(',') from lines in fn.readlines()
  STOCK_PRICE isa str
}

```

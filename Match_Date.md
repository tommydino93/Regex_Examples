### Given an input text like:

```sh
>>> import re

>>> input_text = "ONCOLOGIE MEDICALE '\
Paris, le 28.01.2016 '\
XX, YY 03.06.1966 M                                 1600004044    2385846 '\
Conclusions: stabilité de la maladie."  # type: str # input path
```
### if we want to retrieve just the first date, we could write:

```sh
>>> match_list = re.findall(".aris, le \d+\.\d+\.\d+", input_text)
>>> match_list
['Paris, le 28.01.2016']

# extract first element of list
>>> match_string = match_list[0]  # type: str 
>>> match_string
'Paris, le 28.01.2016'
```

### Side notes:

* **\\.** is used for exactly matching the "." character between dd.mm.yyyy
* **.** is used to match the first letter of the city which could be either capital or non-capital

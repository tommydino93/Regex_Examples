### Given an input path (python string), extract only one specific part
```sh
>>> import re

>>> input_path = "/home/to5743/ds_data_augm_standardized_without_coords/out/"  # type: str # input path
```

### Now suppose we only want to extract:
```sh
ds_data_augm_standardized_without_coords
```

### We could write:

```sh
# extract specific part of path and store in list
>>> match_list = re.findall("ds\w+", input_path)  # type: list 
>>> match_list
['ds_data_augm_standardized_without_coords']

# extract first element of list
>>> match_string = match_list[0]  # type: str 
>>> match_string
'ds_data_augm_standardized_without_coords'
```

### Side notes:

* **ds** is used for matching the beginning of the specified string
  
* **\w+** matches a sequence of alphanumeric characters (including _), but does not match special characters such as "/". That's why the rest of the input string is discarded

* Had we written **ds.+** instead of **ds\w+**, we would have had:

```sh
>>> match_list
['ds_data_augm_standardized_without_coords/out/']
```

### Given the following list and text:

```sh
>>> comparative_list = ["comparatif", "Comparatif", "comparaison", "Comparaison", "comparatifs", "Comparatifs",
                        "comparatives", "Comparatives", "comparé", ".Comparatif", "asd.Comparatif"]
                        
>>> free_text = "Service de radiologie. Comparatif du 16.07.2"
```
### if we want to match any of the similar words of ```comparative_list``` in ```free_text```, we could write:

```sh
>>> import re
>>> regex = re.compile('(.*)[Cc]ompar')
```

### then to find the index of the word(s) that matched:
```sh
>>> from nltk import word_tokenize
>>> tokenized_text = word_tokenize(free_text)  # tokenize the free text
>>> comparative_idxs = [i for i, x in enumerate(tokenized_text) if re.match(regex, x)]

>>> comparative_idxs
[4]  # the fourth token ("Comparatif") corresponds to the match we're interested in
```

### Side notes:

* **(\.*)** is used to match a group (because of ()) of 0 or more of any character (because of \.*); it useful for cases where there is no whitespace after the dot (e.g. "end of sentence.Comparatif")
* **[Cc]** is used to match the first letter "c" which could be either capital or non-capital

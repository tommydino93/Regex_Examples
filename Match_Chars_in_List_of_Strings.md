### Given the input list
```sh
>>> all_sequences = ["T2-gresag", "T1-axial", "t2_coronal", "PD", "axialT2"]
```
### we want to extract only the items that contain the chars "T2" or "t2":
```sh
>>> r = re.compile("(.+)?[Tt]2")  # define regex to match
>>> t2_sequences = list(filter(r.match, all_sequences))  # only extract sequences that match the regex
>>> t2_sequences
['T2-gresag', 't2_coronal', 'axialT2']
```
### Side notes:

* **[Tt]** is used for matching the the letter T either capital or lowercase
  
* **(.+)** matches a a group of any characters

* **?** indicates that the group inside parentheses is optional

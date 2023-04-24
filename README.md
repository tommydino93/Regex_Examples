# Regex Examples
This repository contains examples of regular expressions in python

![alt text](https://github.com/tommydino93/Regex_Examples/blob/master/regex.png)

## Specific matching rules:
* **\\.** is used for exactly matching the "." character (e.g. between dd.mm.yyyy)
* **.** is used to match whichever character (either capital or non-capital)
* **\w+** matches a sequence of alphanumeric characters (including _), but does not match special characters such as "/"
* **\d+** matches a series of digits
* **(\.*)** is used to match a group (because of ()) of 0 or more of any character (because of \.*); it useful for cases where there is no whitespace after the dot (e.g. "end of sentence.Comparatif")
* **[Cc]** is used to match the letter "c" which could be either capital or non-capital
* **?** indicates that a char (or group) is optional. E.g. "aa?" will match either one or two letters "a" cause the second char is optional
* **|** is used to reproduce the **logical OR**. E.g. `re.compile("Sent from (iPhone|iPod)")` to match either iPhone OR iPod
* **secret[\\.,]** is used to match the word "secret" followed either by a "." or a ","
* **(secret)[\.,]** is used to match only the word "secret" and get rid of the punctuation that comes after it
## General rules:
* `re.search(r"smth", file)` finds only the first match, and also provides the indexes of the match in the text
* `re.findall(r"smth", file)` finds all the matches, but we lose the information about the indexes
* `re.finditer(r"smth", file)` finds all the matches and also retains the indexes. It must be run as:
```
for match in re.finditer(r"(secret)[\.,]", file_content):
   print(match)
```

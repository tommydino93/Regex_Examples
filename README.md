# Regex Examples
This repository contains examples of regular expressions in python


## Useful rules:
* **\\.** is used for exactly matching the "." character (e.g. between dd.mm.yyyy)
* **.** is used to match whichever character (either capital or non-capital)
* **\w+** matches a sequence of alphanumeric characters (including _), but does not match special characters such as "/"
* **\d+** matches a series of digits
* **(\.*)** is used to match a group (because of ()) of 0 or more of any character (because of \.*); it useful for cases where there is no whitespace after the dot (e.g. "end of sentence.Comparatif")
* **[Cc]** is used to match the letter "c" which could be either capital or non-capital

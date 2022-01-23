# RegEx

```RegEx```, or Regular Expression, is a search pattern used to check if a certain string contains the specified search pattern. 

You can use ```RegEx``` in python by importing the <strong>re</strong> module. 

There are several symbols in ```RegEx``` that have special meanings, and they are called <strong>Meta characters</strong>. Meta characters are used to define the search criteria and any text manipulation. Some of the examples are listed below:
| Meta Characters | Meaning |
|-----|-----|
| ^x | the character x comes at the beginning of the line |
| x$ | the character x comes at the end of the line |
| . | any single character |
| x+ | repeat the preceding character x one or more times |
| x* | repeat the preceding character x zero or more times |
| x\|y | either the character x or y comes |
| x? | the character x can exists or not exist |
| \b | indicates the word positioned between a word and a space (e.g. er\b matches "er" in "never ")|
| \d | indicates a digit character |
| \s | indicates a space | 
| \t | indicates a tab | 
| \w | indicates any word including underscore, i.e., a-z, A-Z, 0-9, and _ |

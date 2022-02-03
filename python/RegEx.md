# RegEx

```RegEx```, or Regular Expression, is a search pattern used to check if a certain string contains the specified search pattern. 

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

You can use ```RegEx``` in python by importing the <strong>re</strong> module. 

The <strong>re</strong> module provides several functions that allows us to match a certain string with the specified search pattern.
```python
import re 

p = re.compile('[a-z]+') # Regular Expression: repeat an alphabet from a to z 1 or more times

# match
m = p.match('python') 
print(m) # output: <re.Match object; span=(0, 6), match='python'> -> starting the match from index 0
print(m.group()) # output: python -> matched string
print(m.start()) # output: 0
print(m.end()) # output: 6
print(m.span()) # output: (0, 6)

m2 = p.match('3 python') 
print(m2) # output: None -> doesn't match because of 3 (non-alphabet)

# search
s = p.search('3 python') 

print(s) # output: <re.Match object; span=(2, 8), match='python'> -> match from index 2, even though non-alphabet is included in the string

# findall
f = p.findall('life is too short') 

print(f) # output: ['life', 'is', 'too', 'short'] -> list of strings that contain reg exp search pattern

# finditer
i = p.finditer('life is too short') # <callable_iterator object at 0x7fa397ba0eb0> -> iterable object

for r in i:
    print(r) # output: <re.Match object; span=(0, 4), match='life'>, <re.Match object; span=(5, 7), match='is'>, <re.Match object; span=(8, 11), match='too'>, <re.Match object; span=(12, 17), match='short'>
```

There are several options for ```re.compile()``` to extend its functionality:
1. <strong>DOTALL, S</strong>: allow '.' character to match with any character including newline '\n'
```python
# DOTALL, S
import re

p = re.compile('a.b', re.DOTALL) 
m = p.match('a\nb') 
print(m) # output: <re.Match object; span=(0, 3), match='a\nb'>
```
2. <strong>IGNORECASE, I</strong>: ignore uppercases/lowercases
```python
# IGNORECASE, I
import re

p = re.compile('[a-z]+', re.IGNORECASE)
print(p.match('python')) # output: <re.Match object; span=(0, 6), match='python'>
print(p.match('PyThon')) # output: <re.Match object; span=(0, 6), match='PyThon'> 
```
3. <strong>MULTILINE, M</strong>: check strings in next line whether they match the search pattern
```python
# MULTILINE, M
import re
p = re.compile("^python\s\w+", re.MULTILINE)

data = """python one
life is too short
python two
you need python
python three"""

print(p.findall(data)) # output: ['python one', 'python two', 'python three']
```

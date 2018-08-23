# Python  
  
## Libraries  
```python
import re  
```
  
## matching  
```python
re.search('Pattren', 'String')  
```

## Splitting 
```python 
'String'.split('Pattren')
```
## Replacement  
```python
str = "<20"  
output = re.sub(r'<(?=\d)', r'\r\n<', str)
output  
'\r\n<20'  
```  
## Grouping and Extracting 
```python
s = 'Hello from csev@umich.edu to cwen@iupui.edu about the meeting @2PM'  
lst = re.findall('\S+@\S+', s)  
lst  
['csev@umich.edu', 'cwen@iupui.edu']  
```
## group()
 A group() expression returns one or more subgroups of the match.     
 ```python
     >>> import re
     >>> m = re.match(r'(\w+)@(\w+)\.(\w+)','username@hackerrank.com')
     >>> m.group(0)       # The entire match 
     'username@hackerrank.com'
     >>> m.group(1)       # The first parenthesized subgroup.
     'username'
     >>> m.group(2)       # The second parenthesized subgroup.
     'hackerrank'
     >>> m.group(3)       # The third parenthesized subgroup.
     'com'
     >>> m.group(1,2,3)   # Multiple arguments give us a tuple.
     ('username', 'hackerrank', 'com')```
       
## groups()  
 A groups() expression returns a tuple containing all the subgroups of the match.   
```python 
      >>> import re
      >>> m = re.match(r'(\w+)@(\w+)\.(\w+)','username@hackerrank.com')
      >>> m.groups()
      ('username', 'hackerrank', 'com')   ```
      
 

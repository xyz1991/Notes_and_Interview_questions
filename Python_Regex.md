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

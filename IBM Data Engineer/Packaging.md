A package is a **collection of Python modules** [[Python]] into a dictionary with an init.py file, which distinguishes it from just a dictionary of Python scripts
- To create a package:
    - Create a folder with the package name
    - Create an empty __init__.py file
    - Create the required modules
    - In the __init__.py file, add code to reference the modules needed in the package
- You can verify the package via the bash terminal in a Python shell.
## Create package

```markdown-tree
lib
	__init__.py
	module1.py
	module2.py
```
You create a folder lib which store all module and using `__init__.py`  file to store a dictionary of module (It's **not necessary** to have the same folder, but it's recommend to same folder for easy maintenance and implementation)
- `__init__.py` 
```python
from . import module1
from . import module2
```
- `module1.py`
```python
def square(number):
    return number ** 2
    
def double(number):
    return number * 2
    
def add(a, b):
    return a + b
```
- `module2.py`
```python
def mean(numbers):
    return sum(numbers) / len(numbers)  # Return the mean value.
    
def median(numbers):
    numbers.sort()
    if len(numbers) % 2 == 0:
        median1 = numbers[len(numbers) // 2]  # The higher index of the two middle values.
        median2 = numbers[len(numbers) // 2 - 1]  # The lower index of the two middle values.
        mymedian = (median1 + median2) / 2  # Average of the two middle values.
    else:
        mymedian = numbers[len(numbers) // 2] 
    return mymedian
```
## Verify package
- Terminal
```
python3 
import lib 
exit()
```
## Using package

- When you create a file to run, you can import package name as a module (`import {foldername}`)
```python 
from lib.module1 import add, square
from lib.module2 import mean, median
```
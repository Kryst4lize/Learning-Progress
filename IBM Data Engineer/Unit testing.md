Unit testing is a method to validate if units of code are operating as designed. 
A unit is a smaller, testable part of an application 

In [[Python]], We can use built-in unittest package to control
Scenario : You have one module **functional.py** and you want to test those function can run well or not
- functional.py
```python
def double(number):
    return number * 2

def add(a,b=5):
    return a + b
```
- test.py:
```python
import unittest # To create unit tests for your code
from functional import add, double # import function from module we want to test

class TestDouble(unittest.TestCase): # This class inherit TestCase class of module
    # Define the first test method for the 'double' function.
    def test1(self):
    
		# test when 2 is given as input the output is 4.
        self.assertEqual(double(2), 4) 
        
		# test when -3.1 is given as input the output is -6.2.
        self.assertEqual(double(-3.1), -6.2) 
        
        # test when 0 is given as input the output is 0.

class TestAdd(unittest.TestCase):

    def test1(self):
    
		# test when 3,5 is given as input the output is 8.
        self.assertEqual(add(5,3),8)

		# test when 0,8 is given as input the output is 8.
        self.assertEqual(add(8,0),8)
	# Second test (may be your function have multiple usecase or different input)
    def test2(self):

        self.assertEqual(add(2),5) # Because b=3 in default, so you can use this 
							       #to test if 22 is given as input the output is 5

unittest.main()
```

- Run test : terminal
```
python test.py
```
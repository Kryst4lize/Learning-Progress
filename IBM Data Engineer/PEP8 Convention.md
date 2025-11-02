Best practices for coding as documented in the Python Enhancement Proposal (PEP8) style guide. You will learn about static code analysis, ensuring that your code adheres to the coding rules. Next, you will learn how to create and run unit tests. Finally, you will learn how to create, verify, and run Python packages. [Source](https://peps.python.org/pep-0008/)
# Static code analysis 
## Identation

- Use 4 spaces per indentation level. 
- The 4-space rule is optional for continuation lines.
Example:
```python
# Optional because it is continuation lines 
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

# Add 4 spaces (an extra level of indentation) to distinguish arguments from the rest.
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)

# Hanging indents should add a level.
foo = long_function_name(
    var_one, var_two,
    var_three, var_four)
```
- Spaces are the preferred indentation method. Tabs should be used solely to remain consistent with code that is already indented with tabs. Python **disallows mixing tabs and spaces for indentation**.
## Maximum Line Length
Limit all lines to a maximum of **79 characters.**
For flowing long blocks of text with fewer structural restrictions (docstrings or comments), the line length should be limited to 72 characters.
## Should a Line Break Before or After a Binary Operator?
```python
# Correct:
# easy to match operators with operands and more readable
income = (gross_wages
          + taxable_interest
          + (dividends - qualified_dividends)
          - ira_deduction
          - student_loan_interest)
```
## Blank Lines

Surround top-level function and class definitions with **two blank lines.**
Method definitions inside a class are surrounded by a **single blank line.**
Use blank lines in functions, sparingly, to indicate logical sections.
## Imports 
- Imports are always put at the top of the file, just after any module comments and docstrings, and before module globals and constants.
```python
# Correct:
import os
import sys
# Wrong:
import sys, os
# Correct:
from subprocess import Popen, PIPE
```
- Absolute imports are recommended, as they are usually more readable and tend to be better behaved (or at least give better error messages) if the import system is incorrectly configured
```python
import mypkg.sibling
from mypkg import sibling
from mypkg.sibling import example
```
## [Whitespace in Expressions and Statements](https://peps.python.org/pep-0008/#whitespace-in-expressions-and-statements)
Avoid extraneous whitespace in the following situations:
- Immediately inside parentheses, brackets or braces
```python
# Correct:
spam(ham[1], {eggs: 2})
# Wrong:
spam( ham[ 1 ], { eggs: 2 } )
```
- Between a trailing comma and a following close parenthesis
```python
# Correct:
foo = (0,)
# Wrong:
bar = (0, )
```
- Immediately before a comma, semicolon, or colon
```python
# Correct:
if x == 4: print(x, y); x, y = y, x
# Wrong:
if x == 4 : print(x , y) ; x , y = y , x
```
- However, in a slice the colon acts like a binary operator, and should have equal amounts on either side (treating it as the operator with the lowest priority). In an extended slice, both colons must have the same amount of spacing applied. Exception: when a slice parameter is omitted, the space is omitted:
```python
# Correct:
ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
ham[lower:upper], ham[lower:upper:], ham[lower::step]
ham[lower+offset : upper+offset]
ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
ham[lower + offset : upper + offset]
# Wrong:
ham[lower + offset:upper + offset]
ham[1: 9], ham[1 :9], ham[1:9 :3]
ham[lower : : step]
ham[ : upper]
```
- Immediately before the open parenthesis that starts the argument list of a function call and before the open parenthesis that starts an indexing or slicing:
```python
# Correct:
spam(1)
dct['key'] = lst[index]
# Wrong:
spam (1)
dct ['key'] = lst [index]
```
- More than one space around an assignment (or other) operator to align it with another
```python
# Correct:
x = 1
y = 2
long_variable = 3
# Wrong:
x             = 1
y             = 2
long_variable = 3
```
## Comments
### Inline 
### [Block Comments](https://peps.python.org/pep-0008/#block-comments)

Block comments generally apply to some (or all) code that follows them, and are indented to the same level as that code. Each line of a block comment starts with a `#` and a single space (unless it is indented text inside the comment).

Paragraphs inside a block comment are separated by a line containing a single
An inline comment is a comment on the same line as a statement. Inline comments should be separated by at least two spaces from the statement. They should start with a # and a single space.

Inline comments are unnecessary and in fact distracting if they state the obvious. Don’t do this:
```
False:
x = x + 1                 # Increment x
True: 
x = x + 1                 # Compensate for border
```
## Naming convention
-  Naming function using `Snake_slither
-  Function names should be lowercase, with words separated by  underscores as necessary to improve readability (`sly_snake`)
-  Variable names follow the same convention as function names.
-  Constant variable names using full uppercase (`A`)
-  Module names using lowercase (`lib`)
-  Always use `self` for the first argument to instance methods.
-  Always use `cls` for the first argument to class methods.
Example: 
```python
class Sample:
    def __init__(self, a):
        self.a = a
    def method(self):
        print(self.a) 
```
---
## How to practices 
- Using pylints package 
Terminal:
	Install: `!pip install pylint `
	Running to check : `!pylint {filename}.py`
Using in [VSCode](https://stackoverflow.com/questions/62473201/how-to-enable-pylint-in-vscode): 
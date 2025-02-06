# Find the Class
Update the following code so that instead of printing the values, each statement prints the name of the class to which it belongs.

```python
# Comments show expected output
print("Hello")                # <class 'str'>
print(5)                      # <class 'int'>
print([1, 2, 3])              # <class 'list'>
```
## Solution
```python
print(type("Hello"))
print(type(5))
print(type([1, 2, 3]))
```

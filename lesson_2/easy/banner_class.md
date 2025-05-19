# Banner Class

Behold this incomplete class for constructing boxed banners:

```python
class Banner:
    def __init__(self, message):
        pass

    def __str__(self):
        return "\n".join([self._horizontal_rule(),
                          self._empty_line(),
                          self._message_line(),
                          self._empty_line(),
                          self._horizontal_rule()])

    def _empty_line(self):
        pass

    def _horizontal_rule(self):
        pass

    def _message_line(self):
        return f"| {self.message} |"
```

Complete this class so that the test cases shown below work as intended. You are free to add any methods 
or instance variables you need. However, methods prefixed with an underscore are intended for internal use 
and should not be called externally.

You may assume that the input will always fit in your terminal window.

```python
# Comments show expected output

banner = Banner('To boldly go where no one has gone before.')
print(banner)
# +--------------------------------------------+
# |                                            |
# | To boldly go where no one has gone before. |
# |                                            |
# +--------------------------------------------+

banner = Banner('')
print(banner)
# +--+
# |  |
# |  |
# |  |
# +--+
```z
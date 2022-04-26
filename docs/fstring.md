## F-strings

Do you hate using `+` to put two strings together? Then this is your lucky day!

```py
>>> f"Hi! I'm a useless f-string."
"Hi! I'm a useless f-string."
>>> f"The {True}"
'The True'
>>> f'quick {float("3.14")}'
'quick 3.14'
>>> var = "hello"
>>> f"brown {var}"
'brown hello'
>>> f"fox {var!r}"
"fox 'hello'"
>>> f"jumps {var = }"
"jumps var = 'hello'"
>>> dct = {"well": "hello"}
>>> try:
...     # https://stackoverflow.com/a/63302121
...     # https://stackoverflow.com/a/61206080
...     # https://stackoverflow.com/a/60605169
...     f"over {dct["well"]} the"
... except SyntaxError:
...     "Oh no!"
'Oh no!'

```

### Other guides

- [https://datagy.io/python-f-strings/](https://datagy.io/python-f-strings/)
- [https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/)
- [https://realpython.com/python-f-strings/#f-strings-a-new-and-improved-way-to-format-strings-in-python](https://realpython.com/python-f-strings/#f-strings-a-new-and-improved-way-to-format-strings-in-python)
- [https://www.freecodecamp.org/news/python-f-strings-tutorial-how-to-use-f-strings-for-string-formatting/](https://www.freecodecamp.org/news/python-f-strings-tutorial-how-to-use-f-strings-for-string-formatting/)

- [Video: "Python f-strings can do more than you thought. f'{val=}', f'{val!r}', f'{dt:%Y-%m-%d}'"](https://youtu.be/BxUxX1Ku1EQ)
- [Video: "Using f-strings in Python to format output"](https://youtu.be/ptlQiNju11k)
- [Video: "Python Quick Tip: F-Strings - How to Use Them and Advanced String Formatting"](https://youtu.be/nghuHvKLhJA)

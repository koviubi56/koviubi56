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

### Recap

1. Make an f-string. `var = "fox"`. Print out `Hello quick brown fox` using an f-string (`fox` should be the variable `var`).
2. Make an f-string. `var = "fox"`. Print out `Hello quick brown 'fox'` using an f-string (`fox` should be the variable `var`).
3. Make an f-string. `my_dict = {"dog": "lazy"}`. Print out `The dog is lazy` using an f-string (`lazy` should be the `my_dict`'s `dog`).

The answers can be found [here](#recap-answers).

---

This is only here, so this text can hide the code below, which is the answer to the question.

- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below
- Spoiler below

---

#### Recap answers

```py
# ========== SPOILER ==========

# 1:
var = "fox"
print(f"Hello quick brown {var}")

# 2:
var = "fox"
print(f"Hello quick brown {var!r}")
#                          ~~~~~
#            Or you could just use `repr(var)`

# 3:
my_dict = {"dog": "lazy"}
print(f"The dog is {my_dict['dog']}")
# ----- OR -----
my_dict = {"dog": "lazy"}
print(f'The dog is {my_dict["dog"]}')
```

### Other guides

- [https://datagy.io/python-f-strings/](https://datagy.io/python-f-strings/)
- [https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/)
- [https://realpython.com/python-f-strings/#f-strings-a-new-and-improved-way-to-format-strings-in-python](https://realpython.com/python-f-strings/#f-strings-a-new-and-improved-way-to-format-strings-in-python)
- [https://www.freecodecamp.org/news/python-f-strings-tutorial-how-to-use-f-strings-for-string-formatting/](https://www.freecodecamp.org/news/python-f-strings-tutorial-how-to-use-f-strings-for-string-formatting/)

- [Video: "Python f-strings can do more than you thought. f'{val=}', f'{val!r}', f'{dt:%Y-%m-%d}'"](https://youtu.be/BxUxX1Ku1EQ)
- [Video: "Using f-strings in Python to format output"](https://youtu.be/ptlQiNju11k)
- [Video: "Python Quick Tip: F-Strings - How to Use Them and Advanced String Formatting"](https://youtu.be/nghuHvKLhJA)

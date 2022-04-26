## Arguments

### Normal arguments

Normal (default) arguments can be passed as _positional_ arguments, or _keyword_ arguments. The argument's name can be anything, it does not matter.

```py
>>> def func(normal_arg):
...     return normal_arg
>>> func(1)
1
>>> func(normal_arg=1)
1
>>> func("Hello, and welcome")
'Hello, and welcome'
>>> func(normal_arg="Hello, and welcome")
'Hello, and welcome'

```

### Positional only arguments (`/`)

_Positional only_ arguments are arguments that are _required_ to be passed as _positional_ arguments. The argument's name can be anything, it does not matter; the slash (`/`) **does** matter. It marks the arguments **_before it_** as _positional only_.

```py
>>> def func(pos_only_arg, /):
...     return pos_only_arg
>>> func(1)
1
>>> func(pos_only_arg=1)
Traceback (most recent call last):
TypeError: func() got some positional-only arguments passed as keyword arguments: 'pos_only_arg'

```

### Keyword only arguments (`*`)

_Keyword only_ arguments are arguments that are _required_ to be passed as _keyword_ arguments. The argument's name can be anything, it does not matter; the asterisk (`*`) **does** matter. It marks the arguments **_after it_** as _keyword only_.

```py
>>> def func(*, kw_only_arg):
...     return kw_only_arg
>>> func(kw_only_arg=1)
1
>>> func(1)
Traceback (most recent call last):
TypeError: func() takes 0 positional arguments but 1 was given

```

### Recap

1. Make a function. It should have an argument `a`, that can be passed in any way. The function should return the got argument. (`(a: T) -> T`)
2. Make a function. It should have an argument `b`, that must be passed as a keyword argument. The function should return the got argument. (`(b: T) -> T`)
3. Make a function. It should have an argument `c`, that must be passed as a positional argument. The function should return the got argument. (`(c: T) -> T`)

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
def func(a):
    return a

# 2:
def func(*, b):
    return b

# 3:
def func(c, /):
    return c
```

### Other guides

- [https://peps.python.org/pep-0570/](https://peps.python.org/pep-0570/)
- [https://www.geeksforgeeks.org/positional-only-parameter-in-python3-8/](https://www.geeksforgeeks.org/positional-only-parameter-in-python3-8/)
- [https://medium.com/analytics-vidhya/keyword-only-arguments-in-python-3c1c00051720](https://medium.com/analytics-vidhya/keyword-only-arguments-in-python-3c1c00051720)
- [https://peps.python.org/pep-0457/](https://peps.python.org/pep-0457/)
- [https://peps.python.org/pep-3102/](https://peps.python.org/pep-3102/)
- [https://stackoverflow.com/questions/14301967/bare-asterisk-in-function-arguments](https://stackoverflow.com/questions/14301967/bare-asterisk-in-function-arguments)
- [https://docs.python.org/3.11/glossary.html#term-argument](https://docs.python.org/3.11/glossary.html#term-argument)
- [https://www.sefidian.com/2021/06/18/positional-only-and-keyword-only-arguments-in-python/](https://www.sefidian.com/2021/06/18/positional-only-and-keyword-only-arguments-in-python/)

- [Video: "Positional-only and keyword-only arguments in Python"](https://youtu.be/R8-oAqCgHag)
- [Video: "Beginner Python Tutorial 92 - Positional Only Parameter"](https://youtu.be/asVVMewsuMk)
- [Video: "The asterisk (\*) operator in Python - Advanced Python 19 - Programming Tutorial"](https://youtu.be/M7daahMOMMc)

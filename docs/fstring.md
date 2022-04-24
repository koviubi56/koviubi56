## F-strings

Do you hate using `+` to put two strings together?
Then this is your lucky day!

```py
>>> f"Hi! I'm a useless f-string."
"Hi! I'm a useless f-string."
>>> f"The {True}"
'The True'
>>> f"quick {float("3.14")}"
'quick 3.14'
>>> var = "hello"
>>> f"brown {var}"
'brown hello'
>>> f"fox {var!r}"
"fox 'hello'"
>>> f"jumps {var = }"
"jumps var = 'hello'"
>>> dct = {"well": "hello"}
>>> #~         OK   OK      ~
>>> f"over {dct['well']} the"
'over hello the'
>>> #~          !    !      ~
>>> f"over {dct["well"]} the"
Traceback (most recent call last):
SyntaxError: f-string: unmatched '['

```

[Video: "Python f-strings can do more than you thought. f'{val=}', f'{val!r}', f'{dt:%Y-%m-%d}'"](https://youtu.be/BxUxX1Ku1EQ)

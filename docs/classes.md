## Classes

A class is basically a container for keys and values, and it has some methods.

To make an instance of a class (an object) just type `NameOfTheClass()`, so you call the class like a function. This will return an instance, you should assign it to a variable, so you can use it later.

```py
>>> instance = bool()
>>> instance
False

```

### Make a class

```py
>>> class MyClass:
...     pass

>>> instance = MyClass()
>>> isinstance(instance, MyClass)
True

```

### `__init__`

With the `__init__` method you can initialize the instance.
Please note, that `__init__` does **not** _create_ the instance!
`__init__` must return `None` (or should not return).

```py
>>> class MyClass:
...     def __init__(self):
...         self.instance_variable = 56

>>> var = MyClass()
>>> isinstance(var, MyClass)
True
>>> var.instance_variable
56
>>> var.instance_variable = "Something new"
>>> var.instance_variable
'Something new'

```

[Video: "Defining \_\_init\_\_"](https://youtu.be/AjYOMk-4NIU)

### `__new__`

With the `__new__` method you can create an instance of a class.
Unless you absolutely need it, use `__init__` instead!

```py
>>> class MyFirstClass:
...     def __new__(cls):
...         # The argument cls would be MyFirstClass
...
...         # All classes (including this one) inherits from object.
...         # object already has a __new__ method, so we can just call it with super.
...         # super (in most cases) returns the class above this class.
...         # Since we didn't specify a parent class, super returns object.
...         return super().__new__(cls)

>>> first_inst = MyFirstClass()
>>> isinstance(first_inst, MyFirstClass)
True

>>> class MySecondClass:
...     def __new__(cls):
...         # But __new__ can return anything.
...         return 42
>>> second_inst = MySecondClass()
>>> second_inst
42
>>> isinstance(second_inst, MySecondClass)
False

```

[Video: "\_\_new\_\_ vs \_\_init\_\_ in Python"](https://youtu.be/-zsV0_QrfTw)

### Class variables for dataclasses

To make class variables with dataclasses, mark it with `typing.ClassVar`.

```py
>>> import typing
>>> import dataclasses
>>> @dataclasses.dataclass
... class MyClass:
...     classvar: typing.ClassVar[float] = 3.14
...     arg: bool
>>> inst = MyClass(False)
>>> isinstance(inst, MyClass)
True
>>> inst.classvar
3.14
>>> inst.arg
False
>>> MyClass.classvar
3.14
>>> MyClass.arg
Traceback (most recent call last):
AttributeError: type object 'MyClass' has no attribute 'arg'

```

# Python Style Guidelines

## Abstract

Since we make free and open-source software (FOSS), we accept contributions from people across the world. Everyone has their way of writing code. But the code should be consistent.

## Specification

### Requirements

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in BCP 14 [RFC2119] [RFC8174] when, and only when, they appear in all capitals, as shown here.

The guidelines stated here should only be used if it is reasonable, and it isn't required/noted otherwise.

### The Guidelines

- The code MUST follow [PEP 8](https://peps.python.org/pep-0008/). Some additional stuff to PEP 8:
  - If you cannot break a line, try to use a backslash (`\`)
  - All text files SHALL be encoded in UTF-8. Source code files SHOULD only consist of the printable ASCII character (from 30 (0x20) to 126 (0x7E) inclusive).
  - Except for one-line ones, docstring MUST have a new line after the opening, and before the closing([example](https://github.com/sco1/flake8-annotations/blob/7e44ba73866e92fcce8d1c9ca082ffaabec99d9c/flake8_annotations/checker.py#L53-L58)). (This is permitted by [PEP 257](https://archive.ph/kY0Hw#selection-615.313-615.399).)
  - The project's formatting utility SHALL be used before committing. See [Lemming](https://github.com/koviubi56/lemming)'s `format` subcommand.

- Double-quotes MUST be used. If double-quotes are already in the string, single-quotes SHOULD be used; escaping (`\"`) is OPTIONAL.

- Semi-colons in code MUST NOT be used (unless for [timeit](https://docs.python.org/3/library/timeit.html) codes).

- Logging SHOULD be done with [mylog](https://github.com/koviubi56/mylog).

- Exceptions SHOULD NOT inherit directly from `BaseException`.

- There SHOULD be reasonable effort made for backwards and forward compatibility.

- Properties SHOULD NOT have setters. Try changing them to an instance variable, or make a `set_*` method for it.

- "Hiding" important function calls within if and other statements is NOT RECOMMENDED:

  ```python
  if run_important_thing() == 0:
      ...
  ```

- `is` and `is not` MUST be used for [real constants](https://docs.python.org/3/library/constants.html#built-in-constants), classes, and singletons, and they MUST NOT be used for literals (str, int, float, ...).

- Instead of doing this: `MISSING = object()`, it SHOULD be like this:

  ```python
  class _Missing:
      pass  # the class MAY be a dataclass or MAY have a __repr__
  
  Missing = _Missing()
  ```

- "Just container" classes SHOULD use [dataclasses](https://docs.python.org/3/library/dataclasses.html).

- Properties MUST be kept short, they MUST NOT do expensive calculations.

- About I/O:
  - For paths `pathlib.Path` and [its methods](https://docs.python.org/3/library/pathlib.html) SHOULD be used.

  - If a function allows it and reasonable, the file descriptors SHALL be passed instead of the contents. For example:

  ```py
  with open("some_file.json", "rb") as file:
      #                         ^ see next point for why this is binary
      json.load(file)
  ```

  - If a function allows it and reasonable, binary I/O SHALL be used instead of string. For example:

  ```py
  #                             v
  with open("some_file.json", "rb") as file:
      # json.loads() allows bytes, so use that instead of strings
      json.loads(file.read())
  # NOTE: This example is only used to demonstrate the point.
  #       This example does not follow this guide!
  #       See the previous example for code that follows this guide!
  ```

  - For encodings utf-8 MUST be used. The encoding argument MUST be explicitly passed as a keyword argument (`encoding=`), and it MUST be written as `"utf-8"` (all lowercase).

- f-strings SHOULD be used instead of `"{}".format()`, `"" + x + ""`, and `"%s" % str`. Percent formatting `"%s"` MUST NOT be used. In f-strings `{x!r}` (and others) SHOULD be used instead of `{repr(x)}`.

- Too broad `except`s SHOULD NOT be used, unless reasonable (because there are situations where you _do_ need it).

- The code SHOULD have comments. Older codes that don't have enough/good comments SHOULD be updated, but

  > Comments that contradict the code are worse than no comments.

- The code should be in a logical order, where the basic stuff are at the beginning, and the more advanced things that use the basic things are defined later. For example:

  ```py
  class Level:
      DEBUG = 10
      ...
  
  class LogEvent:
      level: Level
      ...
  
  class Logger:
      ...
      def format_message(self, event: LogEvent):
          ...
      ...
  ```

#### Docstrings

- The [Google docstring style](https://www.sphinx-doc.org/en/master/usage/extensions/example_google.html) MUST be used, BUT:
  - There MUST be a new line after the opening triple-quotes.
  - Module/Package/Class level docstrings' "Attributes" section is OPTIONAL
  - Docstrings SHOULD NOT have a Todo(s) section.
  - reStructuredText or anything like that MUST NOT be used (instead use markdown).
  - Examples (doctests) MUST be placed after the main description, and before the arguments (but doctests are OPTIONAL).
  - Argument types in docstrings MUST reflect the type hints (so `:obj:int` and `list(str)` MUST NOT be used, `list[str]` MUST be used instead).
  - Argument types in docstrings MUST have `, optional` before the `)` if they are optional, and they MUST have `Defaults to x.` at the end.
  - Properties' and special/magic methods' docstrings MUST be the same as if they were a normal regular function.
  - `self` MUST NOT be included in `Args`.
- Every function SHOULD have a docstring, and they MAY have a doctest. Docstrings for functions that starts with an underscore (e.g. `_private`, `__really_private`, `__magic__`) is OPTIONAL.

#### Type hinting

- Type hints MUST be used for function arguments, function return values, and other places where reasonable.
- Type hints for local and/or private variables are OPTIONAL.
- The generics MUST be provided when using generic types (`list[str]`, `dict[str, int]`, ...).
- `typing` generics (`typing.List`) SHOULD NOT be used. Instead, the normal ones (`list`) SHOULD be used.
- The `if TYPE_CHECKING: import` style([example](https://github.com/pydantic/pydantic/blob/5dd9b4f5ca5715ed2bd65378201473b45c419c89/pydantic/main.py#L74-L91)) MUST NOT be used. Additionally only type hinting something when `TYPE_CHECKING` is True([example](https://github.com/pydantic/pydantic/blob/5dd9b4f5ca5715ed2bd65378201473b45c419c89/pydantic/main.py#L312-L327)) MUST NOT be used either.
- If possible, most of the type hinting stuff imported from `typing` SHOULD be moved to `typing_extensions` for compatibility, _unless_ the object being imported is already in `typing` on the oldest supported python version.
- `collections.abc` SHOULD be used instead of `typing` for objects that are in both.

## Copyright

This document has been placed in the public domain.

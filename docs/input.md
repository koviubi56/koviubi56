## input()

The built-in function `input()` returns a **_string_** of what the user typed into the terminal, until the user presses return (enter). The new line (`\n`) is stripped.

```py
ans = input("What is your name? ")
# Output (without quotes): "What is your name? "
# The user types in: "J" "o" "e" [return (enter)]
print(ans)
# "Joe"
# The `\n` is stripped.
```

### Input ain't int

```py
# INCORRECT
ans = input("How old are you? ")
if ans < 18:  # !!!!! ERROR: TypeError: '<' not supported between instances of 'str' and 'int'>
    print("no")
if ans == 0:  # Will never work
    print("no")

# Instead, do this:
# Convert str (text) to int (number)
#     ~~~~
ans = int(input("How old are you? "))
#         ~~~~~~~~~~~~~~~~~~~~~~~~~~
#               Get str (text)
if ans < 18:  # OK
    print("no")
if ans == 0:  # OK
    print("no")
```

### How do I print out the answer?

```py
input("What is your name? ")
# Oh no! How can I print out the name?? Help!

# Assign it to a variable
#    ~
name = input("What is your name? ")
print(name)
#     ~~~~
# Print the variable (the name)
```

### Other guides

- [https://www.w3schools.com/python/python_user_input.asp](https://www.w3schools.com/python/python_user_input.asp)
- [https://www.pythonforbeginners.com/basics/how-to-take-user-input-in-python](https://www.pythonforbeginners.com/basics/how-to-take-user-input-in-python)
- [https://pynative.com/python-input-function-get-user-input/](https://pynative.com/python-input-function-get-user-input/)
- [https://www.educba.com/python-user-input/](https://www.educba.com/python-user-input/)
- [https://www.tutorialspoint.com/python-get-a-list-as-input-from-user](https://www.tutorialspoint.com/python-get-a-list-as-input-from-user)

- [Video: "How to get Users input in Python"](https://youtu.be/1344J3t1by0?t=131)
- [Video: "Getting Input From Users | Python | Tutorial 8"](https://youtu.be/1gEZi0uJ3sw)
- [Video: "4 - Python and Getting User Input"](https://youtu.be/zWtFRd4dA_Y)

## input()

The built-in function `input()` returns a **_string_** of what the user typed into the terminal, until the user presses return (enter).
The new line (`\n`) is stripped.

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

# Instead, do this:
# Convert str (text) to int (number)
#     ~~~~
ans = int(input("How old are you? "))
#         ~~~~~~~~~~~~~~~~~~~~~~~~~~
#               Get str (text)
if ans < 18:  # OK
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

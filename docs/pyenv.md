## Problems with imports, environments

<style>
hr {
    height: 2em;
    margin: 5em;
}
</style>

_After you're done, **please** give us some [feedback](#feedback). It would **really** help us make this website better for everyone._

Note: **Do not** download python from the Microsoft Store! If you try to do this anyway, I guarantee you will be in a world of hurt. Instead, download it from the [official site](https://python.org)!

The good old problem. First what happened/what do you see? _(please click)_

[![Pylance gave me an error](/assets/pyenv-pylance.png)](#pylance)

Or

[ModuleNotFoundError](#is-relative)

_If you got an exception other than `ModuleNotFoundError` this page might not help._

---

### Pylance

First, make sure you installed the package. After installing it, reload VS Code (`Developer: Reload window`). If you did everything right, the message should have disappeared. If it did not, follow the instructions [here](#selectenv-vscode).

---

### Is relative

Is the file that you are trying to import next to the file you try to import it from ("relative import")? _(please click)_

<a href="#relative"><img src="/koviubi56/assets/yes.png" alt="Yes, it is!" style="width: 5em;"></a>
<a href="#did-you-install"><img src="/koviubi56/assets/no.png" alt="No, it is not!" style="width: 5em;"></a>
<a href="#help-relative"><img src="/koviubi56/assets/what.png" alt="What? I don't get it." style="width: 5em;"></a>

---

#### Help relative

Yes:

```py
# |-- file1.py
# |-- file2.py

# file1.py
import file2
# This IS a relative import (yes)

# file2.py
something = "This does not matter"
```

No:

```py
import numpy
# This is NOT a relative import (no)
```

If you now know it, click [here](#is-relative)!

If you still don't get it, please, [give us your feedback](#feedback)!

---

### Relative

Try this: [https://stackoverflow.com/a/43859946](https://stackoverflow.com/a/43859946).
If it doesn't work try this: [https://youtu.be/hgCVIa5qQhM](https://youtu.be/hgCVIa5qQhM).

The guide is over. Bye!

---

### Did you install

Did you [install the package](/koviubi56/package#no)? _(please click)_

<a href="#modulenotfounderror"><img src="/koviubi56/assets/yes.png" alt="Yes, I did!" style="width: 5em;"></a>
<a href="/koviubi56/package#no"><img src="/koviubi56/assets/no.png" alt="No, I did not!" style="width: 5em;"></a>

---

### ModuleNotFoundError

The most common error, is that the package is installed, _in the wrong environment_.

Open up the terminal _([Need more help with Windows?](#win-terminal))_.

If you're on Windows, run `py -3 -m pip install PACKAGE`, otherwise `python3 -m pip install PACKAGE`.

For example (if you're on Windows): `py -3 -m pip install pygame`

Now, run your code _still in the terminal_

If you're on Windows, run `py FILE.py`, otherwise `python3 FILE.py`.

For example (if you're on Windows): `py -3 main.py`.

Did it work as expected? _(please click)_

<a href="#yes"><img src="/koviubi56/assets/yes.png" alt="Yes, it did!" style="width: 5em;"></a>
<a href="#no"><img src="/koviubi56/assets/no.png" alt="No, it did not!" style="width: 5em;"></a>

#### Yes

Well done! If you tried to run it in your text editor, and it did not work, make sure that it is set to the right environment _([Need more help with VS Code?](#selectenv-vscode))_.

#### No

Hmm... interesting. You should check out [our guide for installing packages](/koviubi56/package#no). It might help. We would also appreciate if you would [give feedback](#feedback)!

---

### Win terminal

We assume you have Windows 7 or above. Click on the Windows icon in the left corner. In the start menu, search for `cmd.exe`. Run it. Yayy, you opened the terminal!

![Windows Icon](/assets/pyenv-winterminal-winicon.png)

![Search for "cmd.exe"](/assets/pyenv-winterminal-search.png)

![Click on "cmd.exe"](/assets/pyenv-winterminal-searchcmd.png)

![Yayy!](/assets/pyenv-winterminal-terminal.jpg)

[Go back](#modulenotfounderror)

---

### Selectenv VSCode

First, get the version of python.

If you're on Windows, run `py -VV`, otherwise `python3 -VV` (or you can also run `pip -V`). Remember what it says.

Now, open up a python file (in VS Code). Click on the _Select interpreter_ button, in the corner in the status bar.

Now select the interpreter that is the closest to the one that python said above in the terminal. If you're in a _virtual environment (venv)_, ensure that you selected that!

And the warning should have disappeared. If not, continue [here](#modulenotfounderror).

#### Windows

![Type in "py -VV"](/assets/pyenv-vscode-winpyver.png)

![Click on "Select interpreter"](/assets/pyenv-vscode-interpreter.png)

![Select the closest one](/assets/pyenv-vscode-winforme.png)

#### Other

I used Ubuntu (WSL).

![Type in "python3 -VV"](/assets/pyenv-vscode-ubuntupyver.png)

![Click on "Select interpreter"](/assets/pyenv-vscode-interpreter.png)

![Select the closest one](/assets/pyenv-vscode-ubuntuforme.png)

---

### Feedback

Thank you very much! You can give us your feedback [by creating an issue](https://github.com/koviubi56/koviubi56/issues)!

---

### Other great guides

- [pip python mismatch](https://gist.github.com/n0Oo0Oo0b/8c12660aa08cb77bae00e8b043b76b5d)
  
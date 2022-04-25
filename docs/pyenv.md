## Problems with imports, environemts

_After you're done, **please** give us some [feedback](https://cryptpad.fr/form/#/2/form/view/I6nKlsw+0HPdRsPLjiMs6Hd58P227Y8Tlw1td74myNs/). It would **really** help us make this website better for everyone._

The good old problem. First what happened/what do you see? _(please click)_

[![Pylance gave me an error](/assets/pyenv-pylance.png)](#pylance)

Or

[ModuleNotFoundError](#is-relative)

_If you got an exception other than `ModuleNotFoundError` this page probably will **not** help._

---

### Pylance

First, make sure you installed the package. After installing it, reload VS Code (`workbench.action.reloadWindow`).
If you did everything right, the message should have disappeared. If it did not, follow the instructions [below](#modulenotfounderror).

---

### Is relative

Is the file that you are trying to import next to the file you try to import it from ("relative import")? _(please click)_

<a href="#relative"><img src="/koviubi56/assets/yes.png" alt="Yes, it is!" style="width: 5em;"></a>
<a href="#did-you-install"><img src="/koviubi56/assets/no.png" alt="No, it is not!" style="width: 5em;"></a>

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
# |-- file.py

# file.py
import numpy
# This is NOT a relative import (no)
```

---

### Relative

Refer to: https://stackoverflow.com/a/43859946

The guide is over. Bye!

---

### Did you install

Did you [install the package](/koviubi56/package)? _(please click)_

<a href="#modulenotfounderror"><img src="/koviubi56/assets/yes.png" alt="Yes, I did!" style="width: 5em;"></a>
<a href="/koviubi56/package"><img src="/koviubi56/assets/no.png" alt="No, I did not!" style="width: 5em;"></a>

---

### ModuleNotFoundError

The most common error, is that the package is installed, _in the wrong environment_.

Open up the terminal _([Need more help with Windows?](#win-terminal))_.

If you're on Windows, run `py -3 -m pip install <packagename>`, otherwise `python3 -m pip install <packagename>`. Of course, **replace `<packagename>` with the package's name** (without the `<>`)!

For example (if you're on Windows): `py -3 -m pip install pygame`

Now, run your code _still in the terminal_

If you're on Windows, run `py -3 <file>`, otherwise `python3 -m pip install <file>`. Of course, **replace `<file>` with the path to your code** (without the `<>`)!

For example (if you're on Windows): `py -3 main.py`.

Did it work as expected? _(please click)_

<a href="#yes"><img src="/koviubi56/assets/yes.png" alt="Yes, it did!" style="width: 5em;"></a>
<a href="#no"><img src="/koviubi56/assets/no.png" alt="No, it did not!" style="width: 5em;"></a>

#### Yes

Well done! If you tried to run it in your text editor, and it did not work, make sure that it is set to the right environment _([Need more help with VS Code?](#selectenv-vscode))_.

#### No

Hmm... interesting. You should check out [our guide for installing packages](/koviubi56/package). It might help.

---

### Win terminal

We assume you have Windows 7 or above. Click on the Windows icon in the left corner. In the start menu, search for `cmd.exe`.
Run it. Yayy, you opened the terminal!

![Windows Icon](/assets/pyenv-winterminal-winicon.png)

![Search for "cmd.exe"](/assets/pyenv-winterminal-search.png)

![Click on "cmd.exe"](/assets/pyenv-winterminal-searchcmd.png)

![Yayy!](/assets/pyenv-winterminal-terminal.jpg)

[Go back](#modulenotfounderror)

---

### Selectenv VSCode

First, get the version of python.

If you're on Windows, run `py -3 -VV`, otherwise `python3 -VV`. Remember what it says.

Now, open up a python file (in VS Code). Click on the _Select interpreter_ button, in the corner in the status bar.

Now select the interpreter that is the colsest to the one that python said above in the terminal.

#### Windows

![Type in "py -3 -VV"](/assets/pyenv-vscode-winpyver.png)

![Click on "Select interpreter"](/assets/pyenv-vscode-interpreter.png)

![Select the closest one](/assets/pyenv-vscode-winforme.png)

#### Other

I used Ubuntu (WSL).

![Type in "python3 -VV"](/assets/pyenv-vscode-ubuntupyver.png)

![Click on "Select interpreter"](/assets/pyenv-vscode-interpreter.png)

![Select the closest one](/assets/pyenv-vscode-ubuntuforme.png)

---

### Other guides

- https://www.pythonpip.com/python-tutorials/how-to-solve-modulenotfounderror-in-python/
- https://careerkarma.com/blog/python-modulenotfounderror/

# pip and installing packages

Did you get a `ModuleNotFoundError`? _(please click)_

<a href="/koviubi56/pyenv"><img src="/koviubi56/assets/yes.png" alt="Yes, I did!" style="width: 5em;"></a>
<a href="#no"><img src="/koviubi56/assets/no.png" alt="No, I did not!" style="width: 5em;"></a>

---

## No

Great. First, make sure python is installed, with this command: `py --version` if you're on Windows, `python3 --version` otherwise (run the command in a shell/terminal/consol).

What do you see? _(please click)_

[![I see "Pyton X.Y.Z"](/assets/package-pyver.png)](#pyver)

[![I see "Command not found"](/assets/package-notfound1.png)](#notfound)

[`[Clickable] NameError: name 'python' is not defined`](#nameerror)

---

### NameError

You got this, beacuse this command and other suggested commands in this tutorial are intended to be run in a _shell_ (also called a terminal or console). See the Python for Beginners [getting started tutorial](https://opentechschool.github.io/python-beginners/en/getting_started.html#what-is-python-exactly) for an introduction to using your operating system's shell and interacting with Python.

If you're done, [start again](#).

---

### NotFound

If you're on Windows, make sure that you wrote `py --version`.
If you're _**not**_ on Windows, make sure that you wrote `python3 --version`.

If you _still_ get an error, try to install python from [python.org](https://www.python.org/) or refer to the [Installing Python](https://docs.python-guide.org/starting/installation/#installation) section of the Hitchhiker’s Guide to Python.

If you're done, [start again](#).

---

### Pyver

Super! Now check if you have pip installed. If you're on Windows, run `py -m pip --version`, `python3 -m pip --version` otherwise.

If you got something like `pip X.Y.Z from path/to/pip (python x.y)` click [here](#gotpip).

If not, install pip.
On Windows: `py -m ensurepip --default-pip`
Everywhere else: `python3 -m ensurepip --default-pip`

**If** you got an error, download [`get-pip.py`](https://bootstrap.pypa.io/get-pip.py), and run it. [Warning!](#getpip-warning)

Then [try again](#pyver).

---

### Gotpip

Great! Now make sure that pip, setuptools, and wheel is up-to-date.
On Windows: `py -m pip install --upgrade pip setuptools wheel`
Everywhere else: `python3 -m pip install --upgrade pip setuptools wheel`

It is _optional_, but you can use a [virtual environment](https://packaging.python.org/en/latest/tutorials/installing-packages/#optionally-create-a-virtual-environment), but it is **optional**, not required.

Now you just need to install the package. Click [here](#final) for the final step.

---

### Final

What do you want? _(please click)_

- [Install the latest version](#install-latest)
- [Install a specific version](#install-specific)
- [Upgrade a package](#install-upgrade)
- [Install from a `requirements.txt` file](#install-file)
- [Install from a VSC (for example git(hub))](#install-vsc)
- [Install a package from a local src tree](#install-local)

Advanced stuff:
- [Installing from local archives](https://packaging.python.org/en/latest/tutorials/installing-packages/#installing-from-local-archives)
- [Installing from other sources](https://packaging.python.org/en/latest/tutorials/installing-packages/#installing-from-other-sources)
- [Installing Prereleases](https://packaging.python.org/en/latest/tutorials/installing-packages/#installing-prereleases)
- [Installing Setuptools "Extras"](https://packaging.python.org/en/latest/tutorials/installing-packages/#installing-setuptools-extras)

---

#### Install latest

On Windows: `py -m pip install "<packagename>"`
Everywhere else: `python3 -m pip install "<packagename>"`
**Of course, replace `<packagename>` with the package's name!** (Without the `<>`; the quotes are recommended)

And you are done! Have a good day!

---

#### Install specific

On Windows: `py -m pip install "<packagename>==<version>"`
Everywhere else: `python3 -m pip install "<packagename>==<version>"`
**Of course, replace `<packagename>` with the package's name, and `<version>` with the version you want to install!** (Without the `<>`; the quotes are recommended)

And you are done! Have a nice day!

---

#### Install upgrade

On Windows: `py -m pip install --upgrade <packagename>`
Everywhere else: `python3 -m pip install --upgrade <packagename>`
**Of course, replace `<packagename>` with the package's name!** (Without the `<>`)

And you are done! Have a wonderful day!

---

#### Install file

_If the file isn't named `requirements.txt`, then replave `requirements.txt` in the commands with the file's name!_

On Windows: `py -m pip install -r requirements.txt`
Everywhere else: `python3 -m pip install -r requirements.txt`

And you are done! Have a lovely day!

---

#### Install VSC

**Please make sure to replace the URLs, with the ones that you want.**

For more information click [here]().

On Windows:
```text
py -m pip install -e git+https://git.repo/some_pkg.git#egg=SomeProject          # from git
py -m pip install -e hg+https://hg.repo/some_pkg#egg=SomeProject                # from mercurial
py -m pip install -e svn+svn://svn.repo/some_pkg/trunk/#egg=SomeProject         # from svn
py -m pip install -e git+https://git.repo/some_pkg.git@feature#egg=SomeProject  # from a branch
```
Everywhere else:
```text
python3 -m pip install -e git+https://git.repo/some_pkg.git#egg=SomeProject          # from git
python3 -m pip install -e hg+https://hg.repo/some_pkg#egg=SomeProject                # from mercurial
python3 -m pip install -e svn+svn://svn.repo/some_pkg/trunk/#egg=SomeProject         # from svn
python3 -m pip install -e git+https://git.repo/some_pkg.git@feature#egg=SomeProject  # from a branch
```

And you are done! Have a good one!

---

#### Install local

Go (change the working directory) to the root folder, that contains the `setup.py` file.

On Windows: `py -m pip install -e .`
Everywhere else: `python3 -m pip install -e .`

_If you do **not** want to install it in editale mode, remove the `-e`._

And you are done! Goodbye!

---

### getpip warning

**Warning**: Be cautious if you’re using a Python install that’s managed by your operating system or another package manager. get-pip.py does not coordinate with those tools, and may leave your system in an inconsistent state. You can use `python get-pip.py --prefix=/usr/local/` to install in `/usr/local` which is designed for locally-installed software. 

**Warning**: Make sure to download `get-pip.py` **securely**. So with a modern webbrowser, or with curl. The SSL certificates should be verified.

**Warning**: Using `get-pip.py` may require root or administrator privileges.

[Go back](#pyver)
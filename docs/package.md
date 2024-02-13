## pip and installing packages

<style>
hr {
    height: 2em;
    margin: 5em;
}
</style>

_After you're done, **please** give us some [feedback](#feedback). It would **really** help us make this website better for everyone._

Note: **Do not** download python from the Microsoft Store! If you try to do this anyway, I guarantee you will be in a world of hurt. Instead, download it from the [official site](https://python.org)!

Did you get a `ModuleNotFoundError`? _(please click)_

<a href="/koviubi56/pyenv#is-relative"><img src="/koviubi56/assets/yes.png" alt="Yes, I did!" style="width: 5em;"></a>
<a href="#no"><img src="/koviubi56/assets/no.png" alt="No, I did not!" style="width: 5em;"></a>

---

## No

Great. First, make sure python is installed, with this command: `py --version` if you're on Windows, `python3 --version` otherwise (run the command in a shell/terminal/console).

What do you see? _(please click)_

[![I see "Python X.Y.Z"](/assets/package-pyver.png)](#pyver),

[![I see "Command not found"](/assets/package-notfound1.png)](#notfound), or

[`"NameError: name 'python' is not defined"`](#nameerror)

---

### NameError

You got this, because this command and other suggested commands in this tutorial are intended to be run in a _shell_ (also called a terminal or console). See the Python for Beginners [getting started tutorial](https://opentechschool.github.io/python-beginners/en/getting_started.html#what-is-python-exactly) for an introduction to using your operating system's shell and interacting with Python.

If you're done, [start again](#no).

---

### NotFound

If you're on Windows, make sure that you wrote `py --version`. If you're _**not**_ on Windows, make sure that you wrote `python3 --version`.

If you _still_ get an error, try to install python from [python.org](https://www.python.org/) or refer to the [Installing Python](https://docs.python-guide.org/starting/installation/#installation) section of the Hitchhiker's Guide to Python.

If you're done, [start again](#no).

---

### Pyver

Super! Now check if you have pip installed. If you're on Windows, run `py -m pip --version`, otherwise run `python3 -m pip --version`.

Did you get something like `pip X.Y.Z from path/to/pip (python x.y)`? _(please click)_

<a href="#gotpip"><img src="/koviubi56/assets/yes.png" alt="Yes, I did!" style="width: 5em;"></a>
<a href="#no-pip"><img src="/koviubi56/assets/no.png" alt="No, I did not!" style="width: 5em;"></a>

---

### No pip

On Windows run: `py -m ensurepip --default-pip` Everywhere else run: `python3 -m ensurepip --default-pip`

Did you get an error? _(please click)_

<a href="#no-pip-error"><img src="/koviubi56/assets/yes.png" alt="Yes, I did!" style="width: 5em;"></a>
<a href="#pyver"><img src="/koviubi56/assets/no.png" alt="No, I did not!" style="width: 5em;"></a>

### No pip error

**If** you got an error, download `get-pip.py` [from here](https://bootstrap.pypa.io/get-pip.py), and run it. [Warning!](#getpip-warning)

Did you get an error? _(please click)_

<a href="#no-pip-error-feedback"><img src="/koviubi56/assets/yes.png" alt="Yes, I did!" style="width: 5em;"></a>
<a href="#pyver"><img src="/koviubi56/assets/no.png" alt="No, I did not!" style="width: 5em;"></a>

---

### No pip error feedback

If you got an error while running `get-pip.py`, click [here](#feedback), and we'll try to make this guide better.

---

### Gotpip

Great! Now make sure that pip, setuptools, and wheel is up-to-date. On Windows run: `py -m pip install --upgrade pip setuptools wheel` Everywhere else run: `python3 -m pip install --upgrade pip setuptools wheel`

It is _optional_, but you can use a [virtual environment](https://packaging.python.org/en/latest/tutorials/installing-packages/#optionally-create-a-virtual-environment).

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

[You didn't find the thing you are looking for?](#feedback)

---

#### Install latest

On Windows run: `py -m pip install "PACKAGE"` Everywhere else run: `python3 -m pip install "PACKAGE"`

And you are done! Have a good day! Could you please [give us your feedback](#feedback)?

---

#### Install specific

On Windows run: `py -m pip install "PACKAGE==VERSION"` Everywhere else run: `python3 -m pip install "PACKAGE==VERSION"`

And you are done! Have a nice day! Could you please [give us your feedback](#feedback)?

---

#### Install upgrade

On Windows run: `py -m pip install --upgrade PACKAGE` Everywhere else run: `python3 -m pip install --upgrade PACKAGE`

And you are done! Have a wonderful day! Could you please [give us your feedback](#feedback)?

---

#### Install file

_If the file isn't named `requirements.txt`, then replace `requirements.txt` in the commands with the file's name!_

On Windows run: `py -m pip install -r requirements.txt` Everywhere else run: `python3 -m pip install -r requirements.txt`

And you are done! Have a lovely day! Could you please [give us your feedback](#feedback)?

---

#### Install VSC

**Please make sure to replace the URLs, with the ones that you want.**

For more information click [here](https://packaging.python.org/en/latest/tutorials/installing-packages/#installing-from-vcs).

On Windows run:

```text
py -m pip install -e git+https://git.repo/some_pkg.git#egg=SomeProject          # from git
py -m pip install -e hg+https://hg.repo/some_pkg#egg=SomeProject                # from mercurial
py -m pip install -e svn+svn://svn.repo/some_pkg/trunk/#egg=SomeProject         # from svn
py -m pip install -e git+https://git.repo/some_pkg.git@feature#egg=SomeProject  # from a branch
```

Everywhere else run:

```text
python3 -m pip install -e git+https://git.repo/some_pkg.git#egg=SomeProject          # from git
python3 -m pip install -e hg+https://hg.repo/some_pkg#egg=SomeProject                # from mercurial
python3 -m pip install -e svn+svn://svn.repo/some_pkg/trunk/#egg=SomeProject         # from svn
python3 -m pip install -e git+https://git.repo/some_pkg.git@feature#egg=SomeProject  # from a branch
```

And you are done! Have a good one! Could you please [give us your feedback](#feedback)?

---

#### Install local

Go (change the working directory) to the root folder, that contains the `setup.py` file.

On Windows run: `py -m pip install -e .` Everywhere else run: `python3 -m pip install -e .`

_If you do **not** want to install it in editable mode, remove the `-e`._

And you are done! Goodbye! Could you please [give us your feedback](#feedback)?

---

### getpip warning

**Warning**: Be cautious if you're using a Python install that's managed by your operating system or another package manager. get-pip.py does not coordinate with those tools, and may leave your system in an inconsistent state. You can use `python get-pip.py --prefix=/usr/local/` to install in `/usr/local` which is designed for locally-installed software.

**Warning**: Make sure to download `get-pip.py` **securely**. So with a modern web browser, or with curl. The SSL certificates should be verified.

**Warning**: Using `get-pip.py` may require root or administrator privileges.

[Go back](#no-pip-error)

---

### Feedback

You can give us your feedback [by creating an issue](https://github.com/koviubi56/koviubi56/issues).

---

### Other great guides

- ["Installing Python Modules" in the official Python documentation](https://docs.python.org/3/installing/index.html)
- ["Installing Packages" tutorial in the Python Packaging User Guide](https://packaging.python.org/en/latest/tutorials/installing-packages/)

- [Video: "Python Tutorial - 12.1 - Install Python Module (using pip)"](https://youtu.be/bij66_Jtoqs)
- [Video: "Python Tutorial for Beginners 53 - How to use Pip and PyPI for managing Python packages"](https://youtu.be/sIan8TOz0GA?t=123)
- [Video: "Python pip 🏗️"](https://youtu.be/9z7gGUbAj5U)

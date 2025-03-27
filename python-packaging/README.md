# Python Packaging

## Why:

reuse code, my code in other projects; code from other people in my projects; ...

## Basic Introduction Packaging
* https://packaging.python.org/en/latest/overview/

### Python source distribution ([sdist](https://packaging.python.org/en/latest/glossary/#term-Distribution-Package)):
* "Multiple Python files, it’s usually organized into a directory structure"
* packed into [`sdists`](); a zip of your code directory
* good enough if you don't rely on any non-python code (lxml needs [libxml2](https://gitlab.gnome.org/GNOME/libxml2) which is written in C)

### Python binary distributions ([Wheel](https://packaging.python.org/en/latest/glossary/#term-Wheel))

* Wheels are a pre-built distribution format
* prefered by [pip](https://github.com/pypa/pip); pip: "is the package installer for Python"
* pip will try to build a wheel from a sdist locally and cache it


## [Packaging Python Projects](https://packaging.python.org/en/latest/tutorials/packaging-projects/)

see e.g. https://github.com/csae8092/csae-pyutils

### set up correct collection structure
* some root directory; usually where you run `git init`
* in the root directy you should have a README, LICENSE, (the usual git-things)
* in the root directory you have **another_directory**  which should be named like you python-package
  * in this **another_directory** you'll need at least one `__init__.py` file.
  * this `__init__.py` file can be empty, or hold the main functions/classes of you python pacakge
  * this **another_directory** can also hold other directory and/or `.py` files
* in the root direcotry you'll need to have a **`pyproject.toml`** file
* in older package you'll find a **`setup.py`** file instead. [Is setup.py deprecated?](https://packaging.python.org/en/latest/discussions/setup-py-deprecated/#setup-py-deprecated)

### pyproject.toml

minimal working example:

#### [build-backend](https://packaging.python.org/en/latest/tutorials/packaging-projects/#choosing-a-build-backend)

> A library that takes a source tree and builds a source distribution or built distribution from it. The build is delegated to the backend by a frontend.
> -- <cite>[Python-Glossary](https://packaging.python.org/en/latest/glossary/#term-Build-Backend)</cite>

```toml
[build-system]
requires = ["hatchling"]
build-backend = "hatchling.build"
```
### [Metadata](https://packaging.python.org/en/latest/tutorials/packaging-projects/#configuring-metadata)

Basics things like **name of the package(!)**, Authors (plus emails), License, Reamde, ...

```toml
[project]
name = "example_package_YOUR_USERNAME_HERE"
version = "0.0.1"
authors = [
  { name="Example Author", email="author@example.com" },
]
description = "A small example package"
readme = "README.md"
requires-python = ">=3.8"
classifiers = [
    "Programming Language :: Python :: 3",
    "Operating System :: OS Independent",
]
license = "MIT"
license-files = ["LICEN[CS]E*"]

[project.urls]
Homepage = "https://github.com/pypa/sampleproject"
Issues = "https://github.com/pypa/sampleproject/issues"
```
> [!WARNING]  
> The structure of the toml file differs, depending on your build backend

#### Dependencies
Python packages your code needs to run, usually what we write done in our `requirements.txt`
```toml
dependencies = [
    "pandas",
    "pyocclient",
    "requests",
]
```
Check the documentation for you build backend on how to pin versions of your dependencies though they should follow https://packaging.python.org/en/latest/specifications/version-specifiers/#id5

#### Python version
You can pin the Python version your code needs
```toml
requires-python = ">=3.9"
```

### Including other files
> If you want to include additional files, see the documentation for your build backend.
> -- <cite>[Python-Packaging](https://packaging.python.org/en/latest/tutorials/packaging-projects/#including-other-files)</cite>


### Building the package

run the command required by you build tool from the directory where the `pyproject.toml` file is located, e.g. 
```shell
python -m build
```

## Publishing a Python Package via pypi

[Pypi](https://pypi.org/) is the **Python Package Index**

* you'll need a user
* create a token (https://pypi.org/manage/account/) (Problem: how to set token scope to my project if my project does not exist yet)
* use e.g. [Twine](https://pypi.org/project/twine/) "a utility for publishing Python packages on PyPI." `twine upload dist/*`


## Tools

there are tools for managing python projects, e.g. creating folder structure, pyproject.toml, License, Readme

### [uv](https://docs.astral.sh/uv/)
new kid in town; written in rust -> fast

### [poetry](https://python-poetry.org/)
was the new kid in town until uv arrived; see https://wagtail.org/blog/uv-overtakes-poetry/

### [hatch](https://hatch.pypa.io/latest/)
provides the build backend hatchling

### [rye](https://rye.astral.sh/)
was bevore uv, from the same community
> If you're getting started with Rye, consider uv, the successor project from the same maintainers.

> [!TIP]  
> If you want to use one of those tools I'd go for `uv` as other people in the institute are using as well [e.g](https://github.com/acdh-oeaw/apis-instance-cookiecutter/commit/5fadae45f2a2a53881ab920f7207bcb0bf7ce611)
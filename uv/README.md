# uv
https://docs.astral.sh/uv/
> An extremely fast Python package and project manager, written in Rust.

## start a new project via command line 

### why?

* because Python projects have the same/similar structure
* creates files you'd need anyways
* handles virtual environments, python versions, requirements
* initializes Git-Repo

```shell
uv init cool-project
cd cool-project
tree
```

creates:

```
├── main.py
├── pyproject.toml
└── README.md

1 directory, 3 files
``` 

### add new package

```shell
uv add acdh-tei-pyutils
cat pyproject.toml
```

no need to curate requirements.txt files!

### run the code 

```shell
uv run main.py
```

### change python version

```shell
cat .python-version
```

# ruff
linter/formatter

## install
```shell
uv add ruff --dev
```
### lint and format

```
uv run ruff check
uv run rff format
```

## format on save with vscode

.vscode/settings.json
```json
{
  "[python]": {
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
      "source.fixAll": "explicit",
      "source.organizeImports": "explicit"
    },
    "editor.defaultFormatter": "charliermarsh.ruff"
  }
}
```
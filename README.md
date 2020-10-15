# vscode-organize-imports-repro

Repro for [Sort imports stopped working (vscode-python/#14399)](https://github.com/microsoft/vscode-python/issues/14399)

The code in `main.py` and `subfolder/main.py` have both had **Organize Imports** run on them, but `subfolder/main.py` has incorrectly grouped `library_a` and `library_b` with the third-party library `flask`.

## Output during Organize Imports

### main.py

```
> ~/dev/vscode-organize-imports-repro/.venv/bin/python3.9 ~/.vscode-insiders/extensions/ms-python.python-2020.9.114305/pythonFiles/pyvsc-run-isolated.py ~/.vscode-insiders/extensions/ms-python.python-2020.9.114305/pythonFiles/sortImports.py - --diff
cwd: ~/dev/vscode-organize-imports-repro
> ~/dev/vscode-organize-imports-repro/.venv/bin/python3.9 ~/.vscode-insiders/extensions/ms-python.python-2020.9.114305/pythonFiles/pyvsc-run-isolated.py ~/.vscode-insiders/extensions/ms-python.python-2020.9.114305/pythonFiles/sortImports.py - --diff
cwd: ~/dev/vscode-organize-imports-repro
```

### subfolder/main.py

```
> ~/dev/vscode-organize-imports-repro/.venv/bin/python3.9 ~/.vscode-insiders/extensions/ms-python.python-2020.9.114305/pythonFiles/pyvsc-run-isolated.py ~/.vscode-insiders/extensions/ms-python.python-2020.9.114305/pythonFiles/sortImports.py - --diff
cwd: ~/dev/vscode-organize-imports-repro/subfolder
> ~/dev/vscode-organize-imports-repro/.venv/bin/python3.9 ~/.vscode-insiders/extensions/ms-python.python-2020.9.114305/pythonFiles/pyvsc-run-isolated.py ~/.vscode-insiders/extensions/ms-python.python-2020.9.114305/pythonFiles/sortImports.py - --diff
cwd: ~/dev/vscode-organize-imports-repro/subfolder
```
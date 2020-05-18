# Installing a Python dev environment

## git and github

- [git installation](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
(git bash for [Windows](https://git-scm.com/download/win)): git is a versioning system.
- [github](https://github.com) is a platform to work collaboratively on the source code of hosted Open Source projects such as scikit-learn and NumPy.

- Clone numpy with git:
  ```
  $ git clone https://github.com/numpy/numpy.git
  ```
- Fork scikit-learn on github then clone your fork with git:
  ```
  $ git clone https://github.com/<myuser>/scikit-learn
  ```
- Configure some aliases for the remote repositories:

  List existing aliases:
  ```
  $ git remote -v
  ```
  
  Add a new alias for your fork on github:
  ```
  $ git remote add upstream https://github.com/scikit-learn/scikit-learn.git
  ```
  
  Check that your new alias has been properly configured:
  ```
  $ git remote -v
  ```

## conda

### Install miniconda

- [miniconda](https://docs.conda.io/en/latest/miniconda.html)
[installation](https://conda.io/projects/conda/en/latest/user-guide/install/index.html) (latest Python3 version)
- initialize the conda command in git bash
  - Windows: open "Git Bash" and type
  ```
  $ ./Miniconda3/Scripts/conda init bash
  ```
  - Linux:
  ```
  $ conda init bash
  ```
- then close your shell and start a new one to type:
  
  ```
  $ conda info
  ```
  or
  
  ```
  $ which conda
  ```
  to check that the conda command is in your PATH and useable from your shell.

### conda environments

- create an environment (`sklworkshop`)
```
$ conda create --name sklworkshop
```
- activate and deactivate environments
```
$ conda activate sklworkshop
(sklworkshop)$ conda deactivate
```
- version, environment and package listing
```
$ conda --version
$ conda env list
$ conda list
```

## VS Code

Install VSCode following your
[system instructions](https://code.visualstudio.com/docs/setup/setup-overview#_cross-platform).

Launch VSCode and configure [Telemetry settings](https://code.visualstudio.com/docs/getstarted/telemetry).

Install the Python extension
- `Ctrl+Shift+X` open the extension manager
- search for the python extension: install

Open project folder for numpy: `Ctrl-k Ctrl-o` 

Open a Python file from the project: `setup.py`.

In order to work with VSCode in your Python environment
- `Ctrl+Shift+P` then "python select interpreter" and choose "sklworkshop"

Open project folder for scikit-learn: `Ctrl-k Ctrl-o`

Activate the "sklworkshop" Python interpreter for the scikit-learn project.

Switch between projects: `Ctrl-r`

Browse the code:
- by files `Ctrl-p`
- by symbols `Ctrl-t`

At some point VSCode will complain about not finding a linter: scikit-learn uses `flake8`
- Install `flake8` in your conda environment
```
$ conda activate sklworkshop
(sklworkshop)$ conda install flake8
```
- Select `flake8` as a linter in VSCode: `Ctrl-Shift-P` "select linter"

## Practical code navigation

Find example files that mention the word "importance" in different ways:
- VSCode: `Ctrl-p` "example importance" and open `plot_permutation_importance.py`
- Github: go to https://github.com/scikit-learn/scikit-learn in your browser, press `t` and type "example/importance"

Navigate to the RandomForestClassifier or Regressor from the `plot_permutation_importance.py` example:
- VSCode: ctrl-clicking on the class name
- github: clicking on the class name

Find the class KMeans in scikit-learn in two different ways:
- from the command line: using `git grep "class KMeans"` (-i case insensitive, note that without "class" you will find
all occurrences) 
- VSCode: `Ctrl-t` KMeans (disable the jedi extension if it doesn't work)

## Installing C/C++ compilers to be able to build native extensions

See instructions for your OS in the [installation guide](https://scikit-learn.org/stable/developers/advanced_installation.html#building-from-source).
- [Windows](https://scikit-learn.org/stable/developers/advanced_installation.html#windows)
- [macOS](https://scikit-learn.org/stable/developers/advanced_installation.html#macos)
- [Linux](https://scikit-learn.org/stable/developers/advanced_installation.html#linux)

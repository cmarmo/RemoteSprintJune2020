# Building the master branch of numpy and scikit-learn

```
$ cd numpy
$ pip install -e .
$ cd ..
$ pip show numpy
$ conda install ipython
$ ipython
>>> import numpy as np
>>> print(np.__version__)
1.19.0.dev0+xxxxx
CTRL-D
```

Unlike numpy, scikit-learn does not list cython as a build dependency in a way understandable by pip yet. We need to install it manually first.
```
$ conda install cython
$ cd scikit-learn
$ pip install -e .
$ cd ..
$ pip show scikit-learn
$ ipython
>>> import sklearn
>>> print(sklearn.__version__)
0.23.dev0
CTRL-D
```

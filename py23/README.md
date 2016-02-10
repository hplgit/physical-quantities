# Common version for Python 2 and 3

This version depends on the `future` package
and was created in the parent directory by

```
futurize --all-imports -w -n -o py23 PhysicalQuantities.py
```
Most tests pass, but one fails: `e.inBaseUnits()`, suggesting that there
is something wrong in the translation from Python 2 to a common version for
Python 2 and 3.


Any help is appreciated.

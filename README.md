# physical-quantities

The PhysicalQuantity class made independent of [K. Hinsen's ScientificPython package](https://bitbucket.org/khinsen/scientificpython/). This class is very useful for computation involving *numbers with units*.

## Demo

```python
    >>> from PhysicalQuantities import PhysicalQuantity as p  # short hand
    >>> distance1 = p('10 m')
    >>> distance2 = p('10 km')
    >>> total = distance1 + distance2
    >>> total
    PhysicalQuantity(10010.0,'m')
    >>> total.convertToUnit('km')
    >>> total.getValue()
    10.01
    >>> total.getUnitName()
    'km'
    >>> total = total.inBaseUnits()
    >>> total
    PhysicalQuantity(10010.0,'m')
    >>>
    >>> t = p(314159., 's')
    >>> # convert to days, hours, minutes, and second:
    >>> t2 = t.inUnitsOf('d','h','min','s')
    >>> t2_print = ' '.join([str(i) for i in t2])
    >>> t2_print
    '3.0 d 15.0 h 15.0 min 59.0 s'
    >>>
    >>> e = p('2.7 Hartree*Nav')
    >>> e.convertToUnit('kcal/mol')
    >>> e
    PhysicalQuantity(1694.2757596034764,'kcal/mol')
    >>> e = e.inBaseUnits()
    >>> str(e)
    '7088849.77818 kg*m**2/s**2/mol'
    >>>
    >>> freeze = p('0 degC')
    >>> freeze = freeze.inUnitsOf ('degF')
    >>> str(freeze)
    '32.0 degF'
    >>>
```

Run

```
pydoc PhysicalQuantities
```
to see an overview of all the physical units and their notation supported
by the `PhysicalQuantities` module.

## Installation

```
sudo pip install  -e git+https://github.com/hplgit/physical-quantities.git#egg=physical-quantities
```

Or
```
git clone https://github.com/hplgit/physical-quantities.git
cd physical-quantities
sudo python setup.py install
```

## Note

The `PhysicalQuantities` module was developed by Dr. Konrad Hinsen
and appears in the [ScientificPython package](https://bitbucket.org/khinsen/scientificpython/). Unfortunately, ScientificPython requires NumPy version 1.8 or
less, and that is why H. P. Langtangen made this `PhysicalQuantities`
module independent of the ScientificPython package such that it is easy
in any project to compute with units.

## Python 3 version

The `PhysicalQuantities.py` file in the present directory is for Python 2.
There is an experimental Python 3 version in the subdirectory `py23`,
which depends on the `future` package.

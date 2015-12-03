# Python Ecosystem

Tags: python

Description: Tools, articles, etc. related to Python development.


# Documentation

Python docs:

  * [The Python Standard Library](https://docs.python.org/3/library/index.html)

  * [Download Python stdlib](https://docs.python.org/3/download.html)

Tooling:

  * [Read the Docs](https://docs.readthedocs.org/en/latest/index.html)

  * [Sphinx](http://sphinx-doc.org/)

  * [CommonMark](http://commonmark.org/): A strongly specified, highly compatible implementation of Markdown


# Packaging

Tools:

  * setuptools
  * wheel
  * twine
  * pyroma: Package checking, actually. Not code.
  * [pypackage](https://github.com/mikelopez/py-packaging-setup): pregenerate setup.py and co.

## Packaging Good Practices

### Releasing

See [Checklist before making a new release of a Python project](https://github.com/pfigue/notes/python/checklist_before_releasing.md).

### zip_safe

This is a parameter in setup.py, the default is True, but if you don't specify a value `pyroma` will complain.

Its meaning is about if it is safe to keep the package as a zip file.

If the program at runtime needs to access files in the package, it is not safe. In other case, it is.

### Integrating py.test with setup.py

[Integrating with distutils / python setup.py test](http://pytest.org/latest/goodpractises.html#integrating-with-distutils-python-setup-py-test)

[Integration with setuptools test commands](http://pytest.org/latest/goodpractises.html#integration-with-setuptools-test-commands)

### Tests layout

Tests in its own directory vs. tests in a subdir of the module(s) you distribute:

    mypkg/tests/
vs

    mypkg/mymodule1/tests

[Py.test: Choosing a test layout / import rules](http://pytest.org/latest/goodpractises.html#choosing-a-test-layout-import-rules)


### Versioning

[Public version identifiers for Python packages](http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers): How to choose the version tag.

[Setuptools: Specifying Your Project’s Version](https://pythonhosted.org/setuptools/setuptools.html#specifying-your-project-s-version)

## References

[How To Package Your Python Code](http://www.scotttorborg.com/python-packaging/index.html)

[Python Packaging User Guide](https://python-packaging-user-guide.readthedocs.org/en/latest/index.html)



# Code checking

## Function parameter and return types
In short:

    def fn(param1: list=[]) -> int:
        return 0
        
It has only **informative** purposes. No exception will be raised if *param1* is (e.g.) a FrozenSet instead of a List.

There is also the *\__annotations__* attribute:

    In [1]: fn.__annotations__
    Out[1]: {'param1': builtins.list, 'return': builtins.int}
    
And some doc *good practice* that was doing the same job as those annotations:

    def fn(param1: list=[]) -> int:
        """
        :param param1: list of sweets
        :type param1: list
        :returns: how many I would not eat
        :rtype: int
        """
        return 0

Annotations are for Python 3. For Python 2, better to use the docs.

To know more:

  * [StackOverflow Question - Function parameter types in Python](http://stackoverflow.com/a/21384492)
  * [PEP 3107 - Function Annotations](http://www.python.org/dev/peps/pep-3107/)
  * [PEP 0484 - Type Hints](https://www.python.org/dev/peps/pep-0484/)

## Syntax checking
[PEP8 - Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)

Tools:

  * flake8
  * pylint: very very strict, but configurable

## Testing

### Frameworks

[py.tests](http://pytest.org/latest/)

[Nosetests](https://nose.readthedocs.org/en/latest/)

[pyUnit]()

### Other
[tox](https://tox.readthedocs.org/en/latest/): running tests in different virtualenvs.

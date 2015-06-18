# Documentation
[Python Lib]()
[Download Python Lib]()
[Read the Docs]()
[Sphinx]()

# Testing
## Frameworks
[Nosetests]()
[py.tests]()
[pyUnit]()

## Other
[tox]()

# Packaging

## References
[How To Package Your Python Code](http://www.scotttorborg.com/python-packaging/index.html)
[Python Packaging User Guide](https://python-packaging-user-guide.readthedocs.org/en/latest/index.html)
[pypackage]()

## Practices: Versioning
[Public version identifiers for Python packages](http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers): How to choose the version tag.
[Setuptools: Specifying Your Project’s Version](https://pythonhosted.org/setuptools/setuptools.html#specifying-your-project-s-version)

## Practices: Tests layout
Tests in its own directory vs. tests in a subdir of the module(s) you distribute:

  mypkg/tests/ vs mypkg/mymodule1/tests

[Py.test: Choosing a test layout / import rules]{http://pytest.org/latest/goodpractises.html#choosing-a-test-layout-import-rules}

## Practises: Integrating py.test with setup.py
[Integrating with distutils / python setup.py test](http://pytest.org/latest/goodpractises.html#integrating-with-distutils-python-setup-py-test)
[Integration with setuptools test commands](http://pytest.org/latest/goodpractises.html#integration-with-setuptools-test-commands)

## Practices: zip_safe
Is it safe to keep the package as a zip file? If the program at runtime needs to access files in the package, it is not safe. In other case, it is.
This is a parameter in setup.py.

# Code checking
PEPx
flake8
pyroma: Package checking, actually. Not code.

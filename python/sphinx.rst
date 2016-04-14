:title: Documenting Python porjects with Sphinx
:tags: python, sphinx, documenting, documentation


*autodoc*: include docstrings into the documentation.

Documenting code through docstrings
===================================
Like `this <https://pythonhosted.org/an_example_pypi_project/sphinx.html#function-definitions>`_.
Like https://pythonhosted.org/an_example_pypi_project/sphinx.html (at the bottom)

It can be imported into Sphinx docs via the *autodoc* plugin of Sphinx.

def f():
  '''This function blah blah

  :param XXX: xxx
  :type XXX: string
  :returns: yyy
  :rtype: tuple
  :raises: ZZZException
  '''
  pass

References
==========
1. `Autodoc documentation <http://www.sphinx-doc.org/en/stable/ext/autodoc.html>`_
2. `Documenting your porject using Sphinx <https://pythonhosted.org/an_example_pypi_project/sphinx.html>`_.

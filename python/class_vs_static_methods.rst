:title: Class vs Static methods in Python
:tags: python
:category: python
:author: pfigue
:date: 2016-03-08
:status: draft

Class method
============

Use cases:
    * Function in a class
    * Which gets the class object to get or set data, or to call methods.
    
Example
-------

.. code-block:: python

    class Foo(object):
        # [...]
        @classmethod
        def method(cls_obj):
            pass


Static method
=============

Use cases:
    * Function in a class
    * Doesn't need the class: neither to access class variables, nor to call methods.

Example
-------

.. code-block:: python

    class Foo(object):
        # [...]
        @staticmethod
        def method():
            pass
   
References
----------

1. `Difference between @staticmethod and @classmethod in Python <http://pythoncentral.io/difference-between-staticmethod-and-classmethod-in-python/>`_
2. `StackOverflow: python class design (staticmethod vs method), first comment. <http://stackoverflow.com/questions/5212071/python-class-design-staticmethod-vs-method#5212190>`_
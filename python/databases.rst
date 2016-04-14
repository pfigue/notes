:title: Python and Databases
:tags: python, databases, postgres, mariadb

Overall
=======

Python tries to standardize the interface of database access modules via
`PEP 0249 -- Python Database API Specification v2.0 <https://www.python.org/dev/peps/pep-0249/>`_.

`Database programming in python <https://wiki.python.org/moin/DatabaseProgramming>`.

PostgreSQL
==========

* `psycopg2 module at Cheeseshop <https://pypi.python.org/pypi/psycopg2>`_
* `psycopg2 docs <http://initd.org/psycopg/docs/module.html>`_


MySQL/MariaDB
=============

MariaDB and MySQL have not so straight forward solution within Python.

* One option: `SimpleDB module <https://pypi.python.org/pypi/SimpleDB/>`_. Python2
* Other option: `simplemysql module <https://pypi.python.org/pypi/simplemysql/>`_
* Another option: ``MySQL-python``. But didn't find docs. It is a dep for SimpleDB, at least. Some docs: http://mysql-python.sourceforge.net/MySQLdb.html
* `moist - Python database adaptor for MySQL, MariaDB, Drizzle, and other watery databases <https://github.com/farcepest/moist>`_

At least one of those packages (MySQL-python) needs the command ``mysql_config`` during install. When using MariaDB, you will need the package ``libmysqlclient-dev`` (in Ubuntu 12.04, at least).

check also `<https://wiki.python.org/moin/MySQL>`_.


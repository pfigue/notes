:tags: redis, cheatsheet
:title: Redis Cheatsheet

General Commands
================

PING
----

FLUSHDB
-------

Empties the current database

FLUSHALL
--------

Empties ALL databases. And never fails.

KEYS <pattern>
---------------

Where pattern could be * or CS* or *-11, for example.
Seems to be like really expensive when you have plenty of keys.
Returns all the keys that follow the pattern.

DBSIZE
------

Size of the currently selected database

SELECT <db_name>
----------------

choose one database

INFO keyspace
-------------

localhost:6379[1]> INFO keyspace
# Keyspace
db1:keys=1866190,expires=0,avg_ttl=0

MONITOR
-------

Data structures: Sets
=====================


SADD
----

SISMEMBER
---------


SMEMBERS
--------

Prints the members of the group.

It is what you need if you ar looking for a get operation on sets.


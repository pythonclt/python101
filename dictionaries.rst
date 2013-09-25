Dictionaries
============

A dictionary is a hash (table) or associative array - it holds objects indexed
by keys (``key: value`` pairs). Dictionaries are:

- unordered
- accessed by key
- nestable
- mutable

Dictionary keys can be any immutable type - e.g. strings or numbers; keys are
also unique per dictionary.

----------

Create
------

Use curly braces:

.. code:: python

    d = {"one": 1, "two": 2}

    vader = {
      "name": "darth",
      "caped": True,
      "sith_rank": 2
    }

Use ``dict`` with keyword args:

.. code:: python

    d = dict(first='Sir', last='Robin')

Use ``dict`` with sequences of key-value pairs:

>>> d = dict([('red', 1), ('blue', 2), ('green', 3)])
>>> d
{'blue': 2, 'green': 3, 'red': 1}

Use ``dict`` with ``zip`` and ``range``:

>>> dict(zip(range(1, 6), range(10, 15)))
{1: 10, 2: 11, 3: 12, 4: 13, 5: 14}

Add To
------

Add to a dictionary:

>>> d = {"one": "uno"}
>>> d['two'] = "dos"
>>> d
{'two': 'dos', 'one': 'uno'}

Access
------

Index by key:

``d['holy_hand_grenade']``

Get number of items in dictionary *d*:

``len(d)``

Use ``keys()`` method to get a list of a dictionary's keys:

>>> d = {"lang": "python", "city": "charlotte"}
>>> d.keys()
['lang', 'city']

Use ``values()`` method to get a list of a dictionary's, um, values:

>>> d = {"lang": "python", "city": "charlotte"}
>>> d.values()
['python', 'charlotte']

Get list of dictionary's key-value pairs:

>>> d = {"lang": "python", "city": "charlotte"}
>>> d.items()
[('lang', 'python'), ('city', 'charlotte')]

Get an iterator over a dictionary's keys, values, or key-value pairs:

.. code:: python

    iterkeys()
    itervalues()
    iteritems()

Check if a key is ``in`` a dictionary:

>>> 'city' in d
True

Get the value for a key:

>>> d.get("city")
charlotte

Add 1 to a key's value:

.. code:: python

    d[key] = d.get(key, 0) + 1

The ``0`` in the code above provides a default key value, so if the key isn't
there, it will return a ``0``. If you don't specify your own default key value,
it will return ``None``. Note that if you do a ``d['key']`` and the key doesn't
exist, you will get an exception.

Delete
------

Use ``del`` operator to remove a key-value pair:

>>> d = {"purple": 1, "red": 2}
>>> del d["purple"]
>>> d
{'red': 2}

Sort
----

Sort by key - well, view a ``sorted`` by key representation:

>>> sorted(d)
['color', 'name', 'quest']
>>> d
{'color': 'blue', 'quest': 'grail', 'name': 'lancelot'}

Sort by value:

>>> sorted(d.items(), key=lambda x: x[1])
[('color', 'blue'), ('quest', 'grail'), ('name', 'lancelot')]

Merge
-----

Use ``update`` to merge 2 dictionaries into 1:

>>> d = {"name": "lancelot", "quest": "grail"}
>>> dd = {"color": "blue"}
>>> d.update(dd)
>>> d
{'color': 'blue', 'quest': 'grail', 'name': 'lancelot'}

Comprehensions
--------------

Create dictionaries from key value expressions:

>>> {x: x**3 for x in (2, 3, 4)}
{2: 8, 3: 27, 4: 64}

Defaultdict
-----------

Use to initialize a default value when a dictionary key is accessed for the
first time.

>>> from collections import defaultdict
>>> some_string = 'farcical aquatic ceremony'
>>> d = defaultdict(int)
>>> for k in some_string:
...     d[k] += 1
...
>>> d.items()
[('a', 4), (' ', 2), ('c', 4), ('e', 2), ('f', 1), ('i', 2), ('m', 1), ('l', 1)
, ('o', 1), ('n', 1), ('q', 1), ('r', 2), ('u', 1), ('t', 1), ('y', 1)]


And Strings
-----------

String formatting:

>>> "%(n)d %(x)s % {"n":1, "x":"spam"}
'1 spam'

And Lists
---------

Python ``lists`` cannot be dictionary keys, but they can be values. You can
also do things like build up a dictionary of lists:

>>> dict((i, range(i, i + 5)) for i in [5, 10])
{10: [10, 11, 12, 13, 14], 5: [5, 6, 7, 8, 9]}

Build a dictionary from 2 lists:

>>> names = ['Iron', 'Gold', 'Silver', 'Neon']
>>> symbols = ['Fe', 'Au', 'Ag', 'Ne']
>>> d = dict(zip(names, symbols))
>>> d
{'Neon': 'Ne', 'Gold': 'Au', 'Iron': 'Fe', 'Silver': 'Ag'}

And JSON
--------

Python dictionaries and JSON data work nicely together:

>>> import json
>>> d = {'Neon': 'Ne', 'Gold': 'Au', 'Iron': 'Fe', 'Silver': 'Ag'}
>>> print(json.dumps(d, indent=4))
{
    "Neon": "Ne",
    "Iron": "Fe",
    "Gold": "Au",
    "Silver": "Ag"
}

Methods
-------

To view the methods available to a dictionary:

>>> d = {"one": 1, "two": 2}
>>> for m in dir(d):
...     print m
...
__class__
__cmp__
__contains__
__delattr__
__delitem__
__doc__
__eq__
__format__
__ge__
__getattribute__
__getitem__
__gt__
__hash__
__init__
__iter__
__le__
__len__
__lt__
__ne__
__new__
__reduce__
__reduce_ex__
__repr__
__setattr__
__setitem__
__sizeof__
__str__
__subclasshook__
clear
copy
fromkeys
get
has_key
items
iteritems
iterkeys
itervalues
keys
pop
popitem
setdefault
update
values
viewitems
viewkeys
viewvalues

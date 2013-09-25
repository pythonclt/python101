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

Get a list of a dictionary's keys:

    >>> d = {"lang": "python", "city": "charlotte"}
    >>> d.keys()
    ['lang', 'city']

Check if a key is ``in`` a dictionary:

    >>> 'city' in d
    True

Get the value for a key:

    >>> d.get("city")
    charlotte

Add 1 to a key's value:

.. code:: python

    d[key] = d.get(key) + 1

String formatting:

    >>> "%(n)d %(x)s % {"n":1, "x":"spam"}
    '1 spam'

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

Defaultdict
-----------

And Strings
-----------

And Lists
---------

And JSON
--------

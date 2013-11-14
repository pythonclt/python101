List Comprehensions
===================

List comprehensions in python provide a concise way to create new lists. Since
I am lazy, they will henceforth be called *LC*. So, what are these
so-called *LC* then anyway?

*LC* might be described as a relative of the ``for`` loop statement and the
functional, uh, functions ``map`` and ``filter``. *LC* are an improvement to
those tools however - *LC* apply an expression (not just a function) to items
in an iterable.

They can also contain nestable loops (multiple ``for`` clauses), but your
python code should be easy to read, so don't get too crazy!
(Remember ``import this``.)

*LC* - formally described in PEP-202_

----------

Speed
-----

List comprehensions are faster than initializing an empty list and appending to
it one element at a time. This does not necessarily mean you should attempt to
replace all of your ``for`` loops with list comprehensions, of course, but
*LC* are generally faster or as fast as their ``for|map`` equivalents.

Usage
-----

Making a new list of cubes using a ``for`` loop:

.. code:: python

    cubes = []
    for x in range(5):
        cubes.append(x**3)

There is a certain amount of interpreter overhead with the ``for`` loop itself,
so one can avoid that ``for`` overhead by using the ``map`` function. To count
the number of characters in each name:

.. code:: python

    names = ['Galahad', 'Arthur', 'Lancelot', 'Robin']
    letter_counts = map(len, names)

Say we need to cube some numbers:

.. code:: python

    def cube(x):
        return x**3

    map(cube, range(5))

This could also be done inline using a ``lambda``:

.. code:: python

    list(map((lambda x: x ** 3), range(5)))

In one line and cleaner with a *LC*:

.. code:: python

    cubes = [x**3 for x in range(5)]

A longer example using ``for`` loops:

.. code:: python

    lob_holy_hand_grenade = []
    number_of_the_counting = [3]
    king_arthurs_options = [0, 1, 2, 3, 4, 5]
    for x in number_of_the_counting:
        for y in king_arthurs_options:
            if x != y:
                print '%d is right out!' % y
            else:
                lob_holy_hand_grenade.append((x, y))

    print lob_holy_hand_grenade

Using a *LC* this would become:

.. code:: python

    [(x, y) for x in [3] for y in range(5) if y == x]
    [x for x in range(5) if x == 3]

What if we only want even numbers?

.. code:: python

    list(filter((lambda x: x % 2 == 0), range(5)))

    [x for x in range(5) if x % 2 == 0]

Now we want to only cube the even numbers - easy and concise with a *LC*:

.. code:: python

    [x**3 for x in range(5) if x % 2 == 0]

Reading through and cleaning the lines in a file object:

.. code:: python

    f = open('/tmp/words')
    lines = f.readlines()
    lines = [line.rstrip() for line in lines]

Not bad but can be improved!

.. code:: python

    [line.rstrip().upper() for line in open('/tmp/words')]
    [line.rstrip().upper() for line in open('/tmp/words') if line[1] == 'b']

We can also nest loops inside *LC*:

.. code:: python

    [x + y for x in 'st' for y in 'aeiouy']
    [(x, x + y) for x in [0,2] for y in range(4)]

Other Comprehensions
--------------------

Dictionary:

.. code:: python

    {line for line in open('/tmp/logstash_index_cleaner.py')}

Set:

.. code:: python

    set(open('/tmp/logstash_index_cleaner.py'))

Definitions
-----------

**list**
An ordered set of values, where each value is identified by an index. The
values in a list are called its *elements*.

**map**
Built-in function that applies a given function to every given item and returns
a list of results (``map(function, items, ...)``).

**filter**
Built-in function that creates a list of the objects from a given iterable
where given function evaluates to true (``filter(function, iterable)``).

**lambda**
Operator that allows creation of anonymous functions in the form of a valid
expression.

Questions?
----------

Fire away!


.. _PEP-202:
    http://www.python.org/dev/peps/pep-0202/


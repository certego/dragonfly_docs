Boolean clause documentation
===============================

At the moment, Dragonfly supports three different boolean clauses:

* And
* Or
* Not

A boolean clause is represented as a dictionary, that have as keys a boolean connector, and as value a list.
Every element of the list must be the representation of a module, or another boolean clause, written as a dictionary object.


Fields
--------
+------------+----------+---------------+-------+------+
| Field name | Required | Default Value | Type  | Type |
+------------+----------+---------------+-------+------+
| order      | False    | False         | bool  | str  |
+------------+----------+---------------+-------+------+

Example
--------

.. code:: python3

    {
      and: [
        {
          module: 'Api',
          syscall: 'VirtualAlloc'
        },
        or: [
            {
              module: 'Api',
              syscall: 'VirtualProtect'
            },
            {
              module: 'Api',
              syscall: 'VirtualDelete'
            }
        ]
      ],
      order: true
    }

.. toctree::
   :maxdepth: 2
   :caption: Modules:

   module/index
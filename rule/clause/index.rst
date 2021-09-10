Boolean clause 
===============================

At the moment, Dragonfly supports three different boolean clauses:

* And
* Or
* Not

A boolean clause is represented as a dictionary, that have as keys a boolean connector, and as value a list.
Every element of the list must be the representation of a module, or another boolean clause, written as a dictionary object.

Fields
-------

.. list-table::
    :widths:  25 10 10 10 45
    :header-rows: 1

    * - Field name
      - Required
      - Variables
      - Regex
      - Type
    * - order
      - False
      - False
      - False
      - bool


.. toctree::
   :maxdepth: 1
   :caption: Modules

   module/index

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

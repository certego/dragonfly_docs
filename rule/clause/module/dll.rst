Dll
-------

The module matches dlls that are loaded or searched by the sample

Fields
^^^^^^^
+--------------+----------+-----------+-------+----------------------------------------------+
| Field name   | Required | Variables | Regex | Type                                         |
+--------------+----------+-----------+-------+----------------------------------------------+
| name         | True     | True      | True  | str                                          |
+--------------+----------+-----------+-------+----------------------------------------------+

Example
^^^^^^^
.. code:: python3

    {
        module:"Dll",
        name:"kernel.*",
    }
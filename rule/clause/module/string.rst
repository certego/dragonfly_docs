String
------------

The module matches strings used by the sample

Fields
^^^^^^^
+------------+----------+-----------+-------+------+
| Field name | Required | Variables | Regex | Type |
+------------+----------+-----------+-------+------+
| input      | True     | True      | True  | str  |
+------------+----------+-----------+-------+------+
| case       | False    | False     | False | bool |
+------------+----------+-----------+-------+------+

Example
^^^^^^^

.. code:: python3

    {
        module:"String",
        input:"FamousMalw.*isHere",
        case:True
    }
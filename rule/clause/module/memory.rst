Memory
========

The module matches memory accesses made by the sample

Fields
-------
+------------+-------------------+-----------+-------+----------------------+
| Field name | Required          | Variables | Regex | Type                 |
+------------+-------------------+-----------+-------+----------------------+
| structure  | True or address   | False     | False | str                  |
+------------+-------------------+-----------+-------+----------------------+
| address    | True or structure | True      | False | Union[str, int]      |
+------------+-------------------+-----------+-------+----------------------+
| offset     | False             | False     | False | int                  |
+------------+-------------------+-----------+-------+----------------------+
| content    | False             | True      | False | str                  |
+------------+-------------------+-----------+-------+----------------------+
| mode       | False             | False     | False | enum["read","write"] |
+------------+-------------------+-----------+-------+----------------------+

Example
-------
.. code:: python3

    {
        module: "Memory",
        structure: "PEB.flag",
        mode: "Read"
    }

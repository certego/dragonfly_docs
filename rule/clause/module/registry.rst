Registry
------------

The module matches registry accesses done by the sample

Fields
^^^^^^^
+------------+----------+-----------+-------+------------------------------------------+
| Field name | Required | Variables | Regex | Type                                     |
+------------+----------+-----------+-------+------------------------------------------+
| key        | True     | True      | True  | str                                      |
+------------+----------+-----------+-------+------------------------------------------+
| action     | False    | False     | False | enum["read", "create", "delete", "list"] |
+------------+----------+-----------+-------+------------------------------------------+
| value_name | False    | True      | True  | str                                      |
+------------+----------+-----------+-------+------------------------------------------+
| value_data | False    | True      | True  | str                                      |
+------------+----------+-----------+-------+------------------------------------------+

Example
^^^^^^^
.. code:: python3

    {
        module: "Registry",
        key: "HKEY_CURRENT_USER\\Keyboard Layout\\Preload",
        value_name: "1",
        value_data: 3,
    }
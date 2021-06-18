File
---------

The module matches files that are created, open or deleted by the sample

Fields
^^^^^^^
+------------+----------+-----------+-------+----------------------------------+
| Field name | Required | Variables | Regex | Type                             |
+------------+----------+-----------+-------+----------------------------------+
| file_name  | False    | True      | True  | str                              |
+------------+----------+-----------+-------+----------------------------------+
| sha256     | False    | False     | False | str                              |
+------------+----------+-----------+-------+----------------------------------+
| content    | False    | True      | True  | s                                |
+------------+----------+-----------+-------+----------------------------------+
| access     | False    | False     | False | enum["open", "create", "delete"] |
+------------+----------+-----------+-------+----------------------------------+

Example
^^^^^^^
.. code:: python3

    {
        module:"File",
        file_name:"MyF.*e",
        access:"create"
    }


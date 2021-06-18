Network
===========

The module matches network requests made by the sample

Fields
-------
+------------+----------+-----------+-------+------+
| Field name | Required | Variables | Regex | Type |
+------------+----------+-----------+-------+------+
| ip         | False    | True      | True  | str  |
+------------+----------+-----------+-------+------+
| hostname   | False    | True      | True  | str  |
+------------+----------+-----------+-------+------+
| port       | False    | False     | False | int  |
+------------+----------+-----------+-------+------+
| payload    | False    | True      | True  | str  |
+------------+----------+-----------+-------+------+
| uri        | False    | True      | True  | str  |
+------------+----------+-----------+-------+------+
| protocol   | False    | True      | False | str  |
+------------+----------+-----------+-------+------+

Example
-------
.. code:: python3

    {
        module: "Network",
        protocol: "tcp",
        hostname: "google.*"
    }

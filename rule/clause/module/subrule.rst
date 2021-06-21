SubRule
===========

The module refers to another rule

Fields
-------
+------------+----------+-----------+-------+------+
| Field name | Required | Variables | Regex | Type |
+------------+----------+-----------+-------+------+
| sub_rule   | True     | False     | False | str  |
+------------+----------+-----------+-------+------+
| owner      | False    | False     | False | str  |
+------------+----------+-----------+-------+------+


Example
-------

.. code:: python3

    {
        module:"SubRule",
        sub_rule:"MyRuleN1"
    }

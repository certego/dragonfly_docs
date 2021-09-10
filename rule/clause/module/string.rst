String
============

The module matches strings used by the sample

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
    * - input
      - True
      - True
      - True
      - str
    * - case
      - False
      - False
      - False
      - bool

Example
-------

.. code:: python3

    {
        module:"String",
        input:"FamousMalw.*isHere",
        case:True
    }
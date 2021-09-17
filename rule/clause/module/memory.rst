Memory
========

The module matches memory accesses made by the sample

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
    * - structure
      - True
      - False
      - False
      - enum["Peb", "Peb.Flag", "Teb"]
    * - mode
      - False
      - False
      - False
      - enum["Read", "Write", "Execute"]
..
    * - content
      - False
      - True
      - True
      - str

Example
-------
.. code:: python3

    {
        module: "Memory",
        structure: "PEB.flag",
        mode: "Read"
    }

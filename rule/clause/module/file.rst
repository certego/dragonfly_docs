File
=========

The module matches files that are created, open or deleted by the sample

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
    * - file_name
      - False
      - True
      - True
      - str
    * - sha256
      - False
      - False
      - False
      - str
    * - access
      - False
      - False
      - False
      - enum["open", "create", "delete"]
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
        module:"File",
        file_name:"MyF.*e",
        access:"create"
    }


Dll
=======

The module matches dlls that are loaded or searched by the sample

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
    * - name
      - True
      - True
      - True
      - str


Example
-------
.. code:: python3

    {
        module:"Dll",
        name:"kernel.*",
    }
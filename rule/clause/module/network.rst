Network
===========

The module matches network requests made by the sample

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
    * - server
      - False
      - True
      - True
      - str
    * - port
      - False
      - False
      - False
      - int
    * - payload
      - False
      - True
      - True
      - str
    * - uri
      - False
      - True
      - True
      - str
    * - protocol
      - False
      - True
      - False
      - str
    * - method
      - False
      - True
      - True
      - str
    * - headers
      - False
      - True
      - True
      - Dict[str,str]

Example
-------
.. code:: python3

    {
        module: "Network",
        protocol: "tcp",
        server: "google.*",
        method: "GET"
    }

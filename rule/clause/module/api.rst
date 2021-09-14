Api
=======

The module matches windows Api calls that are executed by the sample

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
    * - syscall
      - True
      - True
      - True
      - str
    * - return_value
      - False
      - True
      - True
      - Union[str,int]
    * - params
      - False
      - True
      - True
      - Dict[str,Union[str,int,List[Union[str,int]]]
..
    * - params_memory_values
      - False
      - False
      - False
      - Dict[str[\*\+[0-9]+(=|!)], int]

Example
-------
.. code:: python3

    {
        module:"Api",
        syscall:".*Alloc",
        params:{
            "0":[
                16,
                "22"
            ]
        }
        params_memory_values: {
            "0": 0xdf
        }
    }

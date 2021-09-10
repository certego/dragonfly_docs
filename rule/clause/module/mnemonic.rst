Mnemonic
==========

The module matches assembly code executed by the sample

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
    * - instructions
      - True
      - False, ? allowed
      - False
      - List[str]

Example
-------
.. code:: python3

    {
        module: "Mnemonic",
        instructions: [
            "push rax", "?", "mov rax, rsp"
        ]
    }

Mnemonic
==========

The module matches assembly code executed by the sample

Fields
-------
+--------------+---------------------+--------------+-------+----------------------+
| Field name   | Required            | Variables    | Regex | Type                 |
+--------------+---------------------+--------------+-------+----------------------+
| instructions | True or addressTrue | True, only ? | False | List[str]            |
+--------------+---------------------+--------------+-------+----------------------+

Example
-------
.. code:: python3

    {
        module: "Mnemonic",
        instructions: [
            "push rax", "?", "mov rax, rsp"
        ]
    }

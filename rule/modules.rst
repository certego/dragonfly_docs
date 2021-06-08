Boolean Clauses
=================

At the moment, Dragonfly supports three different boolean clauses:

* And
* Or
* Not

A boolean clause is represented as a dictionary, that have as keys a boolean connector, and as value a list.
Every element of the list must be the representation of a module, or another boolean clause, written as a dictionary object.


Fields
--------
+------------+----------+---------------+-------+------+
| Field name | Required | Default Value | Type  | Type |
+------------+----------+---------------+-------+------+
| order      | False    | False         | bool  | str  |
+------------+----------+---------------+-------+------+

Example
--------

.. code:: python3

    {
      and: [
        {
          module: 'Api',
          syscall: 'VirtualAlloc'
        },
        or: [
            {
              module: 'Api',
              syscall: 'VirtualProtect'
            },
            {
              module: 'Api',
              syscall: 'VirtualDelete'
            }
        ]
      ],
      order: true
    }


Modules
===============

A module is a single type of information that Dragonfly stored.
Dragonfly supports a finite number of modules, each one with different keywords that users can use.
There are some fields that are common to every module:

+--------------+----------+-----------+-------+----------------------------------------------+
| Field name   | Required | Variables | Regex | Type                                         |
+--------------+----------+-----------+-------+----------------------------------------------+
| counter      | False    | False     | False | int                                          |
+--------------+----------+-----------+-------+----------------------------------------------+



These are the modules that Dragonfly supports at the moment

Api
-------

The module matches windows Api calls that are executed by the sample

Fields
^^^^^^^

+--------------+----------+-----------+-------+----------------------------------------------+
| Field name   | Required | Variables | Regex | Type                                         |
+--------------+----------+-----------+-------+----------------------------------------------+
| syscall      | True     | True      | True  | str                                          |
+--------------+----------+-----------+-------+----------------------------------------------+
| return_value | False    | True      | True  | Union[str,int]                               |
+--------------+----------+-----------+-------+----------------------------------------------+
| params       | False    | True      | True  | Dict[str,Union[str,int,List[Union[str,int]]] |
+--------------+----------+-----------+-------+----------------------------------------------+


Example
^^^^^^^
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
    }

Dll
-------

The module matches dlls that are loaded or searched by the sample

Fields
^^^^^^^
+--------------+----------+-----------+-------+----------------------------------------------+
| Field name   | Required | Variables | Regex | Type                                         |
+--------------+----------+-----------+-------+----------------------------------------------+
| name         | True     | True      | True  | str                                          |
+--------------+----------+-----------+-------+----------------------------------------------+

Example
^^^^^^^
.. code:: python3

    {
        module:"Dll",
        name:"kernel.*",
    }

File
---------

The module matches files that are created, open or deleted by the sample

Fields
^^^^^^^
+------------+----------+-----------+-------+----------------------------------+
| Field name | Required | Variables | Regex | Type                             |
+------------+----------+-----------+-------+----------------------------------+
| file_name  | False    | True      | True  | str                              |
+------------+----------+-----------+-------+----------------------------------+
| sha256     | False    | False     | False | str                              |
+------------+----------+-----------+-------+----------------------------------+
| content    | False    | True      | True  | s                                |
+------------+----------+-----------+-------+----------------------------------+
| access     | False    | False     | False | enum["open", "create", "delete"] |
+------------+----------+-----------+-------+----------------------------------+

Example
^^^^^^^
.. code:: python3

    {
        module:"File",
        file_name:"MyF.*e",
        access:"create"
    }


Memory
--------

The module matches memory accesses made by the sample

Fields
^^^^^^^
+------------+-------------------+-----------+-------+----------------------+
| Field name | Required          | Variables | Regex | Type                 |
+------------+-------------------+-----------+-------+----------------------+
| structure  | True or address   | False     | False | str                  |
+------------+-------------------+-----------+-------+----------------------+
| address    | True or structure | True      | False | Union[str, int]      |
+------------+-------------------+-----------+-------+----------------------+
| offset     | False             | False     | False | int                  |
+------------+-------------------+-----------+-------+----------------------+
| content    | False             | True      | False | str                  |
+------------+-------------------+-----------+-------+----------------------+
| mode       | False             | False     | False | enum["read","write"] |
+------------+-------------------+-----------+-------+----------------------+

Example
^^^^^^^
.. code:: python3

    {
        module: "Memory",
        structure: "PEB.flag",
        mode: "Read"
    }

Mnemonic
----------

The module matches assembly code executed by the sample

Fields
^^^^^^^
+--------------+---------------------+--------------+-------+----------------------+
| Field name   | Required            | Variables    | Regex | Type                 |
+--------------+---------------------+--------------+-------+----------------------+
| instructions | True or addressTrue | True, only ? | False | List[str]            |
+--------------+---------------------+--------------+-------+----------------------+

Example
^^^^^^^
.. code:: python3

    {
        module: "Mnemonic",
        instructions: [
            "push rax", "?", "mov rax, rsp"
        ]
    }


Network
-----------

The module matches network requests made by the sample

Fields
^^^^^^^
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
^^^^^^^
.. code:: python3

    {
        module: "Network",
        protocol: "tcp",
        hostname: "google.*"
    }

Registry
------------

The module matches registry accesses done by the sample

Fields
^^^^^^^
+------------+----------+-----------+-------+------------------------------------------+
| Field name | Required | Variables | Regex | Type                                     |
+------------+----------+-----------+-------+------------------------------------------+
| key        | True     | True      | True  | str                                      |
+------------+----------+-----------+-------+------------------------------------------+
| action     | False    | False     | False | enum["read", "create", "delete", "list"] |
+------------+----------+-----------+-------+------------------------------------------+
| value_name | False    | True      | True  | str                                      |
+------------+----------+-----------+-------+------------------------------------------+
| value_data | False    | True      | True  | str                                      |
+------------+----------+-----------+-------+------------------------------------------+

Example
^^^^^^^
.. code:: python3

    {
        module: "Registry",
        key: "HKEY_CURRENT_USER\\Keyboard Layout\\Preload",
        value_name: "1",
        value_data: 3,
    }

String
------------

The module matches strings used by the sample

Fields
^^^^^^^
+------------+----------+-----------+-------+------+
| Field name | Required | Variables | Regex | Type |
+------------+----------+-----------+-------+------+
| input      | True     | True      | True  | str  |
+------------+----------+-----------+-------+------+
| case       | False    | False     | False | bool |
+------------+----------+-----------+-------+------+

Example
^^^^^^^

.. code:: python3

    {
        module:"String",
        input:"FamousMalw.*isHere",
        case:True
    }

SubRule
-----------

The module refers to another rule

Fields
^^^^^^^
+------------+----------+-----------+-------+------+
| Field name | Required | Variables | Regex | Type |
+------------+----------+-----------+-------+------+
| sub_rule   | True     | False     | False | str  |
+------------+----------+-----------+-------+------+


Example
^^^^^^^

.. code:: python3

    {
        module:"SubRule",
        sub_rule:"MyRuleN1"
    }

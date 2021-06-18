Api
=======

The module matches windows Api calls that are executed by the sample

Fields
-------

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
    }

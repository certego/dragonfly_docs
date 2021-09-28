Rule 
==========================
Rules the objects that Dragonfly uses to verify malware behaviours.

They can be complex as much as its creator wants, and the syntax that Dragonfly allows, is enough powerful to catch any kind of malware behaviour.

Fields
-----------
- Each rule that an user creates must have an unique name, allowing unique identification
- The weight describe the confidence that the behaviour described by the rule is from a malware.
- In the Malware Family field the user can add the specific malware family that shows the behaviour
- In the Malware Behaviour field the user can select one of the behaviour that Dragonfly supports
- Meta description is a free dictionary field where the user can write whatever s/he wants. It can be used to add information about the rules, add pointers to external documentation and so on.
- In the variables field the user must declare the name of the variables that will be used in the modules. Variables are used to add a constraint between two different keys on the modules sections. An example is provided later.
- Actions: TBD

.. toctree::
   :maxdepth: 1
   
   clause/index.rst


Example
--------------

- Rule: MyFirstRule
- Weight: 10
- MalwareFamily: Emotet
- MalwareBehaviour: Banker
- MetaDescription:
    .. literalinclude:: meta.json
          :language: JSON
- Variables: [ "address"]
- Modules:
    .. literalinclude:: rule.json
      :language: JSON


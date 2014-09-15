

.. _http://stsci.edu/schemas/asdf/0.1.0/unit/defunit:

defunit: Define a new physical unit.
====================================

:soft:`Type:` object.

Define a new physical unit.

Defines a new unit.  It can be used to either:

- Define a new base unit.

- Create a new unit name that is a equivalent to a given unit.

The new unit must be defined before any unit tags that use it.


:category:`Properties:`



  .. _http://stsci.edu/schemas/asdf/0.1.0/unit/defunit/properties/name:

  :entry:`name`

  :soft:`Type:` string ( :soft:`regex` :regexp:`[A-Za-z_][A-Za-z0-9_]+` ). Required.

  

  The name of the new unit.



  .. _http://stsci.edu/schemas/asdf/0.1.0/unit/defunit/properties/unit:

  :entry:`unit`

  :soft:`Type:` :doc:`unit <unit>` :soft:`or` null.

  

  The unit that the new name is equivalent to.  It is optional,
  and if not provided, or ``null``, this ``defunit`` defines a new
  base unit.
  

  :category:`Any of:`



    .. _http://stsci.edu/schemas/asdf/0.1.0/unit/defunit/properties/unit/anyOf/0:

    :entry:`—`

    :soft:`Type:` :doc:`unit <unit>`.

    

    



    .. _http://stsci.edu/schemas/asdf/0.1.0/unit/defunit/properties/unit/anyOf/1:

    :entry:`—`

    :soft:`Type:` null.

    

    

.. only:: html

   :download:`Original schema in YAML <defunit.yaml>`

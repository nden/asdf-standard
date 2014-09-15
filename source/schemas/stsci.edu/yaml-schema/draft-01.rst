

.. _http://stsci.edu/schemas/yaml-schema/draft-01:

draft-01
========

:soft:`Type:` :doc:`schema <http://json-schema.org/draft-04/schema>` :soft:`and` object.



A metaschema extending JSON Schema's metaschema to add support for
some YAML-specific constructions.


:category:`All of:`



  .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/0:

  :entry:`0`

  :soft:`Type:` :doc:`schema <http://json-schema.org/draft-04/schema>`.

  

  



  .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/1:

  :entry:`1`

  :soft:`Type:` object.

  

  

  :category:`Properties:`



    .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/1/properties/tag:

    :entry:`tag`

    :soft:`Type:` string ( *len* ≥ 6 ).

    

    A fully-qualfied YAML tag name that should be associated
    with the object type returned by the YAML parser; for
    example, the object must be an instance of the class
    registered with the parser to create instances of objects
    with this tag. Implementation of this validator is optional
    and depends on details of the YAML parser.
    



    .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/1/properties/propertyOrder:

    :entry:`propertyOrder`

    :soft:`Type:` array :soft:`of` ( string ).

    

    Objects with a defined propertyOrder must be treated as an
    ordered mapping, and its keys must be in the same relative
    order they are listed in this validator. Keys listed in
    propertyOrder are not required to be present in the object,
    and any keys not specified by propertyOrder may come in
    arbitrary order so long as they follow any keys listed here.
    

    :category:`Items:`



      .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/1/properties/propertyOrder/items:

      :soft:`Type:` string.

      

      



    .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/1/properties/examples:

    :entry:`examples`

    :soft:`Type:` array :soft:`of` ( array ).

    

    A list of examples to help document the schema.  Each pair
    is a prose description followed by a string containing YAML
    content.
    

    :category:`Items:`



      .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/1/properties/examples/items:

      :soft:`Type:` array.

      

      

      :category:`Items:`



        .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/1/properties/examples/items/0:

        :entry:`index[0]`

        :soft:`Type:` string.

        

        



        .. _http://stsci.edu/schemas/yaml-schema/draft-01/allOf/1/properties/examples/items/1:

        :entry:`index[1]`

        :soft:`Type:` string.

        

        

.. only:: html

   :download:`Original schema in YAML <draft-01.yaml>`



.. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray:

ndarray: An *n*-dimensional array or table.
===========================================

:soft:`Type:` :ref:`definitions/inline-data <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data>` :soft:`or` object.

An *n*-dimensional array or table.


There are two ways to store the data in an ndarray.

- Inline in the tree: This is recommended only for small arrays.  In
  this case, the entire ``ndarray`` tag may be a nested list, in
  which case the type of the array is inferred from the content.
  (See the rules for type inference in the ``inline-data``
  definition below.)  The inline data may also be given in the
  ``data`` property, in which case it is possible to explicitly
  specify the ``dtype`` and other properties.

- External to the tree: The data comes from a :ref:`block <block>`
  within the same ASDF file or an external ASDF file referenced by a
  URI.


:category:`Definitions:`



  .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype:

  :entry:`scalar-dtype`

  :soft:`Type:` string :soft:`from` ["int8", "uint8", "int16", "uint16", "int32", "uint32", "int64", "uint64", "float32", "float64", "complex64", "complex128", "bool8"] :soft:`or` array.

  

  Describes the type of a single element.
  
  There is a set of numeric types, each with a single identifier:
  
  - ``int8``, ``int16``, ``int32``, ``int64``: Signed integer
    types, with the given bit size.
  
  - ``uint8``, ``uint16``, ``uint32``, ``uint64``: Unsigned
    integer types, with the given bit size.
  
  - ``float32``: Single-precision floating-point type or
    "binary32", as defined in IEEE 754.
  
  - ``float64``: Double-precision floating-point type or
    "binary64", as defined in IEEE 754.
  
  - ``complex64``: Complex number where the real and imaginary
    parts are each single-precision floating-point ("binary32")
    numbers, as defined in IEEE 754.
  
  - ``complex128``: Complex number where the real and imaginary
    parts are each double-precision floating-point ("binary64")
    numbers, as defined in IEEE 754.
  
  There are two distinct fixed-length string types, which must
  be indicated with a 2-element array where the first element is an
  identifier for the string type, and the second is a length:
  
  - ``ascii``: A string containing ASCII text (all codepoints < 128),
    where each character is 1 byte.
  
  - ``ucs4``: A string containing unicode text in the UCS-4
    encoding, where each character is always 4 bytes long.  Here
    the number of bytes used is 4 times the given length.
  

  :category:`Any of:`



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype/anyOf/0:

    :entry:`—`

    :soft:`Type:` string :soft:`from` ["int8", "uint8", "int16", "uint16", "int32", "uint32", "int64", "uint64", "float32", "float64", "complex64", "complex128", "bool8"].

    

    



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype/anyOf/1:

    :entry:`—`

    :soft:`Type:` array.

    

    

    :category:`Items:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype/anyOf/1/0:

      :entry:`index[0]`

      :soft:`Type:` string :soft:`from` ["ascii", "ucs4"].

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype/anyOf/1/1:

      :entry:`index[1]`

      :soft:`Type:` integer  ≥ 0.

      

      



  .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype:

  :entry:`dtype`

  :soft:`Type:` :ref:`definitions/scalar-dtype <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype>` :soft:`or` array :soft:`of` ( :ref:`definitions/scalar-dtype <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype>` :soft:`or` object ).

  

  The data format of the array elements.  May be a single scalar
  dtype, or may be a nested list of dtypes.  When a list, each field
  may have a name.
  

  :category:`Any of:`



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/0:

    :entry:`—`

    :soft:`Type:` :ref:`definitions/scalar-dtype <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype>`.

    

    



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1:

    :entry:`—`

    :soft:`Type:` array :soft:`of` ( :ref:`definitions/scalar-dtype <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype>` :soft:`or` object ).

    

    

    :category:`Items:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1/items:

      :soft:`Type:` :ref:`definitions/scalar-dtype <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype>` :soft:`or` object.

      

      

      :category:`Any of:`



        .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1/items/anyOf/0:

        :entry:`—`

        :soft:`Type:` :ref:`definitions/scalar-dtype <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/scalar-dtype>`.

        

        



        .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1/items/anyOf/1:

        :entry:`—`

        :soft:`Type:` object.

        

        

        :category:`Properties:`



          .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1/items/anyOf/1/properties/name:

          :entry:`name`

          :soft:`Type:` string ( :soft:`regex` :regexp:`[A-Za-z_][A-Za-z0-9_]*` ).

          

          The name of the field



          .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1/items/anyOf/1/properties/dtype:

          :entry:`dtype`

          :soft:`Type:` :ref:`definitions/dtype <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype>`. Required.

          

          



          .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1/items/anyOf/1/properties/byteorder:

          :entry:`byteorder`

          :soft:`Type:` string :soft:`from` ["big", "little"].

          

          The byteorder for the field.  If not provided, the
          byteorder of the dtype as a whole will be used.
          



          .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1/items/anyOf/1/properties/shape:

          :entry:`shape`

          :soft:`Type:` array :soft:`of` ( integer  ≥ 0 ).

          

          

          :category:`Items:`



            .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype/anyOf/1/items/anyOf/1/properties/shape/items:

            :soft:`Type:` integer  ≥ 0.

            

            



  .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data:

  :entry:`inline-data`

  :soft:`Type:` array :soft:`of` ( number :soft:`or` string :soft:`or` null :soft:`or` :doc:`complex <complex>` :soft:`or` :ref:`definitions/inline-data <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data>` :soft:`or` boolean ).

  

  Inline data is stored in YAML format directly in the tree, rather than
  referencing a binary block.  It is made out of nested lists.
  
  If the dtype of the array is not specified, it is inferred from
  the array contents.  Type inference is supported only for
  homogeneous arrays, not tables.
  
  - If any of the elements in the array are YAML strings, the
    ``dtype`` of the dtype of the entire array is ``ucs4``, with
    the width of the largest string in the column, otherwise...
  
  - If any of the elements in the array are complex numbers, the
    ``dtype`` of the entire column is ``complex128``, otherwise...
  
  - If any of the types in the column are numbers with a decimal
    point, the ``dtype`` of the entire column is ``float64``,
    otherwise..
  
  - If any of the types in the column are integers, the ``dtype``
    of the entire column is ``int64``, otherwise...
  
  - The ``dtype`` of the entire column is ``bool8``.
  

  :category:`Items:`



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data/items:

    :soft:`Type:` number :soft:`or` string :soft:`or` null :soft:`or` :doc:`complex <complex>` :soft:`or` :ref:`definitions/inline-data <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data>` :soft:`or` boolean.

    

    

    :category:`Any of:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data/items/anyOf/0:

      :entry:`—`

      :soft:`Type:` number.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data/items/anyOf/1:

      :entry:`—`

      :soft:`Type:` string.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data/items/anyOf/2:

      :entry:`—`

      :soft:`Type:` null.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data/items/anyOf/3:

      :entry:`—`

      :soft:`Type:` :doc:`complex <complex>`.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data/items/anyOf/4:

      :entry:`—`

      :soft:`Type:` :ref:`definitions/inline-data <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data>`.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data/items/anyOf/5:

      :entry:`—`

      :soft:`Type:` boolean.

      

      

:category:`Any of:`



  .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/0:

  :entry:`—`

  :soft:`Type:` :ref:`definitions/inline-data <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data>`.

  

  



  .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1:

  :entry:`—`

  :soft:`Type:` object.

  

  

  :category:`Properties:`



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/source:

    :entry:`source`

    :soft:`Type:` integer :soft:`or` string ( :soft:`format` uri ).

    

    The source of the data.
    
    - If an integer:
    
        - If positive, the zero-based index of the block within the
          same file.
    
        - If negative, the index from the last block within the same
          file.  For example, a source of ``-1`` corresponds to the
          last block in the same file.
    
    - If a string, a URI to an external ASDF file containing the
      block data.  Relative URIs and ``file:`` and ``http:``
      protocols must be supported.  Other protocols may be supported
      by specific library implementations.
    
      The ability to reference block data in an external ASDF file
      is intentionally limited to the first block in the external
      ASDF file, and is intended only to support the needs of
      :ref:`exploded`.  For the more general case of referencing
      data in an external ASDF file, use tree :ref:`references`.
    

    :category:`Any of:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/source/anyOf/0:

      :entry:`—`

      :soft:`Type:` integer.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/source/anyOf/1:

      :entry:`—`

      :soft:`Type:` string ( :soft:`format` uri ).

      

      



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/data:

    :entry:`data`

    :soft:`Type:` :ref:`definitions/inline-data <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/inline-data>`.

    

    The data for the array inline.
    
    If ``dtype`` and/or ``shape`` are also provided, they must
    match the data here and can be used as a consistency check.
    ``strides``, ``offset`` and ``byteorder`` are meaningless
    when ``data`` is provided.
    



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/shape:

    :entry:`shape`

    :soft:`Type:` array :soft:`of` ( integer  ≥ 0 :soft:`or` any :soft:`from` ["*"] ).

    

    The shape of the array.
    
    The first entry may be the string ``*``, indicating that the
    length of the first index of the array will be automatically
    determined from the size of the block.  This is used for
    streaming support.
    

    :category:`Items:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/shape/items:

      :soft:`Type:` integer  ≥ 0 :soft:`or` any :soft:`from` ["*"].

      

      

      :category:`Any of:`



        .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/shape/items/anyOf/0:

        :entry:`—`

        :soft:`Type:` integer  ≥ 0.

        

        



        .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/shape/items/anyOf/1:

        :entry:`—`

        :soft:`Type:` any :soft:`from` ["*"].

        

        



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/dtype:

    :entry:`dtype`

    :soft:`Type:` :ref:`definitions/dtype <http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/definitions/dtype>`.

    

    The data format of the array elements.
    



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/byteorder:

    :entry:`byteorder`

    :soft:`Type:` string :soft:`from` ["big", "little"].

    

    The byte order (big- or little-endian) of the array data.
    

    :soft:`Default:` "big"



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/offset:

    :entry:`offset`

    :soft:`Type:` integer  ≥ 0.

    

    The offset, in bytes, within the data for this start of this view.
    

    :soft:`Default:` 0



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/strides:

    :entry:`strides`

    :soft:`Type:` array :soft:`of` ( integer  ≥ 1 :soft:`or` integer  ≤ -1 ).

    

    The number of bytes to skip in each dimension.  If not provided, the array is assumed by be contiguous and in C order.  If provided, must be the same length as the shape property.
    

    :category:`Items:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/strides/items:

      :soft:`Type:` integer  ≥ 1 :soft:`or` integer  ≤ -1.

      

      

      :category:`Any of:`



        .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/strides/items/anyOf/0:

        :entry:`—`

        :soft:`Type:` integer  ≥ 1.

        

        



        .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/strides/items/anyOf/1:

        :entry:`—`

        :soft:`Type:` integer  ≤ -1.

        

        



    .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/mask:

    :entry:`mask`

    :soft:`Type:` number :soft:`or` :doc:`complex <complex>` :soft:`or` :doc:`ndarray <ndarray>`.

    

    Describes how missing values in the array are stored.  If a scalar number, that number is used to represent missing values. If an ndarray, the given array provides a mask, where non-zero values represent missing values in this array.  The mask array must be broadcastable to the dimensions of this array.
    

    :category:`Any of:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/mask/anyOf/0:

      :entry:`—`

      :soft:`Type:` number.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/mask/anyOf/1:

      :entry:`—`

      :soft:`Type:` :doc:`complex <complex>`.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/core/ndarray/anyOf/1/properties/mask/anyOf/2:

      :entry:`—`

      :soft:`Type:` :doc:`ndarray <ndarray>`.

      

      

:category:`Examples:`

An inline array, with implicit data type::

  !core/ndarray
    [[1, 0, 0],
     [0, 1, 0],
     [0, 0, 1]]
  

An inline array, with an explicit data type::

  !core/ndarray
    dtype: float64
    data:
      [[1, 0, 0],
       [0, 1, 0],
       [0, 0, 1]]
  

An inline table, where the types of each column are automatically detected::

  !core/ndarray
    [[M110, 110, 205, And],
     [ M31,  31, 224, And],
     [ M32,  32, 221, And],
     [M103, 103, 581, Cas]]
  

An inline table, where the types of each column are explicitly specified::

  !core/ndarray
    dtype: [['ascii', 4], uint16, uint16, ['ascii', 4]]
    data:
      [[M110, 110, 205, And],
       [ M31,  31, 224, And],
       [ M32,  32, 221, And],
       [M103, 103, 581, Cas]]
  

A double-precision array, in contiguous memory in a block within the same file::

  !core/ndarray
    source: 0
    shape: [1024, 1024]
    dtype: float64
  

A view of a tile in that image::

  !core/ndarray
    source: 0
    shape: [256, 256]
    dtype: float64
    strides: [8192, 8]
    offset: 2099200
  

A table dtype, with nested columns for a coordinate in (ra, dec), and a 3x3 convolution kernel::

  !core/ndarray
    source: 0
    shape: [64]
    dtype:
      - name: coordinate
        dtype:
          - name: ra
            dtype: float64
          - name: dec
            dtype: float64
      - name: kernel
        dtype: float32
        shape: [3, 3]
  

An array in Fortran order::

  !core/ndarray
    source: 0
    shape: [1024, 1024]
    dtype: float64
    strides: [8192, 8]
  

An array where values of -999 are treated as missing::

  !core/ndarray
    source: 0
    shape: [256, 256]
    dtype: float64
    mask: -999
  

An array where another array is used as a mask::

  !core/ndarray
    source: 0
    shape: [256, 256]
    dtype: float64
    mask: !core/ndarray
      source: 1
      shape: [256, 256]
      dtype: bool8
  

An array where the data is stored in the first block in another ASDF file.::

  !core/ndarray
    source: external.asdf
    shape: [256, 256]
    dtype: float64
  

.. only:: html

   :download:`Original schema in YAML <ndarray.yaml>`

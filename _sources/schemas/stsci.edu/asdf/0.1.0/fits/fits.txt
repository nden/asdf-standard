

.. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits:

fits: A FITS file inside of an ASDF file.
=========================================

:soft:`Type:` array :soft:`of` ( object ).

A FITS file inside of an ASDF file.


This schema is useful for distributing ASDF files that can
automatically be converted to FITS files by specifying the exact
content of the resulting FITS file.

Not all kinds of data in FITS are directly representable in ASDF.
For example, applying an offset and scale to the data using the
``BZERO`` and ``BSCALE`` keywords.  In these cases, it will not be
possible to store the data in the native format from FITS and also
be accessible in its proper form in the ASDF file.


:category:`Items:`



  .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items:

  :soft:`Type:` object.

  

  Each item represents a single header/data unit (HDU).
  

  :category:`Properties:`



    .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/header:

    :entry:`header`

    :soft:`Type:` array :soft:`of` ( array 0 ≤ *len* ≤ 3 ). Required.

    

    A list of the keyword/value/comment triples from the header, in the order they appear in the FITS file.
    

    :category:`Items:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/header/items:

      :soft:`Type:` array 0 ≤ *len* ≤ 3.

      

      

      :category:`Items:`



        .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/header/items/0:

        :entry:`index[0]`

        :soft:`Type:` string ( *len* ≤ 8 :soft:`regex` :regexp:`[A-Z0-9]*` ).

        

        The keyword.



        .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/header/items/1:

        :entry:`index[1]`

        :soft:`Type:` string ( *len* ≤ 60 ) :soft:`or` number :soft:`or` boolean.

        

        The value.

        :category:`Any of:`



          .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/header/items/1/anyOf/0:

          :entry:`—`

          :soft:`Type:` string ( *len* ≤ 60 ).

          

          



          .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/header/items/1/anyOf/1:

          :entry:`—`

          :soft:`Type:` number.

          

          



          .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/header/items/1/anyOf/2:

          :entry:`—`

          :soft:`Type:` boolean.

          

          



        .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/header/items/2:

        :entry:`index[2]`

        :soft:`Type:` string ( *len* ≤ 60 ).

        

        The comment.



    .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/data:

    :entry:`data`

    :soft:`Type:` :doc:`ndarray <../core/ndarray>` :soft:`or` null.

    

    The data part of the HDU.

    :soft:`Default:` null

    :category:`Any of:`



      .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/data/anyOf/0:

      :entry:`—`

      :soft:`Type:` :doc:`ndarray <../core/ndarray>`.

      

      



      .. _http://stsci.edu/schemas/asdf/0.1.0/fits/fits/items/properties/data/anyOf/1:

      :entry:`—`

      :soft:`Type:` null.

      

      

:category:`Examples:`

A simple FITS file with a primary header and two extensions::

  !fits/fits
      - header:
        - [SIMPLE, true, conforms to FITS standard]
        - [BITPIX, 8, array data type]
        - [NAXIS, 0, number of array dimensions]
        - [EXTEND, true]
        - []
        - ['', Top Level MIRI Metadata]
        - []
        - [DATE, '2013-08-30T10:49:55.070373', The date this file was created (UTC)]
        - [FILENAME, MiriDarkReferenceModel_test.fits, The name of the file]
        - [TELESCOP, JWST, The telescope used to acquire the data]
        - []
        - ['', Information about the observation]
        - []
        - [DATE-OBS, '2013-08-30T10:49:55.000000', The date the observation was made (UTC)]
      - data: !core/ndarray
          dtype: float32
          shape: [2, 3, 3, 4]
          source: 0
        header:
        - [XTENSION, IMAGE, Image extension]
        - [BITPIX, -32, array data type]
        - [NAXIS, 4, number of array dimensions]
        - [NAXIS1, 4]
        - [NAXIS2, 3]
        - [NAXIS3, 3]
        - [NAXIS4, 2]
        - [PCOUNT, 0, number of parameters]
        - [GCOUNT, 1, number of groups]
        - [EXTNAME, SCI, extension name]
        - [BUNIT, DN, Units of the data array]
      - data: !core/ndarray
          dtype: float32
          shape: [2, 3, 3, 4]
          source: 1
        header:
        - [XTENSION, IMAGE, Image extension]
        - [BITPIX, -32, array data type]
        - [NAXIS, 4, number of array dimensions]
        - [NAXIS1, 4]
        - [NAXIS2, 3]
        - [NAXIS3, 3]
        - [NAXIS4, 2]
        - [PCOUNT, 0, number of parameters]
        - [GCOUNT, 1, number of groups]
        - [EXTNAME, ERR, extension name]
        - [BUNIT, DN, Units of the error array]
  

.. only:: html

   :download:`Original schema in YAML <fits.yaml>`

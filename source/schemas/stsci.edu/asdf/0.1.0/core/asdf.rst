

.. _http://stsci.edu/schemas/asdf/0.1.0/core/asdf:

asdf: 
======

:soft:`Type:` object.



This schema contains the top-level attributes for every ASDF file.


:category:`Properties:`



  .. _http://stsci.edu/schemas/asdf/0.1.0/core/asdf/properties/data:

  :entry:`data`

  :soft:`Type:` :doc:`ndarray <ndarray>`.

  

  The data array corresponds to the main science data array in the
  file.  Oftentimes, the data model will be much more complex than
  a single array, but this array will be used by applications that
  just want to convert to a display an image or preview of the
  file.  It is recommended, but not required, that it is a
  2-dimensional image array.
  



  .. _http://stsci.edu/schemas/asdf/0.1.0/core/asdf/properties/fits:

  :entry:`fits`

  :soft:`Type:` :doc:`fits <../fits/fits>`.

  

  A way to specify exactly how this ASDF file should be converted
  to FITS.
  

.. only:: html

   :download:`Original schema in YAML <asdf.yaml>`

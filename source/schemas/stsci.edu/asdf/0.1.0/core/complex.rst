

.. _http://stsci.edu/schemas/asdf/0.1.0/core/complex:

complex: Complex number value.
==============================

:soft:`Type:` string ( :soft:`regex` :regexp:`([-+]?[0-9]*\\.?[0-9]+([eE][-+]?[0-9]+)?)?([-+][0-9]*\\.?[0-9]+([eE][-+]?[0-9]+)?[JjIi])?` ).

Complex number value.

Represents a complex number matching the following EBNF grammar::

  plus-or-minus = "+" | "-"
  suffix        = "J" | "j" | "I" | "i"
  complex       = [ieee754] [plus-or-minus ieee754 suffix]

Where ``ieee754`` is a floating point number in IEEE 754 decimal
format.


:category:`Examples:`

1 real, -1 imaginary::

  !core/complex 1-1j

0 real, 1 imaginary::

  !core/complex 1J

-1 real, 0 imaginary::

  !core/complex -1

.. only:: html

   :download:`Original schema in YAML <complex.yaml>`

The connection element information item
=======================================

Connection element information items (referred to in this specification
as connection elements) are element information items in the CellML 1.0,
CellML 1.1, or CellML 1.2 namespace with local name equal to connection.

Specific information items
--------------------------

1. Every connection element MUST contain exactly one ``map_components``
   :doc:`element <map-components-element-item>`.

2. Every connection element MUST contain one or more ``map_variables``
   :doc:`element <map-variables-element-item>`.

.. todo::

   Find a way to get ``map_components`` and ``map_variables`` as part
   of the link. As far as I can see, this would require nested inline
   markup to be possible and it would seem that it isn't (see
   http://docutils.sourceforge.net/FAQ.html#is-nested-inline-markup-possible).

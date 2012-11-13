.. index::
   pair: component_ref; element

The ``component_ref`` element information item
==============================================

``component_ref`` element information items (referred to in this
specification as ``component_ref`` elements) are element information items
in the CellML 1.2 namespace with local name equal to ``component_ref``.

Specific information items
--------------------------

1. Every component\_ref element MUST contain an attribute information
   item in the empty namespace and with local name component. The value
   of this attribute MUST be a valid CellML Identifier, and MUST match
   the name attribute on a component or import component element in the
   CellML Infoset.

2. Every component\_ref element MAY in turn contain zero or more
   component\_ref element children. In addition, component\_ref elements
   that are children of encapsulation elements MUST contain at least one
   component\_ref element child.



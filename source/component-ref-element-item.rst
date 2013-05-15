The component\_ref element information item
===========================================

Component\_ref element information items (referred to in this
specification as component\_ref elements) are element information items
in the CellML 1.1 namespace with local name equal to component\_ref.

Specific information items
--------------------------

1. Every component\_ref element MUST contain an attribute information
   item in the empty namespace and with local name component. The value
   of this attribute MUST be a valid CellML identifier, and MUST match
   the name attribute on a component or import component element in the
   CellML Infoset.

2. Every component\_ref element MAY in turn contain zero or more
   component\_ref element children.

3. In addition, component\_ref elements
   which are children of group elements MUST contain at least one
   component\_ref element child.



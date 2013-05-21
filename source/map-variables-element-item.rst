The map\_variables element information item
===========================================

Map\_variables element information items (referred to in this
specification as map\_variables elements) are element information items
in the CellML 1.1 namespace with local name equal to map\_variables, and
which appear as a child of a connection element.

Specific information items
--------------------------

1. Each map\_variables element MUST contain a variable\_1 attribute in
   the empty namespace. The
   value of the variable\_1 attribute MUST be a valid CellML identifier.
   The value of this attribute MUST be equal to the name attribute on a
   variable element child of the component element referenced by the
   component\_1 attribute on the map\_components element which is a
   sibling of this element.

2. Each map\_variables element MUST contain a variable\_2 attribute in
   the empty namespace. The
   value of the variable\_2 attribute MUST be a valid CellML identifier.
   The value of this attribute MUST be equal to the name attribute on a
   variable element child of the component element referenced by the
   component\_2 attribute on the map\_components element which is a
   sibling of this element.



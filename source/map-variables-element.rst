The map\_variables element information item
===========================================

map\_variables element information items (referred to in this
specification as map\_variables elements) are element information items
in the CellML 1.2 namespace with local name equal to map\_variables
which appear as a child of a connection element.

Specific information items
--------------------------

1. Each map\_variables element MUST contain a variable\_1 attribute. The
   value of the variable\_1 attribute MUST be a valid CellML Identifier.
   The value of this attribute MUST be equal to the name attribute on a
   variable element child of the component element referenced by the
   component\_1 attribute on the connection element parent.

2. Each map\_variables element MUST contain a variable\_2 attribute. The
   value of the variable\_2 attribute MUST be a valid CellML Identifier.
   The value of this attribute MUST be equal to the name attribute on a
   variable element child of the component element referenced by the
   component\_2 attribute on the connection element parent.



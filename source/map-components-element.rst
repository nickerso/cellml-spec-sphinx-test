The map\_components element information item
============================================

map\_components element information items (referred to in this
specification as map\_components elements) are element information items
in the CellML 1.1 namespace with local name equal to map\_components,
and which appear as a child of a connection element.

Specific information items
--------------------------

1. Each map\_components element MUST contain a component\_1 attribute.
   The value of the component\_1 attribute MUST be a valid CellML
   Identifier. The value of this attribute MUST be equal to the name
   attribute on a component or import component element in the CellML
   Infoset.

2. Each map\_components element MUST contain a component\_2 attribute.
   The value of the component\_2 attribute MUST be a valid CellML
   Identifier. The value of this attribute MUST be equal to the name
   attribute on a component or import component element in the CellML
   Infoset. It MUST NOT be equal to the value of the component\_1
   attribute.



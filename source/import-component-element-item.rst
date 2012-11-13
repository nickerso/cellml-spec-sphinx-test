The import component element information item
=============================================

Import component element information items (referred to in this
specification as import component elements) are element information
items in the CellML 1.2 namespace with local name equal to component
which appear as children of import elements.

Specific information items
--------------------------

1. Every import component element MUST contain a name attribute in the
   empty namespace. The value of the name attribute MUST be a valid
   CellML identifier. The value of the name attribute MUST NOT be
   identical to the name attribute of any other import component or
   component element in the CellML Infoset.

2. Every import component element MUST contain a component\_ref
   attribute in the empty namespace. The value of the component\_ref
   attribute MUST be a valid CellML identifier. The value of the
   component\_ref attribute MUST match the value of the name attribute
   on a component or import component element in the imported CellML
   Infoset. The value of the component\_ref attribute MUST NOT match the
   value of the component\_ref attribute on any sibling import component
   element.



The connection element information item
=======================================

Connection element information items (referred to in this specification
as connection elements) are element information items in the CellML 1.2
namespace with local name equal to connection.

Specific information items
--------------------------

1. Every connection element MUST contain a component\_1 attribute in the
   empty namespace. The value of the component\_1 attribute MUST be a
   valid CellML Identifier. The value of this attribute MUST be equal to
   the name attribute on a component or import component element in the
   CellML Infoset.

2. Every connection element MUST contain a component\_2 attribute in the
   empty namespace. The value of the component\_2 attribute MUST be a
   valid CellML Identifier. The value of this attribute MUST be equal to
   the name attribute on a component or import component element in the
   CellML Infoset.

3. Every connection element MUST contain one or more map\_variables
   elements (?).



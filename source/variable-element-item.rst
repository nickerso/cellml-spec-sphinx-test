The variable element information item
=====================================

Variable element information items (referred to in this specification as
variable elements) are element information items in the CellML 1.1
namespace with local name equal to variable, and which appear as a child
of a component element.

Specific information items
--------------------------

1. Every variable element MUST have each of the following attribute
   information items in the empty namespace:

   1. The name attribute. The value of the name attribute MUST be a
      valid CellML Identifier. The value of the name attribute MUST NOT
      be identical to the name attribute on any sibling variable
      element.

   2. The units attribute. The value of the units attribute MUST be a
      valid CellML Identifier, and MUST meet the constraints described
      in ?.

2. Every variable element MAY contain one or more of the following
   attribute information items in the empty namespace:

   1. The public\_interface attribute. If the attribute is present, it
      MUST have value in, out, or none.

   2. The private\_interface attribute. If the attribute is present, it
      MUST have value in, out, or none. It MUST NOT have value in if the
      public\_interface attribute also has the value in.

   3. The initial\_value attribute. If the attribute is present, it MUST
      meet the requirements described in ?.

The variable element information item
=====================================

Variable element information items (referred to in this specification as
variable elements) are element information items in the CellML 1.2
namespace with local name equal to variable which appear as a child of a
component element.

Specific information items
--------------------------

1. Every variable element MUST have each of the following attribute
   information items in the empty namespace:

   1. The name attribute. The value of the name attribute MUST be a
      valid CellML Identifier. The value of the name attribute MUST NOT
      be identical to the name attribute on any sibling variable
      element.

   2. The type attribute. The primary specification does not place any
      restrictions on the value of the type attribute, but secondary
      specifications SHOULD define the types supported in that secondary
      specification.

      A type attribute value of real SHALL be interpreted as indicating
      that the variable is real valued. A type attribute value of
      boolean SHALL be interpretated as indicating that there are two
      possible values, true and false.

2. Every variable element MAY contain one or more of the following
   attribute information items in the empty namespace:

   1. The public\_interface attribute. If the attribute is present, it
      MUST have value yes or no.

   2. The private\_interface attribute. If the attribute is present, it
      MUST have value yes or no.

   3. The units attribute. If the attribute is present, the value MUST
      be a valid CellML Identifier, and MUST meet the constraints
      described in ?. This attribute MUST be present if the type
      attribute has the value real.



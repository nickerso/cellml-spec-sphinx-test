The units element information item
==================================

Units element information items (referred to in this specification as
units elements) are element information items in the CellML 1.1
namespace with local name equal to units, and with either a component or
model element as their parent.

Specific information items
--------------------------

1. Every units element MUST contain a name attribute in the empty
   namespace. The value of the name attribute MUST be a valid CellML
   identifier.

   1. Where the parent of the units element is a model element,
      the value of the name attribute MUST NOT be identical to the name
      attribute of any other units element child of that model element, or
      of any import units element in the CellML Infoset.

   2. Where the parent of the units element is a component element, the
      value of the name attribute MUST NOT be identical to the name
      attribute of any other units element child of that component element.

   3. In any case, the value of the name attribute MUST NOT be equal to a
      cell in the name column of ?.

2. A units element MAY contain a base\_units attribute in the empty
   namespace. If present, the value of the base\_units attribute MUST be
   equal to either yes or no. If the attribute is present and equal to
   yes, then the following paragraph does not apply.

3. A units element MAY contain one or more unit element children (?).



The model element information item
==================================

Top-level of CellML Infosets
----------------------------

The top-level element information item in a CellML Infoset MUST be an
element information item in the CellML 1.2 namespace, with local name
model. This element information item is referred to in this
specification as the model element.

Specific information items
--------------------------

1. Every model element MUST contain a name attribute in the empty
   namespace. The value of the name attribute MUST be a valid CellML
   identifier, and SHALL be interpreted as a unique identifier for the
   CellML Infoset.

2. A model element MAY contain zero or more additional specific
   information item children, each of which MUST be of one of the
   following types:

   1. a component element (?),

   2. a connection element (?),

   3. an encapsulation element (?),

   4. an import element (?),

   5. a units element (?)



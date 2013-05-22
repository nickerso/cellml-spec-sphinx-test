The model element information item
==================================

Top-level of CellML infosets
----------------------------

The top-level element information item in a CellML infoset MUST be an
element information item in the CellML 1.0, CellML 1.1 or CellML 1.2
namespace, with local name ``model``. This element information item is
referred to in this specification as the model element.

Specific information items
--------------------------

1. Every model element MUST contain a name attribute in the empty
   namespace. The value of the name attribute MUST be a valid CellML
   identifier, and SHALL be interpreted as a unique identifier for the
   CellML infoset.

2. A model element MAY contain zero or more additional specific
   information item children, each of which MUST be of one of the
   following types:

   1. a :doc:`component element <component-element-item>`;

   2. a :doc:`connection element <connection-element-item>`;

   3. a :doc:`group element <group-element-item>`;

   4. an :doc:`import element <import-element-item>`; or

   5. a :doc:`units element <units-element-item>`.

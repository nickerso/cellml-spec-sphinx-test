The component element information item
======================================

Component element information items (referred to in this specification
as component elements) are element information items in the CellML 1.0,
CellML 1.1, or CellML 1.2 namespace with local name ``component``, and
which appear as a child of a model element.

Specific information items
--------------------------

1. Every component element MUST contain a name attribute in the empty
   namespace. The value of the name attribute MUST be a valid CellML
   identifier. The value of the name attribute MUST NOT be identical to
   the name attribute on any other component element or import component
   element in the CellML infoset.

2. A component element MAY contain zero or more specific information
   item children, each of which MUST be of one of the following types:

   1. a :doc:`variable element <variable-element-item>`;

   2. an element information item in the MathML namespace, and with
      local name ``math``, which MUST be the top-level of a content MathML
      tree, as described in `MathML 2.0 <http://www.w3.org/TR/2003/REC-MathML2-20031021/>`_; or

   3. a :doc:`units element <units-element-item>`.

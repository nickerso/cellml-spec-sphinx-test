General matters
===============

CellML and XML
--------------

1. Every CellML Infoset SHALL be represented in an XML document that
   conforms with the well-formedness requirements of the XML 1.0
   specification ?.

2. In this document, the remaining provisions relating to CellML
   Infosets shall be interpreted as being constraints on the XML
   Information Set represented by that CellML Infoset.

Equivalent CellML Infosets
--------------------------

1. Two CellML Infosets shall be equivalent if one can be transformed to
   another by making zero or more of the following changes:

   1. Changing the representation the XML file in ways that do not
      change the XML Information Set represented

   2. Adding, removing, and/or modifying comment information items.

   3. Changing (inserting, removing, and/or modifying) one or more
      namespace information items, and/or modifying the prefix of one or
      more information items, without changing the namespace that any
      information item is in.

   4. The following paragraph applies only to character information
      items for which all ancestor element information items are in the
      CellML, the MathML or the RDF namespace.

      Inserting or removing character information items that consist
      entirely of whitespace characters, changing the number of
      whitespace characters in such an information item, or changing the
      number of whitespace characters at the beginning or end of a
      character information item.

2. CellML Processing Software MUST treat CellML Infosets that are
   equivalent according to the above rules in an identical fashion.

Character information items
---------------------------

An element information item in the CellML namespace MUST NOT contain any
character information items, except for character information items that
consist entirely of whitespace characters.

Use of namespaces
-----------------

1. CellML Infosets MUST NOT contain any element or attribute information
   items, except as permitted in this specification.

2. CellML Infosets MUST NOT contain any character information items that
   are children of element information items in a CellML namespace,
   except as permitted in this specification.

3. CellML Processing Software SHOULD NOT attempt to process CellML
   Infosets that contain information items in a CellML namespace other
   than the CellML 1.2 namespaces, unless they have been designed to
   support the version of CellML corresponding to the namespace.

4. CellML Infosets MUST NOT contain any element information items in the
   RDF namespace, unless:

   1. the element information item or one of its ancestors is an element
      information item in the RDF namespace, with local name
      RDF
      (the RDF element information item), and,
   2. the RDF element information item forms the top-level of a valid
      RDF/XML tree, per production 7.2.9 in
      .

5. CellML Infosets MUST NOT contain any element information items in the
   MathML namespace, unless:

   1. the element information item or one of its ancestors is an element
      information item in the MathML namespace, with local name
      math
      (the math element information item), and,
   2. the math element information item forms the top-level of a valid
      MathML tree, as described in
      .

Extension information items
---------------------------

1. CellML Infosets MAY contain zero or more element or attribute
   information items in an extension namespace (extension information
   items), as children of CellML Information Items.

2. Information items in the empty namespace, that appear as children of
   extension element information items, SHALL also be treated as
   extension information items.

3. Extension information items MAY contain extension information items
   as their children. In addition, extension elements MAY contain
   presentation MathML children. For the avoidance of doubt, it is noted
   that extension information items MAY also contain any other
   information items not disallowed by this specification or a
   referenced normative specification.

4. CellML Processing Software MUST NOT raise an error solely because it
   encounters an unrecognised extension element.

5. CellML Processing Software that reads CellML and then writes a
   modified version back out SHOULD preserve unrecognised extension
   information items when the parent information item is not modified.

6. CellML Processing Software MUST NOT allow the mathematical
   interpretation of a CellML Model to be altered by any information
   present in extension information items.

Identifiers
-----------

1. Any element information item in the CellML namespace MAY contain an
   attribute information item with name id, in the CellML Metadata
   Namespace. This attribute information item SHALL be treated as having
   attribute type ID, as defined in section 3.3.1 of ?.

Specific information items
--------------------------

1. A specific information item is an information item that is not:

   1. a comment information item, or,

   2. a character information item, or,

   3. an extension information item or a descendant of such an
      information item, or,

   4. a namespace information item.

2. Specific information items MUST NOT appear in a CellML Infoset except
   where explicitly allowed by this specification, or where allowed by a
   normative specification referenced by this specification.

3. The order in which specific information items appear as children of
   an element information item defined in this specification SHALL NOT
   affect the interpretation of the CellML Model.

RDF Element Information Items
-----------------------------

1. Every element information item in the CellML namespace MAY contain
   zero or more RDF Element Information Item children.

2. An RDF Element Information Item SHALL be an element item in the RDF
   namespace, with local name ``RDF`` (the RDF element information
   item), and MUST form the top-level of a valid RDF/XML tree, per
   production 7.2.9 in ?, and SHALL be a child of an element information
   item in the CellML namespace.

3. CellML Processing Software MUST NOT allow the mathematical
   interpretation of a CellML Model to be altered by any information
   present in RDF data.

4. The "set of all RDF triples" associated with a CellML Infoset SHALL
   refer to the union of all sets of RDF triples produced by parsing all
   the RDF Element Information Items according to the RDF/XML
   specification.

5. Two CellML Infosets that differ only by the addition, removal, or
   modification of RDF Element Information Items (or Information Items
   descended from them), but that have the same set of all RDF triples,
   SHALL be termed RDF-equivalent CellML Infosets.

6. CellML Processing Software MUST NOT treat RDF-equivalent CellML
   Infosets differently.



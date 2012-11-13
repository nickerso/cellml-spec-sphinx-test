The import element information item
===================================

Import element information items (referred to in this specification as
import elements) are element information items in the CellML 1.2
namespace with local name equal to import.

Specific information items
--------------------------

1. Every import element MUST contain the following attribute information
   items:

   1. An attribute information item in the namespace
      http://www.w3.org/1999/xlink, and with local name href. The value
      of this attribute SHALL be a valid locator href, as defined in
      section 5.4 of the XLink specification (?). The href attribute
      SHALL be treated according to the XLink specification, by applying
      the rules for simple-type elements. When describing an import
      element or one of its children, the phrase "imported CellML
      Infoset" SHALL refer to the CellML Infoset obtained by parsing the
      XML document referenced by the href attribute.

   2. An attribute information with local name ``name``, in the CellML
      1.2 namespace. The value of the name attribute MUST be a valid
      CellML Identifier. The value of the name attribute MUST NOT be
      identical to the name attribute on any sibling import element.

2. 
3. Imported CellML Infosets make up part of the model, so for the entire
   model to be valid, all imported CellML Infosets MUST also be valid
   under this specification.

4. Every import element MAY contain zero or more specific information
   children, each of which MUST be of one of the following types:

   1. an import component element (?).

   2. an import units element (?).



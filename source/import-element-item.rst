The import element information item
===================================

Import element information items (referred to in this specification as
import elements) are element information items in the CellML 1.1
namespace with local name equal to import.

Specific information items
--------------------------

1. Every import element MUST contain an attribute information item in
   the namespace \http://www.w3.org/1999/xlink, and with local name href.
   The value of this attribute SHALL be a valid locator href, as defined
   in section 5.4 of the XLink specification (?). The href attribute
   SHALL be treated according to the XLink specification, by applying
   the rules for simple-type elements. When describing an import element
   or one of its children, the phrase "imported CellML Infoset" SHALL
   refer to the CellML Infoset obtained by parsing the XML document
   referenced by the href attribute.

2. Every import element MAY contain zero or more specific information
   children, each of which MUST be of one of the following types:

   1. an import component element (?),

   2. an import units element (?).

3. The imported CellML Infoset SHALL NOT be equivalent to this CellML
   Infoset. Any CellML Infoset imported, directly or indirectly, by the
   imported CellML Infoset SHALL NOT be equivalent to this CellML Infoset.

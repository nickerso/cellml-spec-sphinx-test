Definitions
===========

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in ?.

The key phrase "information item", as well as any specific type of
information item such as an "element information item", are to be
interpreted as described in ?.

CellML Infoset
    An XML Information Set containing a hierarchy of information items
    conforming to the rules described in this document.

CellML Model
    A mathematical model represented by a hierarchy of one or more
    CellML Infosets, according to the rules described in this document.

CellML Processing Software
    Software that processes CellML in accordance with the rules of this
    document.

Namespace
    An XML namespace, as defined in ?.

CellML Namespace
    Any namespace starting with http://www.cellml.org/cellml/

CellML 1.2 Namespace
    The namespace http://www.cellml.org/cellml/1.2#

MathML Namespace
    The namespace http://www.w3.org/1998/Math/MathML

RDF Namespace
    The namespace http://www.w3.org/1999/02/22-rdf-syntax-ns#

CellML Metadata Namespace
    The namespace http://www.cellml.org/metadata/1.0#

Extension Namespace
    Any namespace that is not a CellML namespace, and is not the RDF
    namespace, the MathML namespace,
    http://www.w3.org/XML/1998/namespace, http://www.w3.org/2000/xmlns/,
    http://www.w3.org/1999/xlink, or the empty namespace.

Basic Latin alphabetic character
    A Unicode character in the range U+0041 to U+005A or in the range
    U+0061 to U+007A.

European numeric character
    A Unicode character in the range U+0030 to U+0039.

Basic Latin alphanumeric character
    A Unicode character that is either a basic Latin alphabetic
    character or a European numeric character.

Basic Latin underscore
    The Unicode character U+005F.

Whitespace character
    Any one of the Unicode characters U+0020, U+0009, U+000D or U+000A.

RDF Triple
    As defined in ?.

Independent variable set
    A set of zero variables in the model (each represented by a set of
    one or more connected CellML variables) that are defined externally
    to the model.



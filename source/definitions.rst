Definitions
===========

The key words "**MUST**", "**MUST NOT**", "**REQUIRED**", "**SHALL**", "**SHALL NOT**",
"**SHOULD**", "**SHOULD NOT**", "**RECOMMENDED**", "**MAY**", and "**OPTIONAL**" in this
document are to be interpreted as described in `RFC 2119 <http://www.apps.ietf.org/rfc/rfc2119.html>`_.

The key phrase "information item", as well as any specific type of
information item such as an "element information item", are to be
interpreted as described in `XML Information Set <http://www.w3.org/TR/xml-infoset/>`_.

CellML Infoset
    An XML Information Set containing a hierarchy of information items
    conforming to the rules described in this document.

CellML Model
    A mathematical model represented by a hierarchy of one or more
    CellML Infosets, according to the rules described in this document.

CellML Processing Software
    Software which processes CellML in accordance with the rules of this
    document.

Namespace
    An XML namespace, as defined in `Namespaces in XML <http://www.w3.org/TR/REC-xml-names/>`_.

CellML Namespace
    Any namespace starting with `http://www.cellml.org/cellml/ <http://www.cellml.org/cellml/>`_.

CellML 1.1 Namespace
    The namespace `http://www.cellml.org/cellml/1.1# <http://www.cellml.org/cellml/1.1#>`_.

CellML 1.2 Namespace
    The namespace `http://www.cellml.org/cellml/1.2# <http://www.cellml.org/cellml/1.2#>`_.

MathML Namespace
    The namespace `http://www.w3.org/1998/Math/MathML <http://www.w3.org/1998/Math/MathML>`_.

RDF Namespace
    The namespace `http://www.w3.org/1999/02/22-rdf-syntax-ns# <http://www.w3.org/1999/02/22-rdf-syntax-ns#>`_.

CellML Metadata Namespace
    The namespace `http://www.cellml.org/metadata/1.0# <http://www.cellml.org/metadata/1.0#>`_.

Extension Namespace
    Any namespace which is not a CellML namespace, and is not the RDF
    namespace, the MathML namespace,
    `http://www.w3.org/XML/1998/namespace <http://www.w3.org/XML/1998/namespace>`_,
    `http://www.w3.org/2000/xmlns/ <http://www.w3.org/2000/xmlns/>`_,
    `http://www.w3.org/1999/xlink <http://www.w3.org/1999/xlink>`_,
    or the empty namespace.

CellML Information Item
    Any information item in a CellML namespace.

Basic Latin alphabetic character
    A Unicode character in the range `U+0041 <http://www.fileformat.info/info/unicode/char/0041/index.htm>`_
    to `U+005A <http://www.fileformat.info/info/unicode/char/005A/index.htm>`_ or in the range
    `U+0061 <http://www.fileformat.info/info/unicode/char/0061/index.htm>`_ to
    `U+007A <http://www.fileformat.info/info/unicode/char/007A/index.htm>`_.

European numeric character
    A Unicode character in the range `U+0030 <http://www.fileformat.info/info/unicode/char/0030/index.htm>`_
    to `U+0039 <http://www.fileformat.info/info/unicode/char/0039/index.htm>`_.

Basic Latin alphanumeric character
    A Unicode character which is either a basic Latin alphabetic
    character or a European numeric character.

Basic Latin underscore
    The Unicode character `U+005F <http://www.fileformat.info/info/unicode/char/005F/index.htm>`_.

Whitespace character
    Any one of the Unicode characters `U+0020 <http://www.fileformat.info/info/unicode/char/0020/index.htm>`_,
    `U+0009 <http://www.fileformat.info/info/unicode/char/0009/index.htm>`_,
    `U+000D <http://www.fileformat.info/info/unicode/char/000D/index.htm>`_ or
    `U+000A <http://www.fileformat.info/info/unicode/char/000A/index.htm>`_.

RDF Triple
    As defined in `RDF Concepts and Abstract Syntax <http://www.w3.org/TR/rdf-concepts/>`_.

Interpretation of CellML models
===============================

Component reference
-------------------

1. A component reference SHALL be the name of a component, and SHALL be
   interpreted based on the context within the CellML Model in which it
   occurs.

2. A component reference present in an information item which is a
   descendant of a model element SHALL be identical to either the name
   attribute on a component element or to the name attribute on an
   import component element.

3. A component reference which is identical to the name attribute on a
   component element SHALL be treated as a reference to that component
   element.

4. A component reference which is identical to the name attribute on an
   import component element SHALL be treated as if the component
   reference appeared in the imported model, and referred to the name
   specified in the component\_ref attribute of the import component
   element.

5. It is noted for the avoidance of doubt that CellML Models MAY apply
   the previous rule recursively, to reference an import component
   element which in turn references another import component element.

Variable reference
------------------

1. When present in an information item which is a descendant of a
   component element, a variable reference SHALL be the name of a
   variable, and SHALL refer to the variable element in the same
   component with a name attribute identical to the variable reference.

2. In all other cases, a variable reference SHALL consist of a component
   reference and a variable name. In this case, the variable reference
   SHALL be treated as if it was present in the component element
   referenced by the component reference.

Interpretation of grouping
--------------------------

1.  Two relationship\_ref elements SHALL be considered to refer to the
    same relationship if and only all of the following conditions hold:

    1. the attribute information item with local name ``relationship``
       is in an identical namespace on both element information items.

    2. the attribute information item with local name ``relationship``
       has identical values on each of the element information items.

    3. either the attribute information item in the empty namespace and
       with local name ``name`` is absent on both element information
       items, or, it is present on both element information items and
       has identical value.

2.  For every distinct relationship referred to by a relationship\_ref
    element in the CellML model, there SHALL be a conceptual
    relationship digraph in which there is one node for every component
    in the CellML model.

3.  Where a component\_ref element appears as a child of another
    component\_ref element, then for all relationship\_ref elements
    which are children of the ancestral group element, there SHALL be an
    arc in the relationship digraph corresponding to the relationship
    referenced by the relationship\_ref element, and that arc SHALL be
    from the component referenced by the parent component\_ref element
    and to the component referenced by the child component\_ref element.

4.  The term encapsulation digraph SHALL refer to the relationship
    digraph for the relationship corresponding to the relationship\_ref
    attribute in the empty namespace and with value "encapsulation" (and
    with no name attribute).

5.  The encapsulation digraph MUST NOT contain any loops, and MUST NOT
    contain any cycles in the underlying graph (that is, it must be a
    tree).

6.  The encapsulated set for a component A SHALL be the set of all
    components to which there exists an arc in the encapsulation digraph
    from the node corresponding to A.

7.  The encapsulation parent for a component A SHALL be the component
    corresponding to the node which is the parent node in the
    encapsulation digraph of the node corresponding to A.

8.  The sibling set for a component A SHALL be the set of all components
    which have the same encapsulation parent as A, or in the case that A
    has no encapsulation parent, SHALL be the set of all components
    which do not have an encapsulation parent.

9.  The hidden set for a component A SHALL be the set of all components
    B where component B is not in the encapsulated set for component A,
    and component B is not the encapsulation parent of component A, and
    component B is not in the sibling set for component A.

10. CellML models MUST NOT contain map\_components elements such that
    the component referenced by the component\_1 attribute is in the
    hidden set of the component referenced by the component\_2
    attribute.

Variable equivalence networks
-----------------------------

1.  A variable equivalence network SHALL be a directed graph with one
    node for every variable element in the CellML model.

2.  For every map\_variables element present in the CellML Model, there
    SHALL be an arc in the variable equivalence network.

3.  One endpoint of the arc in the variable equivalence network SHALL be
    the node corresponding to the variable (A) referenced by the
    component\_1 and variable\_1 attributes.

4.  One endpoint of the arc in the variable equivalence network SHALL be
    the node corresponding to the variable (B) referenced by the
    component\_2 and variable\_2 attributes.

5.  CellML models MUST NOT contain any pair of map\_variables elements
    which each make reference to the same sets of variables (without
    regard to whether the variable\_1 attribute of one map\_variables
    element references the variable referenced by the variable\_1 or
    variable\_2 attribute of the other).

6.  When the component parent element of variable A is in the sibling
    set of the component parent element of variable B, the applicable
    interface for variables A and B SHALL be the public interface.

7.  Where the component parent element of variable A is in the
    encapsulated set of the component parent element of variable B, the
    applicable interface for variable A SHALL be the public interface,
    and the applicable interface for variable B SHALL be the private
    interface.

8.  Where the component parent element of variable B is in the
    encapsulated set of the component parent element of variable A, the
    applicable interface for variable A SHALL be the private interface,
    and the applicable interface for variable B SHALL be the public
    interface.

9.  For a given variable, if the applicable interface is the public
    interface, the applicable interface attribute SHALL be the
    public\_interface attribute information item on the corresponding
    variable element. If the applicable interface is the private
    interface, the applicable interface attribute SHALL be the
    private\_interface attribute information item on the corresponding
    variable element.

10. In any case, if the applicable interface attribute is absent, the
    following rules in this section SHALL still apply as if the
    applicable interface attribute was present, and had the value none.

11. CellML models MUST NOT contain map\_variables elements unless the
    value of the applicable interface attributes on variables A and B
    are both either in or out, and those two attribute values are
    different from each other.

12. The direction of the arc SHALL be from the node corresponding to the
    variable with the applicable interface attribute equal to in, and
    SHALL be to the node corresponding to the variable with the
    applicable interface attribute equal to out.

13. For the purposes of this specification, the variable elements in a
    CellML Model SHALL be treated as belonging to one of several
    disjoint sets of connected variables. Each set of connected
    variables is the set of all variable elements for which the
    corresponding nodes in the variable equivalence network form a
    weakly connected subgraph. Each set of connected variables
    represents one variable in the mathematical model.

14. In every set of connected variables, there MUST be exactly one
    variable element which has neither a public interface of in nor a
    private interface of in. This variable element is referred to as the
    source variable element. Within this specification, the variable in
    the mathematical model is described as if it was in the units
    specified on the source variable element.

Units reference
---------------

1. A units reference SHALL be a CellML identifier, and SHALL be
   interpreted based on the context within the CellML Model in which it
   occurs.

2. A CellML Infoset MUST NOT contain a units reference to which all
   scoping rules are inapplicable.

3. Where more than one of the units scoping rules apply, the applicable
   rule which appears first in this specification SHALL be used.

4. The units scoping rules are as follows:

   1. Where a units reference appears in an information item which is
      descended from a component element, and there is a units element
      child of that component element with a name attribute identical to
      the units reference, then the units reference SHALL refer to that
      units element.

   2. Where a units reference appears in an information item which is
      descended from the model element, and there is a units element
      child of that model element with a name attribute identical to the
      units reference, then the units reference SHALL refer to that
      units element.

   3. Where there is an import units element in the CellML Infoset, such
      that the import units element has a name attribute identical to
      the units reference, then the units reference SHALL be treated as
      if the units reference appeared in the imported model, and
      referred to the name specified in the units\_ref attribute of the
      import units element.

   4. Where the units reference is equal to a cell in the name column of
      ?, then the units reference SHALL be a reference to the built-in
      unit corresponding to that row of the table.

.. default-role:: superscript

.. table:: Built-in units

   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | Name            | Is base unit?   | Multiplier and dimensions in terms of base units             | Offset from base units   |
   +=================+=================+==============================================================+==========================+
   | ampere          | yes             | -                                                            | -                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | becquerel       | no              | 1 · second\ `-1`                                             | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | candela         | yes             | -                                                            | -                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | celsius         | no              | 1 · kelvin                                                   | 273.15                   |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | coulomb         | no              | 1 · second · ampere                                          | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | dimensionless   | no              | 1                                                            | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | farad           | no              | 1 · metre\ `-2` · kilogram\ `-1` · second\ `4` · ampere\ `2` | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | gram            | no              | 10\ `-3` · kilogram                                          | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | gray            | no              | 1 · metre\ `2` · second\ `-2`                                | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | henry           | no              | 1 · metre\ `2` · kilogram · second\ `-2` · ampere\ `-2`      | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | hertz           | no              | 1 · second\ `-1`                                             | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | joule           | no              | 1 · metre\ `2` · kilogram · second\ `-2`                     | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | katal           | no              | 1 · second\ `-1` · mole                                      | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | kelvin          | yes             | -                                                            | -                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | kilogram        | yes             | -                                                            | -                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | liter           | no              | 10\ `-3` · metre\ `3`                                        | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | litre           | no              | 10\ `-3` · metre\ `3`                                        | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | lumen           | no              | 1 · candela                                                  | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | lux             | no              | 1 · metre\ `-2` · candela                                    | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | meter           | no              | 1 · metre                                                    | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | metre           | yes             | -                                                            | -                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | mole            | yes             | -                                                            | -                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | newton          | no              | 1 · metre · kilogram · second\ `-2`                          | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | ohm             | no              | 1 · metre\ `2` · kilogram · second\ `-3` · ampere\ `-2`      | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | pascal          | no              | 1 · metre\ `-1` · kilogram · second\ `-2`                    | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | radian          | no              | 1                                                            | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | second          | yes             | -                                                            | -                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | siemens         | no              | 1 · metre\ `-2` · kilogram\ `-1` · second\ `3` · ampere\ `2` | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | sievert         | no              | 1 · metre\ `2` · second\ `-2`                                | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | steradian       | no              | 1                                                            | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | tesla           | no              | 1 · kilogram · second\ `-2` · ampere\ `-1`                   | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | volt            | no              | 1 · metre\ `2` · kilogram · second\ `-3` · ampere\ `-1`      | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | watt            | no              | 1 · metre\ `2` · kilogram · second\ `-3`                     | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+
   | weber           | no              | 1 · metre\ `2` · kilogram · second\ `-2` · ampere\ `-1`      | 0                        |
   +-----------------+-----------------+--------------------------------------------------------------+--------------------------+

.. default-role::

.. table:: Prefix values

   +---------------+---------------+
   | Prefix Name   | Prefix Term   |
   +===============+===============+
   | yotta         | 24            |
   +---------------+---------------+
   | zetta         | 21            |
   +---------------+---------------+
   | exa           | 18            |
   +---------------+---------------+
   | peta          | 15            |
   +---------------+---------------+
   | tera          | 12            |
   +---------------+---------------+
   | giga          | 9             |
   +---------------+---------------+
   | mega          | 6             |
   +---------------+---------------+
   | kilo          | 3             |
   +---------------+---------------+
   | hecto         | 2             |
   +---------------+---------------+
   | deka          | 1             |
   +---------------+---------------+
   | deci          | -1            |
   +---------------+---------------+
   | centi         | -2            |
   +---------------+---------------+
   | milli         | -3            |
   +---------------+---------------+
   | micro         | -6            |
   +---------------+---------------+
   | nano          | -9            |
   +---------------+---------------+
   | pico          | -12           |
   +---------------+---------------+
   | femto         | -15           |
   +---------------+---------------+
   | atto          | -18           |
   +---------------+---------------+
   | zepto         | -21           |
   +---------------+---------------+
   | yocto         | -24           |
   +---------------+---------------+

Interpretation of units
-----------------------

1. The base units SHALL consist of the user defined base units, and the
   built-in base units (those units defined in rows of ? having 'yes' in
   the 'Is base unit?' column).

2. There SHALL be one user defined base unit for every units element in the
   CellML Model which has a base\_units attribute in the empty namespace,
   having value yes.

3. The base unit reduction of a units reference SHALL consist of a real
   valued offset, a real valued multiplier, and a set of tuples each
   consisting of a base unit and a real valued exponent. The base unit
   reduction of a units reference SHALL be determined as follows:

   1. Where the units reference is to a unit which is a base unit, then
      the base unit reduction of the units reference SHALL have offset
      zero, multiplier 1.0, and the set of tuples SHALL have a single
      member, which SHALL consist of the base units being referenced and
      the exponent 1.0.

   2. Where the units reference is to built-in units other than a base
      unit, then the base unit reduction SHALL be derived from the row
      of ? for which the value in the 'Name' column matches the name of
      the units reference. The offset of the base unit reduction SHALL
      be equal to the number in the 'Offset from base units' column of
      the row, and the multiplier SHALL be equal to the number at the
      start of the 'Multiplier and dimensions in terms of base units'
      column of the row. The set of tuples SHALL contain one member for
      every built-in base unit named in the 'Multiplier and dimensions
      in terms of base units' column of the row, and each of these
      tuples SHALL contain the built-in unit referenced, and the
      exponent appearing in superscript immediately after the units name
      in the table cell.

   3. Where the units reference is to a unit which is neither built-in,
      nor a base unit, the resultant base unit reduction SHALL be
      defined as a composition of the base unit reductions referenced
      from the unit element information items (the operand base unit
      reductions), in accordance with the following rules:

      1. The prefix term is a conceptual property of unit elements,
         defined here for later use. If the unit element does not have a
         prefix information item, the prefix term SHALL have value zero.
         If the prefix attribute information item has a value which is a
         real number string, then the prefix term SHALL have the
         corresponding numerical value. Otherwise, the prefix attribute
         information item MUST have a value taken from the 'Prefix Name'
         column of ?, and the prefix term SHALL have the value taken
         from the 'Prefix Term' column of the same row.

      2. The exponent term is a conceptual property of unit elements,
         defined here for later use. If a unit element has no exponent
         attribute information item, the exponent term SHALL have value
         1.0. Otherwise, the value of the exponent attribute information
         item MUST be a real number string, and the value of the
         exponent term SHALL be the numerical value of that string.

      3. The multiplier term is a conceptual property of unit elements,
         defined here for later use. The multiplier term SHALL be the
         real number value of the multiplier attribute information item
         on the units element (or 1.0 in the absence of such an
         attribute information item), multiplied by 10.0 raised to the
         power of the product of the prefix term and the exponent term.

      4. The offset term is a conceptual property of unit elements,
         defined here for later use. If a unit element has no offset
         attribute information item, the offset term SHALL have value
         zero. Otherwise, the value of the offset attribute information
         item MUST be a real number string, and the value of the offset
         term SHALL be the numerical value of that string.

      5. Where the units reference is to a units element with a single
         unit child element, then the resultant base unit reduction
         SHALL have multiplier equal to the product of the multiplier of
         the operand base unit reduction and the multiplier term of the
         unit element. It SHALL have offset equal to the sum of the
         offset of the operand base unit reduction and the offset term
         of the unit element.

      6. Where the units reference is to a units element with a number
         of unit child elements not equal to one, then the resultant
         base unit reduction SHALL have multiplier equal to the product
         of the multipliers of each operand base unit reduction, and the
         multiplier term of each unit element. It SHALL have offset
         equal to zero.

      7. The set of tuples on the resultant base unit reduction SHALL
         have one member for every distinct base unit present in the set
         of tuples for any of the operand base unit reductions. The
         exponent alongside each of these base units in the resultant
         base unit reduction SHALL be the sum, across all tuples for the
         base unit from operand base unit reductions, of pairwise
         products of the exponent term on the corresponding unit element
         and the exponent from the tuple.

The effect of units on variables
--------------------------------

1. The units attribute on a variable element MUST be a valid units
   reference. The target of this units reference is referred to as
   the variable units, and the corresponding base units reduction is
   referred to as the variable base unit reduction.

2. The variable base unit reduction of a variable element MUST have an
   identical set of tuples to the set of tuples on the source variable
   base element units reduction. Two sets of tuples SHALL be considered
   identical if and only if neither set contains any tuple not present
   in the other. Two tuples are considered identical if both the base
   units and exponent on the tuple are the same.

3. The following symbols are defined for the purposes of the formulae in
   the 'Interpretation of Mathematics' section:

   1. m\ :sub:`V` is the multiplier on the variable base unit reduction.

   2. o\ :sub:`V` is the offset on the variable base unit reduction.

   3. m\ :sub:`S` is the multiplier on the source variable base unit reduction.

   4. o\ :sub:`S` is the offset on the source variable base unit reduction.

Interpretation of initial values
--------------------------------

1. This section applies to the interpretation of the initial\_value
   attribute, when it appears as an attribute information item on a
   variable element.

2. The initial\_value attribute MUST either be a real number string, or
   a variable reference.

3. Where the initial\_value attribute has a real number value, it SHALL
   be interpreted as a statement that the variable on which the
   attribute appears is equal to that real number value, under the
   conditions when the initial value holds.

4. Where the initial\_value attribute is a variable reference, it SHALL
   be interpreted as a statement that the variable on which the
   attribute appears is equal to the referenced variable under the
   conditions when the initial value holds.

.. todo::

   Need a reasonable definition of the conditions when the
   initial\_value holds, because we can't really use the 1.1 version
   because it is problematic for a number of reasons.

Interpretation of imports
-------------------------

1. Each import element present in a CellML Infoset (the importing
   infoset) SHALL define a new and separate instance of the CellML
   Infoset referenced by the href attribute (the imported infoset).

2. The following component elements SHALL be "pertinent component
   elements":

   1. all component elements in the top-level CellML Infoset for the
      CellML Model, and,

   2. all component elements referenced by import components in the
      top-level CellML Infoset, and,

   3. all component elements which are descendants in the encapsulation
      digraph of a pertinent component element.

Interpretation of the mathematics
---------------------------------

.. default-role:: subscript

1. Every MathML element in the CellML Model, which appears as a direct
   child information item of the MathML math element information item,
   which in turn appears as a child information item of a pertinent
   component element, SHALL be treated as a statement which holds true
   unconditionally.

2. Every MathML element which appears as a direct child information item
   of the MathML math element information item SHALL be treated as a
   statement which holds true unconditionally.

3. Every variable name given using the MathML ci element SHALL be
   treated as a variable reference within the component element ancestor
   the MathML is contained within.

4. Every such variable reference SHALL be treated as a linear expression
   m\ `V` m\ `S` × x + o\ `V` - m\ `V` m\ `S` × o\ `S`.
   In this equation, x represents the
   variable in the mathematical model, in the units of the source
   variable element, while the remaining variables SHALL be interpreted
   as specified in ?.

5. Every MathML cn element MUST have an attribute information item in
   the CellML 1.1 namespace, with local name ``units``. The value of
   this attribute information item MUST be a valid units reference. The
   referenced units SHALL NOT affect the mathematical interpreation of
   the CellML Model. However, CellML Processing Software MAY use this
   information to assist the user in the detection and correction of
   units errors in the CellML Model.

.. default-role::

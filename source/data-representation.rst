Data representation formats in CellML
=====================================

The following data representation formats are defined for use in this
specification:

1. A CellML identifier:

   1. SHALL be a sequence of Unicode characters.

   2. SHALL NOT contain any characters except basic Latin alphanumeric
      characters and basic Latin underscores.

   3. SHALL contain one or more basic Latin alphabetic characters.

   4. SHALL NOT begin with a European numeric character.

   5. SHALL, when comparing two identifiers, be considered identical to
      another identifier if and only if both identifiers have identical
      sequences of Unicode character codes.

2. A non-negative integer string:

   1. SHALL be a base 10 representation of a non-negative integer.

   2. SHALL consist entirely of European numeric characters.

3. An integer string:

   1. SHALL be a base 10 representation of an integer.

      When the integer being represented is negative, SHALL consist of
      the Basic Latin hyphen-minus character U+002D, followed by the
      non-negative integer string representation of the absolute value
      of the integer.

      When the integer being represented is non-negative, SHALL consist
      of the non-negative integer string representation of the integer.

4. A basic real number string:

   1. SHALL be a base 10 representation of a real number.

   2. Where the number is negative, SHALL begin with the Basic Latin
      hyphen-minus character U+002D as the sign indicator.

   3. MAY contain a single decimal point separator, which SHALL be the
      basic Latin full stop character U+002E.
   4. Other than the sign indicator and the decimal point separator,
      SHALL consist only of European numeric characters.

5. A real number string:

   1. SHALL be a base 10 representation of a real number r = s × 10 e,
      where s is the significand, a real number, and e is the exponent,
      an integer.

   2. The representation of the number SHALL be the representation of
      the significand followed immediately by the representation of the
      exponent.

   3. The significand SHALL be represented as a basic real number
      string.

   4. If the exponent is zero, the exponent MAY be represented by an
      empty string, or MAY be represented according to the following
      rule. If the exponent is non-zero, it MUST be represented
      according to the following rule.

   5. An exponent SHALL be represented by an exponent separator
      character, followed by the integer string representation of the
      exponent's value. The exponent separator character SHALL be either
      the Unicode Basic Latin character 'E' or the Unicode Basic Latin
      character 'e'.



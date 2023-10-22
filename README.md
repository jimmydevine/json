# JDON
* [Overview](#overview)
* [Syntax](#syntax)
  * [Elements](#elements)
    * [Boolean](#boolean)
    * [Numeric](#numeric)
      * [Integer](#integer)
      * [Float](#float)
    * [Strings](#strings)
      * [Single Quote](#single-quote)
      * [Double Quote](#double-quote)
      * [Triple Quote](#triple-quote)
      * [Sextuple Quote](#sextuple-quote)
      * [Unquoted](#unquoted)
    * [Containers](#containers)
      * [Arrays](#arrays)
      * [Objects](#objects)
  * [Functional](#functional)
    * [Paths](#paths)
    * [Variables](#variables)
      * [Environment Variables](#environment-variables)
      * [Local Variables](#local-variables)
    * [Assignments](#assignments)
    * [Expressions](#expressions)
      * [Unary Operators](#unary-operators)
        * [Invert](#invert)
      * [Binary Operators](#binary-operators)
        * [Addition](#addition)
        * [Subtraction](#subtraction)
        * [Multiplication](#multiplication)
        * [Division](#division)
        * [Modulus](#modulus)
        * [Boolean And](#boolean-and)
        * [Boolean Or](#boolean-or)
        * [Boolean Xor](#boolean-xor)
    * [Concatenation](#concatenation)
    * [Includes](#includes)
  * [Non-Functional](#non-functional)
    * [Comments](#comments)
      * [Hash](#hash)
      * [Double Slash](#doubler-slash)
      * [Slash Star](#slash-star)
      * [HTML](#html)
    * [Spacing](#spacing)
      * [White Space](#white-space)
      * [Blue Space](#blue-space)
      * [Green Space](#green-space)


# Overview

JDON is a blend of flexible and functional configuration languages and reduces to a JSON structure.

# Syntax

## Elements

### Boolean

Boolean values are represented by one of the following:

```
0     # boolean false
1     # boolean true
true  # boolean false
false # boolean true
no    # boolean false
yes   # boolean true
```

All characters are case-insensitive

### Numeric

#### Integer

#### Float

### Strings

#### Single Quote

Single quoted strings are strings which start and end with one single quote character.  They may not span multiple lines and may not contain variables, $ is treated literally.

```
' This is a single quoted string '
```

#### Double Quote

Double quoted strings are strings which start and end with one double quote character.  They may not span multiple lines but may contain variables.

```
" This is a single quoted string which may contain a $variable "
```

#### Triple Quote

Triple qouted strings are strings which start and end with three single quote characters.  They may span multiple lines but may not contain variables, $ is treated literally.

```
'''
This is a triple quoted string
'''
```

#### Sextuple Quote

Sextuple quoted strings are strings which start and end with three double quote characters.  They may span multiple lines and may contain variables.

```
"""
This is a sextuple quoted string which may contain a $variable
"""
```

#### Unquoted

### Containers

#### Arrays

#### Objects

## Functional

### Paths

Paths define relative or absolute endpoints in the document structure.  They can be applied to object keys and variables.  Paths are in the form:

```
[start designation]element[.element]+
```

If a start designation is not provided, the path is relative to the current container.  Start designations may be one of:
- ~ indicates the root of the document
- . indicates the current container
- .. indicates the parent container, additional . will reference each successive parent

### Variables

#### Environment Variables

#### Local Variables

### Assignments

### Expressions

#### Unary Operators

##### Invert

#### Binary Operators

##### Addition

Addition operator is a + character and supports the following operations:

Left Type | Right Type | Operation | Notes
--- |--- |--- |--- |
Boolean | Boolean | Boolean And | -
Boolean | Numeric | Boolean And | Number converted to boolean, 0 is false, non-zero is true
Boolean | String | String Concatenation | Boolean converted to string, false or true
Boolean | Array | Array Prepend | -
Boolean | Object | - | Operation not allowed
Numeric | Boolean | Boolean And | Number converted to boolean, 0 is false, non-zero is true
Numeric | Numeric | Arithmetic Add | -
Numeric | String | String Concatenation | Number converted to string
Numeric | Array | Array Prepend | -
Numeric | Object | - | Operation not allowed
String | Boolean | String Concatenation | Boolean converted to string, false or true
String | Numeric | String Concatenation | Number converted to string
String | String | String Concatenation | -
String | Array | Array Prepend | -
String | Object | - | Operation not allowed
Array | Boolean | Array Append | -
Array | Numeric | Array Append | -
Array | String | Array Append | -
Array | Array | Array Concatenation | -
Array | Object | Array Append | -
Object | Boolean | - | Operation not allowed
Object | Numeric | - | Operation not allowed
Object | String | - | Operation not allowed
Object | Array | Array Prepend | -
Object | Object | Object Concatenation | -

##### Subtraction

##### Multiplication

##### Division

##### Modulus

##### Boolean And

##### Boolean Or

##### Boolean Xor

### Concatenation

### Includes

## Non-Functional

### Comments

#### Hash

#### Double Slash

#### Slash Star

#### HTML

### Spacing

#### White Space

White space includes one or more space, tab, newline or carriage return characters.

#### Blue Space

Blue space includes any white space or comments.

#### Green Space

Green space includes spaces, tabs and until-end-of-line comments (hash and double slash).



# The TOML Schema Definition

A TOML schema is a set of elements that define the structure, the names, and the types of configuration data on a TOML file. The TOML Schema is used to validate the input of a TOML file during parsing to reduce or avoid misconfiguration that could potentially damage if only validated during production evaluation.

The schema format follows the TOML specification.

## Element Definition
An element can be defined by constructing a table followed by a set of properties to define that element.

```toml
[<element-name>]
type=<built-in-type>
optional=<boolean>
default=<default-value>
min=<integer>
max=<integer>
```

### Element Name

Declares the name of the element.

### Type

Declares the type of the element. 

## Built-in Types

The allowed types are the ones supported by the TOML Specification:

- String: `string`
- Integer: `integer`
- Float: `float`
- Boolean: `boolean`
- Offset Date-Time: `offset-date-time`
- Local Date-Time: `local-date-time`
- Local Date: `local-date`
- Local Time: `local-time`
- Array: `array`
- Inline Table: `inline-table`
- Table: `table` (*)

The schema definition also explicitly defines the implicit TOML type `table` for specifying child elements associated to the parent.

## Optional

Defines whether this element is optional or not. **Defaults to false**.

## Default

The default value the parser should read when this element is not explicitly defined in the TOML file.

An element of type Boolean will default to `false` unless 

## Min

The minimal value of an element. This attribute is applicable to the following types:

- String: minimum length
- Integer: minimum value
- Float: minimum value

## Max

The maximum value of an element. This attribute is applicable to the following types:

- String: maximum length
- Integer: maximum value
- Float: maximum value


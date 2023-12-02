# Top-level Value types in pRC                 {#ValueTypes}

For consistency and compatibility reasons, pRC comes with its own value types. These include both integer and floating point numbers.

Integer values are stored in a class called pRC::Integer, floating point numbers are stored in pRC::Float. Template parameters of these classes determine the width and sign (for integer types) of these types.

## Integer types
Integer types are supported for Signed and Unsigned variants of 8-bit, 16-bit, 32-bit and 64-bit integers.

They can be accessed through `pRC::Integer<S, W>` with `S` being a bool set to `true` for signed and `false` for unsigned integers. `W` is the width, the values 8, 16, 32 and 64 are supported.

## Floating point types
Float types are supported for 16-bit (half-precision), 32-bit (standard-precision) and 64-bit (double-precision) floating point numbers.

They can be accessed through `pRC::Float<W>` with `W` being the width, possible values are 16, 32 and 64.

## Class methods
The following list is a quick overview over the methods that are supported for pRC value types. `Type` is used as a placeholder for the respective type (`pRC::Integer` or `pRC::Float`):

- Constructors:
    + `Type(basic)`, where basic is a standard type object
    + `Type(value)`, where value is an object of (possibly different) pRC value type
    + `Type(cmplxvalue)`, where cmplxvalue is an object of pRC Complex type
    + `Type(special)`, where special is an object of pRC::Zero, pRC::Unit or pRC::Identity type
- Operators:
    + `=` operator, with the same behavior and allowed arguments as the constructor
    + `+=` operator
    + `-=` operator
    + `*=` operator
    + `/=` operator, for Integer, this does integer division
    + `%=` operator, only for Integer
    + `()` operator, accessing the underlying value directly
- Misc:
    + `Fundamental()`: same as `()` operator

## Type Traits
The types exhibit the following type traits, which can be used e.g. for template restrictions:

Type Trait | `Float<W>` | `Integer<false, W>` | `Integer<true, W>`
-----------|------------|---------------------|-------------------
IsFloat    | true       | false               | false
IsSignedInteger | false | false               | true
IsUnsignedInteger | false | true              | false
IsInteger  | false      | true                | true
IsValue    | true       | true                | true


## Type Modifiers
Type modifiers are defined which can be accessed through `Type::Modifier`.
For a value Type `pRC::Integer<S, W>`, the following table shows the template parameters `S` and `W` of the type obtained through the modifier. `S` and `W` refer to the template parameters of the old type, any change is denoted by a different letter and a template parameter in the modifier. `Type<Q, R>` denotes some pRC value class with template parameters `Q` and (for Integer) `R`. For `pRC::Float<W>`, the column `S` should be ignored:

Modifier | W | S
---------|---|--
ChangeValue<Type<Q, R>> | Q | R
ChangeSigned<R> | W | R
ChangeWidth<Q> | Q | S

## Complex numbers
Lastly, for working with complex numbers, the following are defined (mostly for consistency):

- `IsComplexified` is a synonym for `False<>`
- `Complexify` is a synonym for `Complex<Type>`
- `NonComplex` is a synonym for `Type`

## Functions
The functions implemented for pRC values include most of the functions defined in the standard library header `cmath`. Additional functions are defined for easier use of the library, or for consistency with other parts of the library. The following list summarizes all available functions.

\todo
Add list with links to individual documentations!

# Tensorish types in pRC                 {#TensorTypes}

In pRC, tensors are stored as pRC::Tensor objects of a specified [pRC value type](#ValueTypes) and specified sizes. The value type and the sizes are template arguments of the pRC::Tensor class, meaning that all sizes have to be specified at compile time. This allows for efficient data storage and accelerates calculations.

## Tensor types
Tensors types are accessed through `pRC::Tensor<T, Ns...>` with T being the [pRC value class](#ValueTypes), and Ns... being the mode sizes of the tensor.

## Tensorviews
\todo
explain lazy evaluation, how this is done in pRC

## Class methods
The following list is a quick overview over the methods that are supported for pRC tensor types. `Type` is used as a placeholder for the class `pRC::Tensor`:

- Static:
    + `Type::size()`: number of entries of `Type` (product of its mode sizes)
    + `Type::size(dimension)`: size of `Type`'s `dimension`'th mode size
    + `Type::Single(value, subscripts)`: returns a Tensor of class `Type` that has only one non-zero entry (specified by value and subscripts)
- Constructors:
    + `Type(other)`: constructor from another Tensor of compatible type
- Operators:
    + `(indices...)`: access to Tensor element specified by `Index` objects
    + `(subscripts)`: access to Tensor element specified by `Subscripts` object
    + `[index]`: access to Tensor element specified by linearized `Index` object
    + `=`
    + `+=`
    + `-=`
    + `*=`: `a *= b` translates to applying b on the right of a
    + `/=`: does element-wise division
    + `T()`: conversion operator from zero-dimensional `Tensor<T>` to `T`
- Other:
    + `applyOnTheLeft`: applies the argument on the left of the `Type` object
    + `applyOnTheRight`: applies the argument on the right of the `Type` object

## Type Traits
The types exhibit the following type traits, which can be used e.g. for template restrictions:

Type Trait | `Tensor<T, Ns...>` | `TensorViews::View<T, N, F>`
-----------|--------------------|-----------------------------
IsTensor   | true               | false
IsTensorView | false            | true
IsTensorish | true              | true

## Type Modifiers
Type modifiers are defined which can be accessed through `Type::Modifier`.
For a Tensor Type `pRC::Tensor<T, Ns...>`, the following table shows the template parameters `T` and `Ns...` of the type obtained through the modifier. `T` and `Ns...` refer to the template parameters of the old type, any change is denoted by a different letter and a template parameter in the modifier:

Modifier | T | Ns...
---------|---|--
ChangeType<C> | C | Ns...
ChangeSizes<Ss...> | T | Ss...
ChangeValue<V> | T::ChangeValue<V> | Ns...
ChangeSigned<R> | T::ChangeSigned<R> | Ns...
ChangeWidth<Q> | T::ChangeWidth<Q> | Ns...

## Complex Numbers
Lastly, for working with complex numbers, the following are defined for a class `Tensor<T, Ns...>`:

- `IsComplexified` is a synonym for `T::IsComplexified`
- `Complexify` is a synonym for `Tensor<T::Complexify, Ns...>`
- `NonComplex` is a synonym for `Tensor<T::NonComplex, Ns...>`

## Functions
\todo
this



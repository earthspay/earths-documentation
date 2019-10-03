# Math functions

| # | Name | Description | Complexity |
|:---| :--- | :--- | :--- |
| 1 | [fraction(Int, Int, Int): Int](#fraction) | Converts arbitrarily large signed integer to integer | 1 |
| 2 |[log(Int, Int, Int, Int, Int, Union): Int](#log)| Calculates logarithm of the number | 100 |
| 3 |[pow(Int, Int, Int, Int, Int, Union): Int](#pow) | Raises the number to a power| 100 |

## fraction(Int, Int, Int): Int<a id="fraction"></a>

Converts arbitrarily large signed integer to integer.

```ride
fraction(value: Int, numerator: Int, denominator: Int): Int
```

### Parameters

#### `value`: Int

Arbitrarily large signed integer.

#### `numerator`: Int

Numerator of the fraction.

#### `denominator`: Int

Denominator of the fraction.

### Conversion formula

Conversion is performed according to the following formula:

```ride
fraction = value × numerator / denominator
```

### Examples

```ride
fraction(2,2,3) # Returns 1
fraction(3,3,3) # Returns 3
fraction(3,2,3) # Returns 2
```

## log(Int, Int, Int, Int, Int, Union): Int<a id="log"></a>

Calculates logarithm of the number.

``` ride
log(value: Int, ep: Int, base: Int, bp: Int, rp: Int, round: Union): Int
```

### Parameters

#### `value`: Int

Given number.

#### `ep`: Int

Number of decimals of the given number.

#### `base`: Int

Base of the logarithm.

#### `bp`: Int

Number of decimals of the base.

#### `rp`: Int

Number of decimals of the resulting value.

#### `round`: Union

One of the [rounding function](#rounding-functions).

The `HalfUp()` function may be used as the default value.

### Examples

* log<sub>2</sub>(0) = -Infinity
* log<sub>2</sub>(2) = 0
* log<sub>2</sub>(10.555) = 3.4
* log<sub>2</sub>(16.25) = 4.02

```ride
log(0, 0, 2, 0, 0, HalfUp()) # -Infinity
log(1, 0, 2, 0, 0, HalfDown()) # Returns 0
log(10555, 3, 2, 0, 3, HalfEven()) # Returns 3400
log(1625, 2, 2, 0, 2, Up()) # Returns 403
```

## pow(Int, Int, Int, Int, Int, Union): Int<a id="pow"></a>

Raises the number to a power.

``` ride
pow(base: Int, bp: Int, exponent: Int, ep: Int, rp: Int, round: Union): Int
```

### Parameters

#### `base`: Int

Given number.

#### `bp`: Int

Number of decimals of the given number.

#### `exponent`: Int

Power.

#### `ep`: Int

Number of decimals of power.

#### `rp`: Int

Number of decimals of the resulting value.

#### `round`: Union

One of the [rounding functions](#rounding-functions).

The `HalfUp()` function may be used as the default value.

### Examples

* 1<sup>0</sup> = 1
* 2<sup>4</sup> = 16
* 2.5<sup>2.5</sup> = 9.88
* 3.33<sup>3</sup> = 36.926

```ride
pow(1, 0, 0, 0, 0, Up()) # Returns 1
pow(2, 0, 4, 0, 0, HalfUp()) # Returns 16
pow(25, 1, 25, 1, 2, Floor()) # Returns 988
pow(333, 2, 3, 0, 3, Down()) # Returns 36926
```

## Rounding functions

The rounding functions are _only_ used as the parameters of [log](#log) and [pow](#pow) functions and they are not used by themselves.

|Name | Description |
| :--- | :--- |
| Ceiling(): Int | Rounding towards positive infinity |
| Down(): Int | Rounding towards zero |
| Floor(): Int | Rounding towards negative infinity |
| HalfDown(): Int | Rounding down towards the nearest integer |
| HalfEven(): Int | Rounding towards the nearest even integer |
| HalfUp(): Int   | Rounding up towards the nearest integer   |
| Up(): Int | Rounding away from zero |

### Examples

| | -1.6 | -1.5 | -1.4 | -1.0 | 1.0 | 1.4 | 1.5 | 1.6 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Ceiling | -1 | -1 | -1 | -1 | 1 | 2 | 2 | 2 |
| Down | -1 | -1 | -1 | -1 | 1 | 1 | 1 | 1 |
| Floor | -2 | -2 | -2 | -1 | 1 | 1 | 1 | 1 |
| HalfDown | -2 | -1 | -1 | -1 | 1 | 1 | 1 | 2 |
| HalfEven | -2 | -2 | -1 | -1 | 1 | 1 | 2 | 2 |
| HalfUp | -2 | -2 | -1 | -1 | 1 | 1 | 2 | 2 |
| Up | -2 | -2 | -2 | -1 | 1 | 2 | 2 | 2 |

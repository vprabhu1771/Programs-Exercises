`math.h` is a C standard library header file that provides mathematical functions.

## Basic Math Functions

| Function    | Description                               |
| ----------- | ----------------------------------------- |
| `sqrt(x)`   | Square root of x                          |
| `cbrt(x)`   | Cube root of x                            |
| `pow(x, y)` | x raised to power y                       |
| `fabs(x)`   | Absolute value of a floating-point number |
| `ceil(x)`   | Rounds up to nearest integer              |
| `floor(x)`  | Rounds down to nearest integer            |
| `round(x)`  | Rounds to nearest integer                 |
| `trunc(x)`  | Removes fractional part                   |

---

## Exponential and Logarithmic Functions

| Function   | Description              |
| ---------- | ------------------------ |
| `exp(x)`   | Calculates e^x           |
| `log(x)`   | Natural logarithm (ln x) |
| `log10(x)` | Base-10 logarithm        |
| `log2(x)`  | Base-2 logarithm         |
| `expm1(x)` | Calculates e^x - 1       |

---

## Trigonometric Functions

| Function      | Description                |
| ------------- | -------------------------- |
| `sin(x)`      | Sine of angle (radians)    |
| `cos(x)`      | Cosine of angle (radians)  |
| `tan(x)`      | Tangent of angle (radians) |
| `asin(x)`     | Inverse sine               |
| `acos(x)`     | Inverse cosine             |
| `atan(x)`     | Inverse tangent            |
| `atan2(y, x)` | Inverse tangent of y/x     |

---

## Hyperbolic Functions

| Function   | Description                |
| ---------- | -------------------------- |
| `sinh(x)`  | Hyperbolic sine            |
| `cosh(x)`  | Hyperbolic cosine          |
| `tanh(x)`  | Hyperbolic tangent         |
| `asinh(x)` | Inverse hyperbolic sine    |
| `acosh(x)` | Inverse hyperbolic cosine  |
| `atanh(x)` | Inverse hyperbolic tangent |

---

## Remainder and Floating-Point Functions

| Function            | Description                         |
| ------------------- | ----------------------------------- |
| `fmod(x, y)`        | Remainder of x/y                    |
| `remainder(x, y)`   | IEEE remainder                      |
| `modf(x, &intpart)` | Splits integer and fractional parts |
| `frexp(x, &exp)`    | Extracts mantissa and exponent      |
| `ldexp(x, exp)`     | Computes x × 2^exp                  |

---

## Maximum and Minimum Functions

| Function     | Description         |
| ------------ | ------------------- |
| `fmax(x, y)` | Larger value        |
| `fmin(x, y)` | Smaller value       |
| `fdim(x, y)` | Positive difference |

---

## Common Constants

Some compilers provide:

```c
M_PI       // 3.141592653589793
M_E        // 2.718281828459045
M_SQRT2    // 1.414213562373095
```

---

## Examples

### Square Root

genui{"math_block_widget_always_prefetch_v2":{"content":"y=\sqrt{x}"}}

```c
#include <stdio.h>
#include <math.h>

int main() {
    printf("%.2f", sqrt(25));
    return 0;
}
```

Output:

```text
5.00
```

### Power Function

genui{"math_block_widget_always_prefetch_v2":{"content":"y=x^n"}}

```c
printf("%.0f", pow(2, 3));
```

Output:

```text
8
```

### Ceiling and Floor

```c
printf("%.0f\n", ceil(4.2));   // 5
printf("%.0f\n", floor(4.8));  // 4
```

### Trigonometric Function

```c
printf("%.2f", sin(0));
```

Output:

```text
0.00
```

## Most Important `math.h` Functions for Students

1. `sqrt()`
2. `pow()`
3. `ceil()`
4. `floor()`
5. `round()`
6. `fabs()`
7. `sin()`
8. `cos()`
9. `tan()`
10. `log()`
11. `log10()`
12. `exp()`
13. `fmod()`
14. `fmax()`
15. `fmin()`

These are the functions most commonly used in C programming, practical labs, and interview questions.

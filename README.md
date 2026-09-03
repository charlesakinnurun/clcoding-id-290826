# Python `any()` and Division by Zero

This project demonstrates how Python evaluates a list containing boolean-like values and what happens when an expression causes a **division-by-zero error**.

## Code

```python
x = [0, 0, 5, 1/0]

print(any(x))
```

## Explanation

### 1. Creating the List

The code attempts to create the following list:

```python
x = [0, 0, 5, 1/0]
```

The values `0`, `0`, and `5` are valid Python numbers.

However:

```python
1/0
```

attempts to divide `1` by `0`.

Python does not allow division by zero, so it immediately raises:

```text
ZeroDivisionError: division by zero
```

### 2. Does `any(x)` Run?

No.

Because the error occurs while Python is creating the list, the variable `x` is never successfully assigned.

Therefore, this line:

```python
print(any(x))
```

is **never executed**.

## Expected Output

```text
ZeroDivisionError: division by zero
```

The exact traceback will also show the line where `1/0` occurred.

## About `any()`

If the division-by-zero expression were removed:

```python
x = [0, 0, 5]

print(any(x))
```

The output would be:

```text
True
```

This is because `any()` returns `True` if **at least one element** in an iterable is truthy.

In Python:

* `0` → `False`
* Non-zero numbers → `True`

So:

```python
any([0, 0, 5])
```

returns:

```text
True
```

## Key Concepts

* Python list creation
* `any()` function
* Truthy and falsy values
* Division by zero
* `ZeroDivisionError`
* Python exception handling

## Learning Outcome

This example demonstrates that Python evaluates expressions while constructing a list. An exception such as `1/0` occurs **before** functions like `any()` can operate on the list.

## Requirements

* Python 3.x

## Author

Created as a Python learning project exploring built-in functions and exception behavior.

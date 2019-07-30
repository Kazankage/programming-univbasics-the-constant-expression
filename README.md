# The Constant Expression

## Learning Goals

* Identify the _constant expression_
* Explain how the _constant expression_ stops evaluation

## Introduction

Lets repeat our definition of _expression_

> **Definition**: Expression: A combination of information called _data_ and
> _symbols_ indicating how to combine _data_ called _operators_.

What if we were to make an expression that had no _operators_, it only had
_data_. Here we're giving just such a thing to Ruby in IRB.

![IRB Constant Expression](https://curriculum-content.s3.amazonaws.com/prework/constant_expr_animation.gif)

This expression is the _constant expression_ and it's very important, although
very boring. It's boring because it doesn't do anything except be itself. But
it's important because it confirms that Ruby knows when an expression is done;
it tells Ruby the evaluation is done and that it has arrived at _an answer_.

### Explain How the _Constant Expression_ Stops Evaluation

Let's consider a simple arithmetic expression. Keep in mind we apply operators
in "[PEMDAS][]" order: parenthesis, exponents, multiplication, division,
addition, subtraction.

| Expression       | Has Operators? | Operators | Are we done? | Which to Apply |
| ---------------- | -------------- | --------- | ------------ | -------------- |
| `3 * ( 10 - 4 )` | YES            | `*`, `()` | NO           | Zoom-in on new sub-expression in `()` because of [PEMDAS][]|
| `( 10 - 4 )`     | YES            | `-`       | NO           | Evaluate sub-expressions|
| `10`             | NO             | NONE      | YES          | Zoom in on expression `10`. Constant expression! Return the value of the constant, we're done!|
| `4`              | NO             | NONE      | YES          | Zoom in on expression `4`. Constant expression! Return the value of the constant, we're done!|
| `( 10 - 4 )`     | YES            | `-`       | NO           | Replace `( 10 - 4 )` with application of `-` to `10` and `4` making `6`
| `3 * 6`          | YES            | `*`       | NO           | Zoom-out and replace the sub-expression with its value we just determined|
| `3 * 6`          | YES            | `-`       | NO           | Zoom-in on sub-expression|
| ` 3`             | NO             | NONE      | YES          | Zoom in on expression `3`. Constant expression! Return the value of the constant, we're done!|
| `6`              | NO             | NONE      | YES          | Zoom in on expression `6`. Constant expression! Return the value of the constant, we're done!|
| `3 * 6`          | YES            | `*`       | NO           | Replace `3 * 6` with application of `*` to `3` and `6` making `18`|
| `18`             | NO             | NONE      | YES          | Constant expression! Return the value of the constant, we're done!|

Whew! Fortunately, Ruby does _all this work_ of zooming in and zooming out very
quickly!  The _constant expression_ is _always_ the last expression in a complex
expression. It's how Ruby knows it has _data_ that it can work with.

Another way of looking at this process of evaluation is looking at the
expression in a tree-like structure.

Figure 1

## Conclusion

While the _constant expression_ might seem dull, it lets us know when
expression evaluation is done _and_ establishes a groundwork for all the
following expressions.

[PEMDAS]: https://en.wikipedia.org/wiki/Order_of_operations

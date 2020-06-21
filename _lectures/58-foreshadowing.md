---
title: Foreshadowing
description: Towards multivariable calculus 
lecture_number: 58
topic_number: 6
layout: lecture
mathjax: true
---
In this module we give a hint at what is to come in multivariable calculus.
Functions

As in single variable calculus, multivariable calculus is primarily a study of functions. But instead of functions with one input and one output, multivariable calculus looks at functions with multiple inputs and outputs. The notation for a function ($f$) with ($n$) real inputs and ($m$) real outputs is

(:latex:) \[ f: \mathbb{R}^n \rightarrow \mathbb{R}^m. \] (:latexend:)
Matrices

When dealing with multiple inputs and multiple outputs, it becomes necessary to keep track of several pieces of information when dealing with, say, the derivative. The data structure which makes this possible is a matrix, which is an array of numbers arranged in rows and columns. For example, a ($4 \times 3$) matrix has 4 rows and 3 columns, and might look like

(:latex:) \[ \left[\begin{array}{ccc} 3 & 1 & 4
1 & 5 & 9
2 & 6 & 5
3 & 5 & 8 \end{array} \right]. \] (:latexend:)

A square matrix has the same number of rows and columns. A particular square matrix with a special name is the identity matrix, which has 1's on the main diagonal and 0's everywhere else. For example, the ($3 \times 3$) identity matrix is given by

(:latex:) \[ I = \left[\begin{array}{ccc} 1 & 0 & 0
0 & 1 & 0
0 & 0 & 1 \end{array} \right]. \] (:latexend:)
Matrix algebra

One feature of matrices is that they can be multiplied, by a slightly unintuitive process. Consider the product of a ($2 \times 3$) matrix with a ($3 \times 3$) matrix:

(:latex:) \[ \left[\begin{array}{ccc} 1 & -1 & 4
2 & 5 & 7 \end{array} \right] \cdot \left[\begin{array}{ccc} 2 & 1 & 0
4 & 4 & 3
-2 & 7 & 1 \end{array} \right] = \left[\begin{array}{ccc} -10 & 25 & 1
10 & 71 & 22 \end{array} \right] \] (:latexend:)

To see where these numbers come from, arrange the matrices a little differently:

To get an entry in the resulting matrix (bottom right), take the corresponding row from the matrix to the left and the corresponding column from the matrix above, multiply their corresponding entries together, and add. The above example shows the calculation for two entries in the result.

Note that for this multiplication to be defined, the number of columns in the first matrix must match the number of rows in the second matrix (otherwise there would not be the correct number of entries to multiply together and add).

There are some nice features of matrix multiplication, and some features which are a little bit different than regular multiplication:

    The identity matrix can be thought of as the matrix equivalent of 1, since multiplying by the identity (of the appropriate size) gives back the same matrix with which we began.
    Matrix multiplication is associative (i.e. ($(AB)C = A(BC)$) for appropriately sized matrices ($A,B,C$)), but it is not commutative (i.e. ($AB \neq BA$)) in general. Indeed, both orders of multiplication is only defined if ($A$) and ($B$) are square matrices of the same size.
    There is a matrix version of ($\sqrt{-1}$) (again thinking of ($I$) as 1). Note that 

(:latex:) \[ \left[\begin{array}{cc} 0 & -1 \\ 1 & 0 \end{array}\right] \cdot \left[\begin{array}{cc} 0 & -1 \\ 1 & 0 \end{array}\right] = \left[\begin{array}{cc} -1 & 0 \\ 0 & -1 \end{array}\right] = -I. \] (:latexend:)

    It is possible that the product of two non-zero matrices to give the zero matrix: 

(:latex:) \[ \left[\begin{array}{cc} 0 & 1 \\ 0 & 0 \end{array}\right] \cdot \left[\begin{array}{cc} 0 & 1 \\ 0 & 0 \end{array}\right] = \left[\begin{array}{cc} 0 & 0 \\ 0 & 0 \end{array}\right] \] (:latexend:)
Vectors

Another data structure of importance is a vector, which can be thought of as a single row or single column matrix (depending on context). A useful way to visualize a vector is as a difference between two points, or an arrow from one point to another. So a vector can be thought of as a line segment with both a magnitude (the distance between the two points) and a direction (which way the arrow points).

Vectors can be added by visualizing placing the tail of one vector at the head of the other. Vectors can also be multiplied by a matrix to give another vector (the multiplication is just matrix multiplication, again by thinking of the vector as a matrix with just a single column). 
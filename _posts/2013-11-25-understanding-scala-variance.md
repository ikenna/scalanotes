---
layout: post
title: "An overview of polymorphisim in Scala"
description: ""
category: 
tags: []
---
{% include JB/setup %}

## Scala Variance

* Add examples, maybe even start with them
* You may want to give an overview of the concepts of Types and Polymorphisim. Then discuss how Scala implements these ideas

To understand Variance in Scala, lets first review the concepts of Type and polymorphisism. 


# Type
A Type helps us enforce levels of abstraction (Reynolds 1983). 

Polymorphisim literally translated from the greek, means having many forms. 

Polymorphic languages are in contrast to monomorphic languages - languages in which values and variables have only one type (for example C and Pascal). 
 
- Types help us categorize objects according to their usage and behaviour [2].We can think of types as sets of objects with uniform behaviour. Types help us enforce constraints on how objects interact with other objects, to prevent invalid or inconsistent interactions from occuring.  

A programming language is statically typed, if at compile time, all variables and values are bound to a type at a compile time. Static typing means that type inconsistencies can be discovered at compile time - if a program compiles, it is type-consistent [1] . 

- Polymorphisim 'is the provision of a single interface to entities of different types'. A programming language is said to be monophormic if every variable and value can be of only one type.  A language is polymorphic when values and variables can be of more than one tpe. On a more detailed level, a function is polymorhic if its parameter can have more than one type [1]. A value is polymorphic if it can have more than one type [3].  

There are 2 major kinds of polymorphisim : 

Universal Polymorphisim: Universal polymorphic functions will work on all kind of types that exhibit a common structure.  

Adhoc PolyMorphisim:
Functions that work on a finite set of different or unrelated types (Luca 1985)
Will execute different code for each type of arguement it gets. This is aparent polymorphisim.

Universal PolyMorphisim: Will execute the same code for arguements of an infinite range of types. 


- Parametric Polymorphisim
 a function works consistently on a range of types (as specified by the type parameter), which have all have a common structure. The function takes a type parameter.

 - Inclusion polymorphisim
An object is thought of as belonging to many different classes. 

- Overloading 
 Same variable name is used to denote different functions. 

- Coercion 
An arguement is converted to the type expected by a funtion to prevent a type error. 


References

1.Stroustrup, B. (1994). C++ Programming Language, 3/e. Pearson Education India.

2. Luca Cardelli and Peter Wegner. 1985. On understanding types, data abstraction, and polymorphism. ACM Comput. Surv. 17, 4 (December 1985), 471-523. DOI=10.1145/6041.6042 http://doi.acm.org/10.1145/6041.6042

3. John Reynolds. Types, Abstraction, and Parametric Polymorphism. 1983

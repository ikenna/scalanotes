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

#Type
Types help us categorize objects according to their usage and behaviour [2]. Types help us enforce constraints on how objects interact with other objects, to prevent invalid or inconsistent interactions from occuring.  

#Static Typing
A programming language is statically typed, if at compile time, all variables and values are bound to a type at a compile time. Static typing means that type inconsistencies can be discovered at compile time. [1] . 

#Polymorphisim
Polymorphisim literally translated from the greek, means having many forms.

=> Polymorphic language: A language is polymorphic when values and variables can be of more than one tpe. A programming language is said to be monophormic if every variable and value can be of only one type (for example C and Pascal).  

=> Polymorphic function
 On a more detailed level, a function is polymorhic if its parameter can have more than one type [1]

Kinds of polymorphisim

=> Universal Polymorphisim: This is true polymorphisim: universal polymorphic functions will work on all kind of types that exhibit a common structure. The same code is executed for arguements of an infinite range of types. 

There are 2 kinds of Universal Plymorphisim : 

=> Parametric Polymorphisim: functions work consistently on a range of types (as specified by the type parameter), which have all have a common structure. The function takes a type parameter.


=> Adhoc PolyMorphisim: This is aparent polymorphisim: adhoc polymorphic functions work on a finite set of different or unrelated types (Luca 1985). The will execute different code for each type of arguement it gets. 

 - Inclusion polymorphisim
An object is thought of as belonging to many different classes. 

- Overloading 
- One function name is associated with many function definitions. For example 
    

- Coercion 
An arguement is converted to the type expected by a funtion to prevent a type error. 


References

1.Stroustrup, B. (1994). C++ Programming Language, 3/e. Pearson Education India.

2. Luca Cardelli and Peter Wegner. 1985. On understanding types, data abstraction, and polymorphism. ACM Comput. Surv. 17, 4 (December 1985), 471-523. DOI=10.1145/6041.6042 http://doi.acm.org/10.1145/6041.6042

3. John Reynolds. Types, Abstraction, and Parametric Polymorphism. 1983

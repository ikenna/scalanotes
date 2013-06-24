---
layout: page
title: "Any"
description: ""
---
{% include JB/setup %}

scala.Any is the Scala root class and is similar to java.lang.Object

scala.Any has two subclasses AnyVal and AnyRef. Most scala classes are subclasses of these.  

Int, Long, Float, Double, Short, Char, Byte Boolean are subclasses of AnyVal. At runtime, their values are represented as Java primitives. You can't new these up. 

    
    scala> new Char('x')
    <console>:8: error: class Char is abstract; cannot be instantiated
              new Char('x')


You can't use AnyVal in an Any.isInstanceOf test. You also can't use Any.isInstanceOf to check if an AnyVal is an AnyRef 



    scala> val a = 'a'
    a: Char = a

    scala> a.isInstanceOf[AnyVal]
    <console>:9: error: type AnyVal cannot be used in a type pattern or isInstanceOf test
              a.isInstanceOf[AnyVal]
                            ^

    scala> a.isInstanceOf[AnyRef]
    <console>:9: warning: fruitless type test: a value of type Char cannot also be a AnyRef
              a.isInstanceOf[AnyRef]
                            ^
    <console>:9: error: isInstanceOf cannot test if value types are references.
              a.isInstanceOf[AnyRef]


String is a subclass of AnyRef.

Unit is similar to Java's void


scala.Nothing is 
- a subtype of every other Scala type
- has no instances
- used as a return type for methods with abnormal termination, e.g methods that throw exceptions 

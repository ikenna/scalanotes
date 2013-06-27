---
layout: page
title: "Traits"
description: ""
---
{% include JB/setup %}

Traits (mixins)
can have method and field definitions. A trait can be used to enrich a classes interface


    trait RichInterfaceTrait {
        def someConcreteMethod : String 
        def someUsefulMethod() : Unit= {
            println(someConcreteMethod + " and something more")
        }
    }

    class ConcreteClassWithThinInterface extends RichInterfaceTrait{ 
        def someConcreteMethod() : String  = "do something "
    } 

    val a = new ConcreteClassWithThinInterface()
    a.someUsefulMethod // do something  and something more


- traits provide stackable method modification. 
- If a class has multitple traits, the traits are applied starting from the right to the left. If a method on a trait calls super, the call is made to the trait on its left. (Linearization - inherited classes and traits are put in a linear order. Linearization gets round the Diamond Problem (link to wikipedia) that you can get with multiple inheritance ) 
- super calls in traits are dynamically bound
- traits give you flexibility. Merely switching the order of the traits on a calss can give you a different implementation.


Examples

    scala> abstract class Adder { def add(x: Int):String }
    defined class Adder

    scala> class MyInt(val anInt: Int) extends Adder {  override def add(x: Int):String = "" + anInt + " + " +  x }
    defined class MyInt

    scala> new MyInt(0).add(1)
    res17: String = 0 + 1
        
    scala> trait Add2 extends Adder { abstract override def add(x: Int):String = "2 + " + super.add(x)}
    defined trait Add2

    scala> (new MyInt(1) with Add2).add(0)
    res18: String = 2 + 1 + 0

    scala> trait Add3 extends Adder { abstract override def add(x: Int):String = " 3 + " + super.add(x) }
    defined trait Add3

    scala> (new MyInt(1) with Add2 with Add3).add(0)
    res19: String = " 3 + 2 + 1 + 0"

    scala> (new MyInt(1) with Add3 with Add2).add(0)
    res20: String = 2 +  3 + 1 + 0




- in the above example, note that the abstract methods  on the traits Add2 and Add3 actually have an implementation. 

One more extension on the above

    scala> class ExtendsMyInt(antInt: Int) extends MyInt(antInt: Int)
    defined class ExtendsMyInt

    scala> (new ExtendsMyInt(1)).add(0)
    res1: String = 1 + 0

    scala> (new ExtendsMyInt(1) with Add2 with Add3).add(0)
    res2: String = " 3 + 2 + 1 + 0"
   

Note that if a trait has a concrete implementation, you can instantiate it like you do anonymous inner classes in Java, if you add {}:

    scala> trait Add4 {def add(x: Int):String = "4 + " + x }
    defined trait Add4

    scala> val x = new Add4{}
    x: Add4 = $anon$1@10115870

    scala> val x = new Add4
    <console>:8: error: trait Add4 is abstract; cannot be instantiated
       val x = new Add4
               ^     

To be able to instatiate a trait with {}, the methods must not be abstract though

    scala> val x = new Add2{}
    <console>:9: error: object creation impossible, since method add in trait Add2 of type (x: Int)String is marked `abstract' and `override', but no concrete implementation could be found in a base class
       val x = new Add2{}
                   ^


You can also instantiate a trait by creating a new class that extends the trait

    scala> class Foo extends Add4
    defined class Foo

    scala> new Foo().add(3)
    res5: String = 4 + 3


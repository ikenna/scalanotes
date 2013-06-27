---
layout: page
title: "Packages"
description: ""
---
{% include JB/setup %}


2 ways to put classes in packages - the package clause at top of file syntax:


    package net.ikenna
    class Foo

or the curly brace syntax :

    package net.ikenna { class Foor }


Note that \_root_ is the top level package all your created packages live in. So if you you create com as the top level package in your project, it lives in \_root_.com

In the curly brace packaging syntax, all names accessible in scopes outside the packaging are also available inside it. 

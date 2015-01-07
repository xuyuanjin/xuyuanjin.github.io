---
layout: post
title: Learning Scala
---

{{ page.title }}
================

<p class="meta">04 Jan 2014 - Beijing, China</p>

* use function as parameter

        def a(f:() => Unit)=f()
        a(()=>println("hi echo"))
* Scala don't support i++ and ++i
* Array is mutable，List and Tuple are not; only Tuples can contain different types of elements.
* Tuple's index starting with 1 is a tradition set by other languages with statically typed tuples, such as Haskell and ML.
* public is Scala's default access level.
* The reason parameters are vals is that vals are easier to reason about. You needn’t look further to determine if a val is reassigned, as you must do with a var.
* you must define both the class and its companion object in the same source file.




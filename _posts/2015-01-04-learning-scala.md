---
layout: post
title: Learning Scala
---

{{ page.title }}
================

<p class="meta">04 Jan 2014 - Beijing, China</p>

1. use function as parameter
  {% highlight scala %}
  def a(f:() => Unit)=f()
  a(()=>println("hi echo"))
  {% endhighlight %}
2. Scala don't support i++ and ++i
3. Array is mutable，List and Tuple are not; only Tuples can contain different types of elements.
4. Tuple's index starting with 1 is a tradition set by other languages with statically typed tuples, such as Haskell and ML.
5. public is Scala's default access level.
6. The reason parameters are vals is that vals are easier to reason about. You needn’t look further to determine if a val is reassigned, as you must do with a var.
7. you must define both the class and its companion object in the same source file.




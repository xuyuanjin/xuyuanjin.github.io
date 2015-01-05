---
layout: post
title: Learning Scala
---

{{ page.title }}
================

<p class="meta">04 Jan 2014 - Beijing, China</p>

1. treat function as parameter

{% highlight scala %}
def a(f:() => Unit)=f()
a(()=>println("hi echo"))
{% endhighlight %}

2. Java的i++和++i再scala里不支持

3. Array可变，List与Tuple不可变; Array和List只能包含一种类型的元素，Tuple可包含多种类型的元素, Tuple的访问下标从1开始

4. public是Scala的默认访问级别
5. Scala中方法参数都是val, 而不是var。 The reason parameters are vals is that vals are easier to reason about. You needn’t look further to determine if a val is reassigned, as you must do with a var.

continue from p73




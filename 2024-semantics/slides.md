---
theme: default
paginate: true
---

<style>
div.twocols {
  margin-top: 35px;
  column-count: 2;
}
div.twocols p:first-child,
div.twocols h1:first-child,
div.twocols h2:first-child,
div.twocols ul:first-child,
div.twocols ul li:first-child,
div.twocols ul li p:first-child {
  margin-top: 0 !important;
}
div.twocols p.break {
  break-before: column;
  margin-top: 0;
}
</style>


# The Egel Language

_semantics, the language, current state, future goals_

M.C.A. (Marco) Devillers

---

# The Egel Language

Egel is an untyped concurrent functional scripting language based on eager combinator rewriting

Primarily about exploring and exploiting a trivialized operational model

---

# A term graph

![](termA.png)

Q: design a machine that evaluates terms like the above?

---

# Solution space

An abstract assembly language (LISP)

A variation of a lambda evaluator a la SECD or CAMC (OCaml)

A combinator machine (Miranda)

A graph reduction machine (Haskell, Clean)

*Or all of the above*

----

# The term graph

![](termB.png)

----

# Twist the term graph

<div class="twocols">

![](termC.png)

<p class="break"></p>

link all redexes with

1. what redex to reduce next
2. where to place the reduction

</div>

----

# Directed Acyclic Graph

![](termD.png)

----

# Evaluation (a)

<div class="twocols">

![](termD.png)

<p class="break"></p>

![](termE.png)

</div>

----

# Evaluation (b)

<div class="twocols">

![](termE.png)

<p class="break"></p>

![](termF.png)

</div>

---

# Evaluation (c)

<div class="twocols">

![](termF.png)

<p class="break"></p>

![](termG.png)

</div>

---

# Evaluation (d)

`fac n = n * fac (n - 1)`

<div class="twocols">

![](termH.png)

<p class="break"></p>

![](termI.png)

</div>

---

# Control flow, extending with handlers

`try 1 + throw 42 catch (\x. x)`

<div class="twocols">

![](termJ.png)

<p class="break"></p>

facilitate exceptional control flow with pointers to handlers 

still a directed acyclic graph

</div>

---
# From DAGs to Reference Counting



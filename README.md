<img align="left" width="100" height="150" src="https://www.scala-lang.org/resources/img/scala-spiral-3d-2-toned-down.png">

# ScalaSchool

Welcome to Headstorm Scala School!
 
This series focuses on learning the core elements of Scala and pure functional programming concepts with a sprinkling of [category theory](https://en.wikipedia.org/wiki/Category_theory).

## Basics

Scala is a strongly typed, functional programming language with an OO heritage. It compiles to Java bytecode and runs on the Java Virtual Machine.

## Table Of Contents
1. [Essential Scala](basics/index.md)
2. [Libraries](libraries/index.md)
3. [Testing](testing/index.md)
4. [CICD](cicd/index.md)

## Setup

### Scala and SBT

You will need to install the Scala compiler and SBT (Simple Build Tool) in order to build your Scala projects

    brew install scala
    brew install sbt

### REPL
Use one of the following tools to run your Scala code as you practice, these tools are [REPLs](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop):

  * **Scala REPL:** Scala itself provides a built in REPL: `brew install scala`
  Now type `scala` on the command line. Welcome to your built in Scala REPL!

  * **Ammonite:** Ammonite is a more powerful REPL and runs after installation with `amm` in your shell. Install Ammonite with the below command:  
```bash
sudo sh -c '(echo "#!/usr/bin/env sh" && curl -L https://github.com/lihaoyi/Ammonite/releases/download/1.7.1/2.13-1.7.1) > /usr/local/bin/amm && chmod +x /usr/local/bin/amm' && amm
```

  * **Scastie:** https://scastie.scala-lang.org/

Now you're ready to learn Scala with the resources below:

---

## Recommended Reading:

### Category Theory in Scala

https://github.com/hmemcpy/milewski-ctfp-pdf/releases/download/v1.3.0/category-theory-for-programmers-scala.pdf

### Functional Database Layer: Doobie

https://tpolecat.github.io/doobie/docs/01-Introduction.html

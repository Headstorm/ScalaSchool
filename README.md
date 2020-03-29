<img align="left" width="150" height="200" src="https://www.scala-lang.org/resources/img/scala-spiral-3d-2-toned-down.png">

# ScalaSchool

Welcome to Headstorm Scala School! This series focuses on learning the core elements of Scala and pure functional programming concepts with a sprinkling of [category theory](https://en.wikipedia.org/wiki/Category_theory).

Scala is a strongly typed, functional programming language with an OO heritage. It compiles to Java bytecode and runs on the Java Virtual Machine.

Use one of the following tools to run your Scala code as you practice, these tools are called [REPLs](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop):

  * The built in Scala REPL: `brew install scala`
  Type `scala` on the command line. Welcome to your built in Scala REPL!

  * Install Ammonite with the below command in your Bash shell:  
```bash
sudo sh -c '(echo "#!/usr/bin/env sh" && curl -L https://github.com/lihaoyi/Ammonite/releases/download/1.7.1/2.13-1.7.1) > /usr/local/bin/amm && chmod +x /usr/local/bin/amm' && amm
``` 
 Ammonite runs automatically after installation, and you can run it later by entering `amm` in your shell.

  * Scastie: https://scastie.scala-lang.org/

  * Scala Fiddle: https://scalafiddle.io/

You're ready to start learning Scala with the resources below:

---

## Scala Excercises

These Scala excercises are the best way to start learning the Scala language and ecosystem as a beginner, but there are alse advanced courses here for those looking to advance their understanding.

https://www.scala-exercises.org/

Complete these excercises from the above link in the following order:
1. [Scala Tutorial](https://www.scala-exercises.org/scala_tutorial/terms_and_types)
2. [FP in Scala](https://www.scala-exercises.org/fp_in_scala/getting_started_with_functional_programming)
3. [STD Lib](https://www.scala-exercises.org/std_lib/asserts)
4. [Cats](https://www.scala-exercises.org/cats/semigroup)
5. Complete the rest in any order

## Coursera class by the creator of scala

https://www.coursera.org/collections/learn-scala

## Actor Pattern and Akka

Akka is an important tool in the Scala ecosystem for building distributed systems and event sourcing.

https://doc.akka.io/docs/akka/2.5.3/scala/guide/actors-intro.html
https://doc.akka.io/docs/akka/current/general/actors.html
https://doc.akka.io/docs/akka/current/guide/introduction.html
https://doc.akka.io/docs/akka/current/typed/guide/tutorial_1.html
https://doc.akka.io/docs/akka/current/general/actor-systems.html

## Cats

Cats is an important, widely-used library amongst Scala users for enabling pure functional programming.

https://typelevel.org/cats/
https://books.underscore.io/scala-with-cats/scala-with-cats.pdf

---

## Optional: But Highly Reccomended

### Category Theory in Scala

https://github.com/hmemcpy/milewski-ctfp-pdf/releases/download/v1.3.0/category-theory-for-programmers-scala.pdf

### Functional Database Layer: Doobie

https://tpolecat.github.io/doobie/docs/01-Introduction.html

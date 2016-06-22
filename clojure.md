tags: clojure

# Clojure IDEs
## Cursive Plugin for IntelliJ
https://cursiveclojure.com/userguide/

## Counterclockwise
  * Install *Eclipse*
  * Install *Eclipse Marketplace* from the *Help->Install New Software...*
  * Install *Counteclockwise* from the *Help->Eclipse Marketplace*.
  * Docs: [Counterclockwise User Guide](http://doc.ccw-ide.org/documentation.html)
  
## Emacs + CIDER/clojure-mode

Check [this](http://clojure-doc.org/articles/tutorials/emacs.html#configuring-emacs), for example.

# Exercises  
  * [SICP Distilled](http://www.sicpdistilled.com/)
  * [4clojure.com](https://4clojure.com)
      * [lein-fore-prob tool](https://github.com/bfontaine/lein-fore-prob) to fetch problems from 4clojure.
      * `{:user {:plugins [ [lein-fore-prob "0.1.2"] ]}}` in `~/.lein/profiles.clj` and Leiningen will fetch and install it in the next run.
  * Exercises of the [Clojure for the Brave and True book](http://www.braveclojure.com/introduction/).
  
# Ecosystem
## Leiningen
Declarative instead of imperative (Boot)

[Leiningen](http://leiningen.org/) as a build tool, like *maven* for Java or *sbt* for Scala.

It **autoinstalls**: you download a little script, that on the first run download the real Leiningen and sets it up.

How to use it?

Example:

    $ lein help
    $ lein new project-name && cd project-name/
    $ lein fore-prob <number>  # Use the lein-fore-prob plugin
    $ lein test
    $ lein midje :autotest :filter -slow timely  # to run midje tests while programming.

## Boot
Imperative instead of declarative (Leiningen)

## UnitTests

midje

## Code Analysis

* [SonarQube plugin for Clojure](https://github.com/zmsp/sonar-clojure)
* [kibit is a static code analyzer for Clojure and other Clojure variants](https://github.com/jonase/kibit)
* [eastwood - a Clojure lint tool](https://github.com/jonase/eastwood)
* [yagni - A Leiningen plugin for finding dead code](https://github.com/venantius/yagni)
* Some other very interesting tools mentioned [here](http://blog.mattgauger.com/blog/2014/09/15/clojure-code-quality-tools/).

# Books

* [Clojure for the Brave and True book](http://www.braveclojure.com/introduction/)

# Jobs

* [https://jobs.braveclojure.com/](https://jobs.braveclojure.com/)


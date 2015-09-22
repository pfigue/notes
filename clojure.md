tags: clojure

# Clojure IDEs
## Cursive Plugin for IntelliJ
https://cursiveclojure.com/userguide/

## Counterclockwise
  * Install *Eclipse*
  * Install *Eclipse Marketplace* from the *Help->Install New Software...*
  * Install *Counteclockwise* from the *Help->Eclipse Marketplace*.
  * Docs: [Counterclockwise User Guide](http://doc.ccw-ide.org/documentation.html)

# Exercises  
  * [SICP Distilled](http://www.sicpdistilled.com/)
  * [4clojure.com](https://4clojure.com)
      * [lein-fore-prob tool](https://github.com/bfontaine/lein-fore-prob) to fetch problems from 4clojure.
      * `{:user {:plugins [ [lein-fore-prob "0.1.2"] ]}}` in `~/.lein/profiles.clj` and Leiningen will fetch and install it in the next run.
  
# Ecosystem
## Leiningen
[Leiningen](http://leiningen.org/) as a build tool, like *maven* for Java or *sbt* for Scala.

It **autoinstalls**: you download a little script, that on the first run download the real Leiningen and sets it up.

How to use it?

Example:

    $ lein help
    $ lein new project-name && cd project-name/
    $ lein fore-prob <number>  # Use the lein-fore-prob plugin
    $ lein test
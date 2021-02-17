# The First Steps

Since I've already been at this for a couple of days, I figure that now is as good a time as any to recap things for myself. The idea here is that as I travel through the braveclojure.com site, at the end of each day I'll write up what it was that I learned as an attempt to try to keep things fresh and retained.

We'll see how this goes.

## Creating new clojure projects

New clojure projects can be created with the [Leiningen](http://leiningen.org/) command line application. Installation is pretty straightforward for us Linux users. It's kind of a given, I would assume, that since clojure runs on the JVM that you would already have a Java Runtime installed.

New clojure projects are created by:

```bash
lein new app <name-of-project>
```

Lein can also be used to run your project, first navigate into the newly created directory and...

```bash
cd <name-of-project> && lein run
```

Lein can create distributables...

```bash
lein uberjar
```

The above creates the _target/uberjar/<name-of-project-with-release-data>-standalone.jar_ file. 

Lein can be used to access a REPL:

```bash
lein repl
```

Of course, you'll most likely want to use an actual editor, which brings us to....[Emacs](2-emacs.md).

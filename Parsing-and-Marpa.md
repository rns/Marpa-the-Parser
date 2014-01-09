### Parsing and Marpa

Let us define [parsing](http://en.wikipedia.org/wiki/Parsing) as a way to convert input (source) to output (target) according to grammar.

To sound proverbially, if all you have is a parser, then everything is a language. Proverbial bias notwithstanding, in a world organized around languages, where one language's semantics is another language's syntax, parser(s) (per the above definition) can be all you need.

With Marpa, it means that [The Interpreter Design Pattern](http://en.wikipedia.org/wiki/Interpreter_pattern), once called [a sort of practical joke](https://sites.google.com/site/steveyegge2/ten-great-books) can now [be practically used](http://jeffreykegler.github.io/Ocean-of-Awareness-blog/individual/2013/03/interpreter.html).

### Interpreter Pattern ([DSL](http://martinfowler.com/dslCatalog/))

+ Input (Source)
+ Syntax
+ Semantics
+ Output (Target)

### Marpa the Parser: libmarpa + interfaces

+ [libmarpa]
+ Perl Interfaces
    - [Scanless Interface](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod) (SLIF)
    - [Named Argument Interface](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/NAIF.pod) (NAIF)
    - [Thin Interface](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Advanced/Thin.pod) (THIF)
+ Interfaces in Other Languages
    - [Higher Level Go module for libmarpa](https://github.com/pstuifzand/go-marpa/)
    - [C++ experiment](https://github.com/pstuifzand/marpa-cpp-rules)

[libmarpa]: http://jeffreykegler.github.io/Marpa-web-site/libmarpa.html

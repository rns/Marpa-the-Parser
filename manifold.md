Parsing and Marpa
-----------------

Let us define [parsing](http://en.wikipedia.org/wiki/Parsing) as a way to convert input (source) to output (target) according to grammar.

To sound proverbially, if all you have is a parser, then everything is a language. Proverbial bias notwithstanding, in a world, organized around languages, where one language's semantics is another language's syntax, parser(s) (per the above definition) can be all you need.

With Marpa, it means that [The Interpreter Design Pattern](http://en.wikipedia.org/wiki/Interpreter_pattern), once called [a sort of practical joke](https://sites.google.com/site/steveyegge2/ten-great-books) can now [be practically used](http://jeffreykegler.github.io/Ocean-of-Awareness-blog/individual/2013/03/interpreter.html).

Outlines
--------

* Parsing/Language
    + Input (Source)
    + Syntax
    + Semantics
    + Output (Target)

* Marpa the Parser
    Marpa the Parser is libmarpa + interfaces.
    + [libmarpa](http://jeffreykegler.github.io/Marpa-web-site/libmarpa.html)
    + Perl Interfaces
        - [Scanless Interface (SLIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod)
        - [Named Argument Interface (NAIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/NAIF.pod)
        - [Thin Interface (THIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Advanced/Thin.pod)
    + Interfaces in Other Languages
        - [Higher Level Go module for libmarpa](https://github.com/pstuifzand/go-marpa/)
        - [C++ experiment](https://github.com/pstuifzand/marpa-cpp-rules)

+ Declarative and/or Procedural Parsing
    - http://jeffreykegler.github.io/Ocean-of-Awareness-blog/individual/2013/06/mixing-procedural.html
    - https://groups.google.com/forum/#!topic/marpa-parser/X8AMiENdpVk

* Using Marpa with Perl
    + The Language
        - Simple calculator
        - Precedence
    + [SLIF](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)
        - Describing Syntax
        - Defining Semantics
            - Actions (semantic_package) and Blessing (bless_package) 
            - [Actions as blessed data](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)
            - [Actions as blessed code](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_gsyn.t)
            - Walking AST
            - Traversing ASF
            - Comparison
        - Putting it all together
        - Tracing and Debugging
    + [NAIF](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/NAIF.pod)
    + THIF
    
* Handling Ambiguity
NAIF
SLIF

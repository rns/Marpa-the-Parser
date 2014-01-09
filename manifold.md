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

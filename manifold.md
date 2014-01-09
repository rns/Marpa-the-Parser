Outlines
--------

* Parsing/Language
    + Input (Source)
    + Syntax
    + Semantics
    + Output (Target)

* Marpa the Parser: libmarpa + interfaces
    + [libmarpa]
    + Perl Interfaces
        - [Scanless Interface (SLIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod)
        - [Named Argument Interface (NAIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/NAIF.pod)
        - [Thin Interface (THIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Advanced/Thin.pod)
    + Interfaces in Other Languages
        - [Higher Level Go module for libmarpa](https://github.com/pstuifzand/go-marpa/)
        - [C++ experiment](https://github.com/pstuifzand/marpa-cpp-rules)

* Declarative and/or Procedural Parsing
    + http://jeffreykegler.github.io/Ocean-of-Awareness-blog/individual/2013/06/mixing-procedural.html
    + https://groups.google.com/forum/#!topic/marpa-parser/X8AMiENdpVk

* Using Marpa with Perl
    + The Language
        - Simple calculator
        - Precedence

    THIF provides direct access to [libmarpa][libmarpa], NAIF allows describing the grammar rules as Perl array/hash, SLIF supports textual grammars, internal/external lexing, general precedence, events.

    + [SLIF][SLIF]
        - Describing Syntax
        - [Defining Semantics](https://github.com/rns/Marpa-the-Parser/blob/master/Defining-Semantics-in-SLIF.md)
        - Putting it all together
        - Tracing and Debugging
    + [NAIF][NAIF]
    + [THIF][THIF]
    
* Handling Ambiguity
    + [NAIF][NAIF]
    + [SLIF][SLIF]

[libmarpa]: http://jeffreykegler.github.io/Marpa-web-site/libmarpa.html

[SLIF]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod

[NAIF]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/NAIF.pod

[THIF]: (https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Advanced/Thin.pod)

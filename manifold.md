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
        - [multisymbols and read()](https://gist.github.com/rns/3683268)
        - [single symbols and alternative()](https://gist.github.com/rns/3683179)
    + [SLIF][SLIF]

* Ideas
    + JSON Parser Comparison
        - JSON::XS (parsing in C, actions in C)
        - JSON::PP (parsing in Perl, actions in Perl)
        - MarpaX::Demo::JSONParser (parsing in C, actions in Perl)
            - bless_package
            - semantics_package
            - AST
            - ASF
            - which is more efficient and how much is the difference?
        - JSON::XS vs. MarpaX::Demo::JSONParser = actions in Perl vs. actions in C

* Misc
    + Lexing in Marpa and Perl
        - [Generating flex Lexical Scanners for Perl Parse::Yapp](http://drops.dagstuhl.de/opus/volltexte/2012/3513/pdf/6.pdf)
        - https://metacpan.org/pod/Parse::Lex
        - Parse::Lex & Parse::CLex
        - Parse::Flex - The Fastest Lexer in the West

[libmarpa]: http://jeffreykegler.github.io/Marpa-web-site/libmarpa.html

[SLIF]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod

[NAIF]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/NAIF.pod

[THIF]: (https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Advanced/Thin.pod)

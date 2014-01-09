Outlines
--------

* Ideas
    + JSON Parsers
        - encoding and decoding
        - JSON::XS (parsing in C, actions in C)
        - JSON::PP (parsing in Perl, actions in Perl)
        - MarpaX::Demo::JSONParser (parsing in C, actions in Perl)

            Actions defined via:

            - bless_package
            - semantics_package
            - [AST](http://jeffreykegler.github.io/Ocean-of-Awareness-blog/individual/2013/03/bnf_to_ast.html)
            - ASF: [high-level](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/ASF.pod), [low level](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Glade.pod)
            - which is more efficient and how much is the difference?

* Misc
    + Lexing in Marpa and Perl
        - [Generating flex Lexical Scanners for Perl Parse::Yapp](http://drops.dagstuhl.de/opus/volltexte/2012/3513/pdf/6.pdf)
        - https://metacpan.org/pod/Parse::Lex
        - Parse::Lex & Parse::CLex
        - Parse::Flex - The Fastest Lexer in the West

[SLIF]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod

[NAIF]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/NAIF.pod

[THIF]: (https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Advanced/Thin.pod)

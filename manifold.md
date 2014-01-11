Outlines
--------

* sequence separator can be [,] not only a symbol name

* out of SLG::symbol_*(), only symbol_display_form() and symbol_name() seem to be compatible with rule_expand()
    - https://groups.google.com/forum/#!topic/marpa-parser/SyBfWJ3ylrE

    - write test L0 vs. G1

        `my ( $lhs, @rhs ) = map { $slg->symbol_display_form($_) } $slg->rule_expand($rule_id, 'L0');`

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

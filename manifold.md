Outlines
--------

* Data::Range::Compare
    + ASF's
        - span/literal-based ambiguity reporting
        - cross-sentence disambiguation
    + MarpaX::Filter

* MarpaX::Interface::SSLIF
    - Writing Marpa Interfaces
        - MarpaX::Interface abstraction: frontend/backend
    - MarpaX::Interface::SSLIF

* MarpaX::Languages::SLIF::AST
    - pretty_print
    - lint
    - translate
        + via MarpaX::Filter?
    - use ASF?

* lhs and name to action adverb
    cpan/lib/Marpa/R2/Value.pm
    See https://groups.google.com/forum/#!topic/marpa-parser/ub5ZOYF3qIQ

* Marpa::R2::Cookbook
    - atof
    - atoi
    - Parse::Recdescent example
    - Interpreter pattern
    
* Parse Patterns
    - given a file, how is it better to parse it?

        `$recce->read(slurp($filename))

        for $line (@lines){
            $recce->read($line);
        }`
    
* making --XS-debug work on windows

    branch added
    
* 'everything else' rule

* sl_panda.t: remove PennTags bless_package and try to do all semantics in ASF

* sequence separator can be [,] not only a symbol name
    See https://groups.google.com/forum/#!topic/marpa-parser/9maeN3sDbxE

* out of SLG::symbol_*(), only symbol_display_form() and symbol_name() seem to be compatible with rule_expand()
    - https://groups.google.com/forum/#!topic/marpa-parser/SyBfWJ3ylrE

    - write test L0 vs. G1

        `my ( $lhs, @rhs ) = map { $slg->symbol_display_form($_) } $slg->rule_expand($rule_id, 'L0');`
        
    See https://github.com/jeffreykegler/Marpa--R2/pull/74

* Ideas
    + JSON Parsers Shoutout
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

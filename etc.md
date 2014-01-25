Braindumps
==========

Meta
----

* item -- Category
    - subitem
    + subitem I'm on
    - everything else
    - hierarchy!
    -- explanations

Priorities
----------

multiple grammars

rule array descriptor - 

MarpaX::Regex::Verbal
MarpaX::Parse
Yaccy
MarpaX::Lotsawa -- The Pattern Pattern

Lotsawa -- [The Translator Pattern](http://c2.com/cgi/wiki?TranslatorPattern), with a twist.

Lotsawa is language translation based on Marpa

The Lotsawa Manifesto

11. The higher beings are connected to the others by analogy, not by composition.
[My philosophical viewpoint](http://web.archive.org/web/20120206150643/http://cs.nyu.edu/kandathi/goedel_viewpoint.html)
-- Kurt Friedrich Godel, c. 1960.

    0. Your really know it only when you talk to it.
    1. Language is syntax and semantics.
    2. One language's syntax is another's semantics.
    3. There are terminal languages (whose semantics is used directly) and non-terminal (intermediate) languages.
    4. Languages form grammars of their own.
    5. Grammars of languages serve as information paths.
    6. Hence, every information problem is a translation problem.
    7. And there is only one true pattern -- The Translator Pattern.

    Links/Prior Art
        http://stackoverflow.com/questions/1949708/translator-pattern
        http://c2.com/cgi/wiki?TranslatorPattern
        http://nickmayne.com/memorystream/the-translator-mapper-pattern
        The God's Proof
        
Minimal Viable Product
    source BNF
    target BNF
    patterns
    
    verbal expressions to regular expressions
    
The Pattern Pattern
    
    pattern-based translation
    
rule_closure()

    sl_panda1.t is ready for testing with ASF::rh_values()
    Deyan's feedback is sought

* add ruleid

* program in BNF

* semantics 
    
    Ain't no OO -- grasp it when you see it

    Rules are `sub`s
        
        MarpaX::Parse
            Declarative and Procedural Parsing unified
            AST/ASF-agnostic
                ASF for ambiguous grammars in the same interface
            Parsing as Traversing -- Semantic parsing 
                traverse input (events)
                    do semantics once the data are ready
                        via events, e.g. sl_json.t trims quotes -- this was an inspiration
                traverse parse tree/forest
            
            Case Study: 

            MarpaX::Parse::JSON -- in the same distro, like Marpa::HTML
            
        
        my $p1 = MarpaX::Parse->new($grammar1, $traverser1); # to act as a filter in pipeline
        my $p2 = MarpaX::Parse->new($grammar2, $traverser2);
        
        my $v = ($p1 | $p2)->value($input);
        
        my $value = MarpaX::Parse->value($grammar, $traverser, $input);
        
        MarpaX::Parse->p(<<GRAMMAR, <<TRAVERSER, <<INPUT);
        
        GRAMMAR
        
        TRAVERSER
        
        INPUT
        
        
                        
                ASF::*::next_symch
                    set data to make them available
                    return
                    for the next call
                    
                closures without eval

            signature-based dispatch
                lhs ::= rhs11 rhs12 rhs12 ... 
                      | rhs21 rhs22 rhs22 ... 
                      ...
                      adverbs
                data -- per array descriptor action
                $node
                    start
                    length
                    lhs
                    rule
                    values
                    grammar (G or L)
                    recognizer
                    phase
                    event
                        trigger
                        read()/resume()
                    

    - must add value()
        - the user must speak her language - i.e. as for value
        - and the grammars must speak theirs
    
    Patterns
        - callbacks
        - AST or ASF based on ambiguity -- idea for MarpaX::Parse?
        - 
        
    - constructing an object from the grammar?
        dispatch -- ASF
        
    - ASF::traverse()
    
    - grammar reuse as a programming unit (grammar of languages)
        - grammar algebra/parser combinators
            - Marpa must be able to parse even a grammar obtained by text-based merging of the rules, but what will be the result
        - filters and pipelines
    - easing the grammar/code impedance mismatch
        
    - but grammar is the code (and data)!
        - recognizers' value() is here        
        - at least the semantic (those containing properly mapped values) nodes of it
        
    - think Perl6 

* lhs_desc -> MarpaX::Interface::SLIF::AST (Marpa::R2::AST hopeful)

    - MarpaX::Interface::SLIF::AST

        - MarpaX::Interface::SLIF::AST->new( $slr );
        - get grammar
        - generate constants in symbols table for every lhs via rule_ids()
        - walker/visitor
            tree node visitor
        - traverser 
            like ASF (all you need is to return)

* ASF
    disamb
    and amb reporting
    
* spaces in array descriptors

* THIF?


NLP
    hornby and ada

JSON

Categories
----------

* Current
* DSLs
* Features
* Internals
* Interfaces
* NLP
* Touchups
* Visibility

Current
-------

* MarpaX::Languages::SLIF::AST
    - pretty_print
    - lint
    - translate to other BNF formats
        + via MarpaX::Filter?
    - use ASF?

* incorporate Drafts (4)

* THIF -- Interfaces
    * code generation or wrapping?
    * MarpaX::Thin::Generator
        - grammar, recognizer, and valuator code generator
    * MarpaX::Thin 
        - narrow level above Marpa::R2::Advanced::Thin

        - MarpaX::Thin::Grammar->new($source_aref)
        - MarpaX::Thin::Recognizer->new(
            grammar from MarpaX::Thin::Grammar or NAIF or SLIF
          )
        - MarpaX::Thin::Value
            MarpaX::Thin::Value->new(MarpaX::Thin::Recognizer)
        - MarpaX::Thin::Parse->new($grammar, $input);

!* spaces in array descriptors -- Internals
    - <result item descriptor list> must remain L0 a lexeme?
        clashes with '[values]' if it's G1
    - sl_to_hash.pl
    + https://github.com/jeffreykegler/Marpa--R2/issues/75

!* lhs and name as array descriptors in action adverb
    - MarpaX::Interface::SLIF::AST -- Marpa::R2::AST would-be
        
    + more tests
        + sl_json_ast.t
        - sl_panda.t: remove PennTags bless_package and try to do all semantics in AST
        - sl_syn_ast.t
        
    - first implementation merged
    - https://groups.google.com/forum/#!topic/marpa-parser/ub5ZOYF3qIQ

!* use cases for Undo's -- Features
    - [forgiving-for-parsing-msvc-warnings.t](https://gist.github.com/rns/8473261)
    - _maybe rules in JD MarpaX::Languages::C::AST
    - Lexy -- Marpa-powered Lex: Lex regexes with Marpa-powered extensions
  
DSLs
----

* MarpaX-DSLs.tws

* 'everything else' rule -- NLP, DSLs

Internals
---------

* decouple Marpa::HTML 
    - as MarpaX::HTML

NLP
---

* MarpaX-NLP.tws

* Data::Range::Compare
    + ASF's
        - span/literal-based ambiguity reporting
        - cross-sentence disambiguation
    + MarpaX::Filter
        - based on ASF/AST [start, length, values]

Interfaces
----------

* Marpa-powered regexes
    - in Perl
    - as mpre - Marpa Powered Regular Expressions
    - THIF

* Yacc on Marpa

    Yacc is syntax, Marpa is semantics
    MarpaX::Languages::Yacc::DSL

* Object-oriented semantics
    - action_object: per-parse variable + actions
    
* MarpaX::Interface::Yaccy (Lexy)
    - Version 0.1
        - inline actions, captures, precedence
                e ::= e * e { $1 + $2 } || e + e { $1 + $2 } | e - e { $1 + $2 }
        - SLIF as a backend
      Future          
        THIF as a backend
        preprocessor, like C preprocessor
            macros
            templates
            includes
    
    - Writing Marpa Interfaces
        - MarpaX::Interface abstraction: frontend/backend

    - Sneakpeak
            Script:
                    Expression (',' Expression )* { @1 }

            Expression: 
                    Number { $1 }
                |   '(' Expression ')' { $2 }
                ||  Expression '**' Expression { $1 ** $3 }
                ||  Expression '*' Expression  { $1 * $3 }
                |   Expression '/' Expression  { $1 / $3 }
                ||  Expression '+' Expression  { $1 + $3 }
                |   Expression '-' Expression  { $1 - $3 }

            Number: m/\d+/ # Named rules

            ws: [\s+] {skip}

    - Features in the order of implementation importance
        - Captures/Predefined vars
            $1, $2 — value of rhs_symbol1, rhs_symbol2

            $lhs
            @rhs
            @values

            @1, @2 — rhs_sequence1, rhs_sequence2
            see how it's done in regexps
            %lhs, %1, %2 — lhs => { rhs_symbol1 => value1 , rhs_symbol2 => value2 } if and rhs names are needed
            insertion order — Tie::IxHash
            insertion order and duplicate keys via 
            Tie::DxHash

        - Reuse -- macros/templates for 
            - rules, RHS alternatives and actions via <> {} and {{var}}
            - Sneakpeak
                <rule template>(<1>, <2>, ...) ::= <lhs_{{1}}>: <rhs_{{2}}> { do_{{1}}, do_{{2}} } 
                {action template}(<1>, <2>, ...) ::= { }
                Rule templates
                <template name>(<1>, <2>) ::= <lhs_{{1}}>: <rhs_{{2}}> { do_{{1}}, do_{{2}} } 
            RHS alternative templates
            Action templates — like C preprocessor macros?

            instantiation/expansion via barewords
            <template-name>(arg1, arg2)

            Action reuse -- references to actions 
            lhs : rhs { @lhs/rhs_alternative_no }

* MarpaX::Parse
    ! this starts when grammar (including lexer) and recognizer are here
    - parser interface to Marpa's grammars and recognizers:
        - you have a gram and a rec: now you can 
            my $p = MarpaX::Parse->new($gram, $rec)->parse($input);
        - you have a gram source (string, file, anything string-tied)
            my $p = MarpaX::Parse->new($gram)->parse($input)
    - ->new($grammar or $grammar_source or grammar_file)
      parse($ref -- string or anything tie'able to string: filename, filehandle)
    - given a file, how is it better to parse it?

        `$recce->read(slurp($filename))

        for $line (@lines){
            $recce->read($line);
        }`

Misc
----

* Marpa::R2::Cookbook
    - atof
    - atoi
    - Parse::Recdescent example
    - Interpreter pattern

* Lexing in Marpa and Perl
    - [Generating flex Lexical Scanners for Perl Parse::Yapp](http://drops.dagstuhl.de/opus/volltexte/2012/3513/pdf/6.pdf)
    - https://metacpan.org/pod/Parse::Lex
    - Parse::Lex & Parse::CLex
    - Parse::Flex - The Fastest Lexer in the West

Touchups
--------

ASF Touchups
    - move Cartesian product into a method of ASF
    - document that $glade->next() may change rule_id

    * ASF.pod =~ s/rh_count()/rh_length()/

        At rule alternatives, the rh_count() and the rh_value() glade methods are of use. The rh_count() method returns the length of the RHS, and the rh_value() method returns the value of one of the RHS children, as determined using its traverser.

    * ASF.pod =~ note about glade->next()

        The code in CHOICE loop calling glade->next() cannot use the glade data 
        obtained before the loop. All glade data must be re-obtained via 
        the relevant getter getters. That's because glade->next() may change 
        the current glade in recursive traverser calls.

* Done

    * indicates that indicates that in api.texi
        + https://github.com/jeffreykegler/Marpa--R2/pull/88
            @deftypevr Macro int MARPA_ERR_INACCESSIBLE_TOKEN
            This error code indicates that
            indicates that
  
    * out of SLG::symbol_*(), only symbol_display_form() and symbol_name() 
        seem to be compatible with rule_expand()
        - https://groups.google.com/forum/#!topic/marpa-parser/SyBfWJ3ylrE
        - show_grammar.t, symbol_dsl_form.t        
        See https://github.com/jeffreykegler/Marpa--R2/pull/74

    * making --XS-debug work on windows
        + https://github.com/jeffreykegler/Marpa--R2/pull/77

    * sequence separator can be [,] not only a symbol name
        See https://groups.google.com/forum/#!topic/marpa-parser/9maeN3sDbxE
        - Fixed in commit 360d0ac.  -- jeffrey
    
Visibility
----------

* Overarching: 

    Translation Pattern
    Every problem is a translation problem
    Interpreter Pattern is really a translation pattern

* Ada quote

* MarpaX::Translate
    
    generalized pattern-based translation
    given 2 BNFs and rules, generate translator
    regexp to 

        Translation Framework

        AST is the same
        use case: verbal expressions to regular expressions

        https://github.com/VerbalExpressions/JSVerbalExpressions
        https://github.com/VerbalExpressions/JSVerbalExpressions/wiki

        pattern hierarchy

        source grammar
            context-insensitive patterns
            context-sensitive patterns
            domain-sensitive patterns  — ремонтный in agriculture
            target grammar

        pattern accumulation
        pattern extraction
        pattern application
        translation

        translation grammar (TG)
            source pattern -> target pattern
        source/target patterns form a grammar
        TG is generated with source patterns as rules and target patterns as actions 
            LHS and RHS are patterns in source and target languages
        static (context-insensitive, 1-to-1) patterns 
        capturing syntax-independent equivalents (base forms)
            выполнять обязательство
        perform obligation
        dynamic (context-sensitive, with variables) patterns 
        capturing syntax

        XSLT
        grammar inference
        source grammar is derived as all LHSes from the translation grammar
        parse will produce ordered sequence of terms to look in equivalence patterns 
        found equivalence patterns will be substituted to RHS
        text to AST cache
        search 
        as a set of all LHS
        parse until match
        translation of algebraic expressions 

* English to mop, Moo, Moops, Mouse, Moose -- natural programming languages
    
    https://github.com/stevan/p5-mop-redux
    
* go-marpa or marpa-go (Stuifzand)
    - https://github.com/pstuifzand/

* interfaces

    Yaccy -- Simplified SLIF

* legacy support
    
    - MarpaX::Languages::Yacc::AST
    
* simplicity
    
    Yaccy
    
* speed
    
    THIF
    MarpaX::Interface::SLIF::AST
    
* articles/books

    Know Thy Rules
    
    Let's start empty. Empty rule that is.
    
        :start  ::= list
        list    ::= elem | list (',') elem
        elem    ::= 
        elem    ::=  'a' | 'b' | 'c'

        -- Jeffrey Kegler, http://scsys.co.uk:8002/291626?submit=Format+it%21

* syntax highlighter for SLIF

    - MarpaX::Languages::SLIF::AST

* modules
    
    - MarpaX::Filter

    - MarpaX::NLP
        - MarpaX::Languages::Russian::AST
        - MarpaX::Languages::English::AST    

    - MarpaX::SGML
    - MarpaX::Languages::JSON::AST
    - MarpaX::Languages::C::AST

* Big Name parsers -- Regex, HTML, XML, SGML, JSON, Markdown, POD
    
    Simple BNF ala Verbal Expressions for regex
        https://groups.google.com/d/msg/marpa-parser/2TZn5nolyzk/u5rCDIZ0gKoJ
        http://search.cpan.org/~abigail/Regexp-Common-2013031301/lib/Regexp/Common.pm
        
    Markdown
    
* proof of linearity -- 
    - JSON
        * MarpaX::Languages::JSON::Benchmark -- determine MarpaX::Languages::JSON::AST
            + test suite
                - import from JSON::XS|PP
                - add files unless already 
                - parse test suite of 
            - JSON::XS (parsing in C, actions in C)
            - JSON::PP (parsing in Perl, actions in Perl)
            - sl_json.t
                Actions defined via:

                - bless_package
                - semantics_package
                - [AST](http://jeffreykegler.github.io/Ocean-of-Awareness-blog/individual/2013/03/bnf_to_ast.html)
                - ASF: [high-level](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/ASF.pod), [low level](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Glade.pod)
                - which is more efficient and how much is the difference?
    - XML
    - HTML
        - Marpa::HTML
    - regex

Debugging
    <print> <where> <what> <how> <stacktrace>;

    warn Dumper(...);
   
    Data::Dump
    Data::Dumper::Concise
    Data::Dumper
    Carp::Always

Refs
====

[SLIF]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod

[NAIF]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/NAIF.pod

[THIF]: (https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Advanced/Thin.pod)

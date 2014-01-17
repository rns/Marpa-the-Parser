### Outline

* Code and Data: `action` `sub`(s) and Parse Nodes' Values
    
    + Blessed is the Code: `bless` `action` `sub`s into `semantic_package`

        Every sub specified with `action` adverb will be called and passed a reference to array holding the parse node' values.

        [Example](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_gsyn.t)

    + Blessed is the Data: `bless` parse nodes' values into `bless_package`

        Every node's values are blessed into `bless_package` and must be processed with `sub`s in that package.

        [Example](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod#Synopsis)

    As only one bless adverb is allowed, the two options above are orthogonal and cannot be mixed and matched.

* Running more [DRY](http://en.wikipedia.org/wiki/Don't_repeat_yourself)

    + Blessed is the Code and the Data
    
        Walking the AST of nodes' values blessed into `bless_package` and subpackages set for individual rules using `bless`.

        Example 1: [writeup](http://jeffreykegler.github.io/Ocean-of-Awareness-blog/individual/2013/03/bnf_to_ast.html), [code](https://gist.github.com/jeffreykegler/5121769)

        [Example 2](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_timeflies.t)

    + Advanced actions, e.g. ambiguious parses, filters: [ASF traverse()](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/ASF.pod#traverse)

        [Example](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_panda.t)
    
        Jeffrey Kegler: I expect the ASF to be the basis of a faster evaluator some day. -- https://groups.google.com/d/msg/marpa-parser/oPnY83-mx7I/AHrZA_Oe_xIJ
    
* Discussion


* Events for semantics -- sl_json.t from Marpa::R2 test suite

    - in the grammar

        `lstring        ~ quote in_string quote
        quote          ~ ["]
        in_string      ~ in_string_char*
        in_string_char  ~ [^"] | '\"'`

    - in the code

        `my $length = length $string;
        for (
            my $pos = $re->read( \$string );
            $pos < $length;
            $pos = $re->resume()
            )
        {
            my ( $start, $length ) = $re->pause_span();
            my $value = substr $string, $start + 1, $length - 2;
            $value = decode_string($value) if -1 != index $value, '\\';
            $re->lexeme_read( 'lstring', $start, $length, $value ) // die;
        } ## end for ( my $pos = $re->read( \$string ); $pos < $length...)`

### References

* [Scanless Interface to Marpa (SLIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)

* The Key Words
    
    - [`action`](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#action) and [`bless`](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#bless) adverbs as apply to 

        - [rules](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#The-structure-of-rules) (except that lexical (L0, '~') rules can't have `action`s

        - [`:default`](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#Default-pseudo-rules) pseudo-rule, and 
        
        - [`lexeme default`](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#Lexeme-default-statement) statement
        
            - [array descriptor](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Semantics.pod#Array-descriptor-actions) actions for default rules
        
    - [`semantic_package`][semantic_package] (SLIF recognizer) and [`bless_package`][bless_package] (SLIF grammar) named arguments

    - [per-parse argument](https://metacpan.org/pod/Marpa::R2::Semantics#The-per-parse-argument) and [per-parse constructor](https://metacpan.org/pod/Marpa::R2::Semantics#The-per-parse-constructor)
    
[semantic_package]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/R.pod#semantics_package

[bless_package]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/G.pod#bless_package

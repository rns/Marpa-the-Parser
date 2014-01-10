### Outline

* [Scanless Interface to Marpa (SLIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)
* The Key Words
    
    - [action](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#action) and [bless](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#bless) adverbs as apply to 

        - [rules](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#The-structure-of-rules)

        - [:default](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#Default-pseudo-rules) pseudo-rule, and 
        
        - [lexeme default](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#Lexeme-default-statement) statement
    
    - [semantic_package][semantic_package] (SLIF recognizer) and [bless_package][bless_package] (SLIF grammar) named arguments
    
* Blessed is the Code

    Actions as subs blessed into semantic_package.
    
    [example](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_gsyn.t)

* Blessed is the Data (and the Code)

    Actions as blessings of parse nodes' values blessed into bless_package processed with subs in the same package.
    
    [example](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)

    As only one bless adverb is allowed, the two options above are orthogonal.

* Blessed is the AST -- walking the blessed 
* Advanced action: ASF traverse()
* Comparison

Code and Data: Action sub(s) and Parse Nodes' Values

Running DRY

- 
- 
- actions as bless_package AST walk 

Advanced actions
- 

[semantic_package]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/R.pod#semantics_package 

[bless_package]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/G.pod#bless_package 

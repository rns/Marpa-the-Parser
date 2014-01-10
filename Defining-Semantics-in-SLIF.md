### Outline

* [Scanless Interface to Marpa (SLIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)
* The Key Words
    
    - [action](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#action) and [bless](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#bless) adverbs as apply to 

        - [rules](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#The-structure-of-rules)

        - [:default](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#Default-pseudo-rules) pseudo-rule, and 
        
        - [lexeme default](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#Lexeme-default-statement) statement
    
    - [semantic_package][semantic_package] (SLIF recognizer) and [bless_package][bless_package] (SLIF grammar) named arguments
    
* [Actions as blessed data](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)
* [Actions as blessed code](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_gsyn.t)
* Walking an AST
* Traversing an ASF
* Comparison

Code and Data: Action sub(s) and Parse Nodes' Values

Running DRY

- actions as subs in semantic_package
- actions as blessings of parse nodes' values via bless_package
- actions as bless_package AST walk 

Advanced actions
- ASF traverse

[semantic_package]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/R.pod#semantics_package 

[bless_package]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/G.pod#bless_package 

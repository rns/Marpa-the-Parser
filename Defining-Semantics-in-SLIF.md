### Outline

* Code and Data: `action` `sub`('s) and Parse Nodes' Values
    
    + Blessed is the Code

        Actions as `sub`'s blessed into `semantic_package`.

        [Example](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_gsyn.t)

    + Blessed is the Data

        Actions as blessings of nodes' values blessed into `bless_package` processed with `sub`'s in the same package.

        [Example](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)

    As only one bless adverb is allowed, the two options above are orthogonal and cannot be mixed and matched.

* Running more DRY

    + Blessed is the Code and the Data
    
        Walking the AST of nodes' values blessed into `bless_package`

        [Example](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_timeflies.t)

    + Advanced actions: [ASF traverse()](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/ASF.pod#traverse)

        [Example](https://metacpan.org/source/JKEGL/Marpa-R2-2.078000/t/sl_panda.t)
    
* Comparison

### References

* [Scanless Interface to Marpa (SLIF)](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless.pod)

* The Key Words
    
    - [`action`](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#action) and [`bless`](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#bless) adverbs as apply to 

        - [rules](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#The-structure-of-rules)

        - [`:default`](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#Default-pseudo-rules) pseudo-rule, and 
        
        - [`lexeme default`](https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/DSL.pod#Lexeme-default-statement) statement
    
    - [`semantic_package`][semantic_package] (SLIF recognizer) and [`bless_package`][bless_package] (SLIF grammar) named arguments


[semantic_package]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/R.pod#semantics_package

[bless_package]: https://metacpan.org/pod/release/JKEGL/Marpa-R2-2.078000/pod/Scanless/G.pod#bless_package

adding 'everything else' rule to a grammar

find all lexemes (symbols being lhs's of ~ rule and literals)

append 
    everything_else ::= join ' | ', @all_lexemes 
rule to the grammar

Add everything_else as an alternative to the start rule

Can everything_else ~ [.]+ do the trick?

General solution requires a filter for a SLIF grammar



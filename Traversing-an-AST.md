test data first
    edge cases (empty and half-empty)
first make sure it visits all nodes

default action is Dumper($ast) and recurse
start handling nodes one by one in if/elsif
keep dumping code handy
my ($id, @nodes) = $ast;

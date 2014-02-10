test data first
    edge cases (empty and half-empty)
first make sure it visits all nodes

default action is Dumper($ast) and recurse
start handling nodes one by one in if/elsif
keep dumping code handy
my ($id, @nodes) = $ast;
    
    [start, length, lhs, rule, value]
    
    walk_ast( ${ $r->value } )
    
    sub walk_ast {
        my ( $ast, $callback ) = @_;

    #    warn "walk_ast: ", Dumper $ast;

        if (ref $ast){
            my ($start, $length, $rule, $id, @nodes) = @$ast;
            $callback->($id, @nodes);
            return map { walk_ast($_, $callback) } @nodes; 
        }
        else{
            $callback->($ast);
        }
    }

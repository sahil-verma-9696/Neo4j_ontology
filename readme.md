# Syntax 

## Node syntax
( variable : node_label )

### Node with specific property
( variable : node_label { property : value })

``` cypher
MATCH ( n : categories { name : 'material' })
RETURN n
```
## Relation syntax
[ variable : relation ] 

## Create a node

``` cypher
CREATE (material:cateogory {name:'materials'})
return material
```

## Create a relation

``` cypher
CREATE 
p = (r:root {name : 'root'})-[:has_category]->(c:cateogory {name:'materials'})
return p
```

p is also a variable

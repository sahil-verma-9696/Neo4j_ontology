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

## Creating root node

``` cypher
create
(n:fashion_items 
{
    name : 'root'
}
)
return n;
```

## Create a relation

``` cypher
MATCH (r:root)
WHERE id(r) = 1
CREATE 
p = (r)-[:has_category]->(c:cateogory {name:'trend'})
return p
```

p is also a variable


## Deleting multiple nodes

deleting category not which not have id [ 3, 10]

## delete all nodes with relation

``` cypher
MATCH (n)
DETACH DELETE n;
```

``` cypher
MATCH (n:cateogory)
WHERE NOT id(n) IN [3,10]
DELETE n
```
## add new node with relation has_parent and has_category

``` cypher
MATCH (root:fashion_items {name: 'root'})
CREATE (newCategory:category {name: 'material'}) 
MERGE (root)-[:has_category]->(newCategory)
MERGE (newCategory)-[:has_parent]->(root)
WITH root
MATCH (c:category)
RETURN root, c
```

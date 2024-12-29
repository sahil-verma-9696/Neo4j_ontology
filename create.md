#Create node at level - 1

``` cypher
MATCH (root:fashion_items {name: 'root'})
MERGE (newCategory:category {name: 'material'})
MERGE (root)-[:has_category]->(newCategory)
MERGE (newCategory)-[:has_parent]->(root)
RETURN root, newCategory
```

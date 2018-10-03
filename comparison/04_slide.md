<!SLIDE bullets>

# Performance

Finding extended friends in a Relational Database vs. in Neo4j

| Depth | RDBMS exec time(s) | Neo4j exec time(s) | Records returned |
|:------|:-------------------|:-------------------|:-----------------|
| 2     | 0.016              | 0.01               | ~2,500           |
| 3     | 30.267             | 0.168              | ~110,000         |
| 4     | 1543.505           | 1.359              | ~600,000         |
| 5     | Unfinished         | 2.132              | ~800,000         |


*<i>1 mln records/nodes</i>



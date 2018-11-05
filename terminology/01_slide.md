<!SLIDE bullets>

# Nodes for Things, Relationships for Structure

## Nodes
  * The objects in the graph
  * Can have properties
  * Can be labeled

## Relationships
  * Relate nodes by type and direction
  * Can have properties

## Modeling your domain

  * [O'Reilly's Graph Databases](https://neo4j.com/lp/book-graph-databases/)


~~~SECTION:notes~~~

* Use nodes to represent entities — that is, the things in our domain that are of interest to us, and which can be labeled and grouped.

* Use relationships both to express the connections between entities and to establish semantic context for each entity, thereby structuring the domain.

* Use relationship direction to further clarify relationship semantics. Many relationships are asymmetrical, which is why relationships in a property graph are always directed. For bidirectional relationships, we should make our queries ignore direction, rather than using two relationships.

* Use node properties to represent entity attributes, plus any necessary entity meta‐ data, such as timestamps, version numbers, etc.

* Use relationship properties to express the strength, weight, or quality of a relationship, plus any necessary relationship metadata, such as timestamps, version numbers, etc.

* Model Facts as Nodes. When two or more domain entities interact for a period of time, a fact emerges. We represent a fact as a separate node with connections to each of the entities engaged in that fact. Modeling an action in terms of its product — that is, in terms of the thing that results from the action—produces a similar structure: an intermediate node that represents the outcome of an interaction between two or more entities. We can use timestamp properties on this intermediate node to represent start and end times.

~~~ENDSECTION~~~
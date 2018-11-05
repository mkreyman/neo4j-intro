<!SLIDE bullets>

# Relational databases

  * Can’t Handle Relationships Well
  * Cannot model or store data and relationships without complexity
  * Performance degrades with number & levels of relationships, and database size
  * Query complexity grows with need for JOINs, aka JOIN hell
  * Adding new types of data and relationships requires schema redesign


~~~SECTION:notes~~~

* relational databases were initially designed to codify paper forms and tabular structures.

* they struggle when attempting to model the ad hoc, exceptional relationships that crop up in the real world.

* Relationships do exist, but only at modeling time, as a means of joining tables.

* As the application grows and as outlier data multiplies, the overall structure of the dataset becomes more complex and less uniform, the relational model becomes burdened with large join tables, sparsely populated rows, and lots of null-checking logic.

* Join tables add accidental complexity; they mix business data with foreign key metadata.

* Foreign key constraints add additional development and maintenance overhead just to make the database work.

* Sparse tables with nullable columns require special checking in code, despite the presence of a schema.

* Several expensive joins are needed just to discover what a customer bought.
  Reciprocal queries are even more costly. "What products did a customer buy?" is relatively cheap compared to "which customers bought this product?", which is the basis of recommendation systems.

* We could introduce an index, but even with an index, recursive questions such as "which customers buying this product also bought that product?" quickly become prohibitively expensive as the degree of recursion increases.


~~~ENDSECTION~~~
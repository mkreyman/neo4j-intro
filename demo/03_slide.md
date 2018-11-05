<!SLIDE bullets>
# Demo 3: <code>:play movie graph</code>

* Actors who played in some movie

        MATCH (m:Movie {title: 'Sleepless in Seattle'})<-[:ACTED_IN]-(a)
        RETURN m, a

* Find the actors with 5+ movies, and the movies in which they acted

        MATCH (a:Person)-[:ACTED_IN]->(m:Movie)
        WITH a, collect(m.title) AS movies
        WHERE length(movies) >= 5
        RETURN a, movies

* Find movies released in the 1990s

        MATCH (nineties:Movie) WHERE nineties.released >= 1990 AND nineties.released < 2000
        RETURN nineties.title
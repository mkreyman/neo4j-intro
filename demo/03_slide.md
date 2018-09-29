<!SLIDE bullets>
# Demo 3: <code>:play movie graph</code>

* Actors who played in some movie

        MATCH (m:Movie {title: 'Forrest Gump'})<-[:ACTS_IN]-(a:Actor)
        RETURN a

* Find the actors with 20+ movies, and the movies in which they acted

        MATCH (a:Actor)-[:ACTS_IN]->(m:Movie)
        WITH a, collect(m.title) AS movies
        WHERE length(movies) >= 20
        RETURN a, movies
        ORDER BY length(movies) DESC
        LIMIT 10
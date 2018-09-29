<!SLIDE bullets>
# Example 3: Recommendation engine (continued...)

* What are the Top 25 Movies that Zoltan Varju has not seen using the average rating by my top 3 neighbors


        MATCH (m:Movie)<-­[r:RATED]-­(b:Person)‐[s:SIMILARITY]-­(p:Person {name:'Zoltan Varju'})
        WHERE NOT((p)‐[:RATED|WATCHED]‐>(m))
        WITH m, s.similarity AS similarity, r.rating AS rating
        ORDER BY m.name, similarity DESC
        WITH m.name AS movie, COLLECT(rating)[0..3] AS ratings
        WITH movie, REDUCE(s = 0, i IN ratings | s + i)*1.0 / LENGTH(ratings) AS recommendation
        ORDER BY recommendation DESC
        RETURN movie, recommendation 
        LIMIT 25


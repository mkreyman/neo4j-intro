<!SLIDE bullets>
# Example 2: Recommendation engine

* Top 25 Movies that I haven't seen with the same genres as Toy Story given high ratings by people who liked Toy Story


        MATCH (watched:Movie {title:"Toy Story”})<-­[r1:RATED]-­()‐[r2:RATED]-­>(unseen:Movie)
        WHERE r1.rating > 7 AND r2.rating > 7
        AND watched.genres = unseen.genres
        AND NOT( (:Person {username: "mkreyman"})‐[:RATED | WATCHED]-­>(unseen) )
        RETURN unseen.title, COUNT(*)
        ORDER BY COUNT(*) DESC
        LIMIT 25


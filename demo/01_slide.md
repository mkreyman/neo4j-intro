<!SLIDE bullets>
# Demo 1: Dependencies graph (<code>mix graph_deps</code>)

* What packages depend on <i>poison</i>? 

        MATCH path = (d1)-->(p:Package {name: "poison"})<--(d2)
        RETURN path

* What packages does <i>poison</i> depend on?

        MATCH path = (p:Package {name: "poison"})-->(d)
        RETURN path




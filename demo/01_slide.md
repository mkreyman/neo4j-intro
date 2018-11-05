<!SLIDE bullets>
# Demo 1: Dependencies graph (<code>mix graph_deps</code>)

* What packages depend on <i>absinthe</i>? 

        MATCH path = (p:Package {name: "absinthe"})<--(d)
        RETURN path

* What packages does <i>absinthe</i> depend on?

        MATCH path = (p:Package {name: "absinthe"})-->(d)
        RETURN path




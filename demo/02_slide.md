<!SLIDE bullets>
# Demo 2: ...with maintainers (<code>mix graph_deps_more</code>)

* Packages maintained by <i>José Valim</i>

        MATCH path = (:Maintainer {name: "José Valim"})<--(:Package)
        RETURN path


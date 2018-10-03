<!SLIDE bullets>
# Nested queries

* What are other maintainers for packages maintained by José Valim?

        { Maintainer(name:"José Valim") {
            name
            packages {
              name
              maintainers {
                name
              }
            }
          }
        }


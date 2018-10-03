<!SLIDE bullets>
# Run queries `http://localhost:7474/graphql/`

* Who maintains `absinthe` package?

        { Package (name:"absinthe") {
            name
            maintainers {
              name
            }
          }
        }

* What packages are being maintained by José Valim?

        { Maintainer(name:"José Valim") {
            name
            packages {
              name
            }
          }
        }
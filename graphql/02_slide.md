<!SLIDE bullets>
# GraphQL schema definition

* Define schema

        CALL graphql.idl(
          'type Maintainer {
            id: ID
            name: String
            packages: [Package] @relation(name:"DEVELOPED_BY",direction:IN)
          }
          type Package {
            id: ID
            name: String
            maintainers: [Maintainer] @relation(name:"DEVELOPED_BY")
          }')

* What's my schema, again?

        CALL graphql.schema()
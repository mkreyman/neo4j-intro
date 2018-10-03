<!SLIDE bullets>
# GraphQL native support

Neo4j server, with a plugin, can act as a GraphQL server

* Drop plugin into `/var/lib/neo4j/plugins`

* Configure in `neo4j.conf`
           
           ...
           dbms.unmanaged_extension_classes=org.neo4j.graphql=/graphql

* Or configure in [`docker-compose.yml`](https://git.io/fxvxE)
          
          ...
          environment:
            - NEO4J_dbms_unmanaged__extension__classes=org.neo4j.graphql=/graphql


~~~SECTION:notes~~~

Docs

* https://neo4j.com/developer/graphql/
* https://github.com/neo4j-graphql/neo4j-graphql
* https://neo4j.com/docs/operations-manual/current/installation/docker/
* https://neo4j.com/docs/operations-manual/current/reference/configuration-settings/

~~~ENDSECTION~~~
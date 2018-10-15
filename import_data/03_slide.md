<!SLIDE bullets>
# Demo continued...

* Check first few raw lines

          LOAD CSV FROM "file:///tmp/deps.csv" AS row
          WITH row
          RETURN row
          LIMIT 5;

* Import all lines

          USING PERIODIC COMMIT 1000
          LOAD CSV FROM "file:///tmp/deps.csv" AS row
          WITH row
          MERGE (callee_module:Module {name: row[0]})
          MERGE (function:Function {name: (row[1] + '/' + row[2])})
          MERGE (caller_module:Module {name: row[3]})
          MERGE (function)-[d:DEFINED_IN]->(callee_module)
          MERGE (caller_module)-[c:CALLS {file: row[4], line: row[5]}]->(function)


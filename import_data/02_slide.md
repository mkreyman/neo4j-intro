<!SLIDE bullets>
# Demo

* Generate dependencies with `Mix.Tasks.Xref.calls()` and export to CSV

          defp fields(%{
                 callee: {callee_module, func, arity},
                 caller_module: caller_module,
                 file: caller_file,
                 line: line
               }) do
            [callee_module, func, arity, caller_module, caller_file, line]
          end

* Create constraints in neo4j

          CREATE CONSTRAINT ON (p:Module) ASSERT p.name IS UNIQUE;
          CREATE CONSTRAINT ON (m:Function) ASSERT m.name IS UNIQUE;




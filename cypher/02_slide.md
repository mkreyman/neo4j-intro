<!SLIDE bullets>
# Example 1: Create a report

* Find all direct reports and how many people they manage, up to 3 levels down


        MATCH (boss)-­[:MANAGES*0..3]-­>(sub), (sub)-­[:MANAGES*1..3]‐>(report)
        WHERE boss.name = 'John Doe'
        RETURN sub.name AS Subordinate, count(report) as Total



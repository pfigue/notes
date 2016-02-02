Postgres EXPLAIN command

tags: postgres, explain, sql

# EXPLAIN statement

  * Workflow: parser -> rewrite -> planner/optimizer -> executor
  * EXPLAIN does not execute the query.
  * EXPLAIN ANALYZE does execute the query.
    * May have side effects
    * Use transactions to avoid side effects. Or slaves.

            BEGIN;
            EXPLAIN ANALYZE ...;
            ROLLBACK;
            
    * Different executions can throw different results. E.g. if data is cached during first execution.
        
  * There are variants (see [2]):

            EXPLAIN (BUFFERS ON, ANALYZE ON) ...

# Output

## Operations
See [3], page 11.

  * Scans: sequential scan and index scans.
    * Indices contain a lot of info. They are big.
    * If the table has not enough columns, walking a big index may be slower than sequentially scanning the table.
    * It depends also where is the data: In SHARED space? In READ space (OS)? Disk?

Hash joins

Sorts

Index Cond. `VACUUM` is necessary to remove old rows and refresh indices.

Aggregate

HashAggregate

# Costs

In an output like:

    Seq Scan on country  (cost=0.00..7.39 rows=239 width=270)
    
1. 0.00 is the cost of fetching the first row.
2. 7.39 if the cost of the full result.
3. The result will contain 329 rows
4. Each row is 270 bytes.

Some costs are calculated with parameters stored in *pg_settings* table (see [3], page 7).

In an output of ANALYZE like:

    Seq Scan on country  (cost=0.00..7.99 rows=48 width=270) (actual time=0.019..0.071 rows=25 loops=1)
       Filter: (name ~~ '%er%'::text)
       Rows Removed by Filter: 214

1. 0.019s is the actual measured time till first row.
2. 0.071s is the total time.
3. 25 is the actual number of returned rows.
4. 1 means that part of the execution plan was done once.

# psql memory organization

Two spaces: SHARED and READ.

SHARED buffer is managed by psql and behaves as a cache layer independent of the OS.

READ space is all the I/O layer at OS level. Include OS caches and secondary storage. By analyzing time spent in queries, it is possible to differentiate sometimes between disk and memory accesses.

# tools

[explain.depesz.com](http://explain.depesz.com)

# Refs

1. [Zalando Tech - SQL Intermediate Course](https://sql-intermediate.acid.zalan.do/explain/)
2. [Postgres Docs - EXPLAIN](http://www.postgresql.org/docs/current/static/sql-explain.html)
3. [Explaining EXPLAIN](https://wiki.postgresql.org/images/4/45/Explaining_EXPLAIN.pdf)
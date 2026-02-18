---
name: query-analyzer
description: Identify N+1 query problems, missing indexes, slow queries, and inefficient ORM usage patterns.
---

# Query Analyzer

## When to use

- When API endpoints are slow
- During code review of database-heavy code
- After adding new ORM relationships
- When query count spikes in APM tools

## Instructions

1. **Detect N+1 patterns**
   - ORM `.find()` calls inside loops
   - Missing `.include()` / `.eager()` / `JOIN` for related data
   - Repeated queries with same parameters

2. **Analyze query efficiency**
   - Missing WHERE clause indexes
   - SELECT * instead of specific columns
   - Missing LIMIT on large tables
   - Inefficient LIKE '%term%' (can't use index)

3. **Check ORM usage**
   - Lazy loading triggering extra queries
   - Missing batch operations (use `insertMany` not loop of `insert`)
   - Transactions not used for multi-step writes

4. **Suggest fixes**
   - Eager loading with specific relations
   - Raw SQL for complex aggregations
   - Query batching with DataLoader pattern
   - Index creation SQL

## Output

- N+1 locations with line numbers
- Query count estimate before/after fix
- Optimized code snippet
- Index creation SQL

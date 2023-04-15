# ACID

## Atomicity

[Atomicity](https://en.wikipedia.org/wiki/Atomicity\_\(database\_systems\)) guarantees that each transaction is treated as a single "unit", which either succeeds completely or fails completely: if any of the statements constituting a transaction fails to complete, the entire transaction fails and the database is left unchanged.&#x20;

```sql
begin tran
update employee
set status = 'active'
insert into employee_salary (12345, 'some_miss_typed_value_here')
commit
```

The above transaction will be failed altogether, meaning even if the Update part of the statements was correct and supposed to update the value in `employee` table but it will be rolled back to its previous state because the following Insert statement was not successfully executed.

## Consistency

[Consistency](https://en.wikipedia.org/wiki/Consistency\_\(database\_systems\)) ensures that a transaction can only bring the database from one consistent state to another, preserving database [invariants](https://en.wikipedia.org/wiki/Invariant\_\(computer\_science\)): any data written to the database must be valid according to all defined rules, including [constraints](https://en.wikipedia.org/wiki/Integrity\_constraints), [cascades](https://en.wikipedia.org/wiki/Cascading\_rollback), [triggers](https://en.wikipedia.org/wiki/Database\_trigger), and any combination thereof.

<figure><img src="../../.gitbook/assets/Screen Shot 2023-04-14 at 10.38.36 PM.png" alt=""><figcaption></figcaption></figure>

## Isolation

Transactions are often executed [concurrently](https://en.wikipedia.org/wiki/Concurrent\_computing) (e.g., multiple transactions reading and writing to a table at the same time). [Isolation](https://en.wikipedia.org/wiki/Isolation\_\(database\_systems\)) ensures that concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially.



## Durability

[Durability](https://en.wikipedia.org/wiki/Durability\_\(computer\_science\)) guarantees that once a transaction has been committed, it will remain committed even in the case of a system failure (e.g., power outage or [crash](https://en.wikipedia.org/wiki/Crash\_\(computing\))). This usually means that completed transactions (or their effects) are recorded in [non-volatile memory](https://en.wikipedia.org/wiki/Non-volatile\_memory).



## Implementation

Processing a transaction often requires a sequence of operations that is subject to failure for a number of reasons. For instance, the system may have no room left on its disk drives, or it may have used up its allocated CPU time. There are two popular families of techniques: [write-ahead logging](https://en.wikipedia.org/wiki/Write-ahead\_logging) and [shadow paging](https://en.wikipedia.org/wiki/Shadow\_paging).&#x20;

In both cases, [locks](https://en.wikipedia.org/wiki/Lock\_\(computer\_science\)) must be acquired on all information to be updated, and depending on the level of isolation, possibly on all data that may be read as well.&#x20;

### Write Ahead Log (WAL)

In write ahead logging, durability is guaranteed by copying the original (unchanged) data to a log before changing the database. That allows the database to return to a consistent state in the event of a crash.&#x20;

### Shadowing

In shadowing, updates are applied to a partial copy of the database, and the new copy is activated when the transaction commits.

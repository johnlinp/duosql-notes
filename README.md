# duosql-notes

This repo is to store my study notes on database transactions with [`duosql`](https://github.com/johnlinp/duosql).


## Database

I am mainly using MySQL.
However, there are still some special cases are in Microsoft SQL Server.


## Topics

### Isolation Levels

#### Read Uncommitted

- [dirty-reads.duo](./isolation-levels/read-uncommitted/dirty-reads.duo): Shows how dirty reads phenomenon will happen.

#### Read Committed

- [dirty-reads.duo](./isolation-levels/read-committed/dirty-reads.duo): Shows how dirty reads phenomenon is prevented by read committed.
- [non-repeatable-reads.duo](./isolation-levels/read-committed/non-repeatable-reads.duo): Shows how non-repeatable reads phenomenon will happen.

#### Repeatable Read

- [non-repeatable-reads.duo](./isolation-levels/repeatable-read/non-repeatable-reads.duo): Shows how non-repeatable reads phenomenon is prevented by repeatable read.
- [phantom-reads.duo](./isolation-levels/repeatable-read/phantom-reads.duo): Intended to show how phantom reads phenomenon will happen in MySQL, but it doesn't happen.
- [phantom-reads-mssql.duo](./isolation-levels/repeatable-read/phantom-reads-mssql.duo): Shows how phantom reads phenomenon will happen in Microsoft SQL Server.

#### Serializable

- [phantom-reads-mssql.duo](./isolation-levels/serializable/phantom-reads-mssql.duo): Shows how phantom reads phenomenon is prevented by serializable in Microsoft SQL Server.


### Locking Reads

#### Select for Update

- [update-while-updating-all.duo](locking-reads/select-for-update/update-while-updating-all.duo): Update a row while another transaction is selecting for update.
- [select-while-updating-all.duo](locking-reads/select-for-update/select-while-updating-all.duo): Select all rows while another transaction is selecting for update.
- [insert-while-counting-all.duo](locking-reads/select-for-update/insert-while-counting-all.duo): Insert a row while another transaction is counting all the rows.
- [both-select-all.duo](locking-reads/select-for-update/both-select-all.duo): Both transactions select all.
- [with-index.duo](locking-reads/select-for-update/with-index.duo): Both transactions select by an index column.
- [no-index.duo](locking-reads/select-for-update/no-index.duo): Both transactions select by a non-index column.
- [with-index-deadlock.duo](locking-reads/select-for-update/with-index-deadlock.duo): Both transactions select by an index column and produce deadlock.


#### Select for Share

- [both-select-all.duo](locking-reads/select-for-share/both-select-all.duo): Both transactions select all.
- [another-insert.duo](locking-reads/select-for-share/another-insert.duo): One transaction select for share, another insert.


### Savepoint

- [basic.duo](savepoint/basic.duo): Basic savepoint example. Rollback to a savepoint and then commit.
- [rollback-across-savepoint.duo](savepoint/rollback-across-savepoint.duo): Rollback accross a savepoint to another savepoint.
- [rollback-all.duo](savepoint/rollback-all.duo): Rollback will delete all savepoints.
- [update-rolled-back.duo](savepoint/update-rolled-back.duo): Rollback and then update the same record.

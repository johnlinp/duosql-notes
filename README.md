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

- [select-all.duo](locking-reads/select-for-update/select-all.duo): Both transactions select all.
- [with-index.duo](locking-reads/select-for-update/with-index.duo): Both transactions select by an index column.
- [no-index.duo](locking-reads/select-for-update/no-index.duo): Both transactions select by a non-index column.
- [with-index-deadlock.duo](locking-reads/select-for-update/with-index-deadlock.duo): Both transactions select by an index column and produce deadlock.

#### Select for Share

- [select-all.duo](locking-reads/select-for-share/select-all.duo): Both transactions select all.
- [another-insert.duo](locking-reads/select-for-share/another-insert.duo): One transaction select for share, another insert.

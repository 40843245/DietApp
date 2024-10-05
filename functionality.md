My package about Android Compose Components and dynamically MySQL statement generator.

Functionalities:
1. About Android Compose Components,
+ use less code to instantiate a series of components through wrapping them into classes.
+ more maintenable (for code), more extensible (to extend this functionality), and more flexible (to use).
2. About dynamically MySQL statement generator,
+ it can dynamically generate MySQL statement. One can configure the properties of classes then use `build` method to instantiate a String object.
+ it supports commonly used MySQL statement. 
+ About basic operation of table,
  - `SELECT` (only supports `SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... LIMIT ... OFFSET ...`)
  - `INSERT`
  - `UPDATE`
  - `DELETE`

+ About other operation of table,
  - `DROP TABLE`
  - `CREATE TABLE` (no functionality about constraints at present)
  - `DESCRIBE`
  - `SHOW TABLES`

+ About operation of database,
  - `USE`
  - `DROP DATABASE`

> [!CAUTION]
> But there is no such functionality to check the syntax of MySQL statement.

> [!CAUTION]
> Also be aware of SQL injection, for more details, see [changelog.md](https://github.com/40843245/DietApp/blob/main/changelog.md).

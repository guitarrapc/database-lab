## MSSQL2MySQL

Database Migration from MSSQL to MySQL for Database / Tables.

## Tools

* DB Migration tool: MySQL Workbench (Database Migration)
* Split single large SQL to each table SQL: MySQL Query Divider

## Steps

### Migrate to MySQL

Open MySQL workbench > Database > Migration Wizard

![image](https://user-images.githubusercontent.com/3856350/62260988-d70e5400-b44e-11e9-810f-1ee4e20fbad4.png)

Set Source RDBMS Connection as Microsoft SQL Server. Select Connection Method as ODBC (native) and confirm Test Connection.

![image](https://user-images.githubusercontent.com/3856350/62260972-c65dde00-b44e-11e9-8485-5913a1c38695.png)

![image](https://user-images.githubusercontent.com/3856350/62261055-045b0200-b44f-11e9-98ca-96ae768f383d.png)

Set Target RDBMS and confirm Test Connection.

![image](https://user-images.githubusercontent.com/3856350/62261123-2d7b9280-b44f-11e9-8281-4e2cb6ec9822.png)

![image](https://user-images.githubusercontent.com/3856350/62261134-39675480-b44f-11e9-80a5-9d6e3b7b9417.png)

next, Fetch and next.

Select MSSQL Schema/Table to migrate.

Confirm Schema/Table list and make sure there are no migration problems found.

![image](https://user-images.githubusercontent.com/3856350/62261202-76cbe200-b44f-11e9-9d22-c478b564dbb9.png)

Select download sql script as migration_script.sql.

Select `Create schema in target RDBMS` and `Create a SQL script file`.

done.

## Split single large SQL to each table

Install MySQLQueryDivider to split sql to each table.

```
dotnet tool install --global mysqlquerydivider
```

Dry run.

```
mysqlquerydivider from_file -i migration_script.sql -o .Tables
```

run.

```
mysqlquerydivider from_file -i migration_script.sql -o .Tables --clean true --dry false
```


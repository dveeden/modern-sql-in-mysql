---
layout: default
---
## What is Modern SQL?

The best introduction for Modern SQL is [modern-sql.com](http://modern-sql.com). Make sure to go
through the [slides](http://modern-sql.com/slides) or watch the
 [video](http://modern-sql.com/video).

## What is the current state of Modern SQL in MySQL?

### SQL:2011

Feature          | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
-----------------|----------------|----------------|----------------|------------
OFFSET           |
AS OF            |
WITHOUT OVERLAPS |

### SQL:2008

Feature          | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
-----------------|----------------|----------------|----------------|------------
FETCH FIRST      |
OVER             |
ARRAY            | | [MDEV-6121](https://mariadb.atlassian.net/browse/MDEV-6121)


### SQL:2003

Feature          | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
-----------------|----------------|----------------|----------------|------------
FILTER           |
OVER             | [Bug #35893](https://bugs.mysql.com/bug.php?id=35893) | [MDEV-6115](https://mariadb.atlassian.net/browse/MDEV-6115)
WITHIN GROUP     |



### SQL:1999

Feature        | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
---------------|----------------|----------------|----------------|------------
LATERAL        | 
WITH           | [Bug #16244](https://bugs.mysql.com/bug.php?id=16244) | [MDEV-8308](https://mariadb.atlassian.net/browse/MDEV-8308)
WITH RECURSIVE |

## Other non-standard behavior

### Functional indexes

### Storage Engine API and CONNECT and CSV

SQL/MED (Management of External Data)

## Other standards

SQL/JSON

## What can I do?

Click 'Affects me' on https://bugs.mysql.com or Vote on the MariaDB JIRA.
FIXME

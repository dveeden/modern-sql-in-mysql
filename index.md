---
layout: default
---
## What is Modern SQL?

The best introduction for Modern SQL is [modern-sql.com](http://modern-sql.com). Make sure to go
through the [slides](http://modern-sql.com/slides) or watch the
 [video](http://modern-sql.com/video).
Many of the newer features in the standard make it iesier to create a clean
and portable (standards complient) solution. This also helps in compatibility
with other databases like SQLite and PostgreSQL.

## What is the current state of Modern SQL in MySQL?

### SQL:2011

Feature          | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
-----------------|----------------|----------------|----------------|------------
[OFFSET](http://www.slideshare.net/MarkusWinand/modern-sql/113)           |
[AS OF](http://www.slideshare.net/MarkusWinand/modern-sql/118)            |
[WITHOUT OVERLAPS](http://www.slideshare.net/MarkusWinand/modern-sql/129) |

### SQL:2008

Feature          | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
-----------------|----------------|----------------|----------------|------------
[FETCH FIRST](http://www.slideshare.net/MarkusWinand/modern-sql/107)      | Non-standard LIMIT Only | Non-standard LIMIT Only |
[OVER](http://www.slideshare.net/MarkusWinand/modern-sql/101)             |
ARRAY            | | [MDEV-6121](https://mariadb.atlassian.net/browse/MDEV-6121)

### SQL:2003

Feature          | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
-----------------|----------------|----------------|----------------|------------
[FILTER](http://www.slideshare.net/MarkusWinand/modern-sql/61)           |
[OVER](http://www.slideshare.net/MarkusWinand/modern-sql/61)             | [Bug #35893](https://bugs.mysql.com/bug.php?id=35893) | [MDEV-6115](https://mariadb.atlassian.net/browse/MDEV-6115)
[WITHIN GROUP](http://www.slideshare.net/MarkusWinand/modern-sql/95)     |

### SQL:1999

Feature        | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
---------------|----------------|----------------|----------------|------------
[LATERAL](http://www.slideshare.net/MarkusWinand/modern-sql/3)        | 
[WITH](http://www.slideshare.net/MarkusWinand/modern-sql/18)           | [Bug #16244](https://bugs.mysql.com/bug.php?id=16244) | [MDEV-8308](https://mariadb.atlassian.net/browse/MDEV-8308)
[WITH RECURSIVE](http://www.slideshare.net/MarkusWinand/modern-sql/40) |

## Other non-standard behavior

### Storage Engine API and CONNECT and CSV

The Storage Engine API allows you to create a wrapper for your data and use
MySQL as SQL frontend for it. It also allows you to combine this data with
data stored in MySQL. It is mainly used to create different backends for
MySQL with slightly different characteristics.

The CONNECT storage engine in MariaDB allows you to connect to different
data sources without the need of writing any code.

The CSV storage engine allows you to use SQL to query a CSV file.

The Federated and FederatedX storage engines allow you to connect to
another MySQL server and combine data from multiple servers.

This is all very useful, but none of these follow the
SQL/MED (Management of External Data) standard syntax.

## Other standards

The *SQL/JSON* standard is being created. Some info is available here:
[http://jtc1bigdatasg.nist.gov/_workshop/08_SQL_Support_for_JSON_abstract.pdf](http://jtc1bigdatasg.nist.gov/_workshop/08_SQL_Support_for_JSON_abstract.pdf).

The *SQL/XML* is part of the bigger SQL standard. MySQL has support for XML and XPath, but to my knowledge this is not
standard compliant.

The *SQL/PSM* standard (Part of SQL:1999) is amazingly well supported in MySQL.

The level of implementation of the *OpenGIS* standard is rapidly improving. Both MySQL 5.7 and MariaDB 10.1 have enhanced
GIS features.

## What can I do?

Click 'Affects me' on [bugs.mysql.com](https://bugs.mysql.com) or Vote on the [MariaDB JIRA](https://mariadb.atlassian.net).
You could also help to implement the features or pay someone else to do that.

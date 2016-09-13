---
layout: default
---

&nbsp;<br>
&nbsp;<br>

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
[FETCH FIRST](http://www.slideshare.net/MarkusWinand/modern-sql/107)      | Non-standard LIMIT Only, [Bug #78929](https://bugs.mysql.com/bug.php?id=78929) | Non-standard LIMIT Only |
[OVER](http://www.slideshare.net/MarkusWinand/modern-sql/101)             |
ARRAY            | [Bug #13830](https://bugs.mysql.com/bug.php?id=13830) | [MDEV-6121](https://mariadb.atlassian.net/browse/MDEV-6121)
NORMALIZE[^nfc_in_postgresql] | [WL#2048](https://dev.mysql.com/worklog/task/?id=2048) [Bug #71563](https://bugs.mysql.com/bug.php?id=71563) |

[^nfc_in_postgresql]: See also: [Unicode Normalization in SQL](http://justatheory.com/computers/databases/postgresql/unicode-normalization.html) by David E. Wheeler

### SQL:2003

Feature          | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
-----------------|----------------|----------------|----------------|------------
[FILTER](http://www.slideshare.net/MarkusWinand/modern-sql/61)           | Thirdparty, [filter_plugin](https://github.com/svetasmirnova/filter_plugin) for 5.7
[OVER](http://www.slideshare.net/MarkusWinand/modern-sql/61) a.k.a. window functions | [Bug #28957](https://bugs.mysql.com/bug.php?id=28957) [Bug #35893](https://bugs.mysql.com/bug.php?id=35893) | [MDEV-6115](https://mariadb.atlassian.net/browse/MDEV-6115) [MariaDB 10.2.0 work-in-progress](https://drive.google.com/file/d/0B7HE7L1OgKJFRnpnLThfS2d5dWc/view)
[WITHIN GROUP](http://www.slideshare.net/MarkusWinand/modern-sql/95)     |
MERGE | [Bug #9018](https://bugs.mysql.com/bug.php?id=9018) |
BETWEEN | [Bug #46867](https://bugs.mysql.com/bug.php?id=46867) |

### SQL:1999

Feature        | Oracle MySQL   | MariaDB        | Percona Server | WebscaleSQL
---------------|----------------|----------------|----------------|------------
[LATERAL](http://www.slideshare.net/MarkusWinand/modern-sql/3)        | [Bug #78930](https://bugs.mysql.com/bug.php?id=78930)
[WITH](http://www.slideshare.net/MarkusWinand/modern-sql/18)           | [Bug #16244](https://bugs.mysql.com/bug.php?id=16244) Will be in 8.0[^with_eight_zero] | [MDEV-8308](https://mariadb.atlassian.net/browse/MDEV-8308)
[WITH RECURSIVE](http://www.slideshare.net/MarkusWinand/modern-sql/40)[^with_recursive] | Will be in 8.0[^with_eight_zero] |
GROUPING | [Bug #46053](https://bugs.mysql.com/bug.php?id=46053) |

[^with_recursive]: See also: [WITH RECURSIVE and MySQL](http://guilhembichot.blogspot.nl/2013/11/with-recursive-and-mysql.html) by Guilhem Bichot.

[^with_eight_zero]: See also: [Iterview with Manyi Lu](https://www.percona.com/blog/2016/09/01/percona-live-europe-featured-talk-manyi-lu-mysql-8-0-whats-new-optimizer/) by Dave Avery (Percona).

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

## Documentation about standards

To update the documentation about standards support: [Bug #75954](https://bugs.mysql.com/bug.php?id=75954)

## Other standards

The *SQL/JSON* standard is being created. Some info is available here:
[http://jtc1bigdatasg.nist.gov/_workshop/08_SQL_Support_for_JSON_abstract.pdf](http://jtc1bigdatasg.nist.gov/_workshop/08_SQL_Support_for_JSON_abstract.pdf).

The *SQL/XML* is part of the bigger SQL standard. MySQL has support for XML and XPath, but to my knowledge this is not
standard compliant.

The *SQL/PSM* standard (Part of SQL:1999) is amazingly well supported in MySQL.

The level of implementation of the *OpenGIS* standard is rapidly improving. Both MySQL 5.7 and MariaDB 10.1 have enhanced
GIS features.

MySQL has good support for [X/Open X/A](http://pubs.opengroup.org/onlinepubs/009680699/toc.pdf) distributed transactions (as Resource Manager).

MySQL 5.7+ support [GeoJSON](http://geojson.org/geojson-spec.html).

MySQL has support for *IEEE 754*. The documentation on the level of compliance is not complete: [Bug #57519](https://bugs.mysql.com/bug.php?id=57519). See also [0.30000000000000004.com](http://0.30000000000000004.com/)

## What can I do?

Click 'Affects me' on [bugs.mysql.com](https://bugs.mysql.com) or Vote on the [MariaDB JIRA](https://mariadb.atlassian.net).
You could also help to implement the features or pay someone else to do that.

Or let others know about this:
<a href="https://twitter.com/share" class="twitter-share-button">Tweet</a>
<script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+'://platform.twitter.com/widgets.js';fjs.parentNode.insertBefore(js,fjs);}}(document, 'script', 'twitter-wjs');</script>

<div id="disqus_thread"></div>
<script type="text/javascript">
    /* * * CONFIGURATION VARIABLES * * */
    var disqus_shortname = 'modernsqlinmysql';
    
    /* * * DON'T EDIT BELOW THIS LINE * * */
    (function() {
        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
        dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>
<a href="https://github.com/dveeden/modern-sql-in-mysql"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/a6677b08c955af8400f44c6298f40e7d19cc5b2d/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677261795f3664366436642e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_gray_6d6d6d.png"></a>

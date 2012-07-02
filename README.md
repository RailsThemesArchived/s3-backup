To do a backup, make sure that you have bundle installed the gems.

Then, run ./backup. This will take railsthemes-production and copy it to a new bucket called railsthemes-prod-backup-YYYYMMDD-HHMMSS.




To get a dump of the current production database:

s3-backups> heroku pgbackups --app railsthemes
ID   | Backup Time         | Size   | Database    
-----+---------------------+--------+-------------
a092 | 2012/05/24 20:00.41 | 31.3KB | DATABASE_URL
a099 | 2012/05/31 20:00.54 | 32.4KB | DATABASE_URL
a106 | 2012/06/07 20:01.54 | 43.2KB | DATABASE_URL
a113 | 2012/06/14 20:01.49 | 47.8KB | DATABASE_URL
a120 | 2012/06/21 20:02.03 | 56.2KB | DATABASE_URL
a124 | 2012/06/25 20:01.59 | 56.4KB | DATABASE_URL
a125 | 2012/06/26 20:01.53 | 56.4KB | DATABASE_URL
a126 | 2012/06/27 20:01.52 | 58.3KB | DATABASE_URL
a127 | 2012/06/28 20:01.55 | 58.3KB | DATABASE_URL
a128 | 2012/06/29 20:01.56 | 58.4KB | DATABASE_URL
a129 | 2012/06/30 20:01.54 | 58.4KB | DATABASE_URL
a130 | 2012/07/01 20:01.45 | 58.4KB | DATABASE_URL

s3-backups> heroku pgbackups:capture --app railsthemes

SHARED_DATABASE (DATABASE_URL)  ----backup--->  b131

Capturing... done
Storing... done

s3-backups> heroku pgbackups:url b131 --app railsthemes
"url"

s3-backups> wget "url"


Could create a script for this pretty easily when we want to do this automatically

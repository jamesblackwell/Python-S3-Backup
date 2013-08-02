Python-S3-Backup
================

Simple Python backup script for backing up files and MySQL dumps on Amazon S3.

Requirements
------------

This script requires boto. To install boto simply -

```
pip install boto
```

Configuration
-------------

The script requires the following configuration parameters

**AWS**

* Access Key - _aws_access_key_
* Secret Key - _aws_secret_key_
* Bucket - _aws_bucket_

**MySQL**

* Hostname - _mysql_hostname_
* Username - _mysql_username_
* Password - _mysql_password_
* MySQL Dump Path - _mysql_dump_path_

**Directories**

You can backup as many directories as you like. Simply define it as a list and include the full path, e.g.

```
dirs = [
        '/srv/www/domain1.com',
        '/srv/www/domain2.com'
        ]
```

**Databases**

You can define the databases to be backed up the same way as the directories. Make sure your user has sufficient privilidges to access all databases, if more than one.

```
dbs = [
        'domain1_app',
        'domain1_blog',
        ]
```

Crontab
-------

Sample cron to run backup every day at 23.00.

```
* 23 * * * python ~/scripts/backup.py
```
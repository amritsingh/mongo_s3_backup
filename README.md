Role Name
========

Ansible role to dumps the current mongo database, tars it, then sends it to an Amazon S3 bucket

Role Variables
--------------

In the current version, following variables can be specified:

- script_dir: Directory to copy the scripts and to store temporary backup
- backup_script_params: These params are required by the role to take backup and push to S3
   - -u      Mongodb user - optional
   - -p      Mongodb password - optional
   - -k      AWS Access Key
   - -s      AWS Secret Key
   - -r      Amazon S3 region
   - -b      Amazon S3 bucket name
   - -x      S3 key prefix
   - -a      Days of data to keep

   eg: "-u ubuntu -p password -k AWS_Access_Key -s AWS_Secret_Key -r Amazon_S3_region -b Amazon_S3_bucket_name -x backup -a 7"
- cron_minute: Minute when the job should run - default: 0
- cron_hour: Hour when the job should run - default: 10
- cron_day: Day when the job should run - default: *
- cron_month: Month when the job should run - default: *
- cron_weekday: Weekday when the job should run - default: *

Dependencies
------------

This package has no dependencies on modules not included with Ansible by default.

License
-------

MIT

Author Information
------------------

Created by Amrit Singh
https://www.twitter.com/_amrit_


---
title: Uploads
layout: page
type: tute
---

## Introduction

Cmfive supports two different types of file adapters for uploads to best suit your needs.

- The <b>Local Adapter</b> is enabled by default and requires no further setup.
- The <b>S3 Adapter</b> provides a more available and reliable solution.

## S3 Adapter

1. Add the following entries into the <b>config.php</b> file in the root directory of your Cmfive project.
```php
Config::set("file.adapters.local.active", false);
Config::set("file.adapters.s3", [
   "active"      => true,
   "region"      => "S3_BUCKET_REGION",
   "version"     => "2006-03-01",
   "credentials" => [
       "key"    => "IAM_KEY",
       "secret" => "IAM_SECRET",
   ],
   "bucket"      => "S3_BUCKET_NAME",
   "options"     => [
       "directory" => "uploads",
       "create"    => true
   ],
]);
```
2. Replace <b>S3_BUCKET_REGION</b>, <b>IAM_KEY</b>, <b>IAM_SECRET</b> and <b>S3_BUCKET_NAME</b> with their respective values.
3. Make sure to clear your config cache to apply your changes.
4. If you have any files stored locally from prior to using the S3 Adapter you can run <b>file migration tool</b> in the admin module from within Cmfive to move them to S3.
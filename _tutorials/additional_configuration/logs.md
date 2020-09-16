---
title: Logs
layout: page
type: tute
---

## Introduction

Cmfive supports two different types of log targets to best suit your needs.

- The <b>AWS Target</b> provides a more reliable solution with the option to specify a retention period (in days).
- The <b>File Target</b> is enabled by default and requires no further setup.

## AWS Target

1. Add the following entries into the <b>config.php</b> file in the root directory of your Cmfive project.
```php
Config::set("admin.logging", [
        "target"           => "aws",
        "retention_period" => RETENTION_PERIOD,
        "cloudwatch"       => [
            "group_name"      => "GROUP_NAME",
            "stream_name_app" => "APP_NAME",
            "region"          => "CLOUDWATCH_REGION",
            "version"         => "latest",
            "credentials"     => [
                "key"    => "IAM_KEY",
                "secret" => "IAM_SECRET"
            ]
        ]
]);
```
2. Replace <b>RETENTION_PERIOD</b>, <b>GROUP_NAME</b>, <b>APP_NAME</b>, <b>CLOUDWATCH_REGION</b>, <b>IAM_KEY</b> and <b>IAM_SECRET</b> with their respective values.
3. Make sure to clear your config cache to apply your changes.
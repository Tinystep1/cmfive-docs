---
title: Using The Log
layout: page
type: tute
---

## The Log Error Function

Sometimes you will want to test the logs by adding a test error to log. You can do this in your index.php file in the actions folder cmfive-boilerplate/modules/example/actions/index.php. 

Copy the line from the code below into your index.php file.

```php
<?php

function index_ALL(Web $w) {

    $w-ctx("tilte", "Example Module");

    // Service classes should be invoked using MyService::getInstance($w), e.g.
    LogService::getInstance($w)->error("Example This is a test");
    
}
```

Note: You will encounter "old" ways of referencing service classes like $w->Log->error(), e.g

```php
$w->Log->error("This is an error message")
```

If you check your most recent log, you should see an error described as 'Example this is a test'.

![Log error test result](/assets/images/log_example.png)

Remember, the most recent log will be the last one in the folder, and your error should be the last line in the file.
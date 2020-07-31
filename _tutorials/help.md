---
title: Tutorials
layout: page
type: tute
---

## Fixing Errors Using the Logs

If you get an error message at any point when you display your code in localhost, CMFive will diagnose it for you using the logs.

Finding the logs is simple. First, open the boilerplate. Go to the .build folder, the storage folder, and the logs folder. The files here store information about every time the CMFive database has been accessed.

Note that each of the log names have cmfive, followed by a date, and are appended by '.log'. To find the log for your error, select the log that has todays date in the name (this should be at the bottom of the list). All entries in the log files start with a date and time stamp in square barckets. Scroll down to the last entry of your file.

For an error the file will show 'cmfive.ERROR' after the date and time stamp. This will be followed by a brief description of the error and 'trace:' which will give the path to the code with the error, followed by the line it's in. For example, the path to the logs is written as /var/www/cmfive-boilerplate/.build/storage/log.
By following this path, and checkting the line shown in the brackets after the path, you should be able to locate the error in your code.

Sometimes you will want to test the logs by adding a test error to log. You can do this in your index.php file in the actions folder /var/www/cmfive-core/modules/example/actions/index.php. 
below your index-ALL function, you should have a line of code starting with '$w->ctx'. Inside the funtions brackets, leave a line of space below this first line of code and write '$w->Log->error("Example this is a test");'. Then save your file, and reload localhost.
If you check your most recent log, you should see an error described as 'Example this is a test'.
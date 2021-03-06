export_evo_script
=================

This is a free php script that generates an SQL script to import posts from the b2evolution platform to wordpress.

About
=====
When moving from the b2evolution platform to wordpress, there are few options for migrating the data.  RSS can be used, but requires configuration changes and does not pring along other data like permalinks and comments.

This script tries to get a more complete dataset by using SQL to import the posts from b2evoltion.  This script was written using b2evolution 4.0.3 and wordpress 3.5.2.

Backup all data before using this script.  This script comes with no warranty.  You are ultimately responsible for your own data.

Usage
======
The export_evo_script directory should be copied to the plugins directory of the b2evolution install.  The script must then be executed on the command line by including user IDs in both systems.

When executing this script, the b2evolution and wordpress user IDs are required, and a database prefix (for the wordpress database) is optional. If the user ID in b2evolution was 4, the user ID in wordpress was 6, and the database prefix was "word_", the command would be ```php export_evo_script.php 4 6 word_```.  The script then exports a file named "wp_user_6_posts.sql".  That SQL script should be run on the wordpress database to import the b2evolution posts for that user.

Notes
=====
This script only moved the blog text, so uploaded files need to be moved seperately.  Because of the size of the SQL scripts, it is safest to run the file on the [command line](http://dev.mysql.com/doc/refman/5.5/en/mysql-batch-commands.html).  Attempting to run the scripts using a desktop client can cause errors.

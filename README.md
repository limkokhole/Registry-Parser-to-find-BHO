bho_parse
=========

Helps parsing logs of browser helper objects that indentify extensions installed by malware


--------------
Documentation
--------------

This parser has been written in an effort to parse logs obtained from querying the browser registry. It creates tables for every browser(chrome/msie/firefox) and clusters them according to browser type and extension installed post infection


Before starting this script it would be necessary to run the following command

$ psql -d <your_db_name> -a -f initdb.sql

This will create a series of tables which will be populated later

Invoke scan.py as shown below

$ ./scan.py
Usage: ./scan.py days msie/chrome/firefox/all

Example: ./scan.py 5 msie
$

The program also does the following
 - Creates file sketchy.sql ; Can be used to populate a database with results
 - Creates file which has information regarding registry keys and corresponding Browser Helper Objects


Due to the nature of the farm it is likely that a log pair (i.e. Pre-infection+Post-infection+Pre-Browsing) may not exist. Such samples are exempted from parsing.

Other than that. Feel free to add/modify/delete anything you wish!

4 Digit SIC codes with descriptions in CSV 
=========

http://data.gov doesn't have a simple list of all the 4 digit SIC codes and their descriptions. It should be easier than this.

This is a downloadable list of the 4 Digit SIC codes in CSV format

How the data was created:

1. copy, pasted, and pythoned from http://www.osha.gov/pls/imis/sic_manual.html
1. save file as CSV format using open office


MySQL Import 
=========

LOAD DATA INFILE '/Users/sameer/www/test/var/sic_data/sic4-list/divisions.csv' INTO TABLE sic_divisions 
FIELDS TERMINATED BY ','
ENCLOSED BY '\"' 
LINES TERMINATED BY '\n' 
IGNORE 1 LINES;

LOAD DATA INFILE '/Users/sameer/www/test/var/sic_data/sic4-list/major-groups.csv' INTO TABLE sic_groups_major 
FIELDS TERMINATED BY ','
ENCLOSED BY '\"' 
LINES TERMINATED BY '\n' 
IGNORE 1 LINES;

LOAD DATA INFILE '/Users/sameer/www/test/var/sic_data/sic4-list/industry-groups.csv' INTO TABLE sic_groups_industry 
FIELDS TERMINATED BY ','
ENCLOSED BY '\"' 
LINES TERMINATED BY '\n' 
IGNORE 1 LINES;

LOAD DATA INFILE '/Users/sameer/www/test/var/sic_data/sic4-list/sic-codes.csv' INTO TABLE sic_codes 
FIELDS TERMINATED BY ','
ENCLOSED BY '\"' 
LINES TERMINATED BY '\n' 
IGNORE 1 LINES;


MongoDB Import
=========

mongoimport -h 127.0.0.1:3001 -d meteor -c sic_divisions --type csv --file /Users/sameer/www/test/var/sic_data/sic4-list/divisions.csv --headerline

mongoimport -h 127.0.0.1:3001 -d meteor -c sic_groups_major --type csv --file /Users/sameer/www/test/var/sic_data/sic4-list/major-groups.csv --headerline

mongoimport -h 127.0.0.1:3001 -d meteor -c sic_groups_industry --type csv --file /Users/sameer/www/test/var/sic_data/sic4-list/industry-groups.csv --headerline

mongoimport -h 127.0.0.1:3001 -d meteor -c sic_codes --type csv --file /Users/sameer/www/test/var/sic_data/sic4-list/sic-codes.csv --headerline

If using Meteor, get Meteor's MongoDB port: 

$ meteor mongo -U

or

$ ps aux | grep 'mongod'

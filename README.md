4 Digit SIC codes with descriptions in CSV 
=========

http://data.gov doesn't have a simple list of all the 4 digit SIC codes and their descriptions. It should be easier than this.

This is a downloadable list of the 4 Digit SIC codes in CSV format

How the data was created:

1. copy, pasted, and pythoned from http://www.osha.gov/pls/imis/sic_manual.html
1. save file as CSV format using open office


MySQL import 
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


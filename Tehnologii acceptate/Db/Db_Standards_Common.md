# Common db standards

## Dabatase naming

Database names will be in English.

Database names will contain the name of the project

Database charset will be `utf8`

Database collation will be `utf8_unicode_ci`

## Database scripting

All projects shall have a Db script folder named `Db scripts`.

A script file named `schema.sql` shall be present in the folder. It will contain an Sql script that will initialize a functional database (database schema + minimum inserts to get a clean install)

Multiple update scripts can be present. They will be named `update-yyyymmdd.sql`. When ran in ascending order they will patch the minimum functional database to the current version.

When commiting a new task, the apropriate db update filess will be placed in the `Db scripts` folder.

A new `schema.sql` file will be generated at the beginnning of each sprint. All existing update scripts will be deleted. The new schema file will contain all of the required updates from the last sprint.

## Reverting Db changes

Where possible, db changes should not be made by hand.

Databases should be patched by either adding an update script in the `Db scripts` folder or by re-running the current `schema.sql` file and all of the update files present.

Database changes should be contained to one sprint. A task (and therefore a db modification) is either included or not. There is no state in between.

## Column data types

Column data types chosen for each column will try to be the LEAST precise type that will accomodate ALL POSSIBLE VALUES in all cases. 

Types that support optimization will be chosen (varchar, bit vs text, blob etc) <br/>

| Type      	   		| Size         		| Description |
| --------------------- |:-----------------:| :----------:|
| `CHAR[Length]` 		| Length bytes 					| A fixed-length field from 0 to 255 characters long   |
| `VARCHAR[Length] ` 	| String length + 1 or 2 bytes	| A variable-length field from 0 to 65,535 characters long   |
| `TINYTEXT`		  	| String length + 1 bytes		| A string with a maximum length of 255 characters   |
| `TEXT`			  	| String length + 2 bytes		| A string with a maximum length of 65,535 characters   |
| `MEDIUMTEXT`	  		| String length + 3 bytes		| A string with a maximum length of 16,777,215 characters  |
| `LONGTEXT`		  	| String length + 4 bytes		| A string with a maximum length of 4,294,967,295 characters   |
| `TINYINT[Length]`  	| 1 byte						| Range of –128 to 127 or 0 to 255 unsigned   |
| `SMALLINT[Length]` 	| 2 bytes						| Range of –32,768 to 32,767 or 0 to 65,535 unsigned   |
| `MEDIUMINT[Length]`	| 3 bytes						| Range of –8,388,608 to 8,388,607 or 0 to 16,777,215 unsigned  |
| `INT[Length]`	  		| 4 bytes						| Range of –2,147,483,648 to 2,147,483,647 or 0 to 4,294,967,295   |
| `BIGINT[Length]`  	| 8 bytes						| Range of –9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 or 0 to 18,446,744,073,709,551,615 unsigned   |
| `FLOAT[Length, Decimals]`  	| 4 bytes				| A small number with a floating decimal point   |
| `DOUBLE[Length, Decimals]` 	| 8 bytes				| A large number with a floating decimal point   |
| `DECIMAL[Length, Decimals]`	| Length +1 or 2 bytes	| A DOUBLE stored as a string, allowing for a fixed decimal point   |
| `DATE` 			  	| 3 bytes						| In the format of YYYY-MM-DD  |
| `DATETIME` 		  	| 8 bytes						| In the format of YYYY-MM-DD HH:MM:SS   |
| `TIMESTAMP`		  	| 4 bytes						| In the format of YYYYMMDDHHMMSS; acceptable range starts in 1970 and ends in the year 2038  |
| `TIME`  		  		| 3 bytes						| In the format of HH:MM:SS  |
| `ENUM`	 		  	| 1 or 2 bytes					| Short for enumeration, which means that each column can have one of several possible values   |
| `SET` 			  	| 1, 2, 3, 4, or 8 bytes		| Like `ENUM` except that each column can have more than one of several possible values   |


### CHAR vs. VARCHAR

Both of these types store strings and can be set with a maximum length. The primary difference between the two is that anything stored as a `CHAR` will always be stored as a string the length of the column (using spaces to pad it; these spaces will be removed when you retrieve the stored value from the database). Conversely, strings stored in a `VARCHAR` column will require only as much space as the string itself. So the word cat in a `VARCHAR(10)` column requires 4 bytes of space (the length of the string plus 1), but in a `CHAR(10)` column, that same word requires 10 bytes of space. Hence, generally speaking, `VARCHAR` columns tend to require less disk space than `CHAR` columns.

However, databases are normally faster when working with fixed-size columns, which is an argument in favor of CHAR. And that same three-letter word—cat—in a `CHAR(3)` only uses 3 bytes but in a `VARCHAR(10)` requires 4. So how do you decide which to use?

If a string field will always be of a set length (e.g., a state abbreviation), use `CHAR`; otherwise, use `VARCHAR`. You may notice, though, that in some cases MySQL defines a column as the one type (like `CHAR`) even though you created it as the other (`VARCHAR`). This is perfectly normal and is MySQL's way of improving performance.

### General considerations

The length attribute for numeric types does not affect the range of values that can be stored in the column. Columns defined as `TINYINT(1)` or `TINYINT(20)` can store the exact same values. Instead, for integers, the length dictates the display width; for decimals, the length is the total number of digits that can be stored.

If you need absolute precision when using non-integers, `DECIMAL` is preferred over `FLOAT` or `DOUBLE`.

MySQL has a `BOOLEAN` type, which is just a `TINYINT(1)`, with `0` meaning `FALSE` and `1` meaning `TRUE`.

MySQL also has several variants on the text types that allow for storing binary data. These types are `BINARY`, `VARBINARY`, `TINYBLOB`, `MEDIUMBLOB`, and `LONGBLOB`. Such types can be used for storing files or encrypted data.

##Other standards

If your language uses CamelCase, then also follow [this] (Db_Standards_CamelCase.md) guideline

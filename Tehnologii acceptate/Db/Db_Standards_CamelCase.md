#Db Standards CamelCase

Acestea sunt standardele pentru Db daca folositi un limbaj cu variabile bazae pe CamelCase (C#, Java). <br/>
Ele sunt scrise in engleza, pentu ca au mai mult sens.

## Dabatase

Database names will be in English.

Database names will contain the name of the project

Database names will contain the suffix Dev for dev environments (ex. `RoTransportDev`) 

Database charset will be `utf8`

Database collation will be `utf8_unicode_ci`


## Tables

Table names will be in English

Table names will be pluralized (`Users` not `User`)

Table names will start with a capital letter (`Users` not `users`)

Table names will use CamelCase (ex: `UserFiles`)

Table names will pluralize only the last noun (`UserFiles` not `UsersFiles`)

All tables will have a primary key. The name of that field will be composed from the table name in singular and then "Id" (`RoleId` not `IdRole`).

All of the required foreign keys shall be present.

## Columns

Column names will be in English

Column names will be singular (`Description` not `Descriptions`)

Column names will start with a capital letter (`Description` not `description`)

Column names will use CamelCase (ex: `CreationDate`)

Foreign keys that are Ids (numeric) will be composed from the table name in singular and then "Id" (`RoleId` not `IdRole`)

Column constraints shall be present where needed

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



#Db Standards CamelCase

Acestea sunt standardele pentru Db daca folositi un limbaj cu variabile bazae pe CamelCase (C#, Java). 
Ele sunt scrise in engleza, pentu ca au mai mult sens.

## Dabatase

Database names will be in English.

Database names will contain the name of the project

Database names will contain the suffix Dev for dev environments (ex. RoTransportDev) 

Database charset will be utf8

Database collation will be utf8_unicode_ci


## Tables

Table names will be in English

Table names will be pluralized (Users not User)

Table names will start with a capital letter (Users not users)

Table names will use CamelCase (ex: UserFiles)

Table names will pluralize only the last noun (UserFiles not UsersFiles)

All tables will have a primary key. The name of that field will be composed from the table name in singular and then "Id" (RoleId not IdRole).

All of the required foreign keys shall be present.

## Columns

Column names will be in English

Column names will be singular (Description not Descriptions)

Column names will start with a capital letter (Description not description)

Column names will use CamelCase (ex: CreationDate)

Foreign keys that are Ids (numeric) will be composed from the table name in singular and then "Id" (RoleId not IdRole)

Column constraints shall be present where needed

## Column data types


Column data types chosen for each column will try to be the LEAST precise type THAT WILL ACCOMMODATE ALL POSSIBLE VALUES in all cases. 

Types that support optimization will be chosen (varchar, bit vs text, blob etc)

| Type      	  	| Size         		| Description |
| ----------------- |:-----------------:| :----------:|
| CHAR[Length] 		| Length bytes 					| A fixed-length field from 0 to 255 characters long   |
| VARCHAR[Length]  	| String length + 1 or 2 bytes	| A variable-length field from 0 to 65,535 characters long   |


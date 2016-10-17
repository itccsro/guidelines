#Db Standards CamelCase

Acestea sunt standardele pentru Db daca folositi un limbaj cu variabile bazae pe CamelCase (C#, Java). Ele sunt scrise in engleza, pentu ca au mai mult sens.

Table names will be in English
Table names will be pluralized (Users not User)
Table names will start with a capital letter (Users not users)
Table names will use CamelCase (ex: UserFiles)

Table names will pluralize only the last noun (UserFiles not UsersFiles)
All tables will have a primary key. The name of that field will be composed from the table name in singular and then "Id" (RoleId not IdRole).
All of the required foreign keys shall be present.

Column names will be in English
Column names will be singular (Description not Descriptions)
Column names will start with a capital letter (Description not description)
Column names will use CamelCase (ex: CreationDate)
Foreign keys that are Ids (numeric) will be composed from the table name in singular and then "Id" (RoleId not IdRole)

Column constraints shall be present where needed

Column data types chosen for each column will be correct. We will use the types that support optimization (nvarchar, bit vs text, blob etc)
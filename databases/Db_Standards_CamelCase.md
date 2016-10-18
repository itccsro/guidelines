#Db Standards CamelCase

Acestea sunt standardele pentru Db daca folositi un limbaj cu variabile bazae pe CamelCase (C#, Java). <br/>
Ele sunt scrise in engleza, pentu ca au mai mult sens.

## Important

On databases that support collations, **always** deploy and test your code in a case sensitive collation database.

## Tables

Table names will be in English, unless the project requirements specify otherwise (some projects have explict Romanian names as a requirement)

Table names will be pluralized (`Users` not `User`)

Table names will start with a capital letter (`Users` not `users`)

Table names will use CamelCase (ex: `UserFiles`)

Table names will pluralize only the last noun (`UserFiles` not `UsersFiles`)

For tables that require a primary key, the primary key shall be a *stable* value (never changes). Most often primary keys are a single column, in which case the recommended form is table name and Id: `RoleId`, not `IdRole`. Remeber, when choosing primary keys, preffer compact and monotonous key values (eg: IDENTITY) over large and random key values (eg: GUID)

[Do not assume the primary key is always the clustered index](http://dba.stackexchange.com/questions/7741/when-should-a-primary-key-be-declared-non-clustered/7744#7744). 

Declare the foreign key constrains explictly. Ensure always the target of a foreign key relation has an appropiate index. Choose an appropiate DELETE/UPDATE policy, but avoid CASCADE.

## Columns

Column names will be in English, unless the project requirements specify otherwise (some projects have explict Romanian names as a requirement)

Column names will be singular (`Description` not `Descriptions`). If the column store multiple values (eg. `Tags`), consider normalizing the value. If still opt for a denormalized value, use plural as appropiate.

Column names will start with a capital letter (`Description` not `description`)

Column names will use CamelCase (ex: `CreationDate`)

Foreign keys should match the name of the relation and column they reference. If the referenced column is the primary key of referenced relation and it conforms the `TableId` convention, to not repeat the relation name.

Column constraints shall be present where needed



![f206d9ad35710541a3cd01b242432b72.png](:/396f2bb9f4554f3984821f80fa6fe25e)

sql = ddl+dml
catalogue: catalogue is a named collection of schema in an sql env
a catalogue always contains a special schema called information schema, which provides info on all the schema in the catalogue and all the elements described in these schemas.

views: views are called virtual or derived tables, because they present the user with what appear to be table however the information in those table is derived from previously defined tables.

# data types
* Number: integer number of various types and floating point numbers of various precision
* Character string: Fixed length character(n) or varying length VARCHAR.
* bitstring: bitstring is a string of bits. the bitstring data type is used to store binary data. the bitstring data type is not supported by all the sql engines. default length of bitstring is 1.
* boolean: true/false, because of the presence of null value a 3 valued logic is used. so a third possible value for boolean data type is unknown
* date and time: 

# constraints
* default: default value for a column. if a column is not specified in an insert statement, the default value is used.
* check: check constraint is used to specify a condition that must be true for each row in a table. the condition is specified as a boolean expression. the check constraint can be specified on a column or on a table.
* referential integrity constraint: the default action that sql takes when a referential integrity constraint is violated is to reject the update or delete operation. this is called the referential action. the referential action can be changed to cascade, set null or set default. however the schema designers can specify an alternative action to be taken when a referential integrity constraint is violated. this is called a referential integrity constraint. the options include set null, set default and cascade.

ambiguous attributes in sql: the same name can be used for two or more attributes as long as they are in different tables. this is called an ambiguous attribute. the sql standard requires that the sql engine must be able to resolve the ambiguity. the sql engine does this by using the table name to disambiguate the attribute name. if the table name is not specified, the sql engine will use the table name that was specified in the from clause of the query.

<!-- retrieve the employees first and last name and the first and last name of his or her immediate supervisor  -->
select e1.first_name, e1.last_name, e2.first_name, e2.last_name
from employee e1, employee e2
where e1.supervisor_id = e2.employee_id;

# drop command 
the drop command can be used to drop name, schema elemets such as tables, domains or constraints.
one can also drop a schema. for eg if one wants to drop the schema called sales, one can use the following command:
drop schema sales cascade;

there are two drop behaviours: cascade and restrict. cascade means that all the objects in the schema are dropped. restrict means that the drop command is rejected if the schema is not empty. 

a query expressed in high level query language such as sql must first be scanned, parsed and validated. The scanner identifies the language token such as sql keywords, attribute names and relation names, in the syntax of the query whereas the parser checks the query sytax to determine whether it is formulated correctly. the validator checks the query semantics to determine whether the query is meaningful. the query must also be validated by checking that all attributes and relations used in the query are defined in the schema and semantically of the particular database being queried.

An internal representation of the query is then created. usually this is a tree structure. this is called the query tree. the query tree is then optimized by the query optimizer. the query optimizer determines the most efficient way to execute the query. this is called the query plan. the query plan is then executed by the query processor. the query processor is responsible for retrieving the data from the database and returning the result to the user.

# query graph
a query typically has many possible execution strategies and the process of choosing the best strategy is called query optimization. the query optimizer uses a query graph to represent the query. the query graph is a directed graph. the nodes of the query graph are the relations in the query. the edges of the query graph are the join conditions in the query. the query graph is constructed by the query optimizer. the query optimizer uses the query graph to determine the best query plan.

# heuristic approach

# translating sql query to relational algebra
<!-- read from book -->

# external sorting
external sorting refers to sorting algorithms that can sort a large file that does not fit into main memory. 
the typical strategy is sort and merge strategy which starts by sorting small subfiles called runs and then merge the sorted runs creating a larger sorted run. this process is repeated until only one sorted run is left. the sorted run is then written back to the original file.
the sort merge algo like other databse algos requires buffer space in main memory where the actual sorting and merging of the runs is performed.
the file is divided into smaller chunks that fit into main memory. each chunk is sorted individually and then merged together to form a sorted file. the merge process is repeated until only one sorted file is left. the sorted file is then written back to the original file.

# algorithms for external sorting

# algorithms for select and join operations
<!-- projection, selection dekh lena bhai -->
- linear search
- binary search
- using a primary index (hashing)
- using a clustering index to retrieve multiple records (happens when relation does not have a primary key)
- equality comparison

# search methods for complex selections
<!-- from book -->

# implementation the join operation

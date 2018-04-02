# MSSQL Wrapper

An easy to use MSSQL wrapper.

Created and maintained by the A.C. Moore software engineering team.  

## Methods

### prepareService
Create the connection pools for provided databases
```javascript
prepareService(config, callback);
```
#### Parameters:
##### config: *object*
A configuration object containing information related to the database is required to connect.
###### config Example:
```javascript
{
    databaseName: {
        'user': 'db_user_name',
        'password': 'db_pass',
        'server': 'PATH\\TOSERVER'
        'database': 'DATABASE_NAME'
        'pool': {
            'max': 10,
            'min': 4,
            'idleTimeoutMillis': 30000
        }
    },
    other db connections...
}
```
___

### executePSQuery
Execute prepared statement
```javascript
executePSQuery(options, callback);
```
#### Parameters:
##### options: *Object*

|Field | Type | Required | Value |
| --- | --- |--- | --- |
|db   | string | true | database name as defined in the config object used to prepare the service|
|qrydata | object | true | object containing query fields, from_objects, and where_clause |
|input | array | true | array of objects containing input name and type (as defined by mssql)|
|params | object | true | key value pairs defining any parameters, where key is the given input name and value is the parameter value |
___

### exeuteSP
Execute a stored procedure
```javascript
executeSP(options, callback);
```
#### Parameters:
##### options: *Object*

|Field | Type | Required | Value |
| --- | --- |--- | --- |
|db   | string | true | database name as defined in the config object used to prepare the service |
|procedure | string | true | procedure name |
|input | array | true | array of objects containing input name, type (as defined by mssql), and value (key: val) |
|output | array | true | array of objects containing output name and type (as defined by mssql) |

___

### executeQuery
call a basic query
```javascript
executeQuery(options, callback);
```
#### Parameters:
##### options: *Object*

|Field | Type | Required | Value |
| --- | --- |--- | --- |
|db   | string | true | database name as defined in the config object used to prepare the service|
|qrydata | array | true | array of objects containing query: fields, from_objects, join_condition, where_clause, group_by, order_by |
|server | string | true | sever location of the database |
|outFormat | array | true | array of objects containing output name and type (as defined by mssql)|

___

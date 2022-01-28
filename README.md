# SQL Cursors

## Cursor Introduction
Sometimes the application needs to process the rows in a singleton fashion, i.e., on row by row basis rather than the entire result-set at once. But, typically, you use cursors when you want to divide a large result-set into parts and process each part individually. Another usage is to return a reference to a cursor that a function has created, allowing the caller to read the rows.
(If you process the result-set at once, you may have a memory overflow error but, PL/pgSQL users do not normally need to worry about memory overflow, since FOR loops automatically use a cursor internally to avoid memory problems.)

## Cursor Actions
- DECLARE
- OPEN
- FETCH 
- CLOSE
- DEALLOCATE (Deletes the cursor defined and releases all system resources associated with the definition)


## Types of Cursors 

###### - [Implicit](https://www.geeksforgeeks.org/cursors-in-pl-sql/) 
> If the Oracle engine opened a cursor for its internal processing it is known as an Implicit Cursor. It is created “automatically” for the user by Oracle when a query is executed and is simpler to code.

###### - [Explicit](https://www.geeksforgeeks.org/cursors-in-pl-sql/)
> A Cursor can also be opened for processing data through a PL/SQL block, on demand. Such a user-defined cursor is known as an Explicit Cursor.


## 4 Steps for Utilizing Explicit Clause
1. DECLARE the cursor in Declaration section
2. OPEN the cursor in Execution section
3. FETCH the data from cursor into PL/SQL variables or records in Exectution section
4. CLOSE the cursor in Exection section before ending PL/SQL block


## Sample Code
Using Cursors
To retrieve a Result-Set holding multiple rows, an application has to declare a cursor and fetch each row from the cursor. You can declare a cursor and then define it later, but what we show here is when you declare and define the cursoe together. 

DECLARE foo_bar CURSOR <br>
	FOR <br>
    SELECT number, ascii FROM foo <br>
    ORDER BY ascii; <br>
OPEN foo_bar; <br>
FETCH foo_bar INTO :FooBar, DooDad; <br>
CLOSE foo_bar; <br>
COMMIT; <br>

## Syntax

DECLARE cursor_name CURSOR		// declare the cursor  
  FOR  
SELECT select_statement			// to define the output for the cursor  
OPEN cursor_name				// open the cursor to store the result set  
FETCH NEXT FROM cursor INTO variable_list  
					// Current row is fetched, column values stored, cursor advances.  
					// %TYPE and %ROWTYPE are useful for declaring the variables_list.  
CLOSE Cursor_name	//Should close the cursor once done with it.  
DEALLOCATE cursor_name  



## References: 
- [Geeks4Geeks - Cursor Overview](https://www.geeksforgeeks.org/cursors-in-pl-sql/)
- [Oracle - Implicit & Explicit Cursor](https://docs.oracle.com/database/121/LNPLS/static.htm#LNPLS99956)
- [PostgreSQL - Cursor Implementations](https://www.postgresql.org/docs/9.2/plpgsql-cursors.html)

# SQL Cursors

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








## References: 
- [Geeks4Geeks - Cursor Overview](https://www.geeksforgeeks.org/cursors-in-pl-sql/)
- [Oracle - Implicit & Explicit Cursor](https://docs.oracle.com/database/121/LNPLS/static.htm#LNPLS99956)
- [PostgreSQL - Cursor Implementations](https://www.postgresql.org/docs/9.2/plpgsql-cursors.html)

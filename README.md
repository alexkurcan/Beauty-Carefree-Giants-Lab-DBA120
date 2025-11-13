# Beauty-Carefree-Giants-Lab-DBA120
### Name: Alex Kurcan
### Date: 11/13/2025
#
## Error Messages
### (Which commands caused errors, and why?)
1. Question 3 had the expected error, which was:
**"Error at line 2/5: ORA-42399: cannot perform a DML operation on a read-only view"** Which did not allow me to run the previous update command.
2. Question 6 has an error, which was:
**"Error at line 1/12: ORA-00942: table or view does not exist"** But that was when I tried DROP TABLE WORD_REL;
I then tried DROP VIEW WORD_REL; Which ended up working out. The previous command hadn't worked becuase it was not table but a view.
#
## Why are DML operations restricted in some views?
**Summary (so you don't have to read all of that):** 
DML commands are restricted whenever the view is mapped between the view and an underlying table that is nonexistent. Usually, simple views that directly correspond to a single table WITHOUT complex transformation allow DML commands.
1. Read-only Views
* Some views, simliar to one we did in the lab, or DBMS auto trets them as read-only becuase they are demend complex
2. Views That Have WHERE Clauses
* Some updates are restricted if the WHERE clause filters out any rows or has an operation that might not affect all rows in the underlying table
3. Views That Are On Multiple Tables
* If a view is. made using a join of multiple tables, SQL might not know which table it should be updating when you use a DML command which could cause some issues
4. Views That Use DISTINCT or Calculated Columns
* If a view has DISTINCT or computed columns, DML is restricted becuase chaning the view does not clearly translate to a change within the underlying table. This also applies to any aggregation i.e. SUM() or COUNT()
5. Views with Group By (Grouping)
* Views that use groupoing cannot be updated because there is no direct mapping to indiviual rows within the base table
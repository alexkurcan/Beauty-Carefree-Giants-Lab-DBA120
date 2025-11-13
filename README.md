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
1. Read-only Views
* Some views, simliar to one we did in the lab, or DBMS auto trets them as read-only becuase they are demend complex.
2. Views that have WHERE Clauses